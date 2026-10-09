# Lista de conferências de tecnologia musical

Este repositório hospeda uma lista de conferências, chamadas de periódicos
e chamadas artísticas para a comunidade ampla de tecnologia musical.

Este é um fork em português, com foco no Brasil, do projeto
[mtg/conferences](https://github.com/mtg/conferences), criado pelo
[Music Technology Group (MTG UPF)](http://mtg.upf.edu).

Qualquer pessoa pode contribuir enviando um pull request com os dados de uma
nova conferência, chamada de periódico ou chamada artística. Veja as instruções abaixo.


## Como contribuir

### Conferências
Faça um fork do repositório e crie um novo arquivo na pasta `_conferences`.
Nomeie-o `[ano]-[sigla][ano].md`, por exemplo `2017-ismir2017.md`.
Escreva a sigla da conferência em minúsculas.
O ano no início serve para ordenar os arquivos na listagem da pasta.

Copie o modelo abaixo para o arquivo e preencha cada campo. As datas devem
estar no formato `aaaa-mm-dd` entre aspas, por exemplo `'2017-04-01'`.
```
---
title:
acronym:
date: '202x-mm-dd' # Data da conferência. Use 2 dígitos para mm e dd
end_date: '202x-mm-dd' # Data de término, deixe vazio se desconhecida
submission_date: '202x-mm-dd' # Prazo de submissão
ext_url: # Link externo para o site da conferência
location: # Cidade, País
---
```

Salve o arquivo e envie a contribuição como pull request.

### Periódicos
Faça o fork como nas conferências e crie um arquivo na pasta `_journals`.
Nomeie o arquivo algo como `[ano]-[nome-do-periodico].md`. Se houver várias
edições do mesmo periódico no mesmo ano, acrescente uma letra ao ano (`2017b-periodico.md`)
ou inclua o nome da edição no arquivo.
Por convenção, usamos minúsculas, hífens no lugar de espaços e apenas letras e números no nome.

Use o conteúdo abaixo. As datas devem estar no formato `aaaa-mm-dd` entre aspas.

O campo `date` é exigido pelo Jekyll, mas não é exibido. Pode ser igual a
`submission_date` ou à data de publicação da edição.

```
---
submission_date: '202x-mm-dd' # Prazo de submissão
date: '202x-mm-dd' # Igual a submission_date, ou data de publicação
journal: # Nome do periódico
issue: # Nome desta edição
ext_url: # Link da chamada de artigos desta edição
---
```

### Chamadas artísticas
Crie um arquivo na pasta `_chamadas`, nomeado `[ano]-[nome-da-chamada].md`
(minúsculas, hífens, só letras e números). O ano é o do prazo de inscrição.
O texto depois do cabeçalho é opcional e serve para um resumo curto.

```
---
title: # Nome da chamada
organization: # Quem organiza
type: # Obra, Performance, Instalação, Residência, Workshop ou Outro
submission_date: '202x-mm-dd' # Prazo de inscrição
date: '202x-mm-dd' # Igual a submission_date (exigido pelo Jekyll)
event_date: '202x-mm-dd' # Data do evento ou da residência, deixe vazio se desconhecida
location: # Cidade, País (ou Online)
conditions: # Taxa, cachê, apoio de viagem etc.
ext_url: # Link da chamada oficial
---
Resumo opcional: formato, duração máxima, requisitos técnicos.
```

## Informações técnicas

Cada ano tem uma página própria. No fim de cada ano é preciso atualizar as
páginas `index.html` e criar as páginas do ano que passou.
- Crie 3 novos arquivos `aaaa.html`: um para conferências (raiz), um para
  periódicos (dentro de `journalcalls`) e um para chamadas artísticas (dentro de `chamadas`).
  Copie o conteúdo de um ano anterior e troque o ano no título e na linha `include`.
- Atualize os três `index.html` (raiz, `journalcalls` e `chamadas`): troque o ano
  na linha `{% include conferences.html year="2026" confs=confs greaterthan=true %}`
  (ou `journals.html` / `chamadas.html`) pelo ano seguinte e acrescente o link do
  ano que passou, por exemplo `<a href="2026">2026</a>`.
