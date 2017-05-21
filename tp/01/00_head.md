# DCC011 - Introdução a Banco de Dados

> Yuri Diego Santos Niitsuma (2011039023)

## Trabalho Prático 1

<!-- ### Esquema relacional

Esse banco de dados contém informações sobre pesquisadores, instituições e artigos publicados no Simpósio Brasileiro de Banco de Dados entre os anos de 1986 a 2010. O esquema relacional desse banco é o seguinte:

```
pais(id, nome)
estado(id, pais id, sigla, nome)
	estado[pais id] → pais[id]
cidade(id, estado id, nome)
	cidade[estado id] → estado[id]
edicao(id, edicao num, ano, cidade id)
	edicao[cidade id] → cidade[id]
sessao(id, edicao id, titulo)
	sessao[edicao id] → edicao[id]
artigo(id, sessao id, titulo)
	artigo[sessao id] → sessao[id]
instituicao(id, nome, pais id)
	instituicao[pais id] → pais[id]
pesquisador(id, nome, sexo, pais id)
	pesquisador[pais id] → pais[id]
autor(id, pesquisador id, instituicao id)
	autor[pesquisador id] → pesquisador[id]
	autor[instituicao id] → instituicao[id]
autoria(autor id, artigo id)
	autoria[autor id] → autor[id]
	autoria[artigo id] → artigo[id]
``` -->
