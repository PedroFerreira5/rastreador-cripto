# Rastreador de Compras — Cripto

Eu estava com dificuldade de acompanhar meus resultados em cripto — fazia várias compras em momentos diferentes, com preços diferentes, e ficava difícil saber se estava ganhando ou perdendo em cada uma. Resolvi criar essa ferramenta para resolver isso, permitindo controlar tanto os ativos em carteira quanto os lucros/prejuízos já realizados de vendas efetuadas.

🔗 **Acesse:** [https://pedroferreira5.github.io/rastreador-cripto/](https://pedroferreira5.github.io/rastreador-cripto/)

---

##   O que faz

###   Gestão de Compras & Carteira
- **Cadastro individual de compras:** você informa o gasto em USDT, o preço pago e, opcionalmente, taxas e cotação do dólar (USD/BRL). A quantidade adquirida é calculada automaticamente.
- **Cálculo de Preço Médio (PM):** calcula automaticamente o preço médio ponderado por moeda, incorporando as taxas pagas no custo base do ativo.
- **Break-even:** exibe o valor unitário exato de venda necessário para empatar o investimento (já considerando taxas).
- **Simulador de Preço de Venda:** permite digitar um preço hipotético para simular o valor exato a receber, lucro/prejuízo e percentual de retorno antes de realizar a ordem.
- **Resultado detalhado por ordem:** mostra o custo, valor atual e resultado não realizado ($ e %) de cada compra individual e do consolidado da moeda.

###   Registro & Histórico de Vendas
- **Registrar vendas parciais ou totais:** abate o saldo disponível em carteira usando o Preço Médio (PM) atual para apurar o **Lucro/Prejuízo Realizado**.
- **Histórico e Filtros por Mês:** tabela dedicada ao histórico de vendas, com filtro por período e recalculo automático do resultado acumulado caso novas compras alterem o PM histórico.

###   Cotações & Câmbio Multi-Moedas
- **Alternância de Moeda (USDT / BRL):** alterne toda a visualização do painel entre dólar (USDT) e reais (R$).
- **Cotação do Dólar em tempo real:** permite definir a taxa USD/BRL atual para atualizar o valor de mercado de todas as posições em Reais.
- **Preço Atual via Binance:** busca cotações automáticas dos pares contra USDT na API pública da Binance ao abrir a página, por botão individual ou geral.

###   Organização & Importação
- **Busca e Ordenação:** campo para filtrar moedas pelo nome e opções de ordenação (alfabética ou por maior volume investido).
- **Importação em Massa:** cole múltiplas compras direto de planilhas (Excel ou Google Sheets).
- **Exportação CSV & Backup JSON:** exporte todo o seu histórico formatado para CSV ou faça backup completo dos seus dados para restauração rápida em qualquer navegador.

---

##   Modelo de tabela para importação em massa

Na aba **📥 Importar Tabela**, cole suas compras no seguinte formato (colunas separadas por TAB ou vírgula):

| Moeda | Usdt | Preco | Cambio | Data |
| :--- | :--- | :--- | :--- | :--- |
| BTC | 500 | 65000 | 5.30 | 2026-03-10 |
| ETH | 300 | 3200 | | 2026-05-02 |
| PEPE | 100 | 0.0000098 | | |

- **Moeda**: o ticker do ativo (ex: BTC, ETH, PEPE).
- **Usdt**: valor total gasto em USDT.
- **Preco**: preço unitário da moeda em USDT na data da compra.
- **Cambio**: cotação USD/BRL na data da compra *(opcional)*.
- **Data**: formato AAAA-MM-DD *(opcional)*.

*Nota: Selecione as células no Excel/Sheets (com ou sem cabeçalho) e cole diretamente na caixa de texto.*

---

##   Armazenamento, Privacidade e Uso Offline

Os dados ficam armazenados **exclusivamente no seu próprio navegador** via `localStorage`. Não existe backend, servidor central ou envio de informações financeiras.

- **Privacidade Total:** Nenhuma informação sobre a sua carteira, compras ou valores é transmitida para terceiros. A única comunicação externa realizada pela página é a consulta pública à API da Binance para obter os preços unitários das criptomoedas.
- **Uso Offline:** Você pode baixar o arquivo `index.html` e executá-lo diretamente no computador sem necessidade de internet (para atualizar os preços manualmente).
- **Portabilidade:** Utilize os botões **"baixar backup"** e **"carregar backup"** no rodapé para transferir com segurança seus dados entre navegadores ou computadores.

---

##   Tecnologias Utilizadas

- **HTML5 & CSS3:** Design responsivo com CSS Grid, Flexbox, variáveis CSS e estilização nativa para modo escuro (*Dark Theme*).
- **JavaScript Vanilla (ES6+):** Lógica desacoplada com manipulação do DOM e IIFE para proteção de escopo.
- **API REST (Binance):** Requisições assíncronas (`fetch` / `async/await`) para obtenção de preços em tempo real.
- **Manipulação de Arquivos:** Geração e leitura de payloads JSON para backup e formatação de arquivos CSV com suporte a UTF-8 BOM.

---

##   Como rodar localmente

Não é necessário configurar servidores, NodeJS ou comandos de build:

1. Faça o download do repositório ou salve o arquivo `index.html`.
2. Dê dois cliques sobre o arquivo `index.html` para abri-lo em qualquer navegador moderno.

---

## ⚠️ Aviso Legal / Disclaimer

Esta ferramenta foi desenvolvida exclusivamente para fins de organização pessoal e controle financeiro.

- **Sem recomendações:** Os valores, cálculos e projeções exibidos não constituem recomendação de investimento, compra ou venda de criptoativos.
- **Precisão das cotações:** As cotações automáticas dependem da API pública da Binance e podem apresentar oscilações ou atrasos de mercado. Confirme sempre suas operações na sua corretora (*exchange*).
