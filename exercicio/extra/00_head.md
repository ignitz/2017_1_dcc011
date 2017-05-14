**Considere o seguinte esquema relacional:**

```
Cliente ([CodCli], NomeCli, UFCli)
Projeto ([Sigla], NomePro, DataInicio, CodCli)
Consultor ([CPF], NomeCon, DataNascCon, UFNascCon)
Equipe ([Sigla, CPF])
Viagem ([CPF, Sigla, Data], Origem, Destino)
Local ([NomeLoc], UFLoc)

Projeto.CodCli -> Cliente.CodCli
Equipe.Sigla -> Projeto.Sigla
Equipe.CPF -> Consultor.CPF
Viagem.CPF -> Consultor.CPF
Viagem.Sigla -> Projeto.Sigla
Viagem.Origem -> Local.NomeLoc
Viagem.Destino -> Local.NomeLoc
```

**Observações:**

Nenhum atributo admite valor nulo
Apenas as seguintes chaves primárias são numéricas: Cliente.CodCli, Consultor.CPF

**Responda às seguintes questões em álgebra relacional e SQL:**

1. Que projetos (sigla e nome) não têm equipe?
2. Que projetos (sigla e nome) não têm em sua equipe consultores nascidos antes de 1987?
3. Que projetos (sigla e nome) têm consultores que realizaram viagens para o Rio Grande do Sul (RS)?
4. Que projetos (sigla e nome) não são do cliente "Kuala Lumpur"?
5. Que projetos (sigla e nome) têm na sua equipe todos os consultores nascidos no Paraná (PR)?
6. Para que UFs viajaram os consultores que participam do projeto de sigla "XP"?
7. Que consultores (CPF e nome) viajaram para o seu estado natal?
8. Em que projetos (sigla e nome) houve casos de consultores viajando para o seu estado natal?
9. Em que projetos (sigla e nome) foram realizadas viagens para a Bahia (BA) em 2007?
10. Para que locais (nome) não houve nenhuma viagem?
11. Que locais (nome) não foram utilizados nem como origem e nem como destino de viagens?
12. Que consultores (CPF e nome) não estão em nenhuma equipe de projeto que tenha iniciado em 2007?
13. Que consultores (CPF e nome) não nasceram no Rio de Janeiro (RJ)?
14. Que consultores (CPF e nome) viajaram por um projeto de cuja equipe não fazem parte?
15. Que consultores (CPF e nome) participam de todos os projetos do cliente "Kuala Lumpur"?1. 
