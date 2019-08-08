#### TRIGGER

```sql
create table USUARIO(
	IDUSUARIO INT primary key auto_increment,
	NOME VARCHAR(30),
	LOGIN VARCHAR(30),
	SENHA VARCHAR(100)
);
```

```sql
create table BKP_USUARIO(
	IDBACKUP INT primary key auto_increment,
	IDUSUARIO INT,
	NOME VARCHAR(30),
	LOGIN VARCHAR(30)
);
```


```sql
DELIMITER ;
create trigger BACKUP_USER
before delete on USUARIO
for each row
begin

	insert into BKP_USUARIO values(null,old.IDUSUARIO,old.NOME,old.LOGIN);
end
$
delimiter ;
drop trigger BACKUP_USER;
insert into USUARIO values (null,'TESTE','TESTE01','FDFDF');

select * from usuario;
select * from bkp_usuario;

delete from usuario where idusuario = 1
```
