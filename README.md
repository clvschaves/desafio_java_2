### Desafio:
Você trabalha em um banco que tem constantes problemas para organizar as filas de atendimento dos clientes. 
Depois de uma reunião com a gerência, foi decidido que os clientes receberão uma senha numérica em seu celular via SMS ao chegar na agência e a ordem da fila será determinada pelo número recebido via SMS, em vez da ordem de chegada. 
Dessa forma, os clientes com números maiores serão atendidos primeiro. 
Sua tarefa é criar uma aplicação que possa reorganizar a fila de acordo com os números recebidos via SMS e determinar quantos clientes não precisarão mudar de posição na reordenação.

### Requisitos:
Para atender ao desafio, você deve desenvolver uma aplicação que permita cadastrar usuários e enviar SMS com sua posição na fila, levando em consideração as regras estabelecidas. 
A aplicação deve ter uma lista de usuários agendados para validação de sua posição na fila. Além disso, é necessário que a descrição do desenvolvimento inclua uma lista de usuários já cadastrados e que sejam criados casos de teste automatizados que possam verificar a mudança na fila de acordo com o número recebido via SMS.

### Instruções:

### Hibernate
1. Crie uma classe Pessoa com os atributos nome, idade e posição na fila. Mapeie essa classe utilizando o Hibernate para uma tabela chamada "pessoas" em um banco de dados MySQL.
    1.1 Escreva uma classe DAO que implemente as operações básicas de CRUD (Create, Read, Update, Delete) para a classe Pessoa utilizando o Hibernate.
Obs.: Lembre-se que o nosso objetivo é será organizar a fila, logo, importante analisar se será necessário criar um outra tabela de nome "organizacaoFila"

### Spring
2. Utilize o Spring para injetar o DAO da classe Pessoa em um controlador REST. O controlador deve implementar as seguintes operações:

GET /pessoas: retorna todas as pessoas cadastradas.
POST /pessoas: adiciona uma nova pessoa.
GET /pessoas/{id}: retorna uma pessoa com o ID especificado.
PUT /pessoas/{id}: atualiza uma pessoa com o ID especificado.
DELETE /pessoas/{id}: deleta uma pessoa com o ID especificado.

Caso tenha implementado a tabela "organizacaoFila" crie o controlador REST para ela.

3. A aplicação deve enviar um sms para a pessoa cadastrada no momento em que a mesma for inserida no banco. Caso você não conheça uma API gratuita para enviar SMS, utilize a plataforma que disponibiliza 5 dólares para teste (https://portal.telesign.com/login). 

### Docker

4. Crie um Dockerfile para empacotar a aplicação Spring em um contêiner Docker.
 4.1 Utilize o docker-compose para criar um ambiente de desenvolvimento local que inclua um contêiner para a aplicação Spring e outro para um banco de dados MySQL.

### GitHub e README
5. Faça um fork do projeto de exemplo https://github.com/spring-guides/gs-rest-service e adapte-o para incluir o Hibernate e o docker-compose.
    5.1 Escreva um README bem detalhado para a aplicação, explicando como instalar e executar a aplicação com o Docker.

6. Adicione um caso de teste para a operação POST /pessoas. O teste deve criar uma nova pessoa utilizando a API REST e verificar se a pessoa foi adicionada corretamente no banco de dados. Além de verificar a sua posição na fila e se será necessário mudá-la de posição


OBS.: Certifique-se de que todas as solicitações estão incluídas no seu repositório público do GitHub e envie o link para cloves.chaves@recife.pe.gov.br.

### Dica

Entrada: 
Para os casos de teste refentes a posiçãpo na fila, cada caso de teste deve começar com um número inteiro M (1 ≤ M ≤ 1000), que representa o número de clientes na fila. 
Em seguida, haverá M números inteiros distintos para cada i (1 ≤ i ≤ 1000), onde o i-ésimo número inteiro indica o número recebido via SMS do i-ésimo cliente. 
Os números inteiros são fornecidos na ordem de chegada, ou seja, o primeiro número inteiro refere-se ao primeiro cliente a chegar na fila, o segundo número inteiro refere-se ao segundo cliente e assim por diante. 

Saida:
Para cada caso de teste, a API deverá  retornar uma linha contendo um número inteiro que indica quantos clientes não precisaram mudar de posição na fila após a reordenação com base no número recebido via SMS e 
liste todos os clientes e sua posição na fila. Como são duas saída diferentes, no seu REST pode haver rotas para listar ambos os comportamentos.




