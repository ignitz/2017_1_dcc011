**Seja o seguinte esquema relacional:**

`Fornecedor ({fid: integer, fnome: string}, endereço: string)`  
`Item ({itemid: integer}, inome: string, cor: string)`  
`Catalogo ({fid: integer, itemid: integer}, preço: real)`  

**Resolva as seguintes consultas usando Álgebra Relacional E SQL:**

- Liste os nomes de fornecedores que fornecem algum item vermelho.
- Liste os ids de fornecedores que fornecem algum item vermelho ou estão localizados na rua dos Alfeneiros, 4.
- Liste os ids dos fornecedores que fornecem algum item vermelho e algum item verde.
- Liste os ids dos fornecedores que fornecem todos os itens.
- Liste os ids dos fornecedores que fornecem todos os itens vermelhos.
- Liste pares de ids dos fornecedores nos quais o primeiro id cobra mais por alguma parte que o segundo id.
- Liste os ids dos itens que são fornecidos por pelo menos dois fornecedores diferentes.
- Liste os ids dos itens mais caros fornecidos pelo fornecedor Brahma.
