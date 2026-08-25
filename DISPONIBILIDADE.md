# Controlar quais jogos estão alugados

Na estante, o cliente escolhe uma **data** e vê a disponibilidade de cada jogo
naquele dia. Isso vem de um arquivo só: **`disponibilidade.txt`**. Você edita ele,
e o site se atualiza sozinho em cerca de 1 minuto. Não precisa mexer em código.

## Como marcar um aluguel

1. Abra o repositório no GitHub (dá pelo celular).
2. Entre no arquivo **`disponibilidade.txt`** e toque no **lápis** (Edit).
3. Lá no fim, escreva uma linha com o **id do jogo**, a **data que sai** e a **data
   que volta**, no formato ano-mes-dia:

   ```
   catan 2026-08-22 2026-08-25
   ```

   Isso deixa o Catan ocupado nos dias 22, 23 e 24, e livre de novo no dia 25.

   Se o aluguel começa hoje, pode escrever só a data de volta:

   ```
   marte 2026-08-25
   ```

4. Toque em **Commit changes** (botão verde) para salvar.
5. Em ~1 minuto o site já responde pela data que o cliente escolher.

## Como liberar

Quando o jogo voltar, edite o arquivo e **apague a linha** dele. Salvar. Pronto.

## Regras que evitam erro

- **Um aluguel por linha.** `id` `data-que-sai` `data-que-volta` (ou só `id` `data-que-volta`).
- **Um jogo pode ter várias linhas** — vários aluguéis em datas diferentes.
- **O que não estiver escrito aparece como disponível.** Você só lista o que está fora.
- **Linhas com `#` são ignoradas** — são anotações, pode usar à vontade.
- **Se você errar** (data estranha, id que não existe, linha bagunçada), o site
  não quebra: aquele aluguel é ignorado e o jogo continua disponível. Nada de tela
  de erro para o cliente.
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

O Catan está alugado de 22 a 24 de agosto, o Terraforming Mars sai hoje e volta
dia 25, e o Azul tem dois aluguéis marcados:

```
catan 2026-08-22 2026-08-25
marte 2026-08-25
azul 2026-08-23 2026-08-24
azul 2026-08-28 2026-08-30
```

Um cliente que escolher o dia 23 vê Catan, Marte e Azul ocupados, e os outros 13
disponíveis. No dia 26, todos livres, menos o Azul a partir do dia 28.
