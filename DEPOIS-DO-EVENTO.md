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
| bloco `application/ld+json` | é o registro de evento que o Google lê, e traz o link do Sympla | **apagar o bloco inteiro** enquanto não houver data nova. Evento sem data no Google vira erro |
| hero | `5ª edição`, `13 de setembro de 2026`, `Parque Burle Marx · São Paulo` | `Próxima edição`, `Em breve`, e apagar o local |
| botões `Garantir ingresso` | 2 ocorrências (menu e hero), apontando para `#ingresso` | `Entrar na lista`, apontando para `#inscricao` |
| **seção `INGRESSO`** | o card com a data, o local e o botão do Sympla | **comentar a seção inteira.** Ela existe só enquanto há ingresso à venda. Ver o passo 3 |
| mensagem do WhatsApp no script | `Quero garantir minha vaga na 5a edicao...` | `Quero entrar na lista da proxima edicao do ELA3.` |
| rodapé | `ELA³ Club · 5ª edição · 13 de setembro de 2026` | `ELA³ Club · Mente, corpo e finanças` |

### `edicoes.html`

- A chamada final ainda anuncia 13 de setembro. Trocar por "a próxima edição está
  sendo desenhada" e o botão para `Entrar na lista`
- Botões `Garantir ingresso` e `Garantir meu ingresso`: viram `Entrar na lista`,
  apontando para `index.html#inscricao`
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
- Botão `Garantir meu ingresso`: vira `Entrar na lista`
- Rodapé, igual ao index

### `parceiros.html` e `obrigada.html`

- Os botões `Garantir ingresso` viram `Entrar na lista` ou voltam para o início

---

## Passo 3 · desligar a venda

A seção `INGRESSO` do `index.html` é a única coisa do site ligada ao Sympla. O
link está em dois lugares:

1. o botão **Comprar meu ingresso**, dentro da seção
2. o campo `offers` do bloco `application/ld+json`, no topo do arquivo

Quando a 5ª edição passar, comente a seção inteira (de
`<!-- ============ INGRESSO ============ -->` até o `</section>` que fecha) e
deixe no ar só o formulário, que já está dentro dela, logo depois do "Ou".

Quando a 6ª edição tiver ingresso à venda, descomente e troque o link do Sympla
pelo do evento novo. **Só o endereço muda**, o resto do card continua servindo.

O que **não** se mexe: a comunidade do WhatsApp e o formulário. Os dois são
permanentes e não dependem de haver edição marcada.

---

## Quando a 6ª edição tiver data

O caminho é o inverso, e mais fácil: volte o bloco TEM DATA, troque data, local,
número da edição e cronograma, e recoloque o bloco `application/ld+json` com as
datas novas. Os textos permanentes não se mexem.

## Como achar tudo de uma vez

No terminal, dentro da pasta do projeto:

```
grep -n "13 de setembro\|5ª edição\|2026-09-13\|sympla\|Garantir" *.html
```

Se esse comando não retornar nada, a virada está completa.
