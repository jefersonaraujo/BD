####  Procedures   
###### EXEC NOME_PROCEDURE
###### DROP PROC NOME_PROCEDURE

/*TRAZER OS TELEFONES DE ACORDO COM O TIPO PASSADO  */

```sql
/* TRAZER OS TELEFONES DE ACORDO COM O TIPO PASSADO */
CREATE PROC TELEFONES @TIPO CHAR(3)
AS
	SELECT NOME, NUMERO
	FROM PESSOA
	INNER JOIN TELEFONE
	ON IDPESSOA = ID_PESSOA
	WHERE TIPO = @TIPO
GO

EXEC TELEFONES 'CEL'
GO

EXEC TELEFONES 'COM'
GO

/* PARAMETROS DE OUTPUT */

SELECT TIPO, COUNT(*) AS QUANTIDADE
FROM TELEFONE
GROUP BY TIPO
GO

/* PROCEDURE DE CADASTRO */

CREATE PROC CADASTRO @NOME VARCHAR(30), @SEXO CHAR(1), @NASCIMENTO DATE,
@TIPO CHAR(3), @NUMERO VARCHAR(10)
AS
	DECLARE @FK INT

	INSERT INTO PESSOA VALUES(@NOME,@SEXO,@NASCIMENTO) --GERAR UM ID

	SET @FK = (SELECT IDPESSOA FROM PESSOA WHERE IDPESSOA
	= @@IDENTITY)

	INSERT INTO TELEFONE VALUES(@TIPO,@NUMERO,@FK)
GO

```
