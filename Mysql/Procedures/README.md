####  Procedures   
> ###### Stored Procedure, que traduzido significa Procedimento Armazenado, é uma conjunto de comandos em SQL que podem ser executados de uma só vez, como em uma função. Ele armazena tarefas repetitivas e aceita parâmetros de entrada para que a tarefa seja efetuada de acordo com a necessidade individual.


Durante a execução usa-se um delimitador, no caso troca o caractere padrão ";", para qualquer outro, execulta o escopo da procedure e volta ao demilitador padrão.

```sql
DELIMITER $
CREATE PROCEDURE CONTA1()
BEGIN
		SELECT 10 + 10 AS "CONTA";
END
$
/* Voltar ao deminitador ';' */
DELIMITER ;
```

```sql
CALL CONTA();

/* CHAMANDO A PROCEDURE*/
```
CONTA|
-----|
20|


######  EXEMPLO

```sql
/* DELIMITADOR */

DELIMITER #

CREATE PROCEDURE CAD_CURSO(P_NOME VARCHAR(30),P_HORAS INT(3),P_PRECO FLOAT(10,2))
BEGIN
		INSERT INTO CURSOS VALUES(NULL,P_NOME,P_HORAS,P_PRECO);
END
#

DELIMITER ;
```
```sql


SELECT * FROM CURSOS;

DELIMITER #

CREATE PROCEDURE SEL_CURSO()
BEGIN
		SELECT IDCURSO, NOME, HORAS, VALOR
		FROM CURSOS;
END
#

DELIMITER ;

CALL SEL_CURSO();
```
