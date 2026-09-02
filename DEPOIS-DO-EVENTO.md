# Como virar o site depois de uma edição

Este site tem duas camadas. Uma é permanente: o que é o ELA³, os três pilares, a
Tatiana, o lema, as edições anteriores, a página de marcas e a de viagem. Essa
camada não muda.

A outra é a edição vigente, hoje a 5ª, de 13 de setembro de 2026 no Parque Burle
Marx. Essa camada vence no dia seguinte ao evento.

Este arquivo lista **todos** os lugares que precisam mudar. Nenhum outro.

---

## Passo 1 · trocar o bloco da próxima edição

Em `index.html`, procure o comentário `PRÓXIMA EDIÇÃO`. Existem dois blocos ali,
já escritos:

- **ESTADO: TEM DATA** — a programação, o cronograma, os selos. É o que está no ar
- **ESTADO: SEM DATA** — "A 6ª edição está sendo desenhada", com o convite para
  entrar na lista. Está comentado, esperando

Comente o primeiro, descomente o segundo. É a única mudança estrutural.

## Passo 2 · trocar a data nos 5 lugares que sobram

### `index.html`

| Linha aproximada | O que está lá | Trocar por |
|---|---|---|
| `<title>` | `5ª edição · 13 de setembro de 2026 · São Paulo` | `ELA³ Club · encontros para mulheres · São Paulo` |
| `meta description` e `og:description` | trazem a data | tirar a data, manter o resto |
| bloco `application/ld+json` | é o registro de evento que o Google lê | **apagar o bloco inteiro** enquanto não houver data nova. Evento sem data no Google vira erro |
| hero | `5ª edição`, `13 de setembro de 2026`, `Parque Burle Marx · São Paulo` | `Próxima edição`, `Em breve`, e apagar o local |
| botões `Quero minha vaga` | 3 ocorrências (menu, hero, formulário) | `Entrar na lista` |
| texto do formulário | `...os detalhes da 5ª edição` | `...assim que a próxima edição tiver data` |
| mensagem do WhatsApp no script | `Quero garantir minha vaga na 5a edicao...` | `Quero entrar na lista da proxima edicao do ELA3.` |
| rodapé | `ELA³ Club · 5ª edição · 13 de setembro de 2026` | `ELA³ Club · Mente, corpo e finanças` |

### `edicoes.html`

- A chamada final ainda anuncia 13 de setembro. Trocar por "a próxima edição está
  sendo desenhada" e o botão para `Entrar na lista`
- Botão do menu: `Quero minha vaga` vira `Entrar na lista`
- Rodapé, igual ao index
- **E o mais importante:** a 5ª edição vira uma edição anterior. Escreva o bloco
  dela na página, no mesmo formato dos outros: pilar em foco, programação, quem
  conduziu e marcas parceiras

### `parceiros.html`

- Hero: `Parcerias · 5ª edição` e a linha com a data
- Rodapé, igual ao index

### `viagem.html`

- A seção final inteira ("A 5ª edição é dia 13 de setembro") sai ou vira o convite
  para a lista
- Rodapé, igual ao index

---

## Quando a 6ª edição tiver data

O caminho é o inverso, e mais fácil: volte o bloco TEM DATA, troque data, local,
número da edição e cronograma, e recoloque o bloco `application/ld+json` com as
datas novas. Os textos permanentes não se mexem.

## Como achar tudo de uma vez

No terminal, dentro da pasta do projeto:

```
grep -n "13 de setembro\|5ª edição\|2026-09-13\|Quero minha vaga" *.html
```

Se esse comando não retornar nada, a virada está completa.
