# Jojocas — jogos & café

Site de aluguel de jogos de tabuleiro em **São João del-Rei e região, MG**.

Protótipo funcional em arquivo único. Abre com dois cliques no navegador. A única
dependência externa são as fontes da marca, carregadas do Google Fonts — offline
o site cai em fontes de reserva sem quebrar.

## A marca

Aplicada a partir do manual (`Jojocas, manual de marca.pdf`):

- **Nome** em Permanent Marker — só o nome e chamadas curtíssimas, nunca frase inteira.
- **Toques manuscritos** ("jogos & café", assinatura) em Caveat.
- **Todo o resto** — títulos, corpo, botões — em Nunito.
- Paleta verde mata + mostarda (ver seção Paleta).

> **Localização a confirmar.** O manual assina a marca em **Tiradentes · MG**
> (onde nasce o café futuro), mas a operação de aluguel atende **São João del-Rei
> e região**. O site usa São João del-Rei por ser a praça do aluguel — trocar é
> um campo só, na capa e no rodapé.

## Como abrir

Dê dois cliques em `index.html`. Não precisa de servidor, Node nem instalação.

Para ver a versão mobile no computador, abra o DevTools (F12) e ligue o modo
responsivo.

## Estrutura

```
index.html      o site inteiro (HTML, CSS e JS num arquivo só)
estudio.html    ferramenta interna para montar e fotografar o guarda-roupa 3D
fotos/          fotos das caixas dos jogos
```

## Paleta

Verde mata + mostarda. As variáveis ficam no `:root`, no início do `<style>`.

| Papel | Variável | Hex |
|---|---|---|
| Identidade | `--verde` | `#1F3D2B` |
| Verde fundo | `--verde-2` | `#16291C` |
| Destaque / CTA | `--mostarda` | `#D9A441` |
| Hover do CTA | `--mostarda-2` | `#B8842E` |
| Fundo geral | `--creme` | `#F5EFE0` |
| Creme rebaixado | `--creme-2` | `#EBE1CC` |
| Superfície | `--branco` | `#FFFFFF` |
| Texto | `--tinta` | `#14261A` |
| Texto de apoio | `--tinta-2` | `#4F5F43` |
| Legenda | `--tinta-3` | `#56634C` |
| Texto sobre verde | `--sobre-verde` | `#EAD9A0` |
| Texto no botão | `--sobre-mostarda` | `#3C2A0A` |

### A regra da mostarda

**Mostarda nunca como texto sobre o creme.** Medido: `--mostarda` sobre
`--creme` dá **1,96:1** e `--mostarda-2` dá **2,87:1** — as duas reprovam até o
mínimo de 3:1 para texto grande.

Onde ela funciona:

- **preenchendo** um elemento (fundo de botão, com `--sobre-mostarda` por cima): **6,11:1**
- **sobre o verde mata** (título da abertura, aba ativa): **5,30:1**

Como texto ou ícone sobre fundo claro, use `--verde`. Os tons de apoio
(`--tinta-2` e `--tinta-3`) foram escurecidos em relação à paleta original por
esse mesmo motivo — os valores propostos ficavam em 3,14 e 4,26:1.

O site tem 132 elementos de texto verificados, todos acima do mínimo AA.

### A abertura é escura de propósito

A tela do guarda-roupa usa `--verde` e `--verde-2` como fundo, e é a única parte
escura do site. Não é inconsistência: **a luz saindo do armário só existe contra
o escuro.** O resto do site é creme, como a paleta pede.

## Disponibilidade (quais jogos estão alugados)

O que aparece como "disponível" ou "volta dia X" vem do arquivo
[`disponibilidade.txt`](disponibilidade.txt), editável direto no GitHub sem mexer
em código. O site lê esse arquivo ao carregar e aplica sobre o acervo; se o
arquivo faltar ou tiver erro de digitação, tudo aparece como disponível e o site
não quebra. O passo a passo está em [`DISPONIBILIDADE.md`](DISPONIBILIDADE.md).

## O acervo

Dezesseis jogos, em três faixas de preço por dia:

| Faixa | Preço | Jogos |
|---|---|---|
| Leve | R$ 15 | Saboteur, Coup, Decisões de Merda |
| Média | R$ 25 | Dixit, Quartz, Azul, 7 Wonders Duel |
| Premium | R$ 35 | Ticket to Ride Europa, Wingspan, Terra Nova, Orla Exterior, Terraforming Mars |

O acervo fica no array `JOGOS`, no início do bloco `<script>`. Para adicionar um
jogo, acrescente um item ao array e uma capa ilustrada em `CAPAS` com a mesma
chave `id`.

## Fotos das caixas

Cada capa tem uma **ilustração vetorial de reserva**. Quando existe foto, ela
cobre a ilustração; quando não existe, a ilustração aparece. Dá para ir
adicionando uma foto por vez.

O nome do arquivo tem que ser o `id` do jogo, **tudo em minúsculo**:

`saboteur` · `coup` · `decisoes` · `dixit` · `quartz` · `azul` · `duel` ·
`ticket` · `wingspan` · `terranova` · `orla` · `marte`

O site tenta `fotos/<id>.webp` primeiro e cai em `fotos/<id>.jpg`. Prefira webp:
pesa menos da metade.

Detalhes de formato e de como fotografar estão em [`fotos/LEIAME.md`](fotos/LEIAME.md).

> Maiúsculas importam. No Windows dá na mesma, mas o GitHub Pages roda em Linux e
> `Azul.jpg` não é o mesmo arquivo que `azul.jpg`.

## Antes de publicar

- [ ] Trocar o número do WhatsApp na constante `ZAP` (hoje está `5532999999999`)
- [ ] Conferir a taxa de entrega nas dúvidas (hoje: grátis até 3 km, R$ 8 acima)
- [ ] Trocar a data fixa de retorno do Terraforming Mars por controle real
- [ ] Confirmar o `@` do Instagram citado em "Quem sou"
- [ ] Fotografar Decisões de Merda, Wingspan e Orla Exterior

## O estúdio (legado)

`estudio.html` foi feito para montar e fotografar o guarda-roupa 3D da versão
anterior. A entrada do site agora é a capa da marca Jojocas, sem guarda-roupa, e
o estúdio não é mais usado pelo site — fica guardado caso o modelo 3D volte a ser
útil em outra peça.
