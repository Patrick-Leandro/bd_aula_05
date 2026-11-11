# bd_aula_05

Exercício 1 (Inserção e Restrições): Escreva o comando SQL para inserir um novo fornecedor chamado 'Suprimentos Globais', com o telefone '(11) 91111-2222' e endereço 'Av. das Nações, 500 - São Paulo, SP'. Em seguida, responda: O que acontecerá se você tentar executar esse mesmo comando uma segunda vez? Por quê?

INSERT INTO Fornecedor (nome, telefone, endereco)
VALUES (
    'Suprimentos Globais',
    '(11) 91111-2222',
    'Av. das Nações, 500 - São Paulo, SP'
);

O que acontece se o comando for executado novamente?
A segunda execução gerará um erro, pois as colunas nome e telefone possuem a restrição UNIQUE.


_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 2 (Filtro por Intervalo): Escreva uma consulta que selecione todos os campos da tabela Fornecedor, mas retorne apenas os registros cujos códigos (id) estejam no intervalo de 3 a 5 (inclusive). Utilize o operador de intervalo adequado visto em aula.

SELECT *
FROM Fornecedor
WHERE id BETWEEN 3 AND 5;

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 3 (Seleção de Valores Específicos):Escreva uma consulta que apresente todas as colunas dos fornecedores que possuem os IDs 1, 2 ou 4. Não utilize o operador OR nesta solução.

SELECT *
FROM Fornecedor
WHERE id IN (1, 2, 4);

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 4 (Ordenação por Posição):Escreva uma consulta que retorne todas as colunas da tabela Fornecedor. O resultado deve ser ordenado de forma decrescente utilizando o nome do fornecedor, porém você deve obrigatoriamente fazer essa ordenação referenciando a posição numérica da coluna na tabela.

SELECT *
FROM Fornecedor
ORDER BY 2 DESC;

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 5 (Ordenação Oculta): Escreva uma consulta que exiba apenas as colunas nome e endereco de todos os fornecedores. Garanta que o resultado venha ordenado do último ID gerado para o primeiro (ordem decrescente de id), mesmo que a coluna id não apareça no resultado final do SELECT.

SELECT nome, endereco
FROM Fornecedor
ORDER BY id DESC;

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 6 (Inserção Padrão): Escreva o comando SQL para cadastrar um único fornecedor com os seguintes dados: Nome: Paraná Madeiras, Telefone: (41) 3322-1111, Endereço: Rua Chile, 1500 - Curitiba, PR.

INSERT INTO Fornecedor (nome, telefone, endereco)
VALUES (
    'Paraná Madeiras',
    '(41) 3322-1111',
    'Rua Chile, 1500 - Curitiba, PR'
);

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 7 (Inserção Múltipla): Escreva um único comando INSERT para cadastrar três fornecedores de uma só vez: Alimentos Nordeste | (81) 9988-7766 | Av. Boa Viagem, 400 - Recife, PE Metais Sudeste | (11) 2233-4455 | Rua das Indústrias, 80 - Osasco, SP Vidros do Sul | (51) 3211-0000 | Av. Farrapos, 1010 - Porto Alegre, RS

INSERT INTO Fornecedor (nome, telefone, endereco)
VALUES
(
    'Alimentos Nordeste',
    '(81) 9988-7766',
    'Av. Boa Viagem, 400 - Recife, PE'
),
(
    'Metais Sudeste',
    '(11) 2233-4455',
    'Rua das Indústrias, 80 - Osasco, SP'
),
(
    'Vidros do Sul',
    '(51) 3211-0000',
    'Av. Farrapos, 1010 - Porto Alegre, RS'
);

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 8 (Inserção Condicional/Nulos): Considerando que a coluna telefone permita valores nulos (ou seja, não é obrigatória), escreva o comando para cadastrar o fornecedor Artesanatos da Bahia, localizado na Rua do Passo, 12 - Salvador, BA, deixando o telefone sem preenchimento (NULL).

INSERT INTO Fornecedor (nome, telefone, endereco)
VALUES (
    'Artesanatos da Bahia',
    NULL,
    'Rua do Passo, 12 - Salvador, BA'
);

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 9 (Seleção Simples): Escreva uma consulta que retorne apenas o nome e o telefone de todos os fornecedores cadastrados na tabela.

SELECT nome, telefone
FROM Fornecedor;

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 10 (Filtro de Texto Exato): Escreva uma consulta que retorne todas as colunas do fornecedor cujo nome seja exatamente 'Metais Sudeste'.

SELECT *
FROM Fornecedor
WHERE nome = 'Metais Sudeste';

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 11 (Filtro de Texto Parcial - LIKE): Escreva uma consulta para listar todos os fornecedores localizados no estado de São Paulo. Para isso, filtre os registros cujo endereço termine ou contenha a sigla 'SP'.

SELECT *
FROM Fornecedor
WHERE endereco LIKE '%SP%';

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 12 (Filtro por ID): Escreva uma consulta que traga as informações completas do fornecedor que possui o código (id) igual a 3.

SELECT *
FROM Fornecedor
WHERE id = 3;

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 13 (Operadores de Comparação): Escreva uma consulta que retorne todos os fornecedores que possuem o id maior ou igual a 4.

SELECT *
FROM Fornecedor
WHERE id >= 4;

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 14 (Ordenação Ascendente): Escreva uma consulta que liste o nome e o endereço de todos os fornecedores, organizados em ordem alfabética (A-Z) pelo nome.

SELECT nome, endereco
FROM Fornecedor
ORDER BY nome ASC;

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
Exercício 15 (Filtro Composto e Ordenação): Escreva uma consulta que selecione todos os campos da tabela. O resultado deve exibir apenas os fornecedores com id entre 2 e 5 e vir ordenado do ID mais alto para o mais baixo (ordem decrescente)

SELECT *
FROM Fornecedor
WHERE id BETWEEN 2 AND 5
ORDER BY id DESC;

_______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
