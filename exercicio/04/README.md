# Exercício 4

> Yuri Diego Santos Niitsuma  
> 2011039023

Dado o seguinte esquema relacional:  
```
Pesquisador ([CodPesq], NomePesq)
Artigo ([CodArt], TituloArt, VeiculoArt, AnoArt)
Referencia ([CodArtReferenciador, CodArtReferenciado])
Autoria ([CodArt, CodPesq], PosicaoAut)
```
ps: Não existe *underline* no markdown então mudei para [].

<!-- ### Símbolos -->

<!-- $$R \bowtie S = \left\{ r \cup s \ \vert \ r \in R \ \land \ s \in S \ \land \ \mathit{Fun}(r \cup s) \right\}$$
$$R\times S:=\{(r_{1},r_{2},\dots ,r_{n},s_{1},s_{2},\dots ,s_{m})|(r_{1},r_{2},\dots ,r_{n})\in R,(s_{1},s_{2},\dots ,s_{m})\in S\}$$
$$\Pi_{a_1, \ldots,a_n}( R )$$
$${\displaystyle \sigma _{{\text{isFriend = true}}\,\lor \,{\text{isBusinessContact = true}}}({\text{addressBook}})}$$
$$\rho_{\text{isBusinessContact / isFriend} } ( \text{addressBook} )$$ -->

<!-- $$
\bowtie
\times
\pi
\sigma
\rho
$$ -->

**Especifique as consultas abaixo usando álgebra relacional:**  

1. Obter os nomes dos pesquisadores que, em 2006, publicaram artigos em veículo intitulado “VLDB Journal”, constando como primeiro autor. Resolver usando produto cartesiano.

$X_1 = \sigma_{Pesquisador.CodPesq = Autoria.CodPesq\ AND\ PosicaoAut = 1} \left( Pesquisador \times Autoria \right)$  
$X_2 = \sigma_{AnoArt=2006\ AND\ VeiculoArt = "VLDB\ Journal"}\left( X_1 \times Artigo \right)$  
$X_3 = \pi_{NomePesq}(X_2)$  

2. Resolver a questão (1) usando junções (naturais, de preferência).

$
\pi_{NomePesq}\left(\sigma_{AnoArt=2006\ AND\ PosicaoAut=1\ AND\ VeiculoArt = "VLDB\ Journal"} \left(Artigo \bowtie \left( Pesquisador \bowtie Autoria \right) \right)\right)
$

3. Obter os nomes dos pesquisadores que não foram autores de artigos.  

> Esta questão tá ambígua se quer de 2006 ou não. Não se sabe se a questãoé continuação da questão 2.

$
\pi_{NomePesq}\left(\sigma_{PosicaoAut>1} \left(Artigo \bowtie \left( Pesquisador \bowtie Autoria \right) \right)\right)
$

4. Obter os códigos dos pesquisadores que publicaram todos artigos de 2006.

$
\pi_{CodPesq}\left(\sigma_{AnoArt=2006} \left(Artigo \bowtie \left( Pesquisador \bowtie Autoria \right) \right)\right)
$
