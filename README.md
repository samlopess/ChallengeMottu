Desafio Mottu – Documentação

1	– Estrutura

1.1	– Pastas

Foi construída uma api em .NET 8, utilizando Entity Framework e banco de dados relacional PostgreSQL. A estrutura do projeto está separada em pastas.

- Controllers
- Business
- Models
- Data
- Dao
- Migration

1.2 – Controllers, Business e DAO.

Os endpoints estão localizados nas controllers, essas controllers chamam as classes de negócio(business) que por sua vez chamam as classes dao que fazem operações no banco de dados utilizando o Entity Framework. Na classe de negócio estão localizadas as regras de negócio, então todas as validações e operações necessárias que precisam ser feitas antes do cadastro, busca, atualização e delete estão nessas classes.
 Essas classes estão separadas com regions que são respectivamente Get, Create, Update, Delete e Private Methods.

1.2	-  Models
A pasta models possuem todos as classes modelos que são as representações das entidades do banco de dados.

1.3	– Data e Migration

	A pasta Data possui o DbContext da aplicação, lá está a connectionString e os DbSets. Já a pasta Migrations possuem todas as migrações realizadas com EntityFramework, inclusive a criação do banco de dados.

1.4	– Appsettings
Contém no Appsettings o caminho do storage onde serão salvas as fotos de CNH dos motoboys.

2 – NuGetPackages
Existem alguns pacotes instalados:

- Microsoft.EntityFrameworkCore
- Microsoft.EntityFrameworkCore.Design
- Microsoft.EntityFrameworkCore.Tools
- Npgsql.EntityFrameworkCore.PostgreSQL

Todos esses pacotes são para auxiliar a manipulação e design do banco de dados.

3 - Entidades
As entidades são:

- DeliveryMans
- Motorcycles
- Orders
- Rentals
- UserAdmins

Order tem um relacionamento com DeliveryMan e recebe o seu respectivo Id.
Rental tem um relacionamento com Motorcycle e DeliveryMan e recebe seus respectivos Ids.
