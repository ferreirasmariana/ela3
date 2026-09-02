# Site do ELA³ Experience

Site estático, sem framework e sem backend. Dois arquivos HTML, uma folha de estilo, os assets.
Abre direto no navegador, sobe em qualquer hospedagem.

```
index.html            página principal (participantes)
parceiros.html        página de parcerias (marcas)
assets/css/style.css  toda a folha de estilo
assets/img/           fotos das edições anteriores, em .webp
assets/svg/           logo, lockup e elementos gráficos, vetoriais
```

## Depois que uma edição acontece

Veja o **[DEPOIS-DO-EVENTO.md](DEPOIS-DO-EVENTO.md)**. Ele lista, arquivo por
arquivo, tudo que vence no dia seguinte ao encontro, e o `index.html` já tem os
dois estados do bloco da próxima edição escritos, bastando comentar um e
descomentar o outro.

## O que precisa ser trocado a cada edição

Tudo está em texto puro no HTML, sem build. Buscar e substituir:

| O quê | Onde aparece |
|---|---|
| `13 de setembro de 2026` | hero, rodapé, `<title>`, meta description, JSON-LD |
| `5ª edição` | hero, `<title>`, rodapé |
| `Parque Burle Marx` | hero, seção "A experiência", JSON-LD |
| Cronograma | `<ul class="crono">`, nos dois arquivos |
| Números da comunidade | `<section class="numeros">`, nos dois arquivos |
| WhatsApp `5511976100953` | formulário, botão flutuante, rodapé |

O bloco `application/ld+json` no topo do `index.html` é o que faz o Google mostrar data e local
do evento na busca. Se a data mudar e esse bloco não, o Google mostra a data velha.

## Fontes e cores

Playfair Display (títulos) e Montserrat (texto), as duas do Manual de Identidade Visual,
carregadas do Google Fonts. As cores estão como variáveis no topo do `style.css`:

`--off-white #f7f4f1` · `--blush #f2d7da` · `--rosa #c98c8f` · `--chocolate #4a2f2a` · `--dourado #d4af37`

## Sobre os SVG

A logo, o lockup "ELA³ experience", as manchas orgânicas e os desenhos botânicos foram
extraídos em vetor dos PDFs originais (Manual de Identidade Visual e Folder 18x12,5).
São os arquivos oficiais, não uma recriação. Escalam sem perder nitidez.

`logo-ela3.svg` usa `currentColor`: se for colocado inline no HTML, herda a cor do CSS.
As variantes `logo-rosa`, `logo-dourado`, `logo-chocolate` e `logo-offwhite` têm a cor fixa,
para uso em `<img>`. Os arquivos `marca-*` são a mesma logo sem a linha "por Tatiana Ribeiro",
para usar em tamanho pequeno, como no menu.

## O formulário

Não tem servidor. Ao enviar, o navegador monta a mensagem e abre o WhatsApp da Tatiana
com tudo preenchido. Funciona no celular e no desktop, não depende de nenhum serviço
e não tem mensalidade.

Se em algum momento for preciso ter os contatos numa planilha, dá para trocar por um
formulário do Tally ou do Formspree sem mexer no visual.

## Como publicar

O site é estático, então qualquer hospedagem serve. As duas opções gratuitas com domínio
próprio incluído:

**Cloudflare Pages** — cria a conta, "Create a project", "Direct Upload", arrasta a pasta.
**Netlify Drop** — app.netlify.com/drop, arrasta a pasta, sai no ar na hora.

Nos dois, o domínio próprio se aponta depois, em Settings.

### Domínio

`ela3.com.br` estava **livre** na consulta de 02/09/2026. Registro é no registro.br,
custa cerca de R$ 40 por ano e precisa do CPF ou CNPJ de quem vai ser dono do domínio.
Quem registra deve ser a Tatiana, para o domínio ficar no nome dela.

As tags `<link rel="canonical">` e as `og:` de cada página já apontam para `https://ela3.com.br`.
Se o domínio escolhido for outro, trocar nos dois arquivos.

## Pendências

- [ ] Registrar o domínio (Tatiana)
- [ ] Foto de retrato da Tatiana em boa resolução, para a seção "Quem cria".
      A que está no ar hoje saiu de um post do Instagram
- [ ] Confirmar se o valor do patrocínio entra na página ou fica sob consulta
      (hoje está "Valores sob consulta")
- [ ] Confirmar se a 5ª edição ainda tem vagas abertas. Se estiver esgotada,
      o CTA vira lista de espera da 6ª
- [ ] Depoimento de participante, se existir. É o que falta para a página convencer sozinha
