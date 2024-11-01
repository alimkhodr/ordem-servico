<p align="center"><img src="https://github.com/user-attachments/assets/6e5de9e9-5e4e-45c9-b7d2-082fdfec102c" width="20%"></p>
<p align="center">Sistema de Ordem de Serviço</p>

## Clonando o Repositório
Clone este repositório usando o comando:
```bash
git clone https://github.com/aptivjam/ordem-servico
```

## SQL
Estrutura SQL da aplicação
```bash
CREATE TABLE TAB_OS_RELATORIO(
	OS_ID INT PRIMARY KEY,
	OS_FERRAMENTA VARCHAR(50) NOT NULL,
	OS_POSICAO VARCHAR(50) NOT NULL,
	OS_DESCRICAO VARCHAR(50),
	OS_PROJETO VARCHAR(50),
	OS_DATA_ENTREGA DATETIME NOT NULL,
	OS_CAIXA INT UNIQUE,
	OS_UNIDADE VARCHAR(50) NOT NULL,
	OS_TIPO VARCHAR(50),
	OS_QUANTIDADE INT NOT NULL,
	OS_QUANTIDADE_FINAL INT,
	OS_CONTA INT,
	OS_SUB_CONTA INT,
	OS_SECAO INT,
	OS_REG_RESPONSAVEL INT NOT NULL,
	OS_SITUACAO VARCHAR(50) NOT NULL,
	OS_DATA_ENVIADA DATETIME,
	OS_DATA_INICIO DATETIME,
	OS_DATA_FIM DATETIME,
);

CREATE TABLE TAB_OS_OPERACAO(
	OP_ID INT PRIMARY KEY IDENTITY,
	OP_NOME_OP VARCHAR(50) NOT NULL,
	OP_DESCRICAO_OP VARCHAR(50),
	OP_ID_OS INT FOREIGN KEY REFERENCES TAB_OS_RELATORIO(OS_ID) ON DELETE CASCADE NOT NULL,
	OP_DATA_ENTREGA DATETIME NOT NULL,
	OP_HORAS_PREV VARCHAR(50),
	OP_HORAS_PREV_UNIT VARCHAR(50),
	OP_FUNCIONARIO INT,
	OP_MAQUINA VARCHAR(50),
	OP_QUANTIDADE INT NOT NULL,
	OP_QUANTIDADE_FINAL INT,
	OP_DATA_INICIO DATETIME,
	OP_DATA_FIM DATETIME,
);

CREATE TABLE TAB_OP_PARADAS(
	PARADA_ID INT PRIMARY KEY IDENTITY,
	PARADA_ID_OP INT FOREIGN KEY REFERENCES TAB_OS_OPERACAO(OP_ID) ON DELETE CASCADE,
	PARADA_DATA_INICIO DATETIME NOT NULL,
	PARADA_MOTIVO VARCHAR(50) NOT NULL,
	PARADA_DATA_FIM DATETIME,
);

CREATE TABLE TAB_OS_PERMISSAO(
	PERMISSAO_ID INT PRIMARY KEY IDENTITY,
	FUN_ID INT FOREIGN KEY REFERENCES FUNCIONARIO(FUN_REGISTRO) ON DELETE CASCADE,
);
```
## Demonstração do sistema
Screenshot das telas do sitema
  <details>
    <summary><b>Login</b></summary>
    <ul><p align="center"><img src="https://github.com/alimkhodr/Ordem-de-Servico/assets/85517447/214f7228-2b6c-4c9b-a42c-b36ec35dc68e"></img></p></ul>
  </details>
    <details>
    <summary><b>Home</b></summary>
    <ul><p align="center"><img src="https://github.com/alimkhodr/Ordem-de-Servico/assets/85517447/902ea023-9183-4f79-af4f-281a7fbbfe95"></img></p></ul>
  </details>
    <details>
    <summary><b>Ordem</b></summary>    
    <ul><p align="center"><img src="https://github.com/alimkhodr/Ordem-de-Servico/assets/85517447/03638a8d-45fa-4863-9ccf-715c45e15e9b"></img></p></ul>
    Editar/Criar ordem de produção e adicionar operações a ela
  </details>
  <details>
    <summary><b>Apontar serviço</b></summary>
    <ul><p align="center"><img src="https://github.com/alimkhodr/Ordem-de-Servico/assets/85517447/56659003-990e-443e-922d-ea94d0b5a086"></img></p></ul>
  </details>
    <details>
    <summary><b>Relatórios</b></summary>
    <ul><p align="center"><img src="https://github.com/alimkhodr/Ordem-de-Servico/assets/85517447/bfd1c6e8-592a-4e89-b53a-ac637f5f538a"></img></p></ul>
  </details>
  <details>
    <summary><b>Máquinas</b></summary>
    <ul><p align="center"><img src="https://github.com/alimkhodr/Ordem-de-Servico/assets/85517447/7722d8bd-349a-4a26-b911-ccd762c73847"></img></p></ul>
  </details>
  <details>
    <summary><b>Impressão</b></summary>
    <ul><p align="center"><img src="https://github.com/alimkhodr/Ordem-de-Servico/assets/85517447/f700cdd6-3da0-43f0-92a5-d85543bd99df"></img></p></ul>
  </details>
<br>
<p align="center"><img src="https://github.com/user-attachments/assets/bb4c0c56-bf3e-4471-9d88-8056135c8f9f" width="20%"></p>

