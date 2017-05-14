\newpage
# Respostas
## Algebra Relacional


1. ${\pi _{(Sigla,\;NomePro)}}\left( {Projeto - {\pi _{(Sigla,\;NomePro)}}\left( {Projeto \bowtie Equipe} \right)} \right)$
2. ${\pi _{(Sigla,\;NomePro)}}\left( {{\sigma _{(DataNascCon\; \ge \;1987)}}\left( {Projeto \bowtie Equipe \bowtie Consultor} \right)} \right)$
3. ${\pi _{(Sigla,\;NomePro)}}\left( {{\sigma _{(Destino = "RS")}}\left( {Projeto \bowtie Equipe \bowtie Consultor \bowtie Viagem} \right)} \right)$
4. ${\pi _{(Sigla,\;NomePro)}}\left( {{\sigma _{(NomeCli\; \ne \;{\rm{"Kuala Lamper"}})}}\left( {Projeto \bowtie Cliente} \right)} \right)$
5. ${\pi _{(Sigla,\;NomePro)}}\left( {{\sigma _{(UFNascCon\; = \;{\rm{"PR"}})}}\left( {Projeto \bowtie Equipe \bowtie Consultor} \right)} \right)$
6. ${\pi _{(UFLoc)}}\left( {{\sigma _{(Destino\; = \;NomeLoc{\rm{ AND }}Sigla\; = \;{\rm{"XP"}})}}\left( {Viagem \times Local} \right)} \right)$
7. ${\pi _{(CPF,NomeCon)}}\left( {{\sigma _{(UFNascCon = UFLoc\;\;{\rm{AND}}\;\;Destino = NomeLoc)}}\left( {Consultor \bowtie Viagem \times Local} \right)} \right)$
8. $X = \left( {Projeto \bowtie Equipe \bowtie Consultor \bowtie Viagem} \right) \times Local$  
   ${\pi _{(SiglaNomePro)}}\left( {{\sigma _{(Destino = NomeLoc\;\;{\rm{AND}}\;\;UFNascCon = UFLoc)}}(X)} \right)$
9. ${\pi _{(Sigla,NomePro)}}\left( {{\sigma _{UFLoc = "BA"\;\;{\rm{AND}}\;\;Data = 2007\;\;{\rm{AND}}\;\;Destino = NomeLoc}}\left( {Projeto \bowtie Viagem \times Local} \right)} \right)$
10. 
11. $X = {\rho _{NomeLocal}}\left( {{\pi _{Origem}}\left( {Viagem} \right)} \right) \cup {\rho _{NomeLocal}}\left( {{\pi _{Destino}}\left( {Viagem} \right)} \right)$  
    ${\pi _{NomeLocal}}\left( {Local} \right) - X$
12. $X = Consultor \bowtie Equipe \bowtie \left( {{\sigma _{Data < 2007}}Projeto} \right)$  
    ${\pi _{CPF,Nome}}\left( {Consultor} \right) - {\pi _{CPF,Nome}}\left( X \right)$
13. $X = Consultor{ \bowtie _{UFNascCon = UFLocal}}Local$  
    ${\pi _{(CPF,Nome)}}\left( {{\sigma _{UFNascCon = "RJ"}}\left( X \right)} \right)$
14. $X = Consultor \bowtie Viagem$  
    ${\sigma _{(X.CPF = EquipeCPF\;\;{\rm{AND}}\;\;X.Sigla \ne Equipe.Sigla)}}\left( {Equipe \times X} \right)$
15.

\newpage