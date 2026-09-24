## Rastreador de Compras — Cripto

Ferramenta simples para acompanhar o resultado de cada compra de criptomoeda, individualmente e no total da carteira.

🔗 Acesse: https://pedroferreira5.github.io/rastreador-cripto/

O que faz
Cadastro de compras por moeda: você informa quanto gastou em USDT e o preço da moeda no momento da compra — a quantidade é calculada automaticamente.
Resultado por compra: mostra o valor investido, o valor atual e o lucro/prejuízo (em USDT e %) de cada compra separadamente, além do total consolidado por moeda e da carteira inteira.
Câmbio do dólar: guarda a cotação USD/BRL no momento de cada compra, permitindo ver os valores tanto em USDT quanto em reais.
Preço atual: pode ser preenchido manualmente ou buscado automaticamente na Binance (par contra USDT), pelo botão "buscar preço" em cada moeda.
Armazenamento

Os dados ficam salvos apenas no navegador de quem acessa a página (localStorage), presos a este domínio. Não há backend, banco de dados ou coleta de informação — nada sai do seu navegador.

Isso significa:

Os dados não sincronizam entre dispositivos ou navegadores diferentes.
Limpar os dados de navegação do navegador apaga o histórico cadastrado.
Sempre acesse pelo mesmo link para manter o que já foi cadastrado.
Tecnologia

HTML, CSS e JavaScript puros, em um único arquivo (index.html), sem dependências além de fontes do Google Fonts e da API pública da Binance para busca de preço.

Rodando localmente

Basta abrir o index.html em qualquer navegador. Não precisa de servidor, build ou instalação.
