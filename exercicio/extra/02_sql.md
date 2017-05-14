\newpage
## SQL

1. 
```sql
SELECT Projeto.Sigla, Projeto.NomePro
FROM Projeto
MINUS
SELECT Sigla, NomePro
FROM Projeto
INNER JOIN Equipe ON Projeto.Sigla = Equipe.Sigla;
```

2. 
```sql
SELECT X1.Sigla, X1.NomePro
FROM Projeto X1
INNER JOIN Equipe X2 ON X1.Sigla = X2.Sigla
INNER JOIN Consultor X3 ON X2.CPF = X3.CPF
INNER JOIN Viagem X4 ON X4.CPF = X2.CPF AND X4.Sigla = X2.Sigla
WHERE X3.DataNascCon >= 1987;
```

3. 
```sql
SELECT X1.Sigla, X1.NomePro
FROM Projeto AS X1
INNER JOIN Equipe X2 ON X1.Sigla = X2.Sigla
INNER JOIN Consultor X3 ON X2.CPF = X3.CPF
INNER JOIN Viagem X4 ON X4.Sigla = X3.Sigla AND X4.CPF = X2.Equipe
WHERE Destino = "RS";
```

4. 
```sql
SELECT X1.Sigla, X1.NomePro
FROM Projeto X1
INNER JOIN Cliente X2 ON X1.CodCli = X2.Cli
WHERE X1.NomeCli <> "KualaLamper";
```

5. 
```sql
SELECT X1.Sigla, X1.NomePro
FROM Projeto X1
INNER JOIN Equipe X2 ON X1.Sigla = X2.Sigla
INNER JOIN Consultor X3 ON X2.CPF = X3.CPF
INNER JOIN Viagem X4 ON X4.CPF = X2.CPF AND X4.Sigla = X2.Sigla
WHERE X3.UFNascCon = "PR";
```

6. 
```sql
SELECT X2.UFLoc
FROM Viagem X1
CROSS JOIN Local X2
WHERE X1.Sigla = "XP" AND X1.Destino = X2.NomeLoc;
```
`CROSS JOIN` = `INNER JOIN` a partir do MySQL 5.0

7. 
```sql
SELECT X1.CPF, X1.NomeCon
FROM Consultor X1
INNER JOIN Viagem X2 ON X1.CPF = X2.CPF
CROSS JOIN Local X3
WHERE X2.Destino = X3.NomeLoc = X2.Destino AND X1.UFNascCon = X3.UFLoc;
```

8. 
```sql
SELECT Projeto.Sigla, Projeto.NomePro
FROM Projeto
INNER JOIN Equipe ON Projeto.Sigla = Equipe.Sigla
INNER JOIN Consultor ON Consultor.CPF = Equipe.CPF
INNER JOIN Viagem ON Viagem.CPF = Consultor.CPF AND Projeto.Sigla = Viagem.Sigla
INNER JOIN Local
WHERE Viagem.Destino = Local.NomeLoc AND Consultor.UFNascCon = Local.UFLoc;
```

\newpage
9. 
```sql
SELECT Projeto.Sigla, Projeto.NomePro
FROM Projetos
INNER JOIN Viagem ON Projetos.Sigla = Viagem.Sigla
INNER JOIN Local
WHERE Local.UFloc AND Data = 2007 AND Viagem.Destino = Local.NomeLoc;
```

10. 
```sql
SELECT NomeLocal
FROM Local
MINUS
SELECT Destino AS NomeLocal
FROM Viagem;
```

11. 
```sql
SELECT NomeLocal
FROM Local
MINUS
(SELECT Origem AS NomeLocal
 FROM Viagem
 UNION
 SELECT Destino AS NomeLocal
 From Viagem);
```

12. 
```sql
SELECT CPF, Nome
FROM Consultor
MINUS
(SELECT Consultor.CPF AS CPF, Consultor.Nome AS Nome
 FROM Consultor AS X1
 INNER JOIN Equipe AS X2 ON X1.CPF = X2.CPF
 INNER JOIN (SELECT * 
             FROM Projeto
             WHERE Data < 2007) AS X3
             ON X3.Sigla = X2.Sigla);
```

13. 
```sql
SELECT Consultor.CPF AS CPF, Consultor.Nome AS Nome
FROM Consultor
INNER JOIN Local ON Consultor = Local.UFLocal
WHERE UFNascCon = "RJ";
```

14. 
```sql
SELECT Equipe.CPF AS CPF, Equipe.Nome AS Nome
FROM Equipe
INNER JOIN (SELECT *
            FROM Consultor
            INNER JOIN Viagem ON Consultor.CPF = Viagem.CPF) AS X
WHERE X.Consultor.CPF = Equipe.CPF AND X.Viagem.Sigla <> Equipe.Sigla;
```

15.
```sql
SELECT CPF, Nome
FROM Consultores
INNER JOIN Equipe ON Consultores.CPF = Equipe.CPF
INNER JOIN Projeto ON Equipe.Sigla = Projeto.Sigla
INNER JOIN Cliente ON Cliente.CodCli = Projeto.CodCli
WHERE Cliente.NomeCli = "Kuala Lumpur";
```

