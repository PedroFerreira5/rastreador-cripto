# Rastreador de Compras — Cripto

Eu estava com dificuldade de acompanhar meus resultados em cripto — fazia várias compras em momentos diferentes, com preços diferentes, e ficava difícil saber se estava ganhando ou perdendo em cada uma. Resolvi fazer essa ferramenta pra resolver isso.

🔗 **Acesse:** https://pedroferreira5.github.io/rastreador-cripto/

## O que faz

- **Cadastro de compras por moeda:** você informa quanto gastou em USDT e o preço da moeda no momento da compra — a quantidade é calculada automaticamente.
- **Resultado por compra:** mostra o valor investido, o valor atual e o lucro/prejuízo (em USDT e %) de cada compra separadamente, além do total consolidado por moeda e da carteira inteira.
- **Câmbio do dólar:** guarda a cotação USD/BRL no momento de cada compra, permitindo ver os valores tanto em USDT quanto em reais.
- **Preço atual:** pode ser preenchido manualmente ou buscado automaticamente na Binance (par contra USDT), por moeda ou em todas de uma vez com o botão "atualizar todos os preços". A busca também roda sozinha ao abrir a página.
- **Busca e ordenação:** campo para filtrar por moeda, e opção de ordenar a lista em ordem alfabética ou pela que tem mais USDT investido.
- **Importação em massa:** dá para colar várias compras de uma vez, direto de uma planilha (Excel/Google Sheets).

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

## Armazenamento e Uso Offline

Os dados ficam salvos apenas no seu próprio navegador (`localStorage`), gravados diretamente no seu dispositivo. Não há backend, banco de dados ou coleta de informação — nada sai do seu navegador.

- **Funciona 100% Offline:** Você pode baixar o arquivo `index.html` e deixá-lo na sua Área de Trabalho para usar como um aplicativo local. Os cadastros, cálculos, importações do Excel e backups salvam normalmente sem precisar de internet.
- **Uso de Internet:** A conexão só é necessária para buscar as cotações em tempo real via API da Binance. Caso esteja offline, você pode preencher o preço atual manualmente.
- **Privacidade Total:** Não existe nenhum servidor recebendo suas informações — tudo fica restrito ao seu navegador/dispositivo.

**Importante sobre o armazenamento local:**
- Os dados não sincronizam entre dispositivos ou navegadores diferentes.
- Limpar os dados de navegação do navegador apaga o histórico cadastrado (recomenda-se usar o botão de "baixar backup" periodicamente).

## Tecnologia e Conceitos Aplicados

- **Interface & Estilização:** HTML5 e CSS3 puro utilizando CSS Grid, Flexbox, variáveis CSS e suporte a áreas seguras em telas móveis (*viewport-fit/safe-area*).
- **Lógica e Dinamismo:** JavaScript Vanilla (ES6+) com manipulação nativa de DOM e escopo isolado via IIFE.
- **Integração com API REST:** Consumo assíncrono (`fetch` com `async/await`) da API pública da Binance para cotações em tempo real e tratamento de erros de rede.
- **Persistência e Arquivos:** Gerenciamento de estado local via `localStorage`, parsing dinâmico de strings (TSV/CSV) para importação e manipulação de arquivos `.json` para exportação/importação de backups.

## Rodando localmente

Basta salvar e abrir o `index.html` em qualquer navegador (dando um duplo clique ou arrastando o arquivo para dentro da janela do navegador). Não precisa de servidor, build ou instalação.

## ⚠️ Aviso Legal / Disclaimer

Esta ferramenta foi desenvolvida exclusivamente para fins de controle financeiro pessoal e organização do próprio usuário. 

- **Sem recomendações:** Os dados e resultados exibidos não constituem recomendação de compra, venda ou investimento em ativos digitais.
- **Precisão das cotações:** As cotações automáticas são obtidas via API pública da Binance e podem apresentar variações, atrasos ou oscilações de mercado. Sempre confirme as informações na sua corretora (exchange) antes de realizar transações.
