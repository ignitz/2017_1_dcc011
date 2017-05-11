**Seja o seguinte esquema relacional:**

`Fornecedor ({fid: integer, fnome: string}, endereço: string)`  
`Item ({itemid: integer}, inome: string, cor: string)`  
`Catalogo ({fid: integer, itemid: integer}, preço: real)`  

**Resolva as seguintes consultas usando Álgebra Relacional E SQL:**

- **Liste os nomes de fornecedores que fornecem algum item vermelho.**

$$\pi_{fnome} \sigma_{cor="vermelho"} \left( Forcenedor \bowtie Catalogo \bowtie Item \right)$$

```SQL
SELECT
	fnome
FROM
	Fornecedor AS X1
INNER JOIN
	Catalogo AS X2 ON X1.fid = X2.fid
INNER JOIN
	Item AS X3 ON X2.itemid = X3.itemid
WHERE X3.cor = "vermelho";
```

- **Liste os ids de fornecedores que fornecem algum item vermelho ou estão localizados na rua dos Alfeneiros, 4.**

$$\pi_{fid} \sigma_{cor="vermelho"\ \text{OR}\ endereco="rua\ dos\ Alfeneiros,\ 4"} \left( Forcenedor \bowtie Catalogo \bowtie Item \right)$$

```SQL
SELECT
	fnome
FROM
	Fornecedor AS X1
INNER JOIN
	Catalogo AS X2 ON X1.fid = X2.fid
INNER JOIN
	Item AS X3 ON X2.itemid = X3.itemid;
```

- **Liste os ids dos fornecedores que fornecem algum item vermelho e algum item verde.**

$${\pi _{fid}}\left( {\left( {Forcenedor \bowtie Catalogo \bowtie Item} \right) \div \left( {{\sigma _{cor = "vermelho"\;{\rm{OR}}\;cor = "verde"}}Item} \right)} \right)$$

```SQL
SELECT
	fid
FROM
	Catalogo AS X1
INNER JOIN
	Item AS X2 ON X1.itemid = X2.itemid
WHERE
	X2.cor='vermelho'
    AND X2.itemid IN (SELECT
							fid
						FROM
							Catalogo AS X1
						INNER JOIN
							Item AS X2 ON X1.itemid = X2.itemid
						WHERE X2.cor='verde');
```

- **Liste os ids dos fornecedores que fornecem todos os itens.**

$${\pi _{fid}}\left( { \pi_{fid,\ itemid}Catalogo\; \div \;\left( {{\pi _{itemid}}Item} \right)} \right)$$

```sql
SELECT X1.fid, X1.itemid
FROM Catalogo as X1
WHERE NOT EXISTS (
	SELECT X2.itemid
    FROM Item as X2
    WHERE X2.itemid NOT IN (
		SELECT X3.itemid
        FROM Item as X3
        WHERE X3.itemid = X1.itemid
    ));
```

- **Liste os ids dos fornecedores que fornecem todos os itens vermelhos.**

$${\pi _{fid}}{\left( {Catalogo\; \div \;\left( {{\pi _{itemid}}{\sigma _{cor = "vermelho"}}Item} \right)} \right)}$$

```sql
SELECT X1.fid, X1.itemid
FROM Catalogo as X1
WHERE NOT EXISTS (
	SELECT X2.itemid
    FROM Item as X2
    WHERE X2.itemid NOT IN (
		SELECT X3.itemid, X3.cor
        FROM Item as X3
        WHERE X3.itemid = X1.itemid AND X3.cor="vermelho"
    ));
```

- **Liste pares de ids dos fornecedores nos quais o primeiro id cobra mais por alguma parte que o segundo id.**

$$\begin{array}{l}
\rho (X,\;Catalogo)\\
\rho (Y,\;Catalogo)\\
{\pi _{X.fid,\;Y.fid}}\left( {{\sigma _{X.fid\; \ne \;Y.fid{\rm{ AND }}X.itemid\; = \;Y.itemid{\rm{ AND }}X.pre\c{c}o\; > \;Y.pre\c{c}o}}\left( {X \times Y} \right)} \right)
\end{array}$$

- **Liste os ids dos itens que são fornecidos por pelo menos dois fornecedores diferentes.**

$$\begin{array}{l}
\rho (X,\;Catalogo)\\
\rho (Y,\;Catalogo)\\
{{\pi _{X.itemid}}\left( {{\sigma _{\left( {X.fid\; \ne \;Y.fid} \right){\rm{AND}}\left( {X.itemid\; = \;Y.itemid} \right)}}\left( {X \times Y} \right)} \right)}
\end{array}$$

- **Liste os ids dos itens mais caros fornecidos pelo fornecedor Brahma.**

> Tirei a ideia daqui.
[http://stackoverflow.com/questions/5493691/how-can-i-find-max-with-relational-algebra](http://stackoverflow.com/questions/5493691/how-can-i-find-max-with-relational-algebra)

$$\begin{array}{l}
X = \left( {Catalogo\; \bowtie \left( {{\pi _{itemid}}{\sigma _{fnome = "Brahma"}}Fornecedor} \right)} \right)\\
\rho \left( {Y,\;X} \right)\\
Z = {\rho _{fid,\;itemid,\;pre\c{c}o}}{\pi _{X.fid,\;X.itemid,\;X.pre\c{c}o}}{\sigma _{X.pre\c{c}o\; < \;Y.pre\c{c}o}}\left( {X \times Y} \right)\\
{\pi _{itemid}}\left( {X - Z} \right)
\end{array}$$
