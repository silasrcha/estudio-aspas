# Estúdio Aspas Debate

Monta os cards de citação (aspas / tweet) da campanha sobre foto: cole o texto,
escolha o modelo e o formato, envie a foto e baixe o PNG.

Veio do gerador que vivia como artifact do Claude. Aqui ele é uma página
independente, adaptada à identidade dos outros estúdios.

```bash
py -3 servidor.py        # http://localhost:8794
```

## O que mudou em relação ao artifact

- **Virou documento completo.** O arquivo do artifact era um *fragmento*: sem
  `<!doctype>`, `<head>` nem `charset` — o runtime do artifact embrulhava. Servido
  direto, o navegador adivinhava a codificação e os acentos quebravam.
- **Identidade dos outros estúdios**: paleta escura, hachura diagonal, selo MR 22,
  Encode Sans na interface. O **card continua em Work Sans** — é a tipografia do
  tweet, não da ferramenta, e trocar mudaria a quebra de linha medida no Figma.
- **Download sem a API de artifact**: o `window.claude.use('downloads')` saiu; o
  caminho normal do navegador já servia de fallback.

## Autossuficiente

Não faz nenhuma chamada externa. As fontes do card e as artes vão embutidas em
base64; a Encode Sans da interface é servida de `ativos/fontes/`. Funciona sem
internet e não depende de fonte instalada.

## Medidas

Vêm do Figma "DA Mídia — MR 2026", página FAST-POSTING (modelos TWEET-*). Se o
layout mudar lá, atualize aqui. A **entreletra de −4%** no texto não é enfeite:
sem ela a quebra de linha sai diferente do Figma.
