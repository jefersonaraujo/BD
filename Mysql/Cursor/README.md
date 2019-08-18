#### TRIGGER

```sql
create procedure INSERIRDADOS()
	begin
		declare fim int default 0;
		declare var1,var2,var3,vtotal,vmedia int;
		declare vnome varchar(50);

		declare REG CURSOR FOR(
			select nome,jan,fev,mar from vendedores = 1;
		);

		open REG;

		REPEAT
			FETCH REG INTO vnome,var1,var2,var3;
			IF NOT FIM THEN

					SET vtotal = var1 + var2 + var3;
					SET vmedia = vtotal / 3;

					INSERT INTO VENT_TOTAL values (vnome,var1,var2,var3);
			END IF;

			UNTIL FIM END REPEAT;

			CLOSE REG;

	end
```
