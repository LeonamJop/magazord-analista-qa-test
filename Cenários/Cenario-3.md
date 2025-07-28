# Casos de testes para o Cenário 3:

## Revisão da documentação e compreensão do fluxo:

- Reunir com o time de desenvolvimento para revisar a documentação da integração, focando no processo de pausa de anúncios.

- Compreender o processo atual de atualização de estoque entre Magazord e Mercado Livre.

## Entendimento das formas de pausar anúncios via API (segundo a documentação do Mercado Livre):

- A pausa de anúncios pode ocorrer de duas formas via API:

    - Alterando a quantidade disponível para zero: PUT { "available_quantity": 0 }.

    - Alterando o status do anúncio: PUT { "status": "paused" }.

## Validação do comportamento do sistema:

- Verificar se a plataforma Magazord está realmente enviando o campo available_quantity: 0 ao zerar o estoque, ou se está apenas alterando o campo status para "paused", o que pode causar comportamento inesperado no Mercado Livre.

- Testar o envio manual com um item de teste para confirmar se o endpoint da API está sendo corretamente chamado com available_quantity: 0 quando o estoque acaba.

## Análise de regras de negócio:

- Verificar se existe alguma regra de negócio implementada que impede o envio de estoque zerado automaticamente, como medida preventiva contra pausas acidentais.

## Avaliação dos logs e resposta da API:

- Analisar os logs da integração para verificar:

    - Se a requisição foi realmente enviada para o ML.

    - Se houve erros como 400 (Bad Request) ou 401 (Unauthorized), que podem indicar falhas de autenticação ou payload inválido.

    - Se o sistema está tratando e registrando essas falhas de forma adequada.

## Possíveis Causas do problema:

- Falha na regra de envio de estoque 0.
    > ERP não envia "available_quantity: 0" automaticamente ao detectar estoque zerado.

- API do ML não está recebendo a requisição corretamente.
    > Pode estar ocorrendo erro 400/401 e o sistema não está tratando/logando adequadamente.

- Travamento de algum job de sincronização.
    > Algum processo agendado pode estar parando antes de enviar atualizações.

- Configuração de anúncios.
    > O cliente pode não ter configurado seus anúncios da melhor maneira.