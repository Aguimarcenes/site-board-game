# Guarda-Jogos

Site de aluguel de jogos de tabuleiro em **São João del-Rei, MG**.

Protótipo funcional em arquivo único, sem dependências, sem build. Abre com dois
cliques no navegador.

## Como abrir

Dê dois cliques em `index.html`. É só isso — não precisa de servidor, Node nem
instalação de nada.

Para ver a versão mobile no computador, abra o DevTools (F12) e ligue o modo
responsivo.

## Estrutura

```
index.html      o site inteiro (HTML, CSS e JS num arquivo só)
estudio.html    ferramenta interna para montar e fotografar o guarda-roupa 3D
fotos/          fotos das caixas dos jogos
```

## O acervo

Doze jogos, em três faixas de preço por 7 dias:

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

## O estúdio

`estudio.html` é ferramenta interna, não faz parte do site. Ele carrega os `.glb`
do guarda-roupa impresso, monta as peças, abre a porta e exporta o PNG que a tela
inicial usa. Precisa de internet na primeira vez (carrega o three.js de CDN).
