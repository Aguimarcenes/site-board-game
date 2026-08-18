# Controlar quais jogos estão alugados

O site mostra, em cada jogo, se ele está **disponível** ou **alugado até tal dia**.
Isso vem de um arquivo só: **`disponibilidade.txt`**. Você edita ele, e o site
se atualiza sozinho em cerca de 1 minuto. Não precisa mexer em código.

## Como marcar um jogo como alugado

1. Abra o repositório no GitHub (dá pelo celular).
2. Entre no arquivo **`disponibilidade.txt`** e toque no **lápis** (Edit).
3. Lá no fim, escreva uma linha com o **id do jogo**, um espaço, e a **data que
   ele volta** no formato ano-mes-dia. Exemplo:

   ```
   marte 2026-08-25
   ```

4. Toque em **Commit changes** (botão verde) para salvar.
5. Em ~1 minuto o site mostra "Terraforming Mars — volta segunda, 25 de agosto".

## Como liberar de novo

Quando o jogo voltar, edite o arquivo e **apague a linha** dele. Salvar. Pronto:
volta a aparecer como disponível.

## Regras que evitam erro

- **Um jogo por linha.** `id` espaço `data`. Só isso.
- **O que não estiver escrito aparece como disponível.** Você só lista o que está
  fora.
- **Linhas com `#` são ignoradas** — são anotações, pode usar à vontade.
- **Se você errar** (data estranha, id que não existe, linha bagunçada), o site
  não quebra: aquele jogo simplesmente continua como disponível. Nada de tela de
  erro para o cliente.
- A data é **ano-mes-dia**: 3 de setembro de 2026 = `2026-09-03`.

## Os ids dos jogos

| id | Jogo |
|---|---|
| `saboteur` | Saboteur |
| `coup` | Coup |
| `decisoes` | Decisões de Merda |
| `tgcqp` | Taco Gato Cabra Queijo Pizza |
| `resistence` | The Resistance |
| `catan` | Catan |
| `dixit` | Dixit |
| `quartz` | Quartz |
| `azul` | Azul |
| `duel` | 7 Wonders Duel |
| `ticket` | Ticket to Ride: Europa |
| `wingspan` | Wingspan |
| `oak` | Oak |
| `terranova` | Terra Nova |
| `orla` | Star Wars: Orla Exterior |
| `marte` | Terraforming Mars |

A mesma lista está dentro do próprio `disponibilidade.txt`, para consultar na hora.

## Exemplo completo

Se o Catan e o Terraforming Mars estão alugados, o arquivo fica assim no fim:

```
catan 2026-08-22
marte 2026-08-25
```

Todos os outros 14 jogos aparecem como disponíveis.
