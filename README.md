# Rastreador de Compras — Cripto

Ferramenta simples para acompanhar o resultado de cada compra de criptomoeda, individualmente e no total da carteira.

🔗 **Acesse:** https://pedroferreira5.github.io/rastreador-cripto/

## O que faz

- Cadastro de compras por moeda: você informa quanto gastou em USDT e o preço da moeda no momento da compra — a quantidade é calculada automaticamente.
- Resultado por compra: mostra o valor investido, o valor atual e o lucro/prejuízo (em USDT e %) de cada compra separadamente, além do total consolidado por moeda e da carteira inteira.
- Câmbio do dólar: guarda a cotação USD/BRL no momento de cada compra, permitindo ver os valores tanto em USDT quanto em reais.
- Preço atual: pode ser preenchido manualmente ou buscado automaticamente na Binance (par contra USDT), por moeda ou em todas de uma vez com o botão "atualizar todos os preços". A busca também roda sozinha ao abrir a página.
- Busca e ordenação: campo para filtrar por moeda, e opção de ordenar a lista em ordem alfabética ou pela que tem mais USDT investido.
- Importação em massa: dá para colar várias compras de uma vez, direto de uma planilha (Excel/Google Sheets).

## Modelo de tabela para importação em massa

No campo "Importar várias compras (tabela)", monte uma planilha com estas colunas, nessa ordem:

| Moeda | Usdt | Preco | Cambio | Data |
|-------|------|-------|--------|------|
| BTC | 500 | 350000 | 5.30 | 2026-03-10 |
| ETH | 300 | 18500 | | 2026-05-02 |
| PEPE | 100 | 0.0000098 | | |

- **Moeda**: o ticker da moeda (BTC, ETH, PEPE...).
- **Usdt**: quanto foi gasto em USDT naquela compra.
- **Preco**: o preço da moeda em USDT no momento da compra.
- **Cambio**: cotação do dólar (USD/BRL) na época da compra — opcional.
- **Data**: data da compra, no formato AAAA-MM-DD — opcional.

Selecione as células da planilha (incluindo o cabeçalho, se quiser — ele é reconhecido e ignorado automaticamente), copie (Ctrl+C) e cole direto na caixa de texto do site. A quantidade de cada compra é calculada sozinha (USDT gasto ÷ preço).

## Armazenamento

Os dados ficam salvos apenas no navegador de quem acessa a página (`localStorage`), presos a este domínio. Não há backend, banco de dados ou coleta de informação — nada sai do seu navegador.

Isso significa:
- Os dados não sincronizam entre dispositivos ou navegadores diferentes.
- Limpar os dados de navegação do navegador apaga o histórico cadastrado.
- Sempre acesse pelo mesmo link para manter o que já foi cadastrado.

## Tecnologia

HTML, CSS e JavaScript puros, em um único arquivo (`index.html`), sem dependências além de fontes do Google Fonts e da API pública da Binance para busca de preço.

## Rodando localmente

Basta abrir o `index.html` em qualquer navegador. Não precisa de servidor, build ou instalação.
