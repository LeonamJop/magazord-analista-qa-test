# Casos de testes para o Cenário 1:

## Documentação e Materiais de Apoio.

### Identificação da documentação:

- Especificações técnicas da API de integração dos marketplaces (Amazon/Mercado Livre).

- Requisitos do projeto fornecidos pelo time de produto.

- Swagger da API desenvolvida internamente.

- Documentação dos fluxos de negócio do e-commerce (estoque, pedidos, etc.).

### Análise da documentação:

- Leitura ativa e revisão em conjunto com o time de desenvolvimento e PO para esclarecer pontos ambíguos.

- Identificação de endpoints, parâmetros obrigatórios, códigos de retorno, autenticação e fluxos de integração.

- Comparação entre a documentação dos marketplaces e o comportamento da integração no sistema.

### Mapeamento dos requisitos:

- Uso de técnicas como “Matriz de Rastreabilidade” para mapear a relação entre requisitos, funcionalidades, casos de testes.

- Criação de checklist com base nos requisitos funcionais e não funcionais da integração.

### Ferramentas utilizadas:

- Jira/Trello para gerenciamento de requisitos e bugs.

- Notion ou Confluence para centralização de documentação.

- Postman ou Hoppscotch para testes em APIs.

## Abrangência dos Testes.

### Funcionalidades a serem testadas:

- Sincronização de estoque entre ERP e marketplaces.

- Envio de anúncios para os marketplaces.

- Recebimento de pedidos oriundos dos marketplaces.

- Atualização de status de pedidos como pagamento, faturamento ou envio.

- Sincronização e atualização de preços.

- Tratamento de erros, exemplo: produto não encontrado, token expirado.

## Casos de uso principais:

### Cenários de sucesso:

- Estoque atualizado corretamente no marketplace.

- Pedido gerado no marketplace refletindo no ERP.

- Preço atualizado sem erro.

- Anúncio enviado com todos os campos obrigatórios preenchidos.

### Cenários de falha:

- Token de autenticação expirado.

- SKU inválido ou inexistente.

- Preço ou estoque negativo.

- Pedido com status inválido.

- Marketplace fora do ar ou com erro 500.

### Cenários de carga e desempenho:

- Enviar um lote grande de anúncios e validar tempo de processamento.

- Simular pico de pedidos recebidos em um curto intervalo de tempo.

### Priorização dos testes:

- Alta: pedidos, estoque e faturamento.

- Média: sincronização de preço e anúncios.

- Baixa: cenários de exceção raros.

## Execução dos Testes.

### Ambiente de teste:

- Ambiente de homologação.

- Mock dos sistemas externos se necessário.

- Ambiente isolado de banco de dados para manipulação segura de dados de teste.

### Dados de teste:

- Produtos com estoque positivo e negativo.

- SKUs válidos e inválidos.

- Preços promocionais, descontos, frete grátis.

- Pedidos completos, incompletos, cancelados.

- Simulação de erro no envio de dados, exemplo: campos obrigatórios ausentes.

### Ferramentas de automação:

- Cypress para automação da interface.

- Postman para testes em API.

### Registro de resultados:

- Jira ou Notion com evidência e steps para bugs.

- Printscreen e gravações para bugs críticos.