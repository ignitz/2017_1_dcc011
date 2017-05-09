**Seja o seguinte esquema relacional:**

`Fornecedor ({fid: integer, fnome: string}, endereço: string)`  
`Item ({itemid: integer}, inome: string, cor: string)`  
`Catalogo ({fid: integer, itemid: integer}, preço: real)`  

**Resolva as seguintes consultas usando Álgebra Relacional E SQL:**

- Liste os nomes de fornecedores que fornecem algum item vermelho.

$$\pi_{fnome} \sigma_{cor="vermelho"} \left( Forcenedor \bowtie Catalogo \bowtie Item \right)$$

- Liste os ids de fornecedores que fornecem algum item vermelho ou estão localizados na rua dos Alfeneiros, 4.

$$\pi_{fid} \sigma_{cor="vermelho" or endereco="rua dos Alfeneiros, 4"} \left( Forcenedor \bowtie Catalogo \bowtie Item \right)$$

- Liste os ids dos fornecedores que fornecem algum item vermelho e algum item verde.

$$\pi_{fid} \sigma_{cor="vermelho" and cor="verde"} \left( Forcenedor \bowtie Catalogo \bowtie Item \right)$$

- Liste os ids dos fornecedores que fornecem todos os itens.

> Divisão.  
> Olhar nos slides um jeito de emular divisão em SQL.

- Liste os ids dos fornecedores que fornecem todos os itens vermelhos.

> Divisão de novo.

- Liste pares de ids dos fornecedores nos quais o primeiro id cobra mais por alguma parte que o segundo id.

> ???

- Liste os ids dos itens que são fornecidos por pelo menos dois fornecedores diferentes.

> Divisão

- Liste os ids dos itens mais caros fornecidos pelo fornecedor Brahma.

> http://stackoverflow.com/questions/5493691/how-can-i-find-max-with-relational-algebra 

