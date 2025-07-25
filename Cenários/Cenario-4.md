# Casos de testes para o Cenário 4:

## Estratégia de Teste:
    3 categorias

    - Testes Positivos (valores válidos)
    - Testes Negavivos (valores inválidos ou ausênsia de valor em campos obrigatórios)
    - Testes de Inteface/Usabilidade

## Campo Nome:

**Positivos:**

    - Inserir nome com acentos e caracteres comuns, exemplo "Jo**ã**o Paulo". 
        Resultado esperado: O Sistema deve aceitar o nome normalmente.

    - Inserir nome com espaço na frente ou atrás, exemplo " Ana Maria ".
        Resultado esperado: O Sistema deve identificar esses espaços, removê-los e aceitar o nome normalmente.

**Negativos**

    - Deixar o campo em branco.
        Resultado esperado: O Sistema deve notificar que o campo é obrigatório.

    - Inserir números ou simbolos especiais, exemplo José86 ou #Maria.
        Resultado esperado: O Sistema deve notificar o usuário que números e caracteres especiais não são válidos no campo Nome.
    
## Campo E-mail:

**Positivos:**

    - E-mail com formato válido, exemplo joao@nomeEmpresa.com
        Resultado esperado: O Sistema deve aceitar o e-mail normalmente.

    - E-mail com domínio com extensão maior, exemplo joao@nomeEmpresa.tech
        Resultado esperado: O Sistema deve aceitar o e-mail normalmente.
    
**Negativos**

    - Campo vazio.
        Resultado esperado: O Sistema deve notificar que o campo é obrigatório.
    
    - E-mail sem "@" ou sem domínio ou com dois "@" ou até mesmo com apenas o "@" e o dominío.
        Resultado esperado: O Sistema deve notificar ao usuário que o formato do e-mail está inválido.
    
    - Verificação de duplicidade (Para esse teste, seria necessário avaliar a regra de negócio, se o sistema permite apenas um e-mail por usuário ou não, comento isso pois já trabalhei com sistema em que diferentes usuários utilizavam o mesmo e-mail empresarial)
        Resultado esperado: O Sistema deve notificar ao usuário que o e-mail já foi cadastrado.

## Campo Número de telefone:

**Positivos:**

    - Telefone com DDD, exemplo (48) 999999999.
        Resultado esperado: O Sistema deve aceitar o telefone normalmente.

    - Telefone sem máscara, exemplo 48999999999.
        Resultado esperado: O Sistema deve formatar o telefone para utilizar a máscara correta, (48) 99999-9999, e aceitar o telefone normalmente.

**Negativos:**

    - Campo vazio.
        Resultado esperado: O Sistema deve notificar que o campo é obrigatório.

    - Número com menos ou mais dígitos.
        Resultado esperado: O Sistema deve notificar ao usuário que o formato do telefone deve ter X digitos.
    
    - Telefone sem DDD, exemplo 999999999.
        Resultado esperado: O Sistema deve notificar ao usuário que o formato do telefone deve conter o DDD.

    - Letras ou caracteres especiais.
        Resultado esperado: O Sistema deve notificar ao usuário que apenas digitos numéricos são aceitos.

## Campo Data de Nascimento:

**Positivos:**

    - Data no formato dd/mm/aaaa
        Resultado esperado: O Sistema deve aceitar a data normalmente.

    - Data sem as barras (/), exemplo: ddmmaaaa
        Resultado esperado: O Sistema deve formatar a data, dd/mm/aaaa, e aceitar a data normalmente.

**Negativos:**

    - Campo em branco.
        Resultado esperado: O Sistema deve notificar ao usuário que o campo é obrigatório.

    - Datas futuras (ex: 30/12/2030).
        Resultado esperado: O Sistema deve notificar ao usuário que datas futuras não são permitidas.

    - Datas inválidas (ex: 31/02/2022).
        Resultado esperado: O Sistema deve notificar ao usuário que a data não é valida.

    - Data com letras ou outros formatos (ex: “2022-31-12”)
        Resultado esperado: O Sistema deve notificar ao usuário que a data não é valida.

## Campo Endereço:

**Positivos:**

    - Endereço completo, rua, bairro, cidade e CEP válido.
        Resultado esperado: O Sistema deve aceitar normalmente.

    - Inserção com máscara exemplo 00000-000.
        Resultado esperado: O Sistema deve aceitar normalmente.

**Negativos:**

    - Campo CEP inválido (menos de 8 dígitos, letras) ou CEP inexistente.
        Resultado esperado: O Sistema notificar ao usuário que o CEP está inválido.

    - CEP, Rua, Cidade ou Estado em branco.
        Resultado esperado: O Sistema notificar ao usuário que o campo deve ser preenchido.

    - UF inválido (ex: “XX”)
        Resultado esperado: O Sistema notificar ao usuário que a UF é inválida.

## Automatização: 
    Considerando o teste de cadastro e/ou edição, acho valido automatizar esse processo com **Cypress** ou **Selenium**,
    caso futuramente os campos voltem a sofrer alterações seria mais simples rodar um teste de regressão para garantir que as regras de negócio ainda funcionem.

## Testes de Inteface/Usabilidade

    - Testar acessibilidade (tab navega entre campos? Labels são lidos corretamente?).

    - Responsividade em diferentes tamanhos de tela.

## Ferramentas que podem ser usadas

    - Postman ou Hoppscotch para testes de cadastro ou edição via API.

    - Ferramenta de automação Cypress ou Selenium para testes automatizados da interface.

    - Bug tracking (Jira/Trello) para registro dos defeitos encontrados.

