# Casos de testes para o Cenário 3:

## Revisão da documentação e Comprenssão do fluxo:

- Junto com o time de desenvolvimento, avaliar os pontos importantes da documentação que está relacionado a pausa de anúcios.

- Compreenssão do processo de atualização de estoque para o MercadoLivre.
    Segundo a documentação do Mercado Livre, para o anúncio pode ser pausado de duas formar via API sendo elas um PUT com o campo "available_quantity": 0 e outra seria um PUT com o campo "status":"paused".

- Validar se a Magazord está enviando o campo correto para atualização de estoque igual a zero ou apenas alternado o status do anúncio para "paused".
    Esse teste vai servir para confirmar se de fato é algum problema de envio da informação, já que o cliente afirma que a atualização manual funciona de forma correta.