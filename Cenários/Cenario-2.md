# Casos de testes para o Cenário 2:

## Documentação e Materiais de Apoio.

### Identificação da documentação:

- Documentação oficial da API do Bling.

- Especificações técnicas da integração definidas pela equipe de desenvolvimento.

- Requisitos do projeto com escopo funcional.

- Fluxos de integração mapeados pelo time de desenvolvimento (ex: sincronização de pedidos, produtos e estoque).

### Mapeamento dos requisitos:

- Análise dos requisitos da integração, reunião de planejamento com o time de desenvolvimento para validações.

- Criação de matriz de rastreabilidade, para entender a relação entre requisitos, funcionalidades, casos de testes.

- Identificação de endpoints utilizados e parâmetros obrigatórios.

### Ferramentas utilizadas:

- Jira/Trello para gerenciamento de requisitos e bugs.

- Swagger (caso fornecido) ou leitura direta da API REST do Bling.

- Notion ou Confluence para centralização de documentação.

- Postman para testes manuais em APIs.

## Abrangência dos Testes

### Funcionalidades a serem testadas:

- Sincronização de produtos: envio e recebimento de produtos entre e-commerce e Bling.

- Atualização de estoque, atualização automática e manual de estoque como entrada, baixa e ajustes.

- Processamento de pedidos: pedidos finalizados no e-commerce devem aparecer no Bling.

- Status de pedidos: cancelamento, faturamento e envio devem ser refletidos corretamente.

- Atualização de preço, se alterado no e-commerce, deve ser sincronizado com Bling.

- Geração de NF ou boletos.

### Priorização dos testes:

- Alta prioridade:

    - Pedidos não sincronizandos corretamente.

    - Estoque divergente entre sistemas.

    - Problemas de autenticação com a API do Bling.

- Média prioridade:

    - Campos opcionais que não impactam diretamente na operação.

    - Atrasos de sincronização aceitáveis.

- Baixa prioridade:

    - Mensagens de erro menos críticas (validação de campos secundários).

    - Layout de mensagens da API.

## Execução dos Testes.

### Dados de teste:

- Produtos com diferentes configurações, com variação de cores ou tamanhos e kits.

- Pedidos com e sem desconto, com vários itens, em diferentes formas de pagamento.

- Estoque zerado, baixo e alto.

- Tokens de autenticação válidos e/ou expirados.

### Ferramentas de automação:

- Postman ou Hoppscotch para testes e validação de resposta.

- Selenium ou Cypress se houver interface para testes end-to-end.