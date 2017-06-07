1. Seja a tabela (não necessariamente normalizada):

`Oferta({CodDisc, AnoSem, SiglaTurma, HoraInicio}, NumHoras, NomeDisc, CreditosDisc)`

E as dependências funcionais:

```
(CodDisc, AnoSem, SiglaTurma, HoraInicio) -> NumHoras
CodDisc -> NomeDisc
CodDisc -> CreditosDisc
```

a) Em qual forma normal a tabela está?

b) Caso não esteja na 3FN, mostre cada forma intermediária da tabela até a 3FN.

--------------------------------------------------------------------------

2. Seja a tabela (não necessariamente normalizada):

`Voo({SiglaCia, NoVoo}, NomeCia, SiglaAeroSaida, NomeAeroSaida, HoraSaida, HoraChegada)`

E as dependências funcionais:

```
(SiglaCia,NoVoo) -> SiglaAeroSaida
(SiglaCia,NoVoo) -> NomeAeroSaida
(SiglaCia,NoVoo) -> HoraSaida
(SiglaCia,NoVoo) -> HoraChegada
SiglaCia -> NomeCia
SiglaAeroSaida -> NomeAeroSaida
```

a) Em qual forma normal a tabela está?

b) Caso não esteja na 3FN, mostre cada forma intermediária da tabela até a 3FN.