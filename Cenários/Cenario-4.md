Campos:
    - Nome completo
    - E-mail
    - Número de telefone
    - Data de nascimento
    - Endereço (com campos para rua, cidade, estado e CEP)

Estratégia de Teste:
    3 categorias

    - Testes Positivos (valores válidos)
    - Testes Negavivos (valores inválidos ou ausênsia de valor em campos obrigatórios)
    - Testes de Inteface/Usabilidade

Campo Nome:
**Positivos:**
    - Inserir nome com acentos e caracteres comuns, exemplo "Jo**ã**o Paulo". 
        Resultado esperado: O Sistema deve aceitar o nome normalmente.

    - Inserir nome com espaço na frente ou atrás, exemplo " Ana Maria ".
        Resultado esperado: O Sistema deve identificar esses espaços, removê-los e aceitar o nome.

**Negativos**
    - Deixar o campo em branco.
        Resultado esperado: O Sistema deve notificar que o campo é obrigatório.

    - Inserir números ou caracteres especiais, exemplo José86 ou #Maria.
        Resultado esperado: O Sistema deve notificar o usuário que números e caracteres especiais não são válidos no campo Nome.
    
Campo E-mail:
**Positivos:**
    - E-mail com formato válido, exemplo joao@email.com
        Resultado esperado: O Sistema deve aceitar o e-mail normalmente.

    - E-mail com domínio com extensão maior, exemplo joao@nomeEmpresa.tech
        Resultado esperado: O Sistema deve aceitar o e-mail normalmente.
    
**Negativos**
    - Campo vazio.
        Resultado esperado: O Sistema deve notificar que o campo é obrigatório.
    
    - E-mail sem "@" ou domínio ou com dois "@" ou até mesmo com apenas o "@" e o dominío.
        Resultado esperado: O Sistema deve notificar ao usuário que o formato do e-mail está inválido.
    
    - Verificação de duplicidade (Para esse teste, seria necessário avaliar a regra de negócio, se o sistema permite apenas um e-mail por usuário ou não, comento isso pois já trabalhei com sistema em que diferentes usuários utilizavam o mesmo e-mail empresarial)
        Resultado esperado: O Sistema deve notificar ao usuário que o e-mail já foi cadastrado.

Campo Número de telefone:
**Positivos:**
    - Telefone com DDD, exemplo (48) 999999999.
        Resultado esperado: O Sistema deve aceitar o telefone normalmente.

    - Telefone sem máscara, exemplo 48999999999.
        Resultado esperado: O Sistema deve formatar o telefone para utilizar a máscara correta, (48) 99999-9999, e aceitar o telefone normalmente.

**Negativos:**
    - Número com menos ou mais dígitos.
        Resultado esperado: O Sistema deve notificar ao usuário que o formato do telefone deve ter X digitos.
    
    - Telefone sem DDD, exemplo 999999999.
        Resultado esperado: O Sistema deve notificar ao usuário que o formato do telefone deve conter o DDD.

    - Letras ou caracteres especiais.
        Resultado esperado: O Sistema deve notificar ao usuário que apenas digitos numéricos são aceitos.

Campo Data de Nascimento:
**Positivos:**
    - Data no formato dd/mm/aaaa
        Resultado esperado: O Sistema deve aceitar a data normalmente.

    - Data sem as barras (/), exemplo: ddmmaaaa
        Resultado esperado: O Sistema deve formatar a data, dd/mm/aaaa, e aceitar a data normalmente.

**Negativos:**
    - Campo em branco.
        Resultado esperado: O Sistema deve notificar que o campo é obrigatório.

    - Datas futuras (ex: 30/12/2030).
        Resultado esperado: O Sistema deve notificar que não aceita datas futuras

    - Datas inválidas (ex: 31/02/2022).
        Resultado esperado: O Sistema deve notificar que a data não é valida e tornar o campo vazio para que o usuário o preencha novamente.

    - Data com letras ou outros formatos (ex: “2022-31-12”)
        Resultado esperado: O Sistema deve notificar que a data não é valida e tornar o campo vazio para que o usuário o preencha novamente.

Campo Endereço:

**Positivos:**
    - Endereço completo com CEP válido.
        Resultado esperado: O Sistema deve preencher os outros campos, rua, cidade e estado, automáticamente.

    - Inserção com máscara exemplo 00000-000.
        Resultado esperado: O Sistema deve preencher os outros campos, rua, cidade e estado, automáticamente.

**Negativos:**
    - Campo CEP inválido (menos de 8 dígitos, letras)

    - Cidade ou estado em branco

    - UF inválido (ex: “XX”)

    - CEP inexistente (usar API externa, se o sistema preencher automático)
