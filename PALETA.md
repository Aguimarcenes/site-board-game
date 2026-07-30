# Paleta de cores — Site de aluguel de jogos de tabuleiro

Direção: verde mata + mostarda (inspirada na natureza do interior de Minas)

## Cores principais

| Papel | Nome | Hex | RGB | Onde usar |
|---|---|---|---|---|
| Primária | Verde mata | `#1F3D2B` | 31, 61, 43 | Cabeçalho, rodapé, fundo de seções, logo |
| Primária (hover) | Verde mata escuro | `#16291C` | 22, 41, 28 | Estado hover/pressed de elementos verdes |
| Destaque / CTA | Mostarda | `#D9A441` | 217, 164, 65 | Botões de ação (alugar, reservar), badges, ícones de destaque |
| Destaque (hover) | Mostarda escura | `#B8842E` | 184, 132, 46 | Estado hover/pressed dos botões de CTA |
| Fundo | Creme | `#F5EFE0` | 245, 239, 224 | Fundo geral das páginas |
| Superfície | Branco | `#FFFFFF` | 255, 255, 255 | Cards de jogos, campos de formulário, modais |

## Texto

| Papel | Nome | Hex | Onde usar |
|---|---|---|---|
| Texto principal | Verde quase preto | `#14261A` | Corpo de texto sobre fundo claro (creme ou branco) |
| Texto secundário | Verde acinzentado | `#5C6E4F` | Legendas, textos de apoio, descrições curtas |
| Texto sobre fundo escuro | Mostarda clara | `#EAD9A0` | Títulos e textos sobre o verde mata (cabeçalho, rodapé) |
| Texto sobre botão CTA | Marrom escuro | `#3C2A0A` | Texto dentro dos botões mostarda (garante contraste) |

## Notas de uso para o dev

- **Mostarda é para destaque, não para áreas grandes.** Usar em botões, badges e ícones de ação. Evitar como cor de fundo de seções inteiras, senão perde o efeito de contraste.
- **Verde mata é a cor de identidade.** Pode ir em cabeçalho, rodapé, fundo de seções e no logo.
- **Sempre usar o texto marrom escuro (`#3C2A0A`) dentro dos botões mostarda**, nunca branco ou verde: o contraste fica baixo.
- **Contraste texto/fundo:** o texto principal (`#14261A`) sobre creme (`#F5EFE0`) e a mostarda clara (`#EAD9A0`) sobre o verde mata (`#1F3D2B`) atendem contraste alto (acessibilidade AA).

## Código para implementação (CSS variables)

```css
:root {
  --color-primary: #1F3D2B;
  --color-primary-hover: #16291C;
  --color-accent: #D9A441;
  --color-accent-hover: #B8842E;
  --color-bg: #F5EFE0;
  --color-surface: #FFFFFF;
  --color-text: #14261A;
  --color-text-muted: #5C6E4F;
  --color-text-on-primary: #EAD9A0;
  --color-text-on-accent: #3C2A0A;
}
```
