# TRABALHO 01:  Sistema de vendas de veículos

# Introdução e Motivação

O projeto em questão visa o desenvolvimento de um inovador sistema de vendas de veículos, pautado na abrangência de um público diversificado, compreendendo desde entusiastas automotivos experientes até aqueles que estão apenas começando a explorar o universo dos automóveis. Nosso compromisso primordial consiste em criar uma solução minuciosa e criteriosa, projetada para oferecer suporte abrangente a qualquer indivíduo que almeje adquirir um veículo novo.

# Sumário

1. [COMPONENTES](#1-componentes)
2. [MINI-MUNDO](#2-mini-mundo)
3. [PERGUNTAS A SEREM RESPONDIDAS](#3-perguntas-a-serem-respondidas)
4. [-](#-)
5. [DESCRIÇÃO DOS DADOS](#5-descrição-dos-dados)
6. [MODELO LÓGICO](#6-modelo-lógico)
7. [MODELO FÍSICO](#7-modelo-físico)
8. [INSERT APLICADO NAS TABELAS DO BANCO DE DADOS](#8-insert-aplicado-nas-tabelas-do-banco-de-dados)
9. [TABELAS E PRINCIPAIS CONSULTAS](#9-tabelas-e-principais-consultas)
   - [CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas)](#91consultas-das-tabelas-com-todos-os-dados-inseridos-todas)
   - [CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)](#92consultas-das-tabelas-com-filtros-where-mínimo-4)
   - [CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)](#93consultas-que-usam-operadores-lógicos-aritméticos-e-tabelas-ou-campos-renomeados-mínimo-11)
   - [CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12)](#94consultas-que-usam-operadores-like-e-datas-mínimo-12)
   - [INSTRUÇÕES APLICANDO ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)](#95instruções-aplicando-atualização-e-exclusão-de-dados-mínimo-6)
   - [CONSULTAS COM INNER JOIN E ORDER BY (Mínimo 6)](#96consultas-com-inner-join-e-order-by-mínimo-6)
   - [CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)](#97consultas-com-group-by-e-funções-de-agrupamento-mínimo-6)
   - [CONSULTAS COM LEFT, RIGHT E FULL JOIN (Mínimo 4)](#98consultas-com-left-right-e-full-join-mínimo-4)
   - [CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)](#99consultas-com-self-join-e-view-mínimo-6)
   - [SUBCONSULTAS (Mínimo 4)](#910subconsultas-mínimo-4)
10. [RELATÓRIOS E GRÁFICOS](#10-relatórios-e-gráficos)
11. [AJUSTES DA DOCUMENTAÇÃO, CRIAÇÃO DOS SLIDES E VÍDEO PARA APRESENTAÇÃO FINAL](#11-ajustes-da-documentação-criação-dos-slides-e-vídeo-para-apresentaçao-final-)
12. [FORMATAÇÃO NO GIT](#12-formatacao-no-git)

### 1. COMPONENTES<br>
Integrantes do grupo<br>
Giovanna Scalfoni: giovanna.scalfoni@gmail.com<br>
Filipe Suhett: filipe.gmx@gmail.com<br>
Bruno Plazzi: brunoplazzi@hotmail.com<br>
Caio Daniel Meireles de Souza: caiodaniel7437@gmail.com<br>


### 2. MINI-MUNDO<br>

> Uma pessoa interessada em adquirir um novo carro decide utilizar um Sistema de Auxílio à Compra de Carros para tornar sua decisão mais informada e conveniente. Primeiramente, ela se cadastra no sistema, fornecendo suas informações pessoais, como nome, endereço e preferências de compra, especificando seu orçamento e o tipo de carro que está buscando.
Com o perfil criado, inicia a pesquisa filtrando os carros disponíveis com base em critérios como marca, modelo, tipo de carroceria, preço do veículo e se é usado ou novo, encontrando várias opções que se encaixam em suas preferências. Para uma decisão mais embasada, utiliza a função de comparação de carros do sistema, analisando detalhadamente diferentes modelos, comparando informações técnicas do carro (motor, desempenho, transmissão, tração, suspensão, freios, direção e dimensões do veículo) e preços. O usuário também pode deixar ou verificas as avaliações de outros motoristas disponíveis no sistema para ter certeza de que os locais de compra são de confiança e possuem um bom atendimento. Além disso, enquanto pesquisa, o usuário recebe notificações sobre ofertas especiais em carros semelhantes aos que está considerando, ajudando-a a se manter atualizada sobre oportunidades de economia.
Após selecionar um dos carros, decide agendar um test drive usando o sistema. Localiza concessionárias locais que oferecem o carro desejado e faz um agendamento conveniente, armazenando data e hora (para que mais de um agendamento não seja marcado no mesmo momento). Concessionárias possuem informações como o nome das mesmas, email de contado e o endereço da unidade. Além disso, clientes podem avaliar as concessionárias em uma escala de 0-5 (estrutura do local, atendimento e outros aspéctos que podem ser observados pelos clientes durante a ida ao local), gerando uma única nota total para a unidade.  
No dia do test drive, visita a concessionária e avalia pessoalmente o carro. Todo o processo que envolve testar o carro, a forma de pagamento e a compra efetiva é feito na concessionária, não tendo relação com o sistema.


### 3. PERGUNTAS A SEREM RESPONDIDAS<br>
#### 3.1 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO?

> A Empresa necessita dos seguintes relatórios:
* Relatório que mostre a quantidade de clientes, para assim saber quais épocas são mais movimentadas e se é possível determinar um padrão
* Relatório que mostre os 20 carros mais acessados na semana, com a quantidade de acessos de cada
* Relatorio que mostre as concessionárias mais populares/bem avaliadas entre os usuários do sistema, com suas localizações e respectiva avaliação final
* Relatório que mostre as informações relacionadas ao perfil dos usuários do sistema. O relatório deve ter informações como: modelos de carro preferidos, marcas preferidas e orçamento médio
* Relatório que obtenha quantos clientes usuários fizeram o agendamento para um test drive com o auxílio do sistema. Deve mostrar a compatibilidade do carro escolhido com as preferências anteriormente especificadas no perfil do cliente, assim como comparar o orçamento com o preço do carro

    
### 5. MODELO CONCEITUAL<br>
    
    Principais entidades do sistema: Pessoa, Carro e Info_tecnicas. São as principais entidades envolvidas na pesquisa e compra dos carros pelos clientes.
    Principais fluxos: Pessoa compra carro, carro possui informações técnicas e carro pertence a concessionária.
	
![image](https://github.com/filipesuhett/Trabalho-BD-1-Veiculos/assets/72825142/22603e77-5199-4ce5-860a-bf2169dfd2ef)





    
    
#### 5.1 Validação do Modelo Conceitual
    Sistema de empregos: Erick Kenzo, Jhonata Polito Demuner
    Sistema rodoviário: Lara Aguilar, Rodolfo Oliveira, Erick Gama, João Marcos Pimentel

Os dois grupos acima analisaram o modelo conceitual feito baseado no mini-mundo também apresentado. 
Ambos concordam que o modelo está condizente, sendo um único detalhe o atributo avaliação, na entidade concessionaria, que pode funcionar tanto como atributo quanto como uma nova entidade, estando correto em ambos os casos.


#### 5.2 Descrição dos dados 

    CARRO: Tabela que armazena informações referentes aos carros cadastrados no sistema;
    CODIGO: campo que armazena o número identificador de cada carro no sistema;
    NOME: campo que armazena o nome de cada carro;
    MARCA: campo que armazena a marca de cada carro;
    TIPO_CARROCERIA: campo que armazena o tipo de carroceria de cada carro;
    PRECO: campo que armazena o preço de cada carro;
    USADO/NOVO: campo que armazena a informação se o carro especificado é usado ou novo.
    MODELO: campo que armazena o modelo do carro especificado.

    INFO_TECNICAS: Tabela que armazena as informações técnicas para cada carro do sistema;
    RECURSOS: campo que armazena os recursos para cada carro;
    MOTOR: campo que armazena o modelo de motor de cada carro;
    DESEMPENHO: campo que armazena as cilindradas de cada carro;
    TRANSMISSAO: campo que armazena o modelo de transmissão do carro especificado;
    TRACAO: campo que armazena a informação de qual a tração do carro especificado;
    SUSPENSAO: campo que armazena o modelo de suspensao de cada carro;
    FREIOS: campo que armazena a informação sobre o tipo de freios para cada carro;
    DIRECAO: campo que armazena a informação sobre o tipo de direção para cada carro;
    DIMENSOES: campo que armazena as dimensões do carro especificado.

    CONCESSIONARIA: Tabela que armazena informações relativas as Concessionárias;
    CODIGO: campo que armazena o codigo identificador de cada concessionária;
    NOME: campo que armazena o nome de cada concessionária;
    ENDEREÇO: campo que armazena o endereço da loja fisica da concessionária;
    TELEFONE: campo que armazena o telefone da loja fisica da concessionária;
    AVALIACAO: campo que armazena a avaliação da concessionária gerada a partir de todas as avaliações feitas pelos clientes.

    PESSOA: Tabela que armazena informações relativas a pessoa interessada em adquirir um carro;
    CODIGO: campo que armazena o codigo identificador de cada pessoa cadastrada no sistema;
    NOME: campo que armazena o nome da pessoa cadastrada;
    ENDERECO: campo que armazena o endereço da pessoa cadastrada;
    PREFERENCIA: campo que armazena a preferência de cada pessoa;
    ORCAMENTO: campo que armazena quanto a pessoa cadastrada tem para comprar o carro;
    TIPO_CARRO: campo que armazena a infromação de qual tipo de carro a pessoa está buscando.

    AGENDAMENTO: Tabela que armazena informações sobre os agendamentos de visitas das pessoas às concessionárias;
    CODIGO: campo que armazena o codigo identificador de cada agendamento realizado;
    DATA: campo que  armazena a data que foi agendada para a visita;
    HORA: campo que armazena o horário para qual a agendada a visita.


># Marco de Entrega 01: Do item 1 até o item 5.2 (5 PTS) <br> 

### 6. MODELO LÓGICO<br>

![image](https://github.com/filipesuhett/Trabalho-BD-1-Veiculos/assets/72825142/c3d2f681-8e32-49bf-a489-361ba8e0e094)


        a) inclusão do esquema lógico do banco de dados
        b) verificação de correspondencia com o modelo conceitual 
        (não serão aceitos modelos que não estejam em conformidade)

### 7. MODELO FÍSICO<br>
	CREATE TABLE MODELO (
	    id INTEGER PRIMARY KEY,
	    nome VARCHAR,
	    sigla VARCHAR,
	    numero_motor VARCHAR,
	    ano INTEGER
	);
	
	CREATE TABLE MARCA (
	    id INTEGER PRIMARY KEY,
	    nome VARCHAR
	);
	
	CREATE TABLE USUARIO (
	    id INTEGER PRIMARY KEY,
	    nome VARCHAR,
	    endereco VARCHAR,
	    email VARCHAR
	);
	
	CREATE TABLE CONCESSIONARIA (
	    FK_USUARIO_id INTEGER PRIMARY KEY,
	    FOREIGN KEY (FK_USUARIO_id) REFERENCES USUARIO(id)
	);
	
	CREATE TABLE PESSOA (
	    orcamento FLOAT,
	    preferencia VARCHAR,
	    tipo_carro VARCHAR,
	    FK_USUARIO_id INTEGER PRIMARY KEY,
	    FOREIGN KEY (FK_USUARIO_id) REFERENCES USUARIO(id)
	);
	
	CREATE TABLE AVALIACAO (
	    id INTEGER PRIMARY KEY,
	    nota FLOAT,
	    comentario VARCHAR,
	    FK_PESSOA_FK_USUARIO_id INTEGER,
	    FOREIGN KEY (FK_PESSOA_FK_USUARIO_id) REFERENCES PESSOA(FK_USUARIO_id)
	);
	
	CREATE TABLE MOTOR (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR
	);
	
	CREATE TABLE TRANSMISSAO (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR
	);
	
	CREATE TABLE TRACAO (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR
	);
	
	CREATE TABLE SUSPENSAO (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR
	);
	
	CREATE TABLE INFO_TECNICAS (
	    id INTEGER PRIMARY KEY,
	    potencia INTEGER,
	    freio_abs BOOLEAN,
	    direcao_hidraulica BOOLEAN,
	    dimensoes VARCHAR,
	    FK_MOTOR_id INTEGER,
	    FK_TRANSMISSAO_id INTEGER,
	    FK_TRACAO_id INTEGER,
	    FK_SUSPENSAO_id INTEGER,
	    FOREIGN KEY (FK_MOTOR_id) REFERENCES MOTOR(id),
	    FOREIGN KEY (FK_TRANSMISSAO_id) REFERENCES TRANSMISSAO(id),
	    FOREIGN KEY (FK_TRACAO_id) REFERENCES TRACAO(id),
	    FOREIGN KEY (FK_SUSPENSAO_id) REFERENCES SUSPENSAO(id)
	);
	
	CREATE TABLE TIPO_CARROCERIA (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR,
	    descricao VARCHAR
	);
	
	CREATE TABLE CARRO (
	    id INTEGER PRIMARY KEY,
	    preco FLOAT,
	    eh_novo BOOLEAN,
	    FK_INFO_TECNICAS_id INTEGER,
	    FK_MARCA_id INTEGER,
	    FK_MODELO_id INTEGER,
	    FK_TIPO_CARROCERIA_id INTEGER,
	    FOREIGN KEY (FK_INFO_TECNICAS_id) REFERENCES INFO_TECNICAS(id),
	    FOREIGN KEY (FK_MARCA_id) REFERENCES MARCA(id),
	    FOREIGN KEY (FK_MODELO_id) REFERENCES MODELO(id),
	    FOREIGN KEY (FK_TIPO_CARROCERIA_id) REFERENCES TIPO_CARROCERIA(id)
	);
	
	CREATE TABLE Compra (
	    FK_PESSOA_FK_USUARIO_id INTEGER,
	    FK_CARRO_id INTEGER,
	    FOREIGN KEY (FK_PESSOA_FK_USUARIO_id) REFERENCES PESSOA(FK_USUARIO_id),
	    FOREIGN KEY (FK_CARRO_id) REFERENCES CARRO(id)
	);
	
	CREATE TABLE AGENDAMENTO (
	    codigo INTEGER PRIMARY KEY,
	    data DATE,
	    hora TIME,
	    FK_PESSOA_FK_USUARIO_id INTEGER,
	    FK_CONCESSIONARIA_FK_USUARIO_id INTEGER,
	    FOREIGN KEY (FK_PESSOA_FK_USUARIO_id) REFERENCES PESSOA(FK_USUARIO_id),
	    FOREIGN KEY (FK_CONCESSIONARIA_FK_USUARIO_id) REFERENCES CONCESSIONARIA(FK_USUARIO_id)
	);

      
### 8. INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
        DROP TABLE IF EXISTS Compra CASCADE;
	DROP TABLE IF EXISTS AVALIACAO CASCADE;
	DROP TABLE IF EXISTS AGENDAMENTO CASCADE;
	DROP TABLE IF EXISTS CARRO CASCADE;
	DROP TABLE IF EXISTS INFO_TECNICAS CASCADE;
	DROP TABLE IF EXISTS PESSOA CASCADE;
	DROP TABLE IF EXISTS CONCESSIONARIA CASCADE;
	DROP TABLE IF EXISTS USUARIO CASCADE;
	DROP TABLE IF EXISTS TIPO_CARROCERIA CASCADE;
	DROP TABLE IF EXISTS MARCA CASCADE;
	DROP TABLE IF EXISTS MODELO CASCADE;
	DROP TABLE IF EXISTS SUSPENSAO CASCADE;
	DROP TABLE IF EXISTS TRACAO CASCADE;
	DROP TABLE IF EXISTS TRANSMISSAO CASCADE;
	DROP TABLE IF EXISTS MOTOR CASCADE;
	
	/* logico_sprints_v6: */
	
	CREATE TABLE MODELO (
	    id INTEGER PRIMARY KEY,
	    nome VARCHAR,
	    sigla VARCHAR,
	    numero_motor VARCHAR,
	    ano INTEGER
	);
	
	CREATE TABLE MARCA (
	    id INTEGER PRIMARY KEY,
	    nome VARCHAR
	);
	
	CREATE TABLE USUARIO (
	    id INTEGER PRIMARY KEY,
	    nome VARCHAR,
	    endereco VARCHAR,
	    email VARCHAR
	);
	
	CREATE TABLE CONCESSIONARIA (
	    FK_USUARIO_id INTEGER PRIMARY KEY,
	    FOREIGN KEY (FK_USUARIO_id) REFERENCES USUARIO(id)
	);
	
	CREATE TABLE PESSOA (
	    orcamento FLOAT,
	    preferencia VARCHAR,
	    tipo_carro VARCHAR,
	    FK_USUARIO_id INTEGER PRIMARY KEY,
	    FOREIGN KEY (FK_USUARIO_id) REFERENCES USUARIO(id)
	);
	
	CREATE TABLE AVALIACAO (
	    id INTEGER PRIMARY KEY,
	    nota FLOAT,
	    comentario VARCHAR,
	    FK_PESSOA_FK_USUARIO_id INTEGER,
	    FOREIGN KEY (FK_PESSOA_FK_USUARIO_id) REFERENCES PESSOA(FK_USUARIO_id)
	);
	
	CREATE TABLE MOTOR (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR
	);
	
	CREATE TABLE TRANSMISSAO (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR
	);
	
	CREATE TABLE TRACAO (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR
	);
	
	CREATE TABLE SUSPENSAO (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR
	);
	
	CREATE TABLE INFO_TECNICAS (
	    id INTEGER PRIMARY KEY,
	    potencia INTEGER,
	    freio_abs BOOLEAN,
	    direcao_hidraulica BOOLEAN,
	    dimensoes VARCHAR,
	    FK_MOTOR_id INTEGER,
	    FK_TRANSMISSAO_id INTEGER,
	    FK_TRACAO_id INTEGER,
	    FK_SUSPENSAO_id INTEGER,
	    FOREIGN KEY (FK_MOTOR_id) REFERENCES MOTOR(id),
	    FOREIGN KEY (FK_TRANSMISSAO_id) REFERENCES TRANSMISSAO(id),
	    FOREIGN KEY (FK_TRACAO_id) REFERENCES TRACAO(id),
	    FOREIGN KEY (FK_SUSPENSAO_id) REFERENCES SUSPENSAO(id)
	);
	
	CREATE TABLE TIPO_CARROCERIA (
	    id INTEGER PRIMARY KEY,
	    tipo VARCHAR,
	    descricao VARCHAR
	);
	
	CREATE TABLE CARRO (
	    id INTEGER PRIMARY KEY,
	    preco FLOAT,
	    eh_novo BOOLEAN,
	    FK_INFO_TECNICAS_id INTEGER,
	    FK_MARCA_id INTEGER,
	    FK_MODELO_id INTEGER,
	    FK_TIPO_CARROCERIA_id INTEGER,
	    FOREIGN KEY (FK_INFO_TECNICAS_id) REFERENCES INFO_TECNICAS(id),
	    FOREIGN KEY (FK_MARCA_id) REFERENCES MARCA(id),
	    FOREIGN KEY (FK_MODELO_id) REFERENCES MODELO(id),
	    FOREIGN KEY (FK_TIPO_CARROCERIA_id) REFERENCES TIPO_CARROCERIA(id)
	);
	
	CREATE TABLE Compra (
	    FK_PESSOA_FK_USUARIO_id INTEGER,
	    FK_CARRO_id INTEGER,
	    FOREIGN KEY (FK_PESSOA_FK_USUARIO_id) REFERENCES PESSOA(FK_USUARIO_id),
	    FOREIGN KEY (FK_CARRO_id) REFERENCES CARRO(id)
	);
	
	CREATE TABLE AGENDAMENTO (
	    codigo INTEGER PRIMARY KEY,
	    data DATE,
	    hora TIME,
	    FK_PESSOA_FK_USUARIO_id INTEGER,
	    FK_CONCESSIONARIA_FK_USUARIO_id INTEGER,
	    FOREIGN KEY (FK_PESSOA_FK_USUARIO_id) REFERENCES PESSOA(FK_USUARIO_id),
	    FOREIGN KEY (FK_CONCESSIONARIA_FK_USUARIO_id) REFERENCES CONCESSIONARIA(FK_USUARIO_id)
	);
	
	-- MODELO
	INSERT INTO MODELO (id, nome, sigla, numero_motor, ano) VALUES 
	(1, 'Sedan X1', 'SX1', true, 2022),
	(2, 'SUV Y2', 'SY2', false, 2023),
	(3, 'Hatchback Z3', 'HZ3', true, 2022),
	(4, 'Crossover A4', 'CA4', false, 2023),
	(5, 'Sedan B5', 'SB5', true, 2023),
	(6, 'Hatchback C6', 'HC6', true, 2022),
	(7, 'SUV D7', 'SD7', false, 2023),
	(8, 'Crossover E8', 'CE8', false, 2022),
	(9, 'Hatchback F9', 'HF9', true, 2023),
	(10, 'Sedan G10', 'SG10', true, 2022);
	
	-- MARCA
	INSERT INTO MARCA (id, nome) VALUES 
	(1, 'MarcaX'),
	(2, 'MarcaY'),
	(3, 'MarcaZ'),
	(4, 'MarcaA'),
	(5, 'MarcaB'),
	(6, 'MarcaC'),
	(7, 'MarcaD'),
	(8, 'MarcaE'),
	(9, 'MarcaF'),
	(10, 'MarcaG');
	
	-- USUARIO
	INSERT INTO USUARIO (id, nome, endereco, email) VALUES 
	(1, 'João Silva', 'Rua A, 123', 'joao.silva@example.com'),
	(2, 'Maria Santos', 'Av. B, 456', 'maria.santos@example.com'),
	(3, 'José Oliveira', 'Rua C, 789', 'jose.oliveira@example.com'),
	(4, 'Ana Souza', 'Av. D, 012', 'ana.souza@example.com'),
	(5, 'Pedro Pereira', 'Rua E, 345', 'pedro.pereira@example.com'),
	(6, 'Sofia Lima', 'Av. F, 678', 'sofia.lima@example.com'),
	(7, 'Carlos Santos', 'Rua G, 901', 'carlos.santos@example.com'),
	(8, 'Luiza Silva', 'Av. H, 234', 'luiza.silva@example.com'),
	(9, 'Marcos Oliveira', 'Rua I, 567', 'marcos.oliveira@example.com'),
	(10, 'Laura Souza', 'Av. J, 890', 'laura.souza@example.com');
	
	-- CONCESSIONARIA
	INSERT INTO CONCESSIONARIA (FK_USUARIO_id) VALUES 
	(1),
	(2),
	(3),
	(4),
	(5),
	(6),
	(7),
	(8),
	(9),
	(10);
	
	-- PESSOA
	INSERT INTO PESSOA (orcamento, preferencia, tipo_carro, FK_USUARIO_id) VALUES 
	(30000.00, 'SUV', 'Novo', 1),
	(25000.00, 'Sedan', 'Usado', 2),
	(35000.00, 'Hatchback', 'Novo', 3),
	(20000.00, 'Crossover', 'Usado', 4),
	(28000.00, 'SUV', 'Novo', 5),
	(32000.00, 'Hatchback', 'Novo', 6),
	(26000.00, 'Sedan', 'Usado', 7),
	(30000.00, 'Crossover', 'Novo', 8),
	(27000.00, 'Hatchback', 'Novo', 9),
	(29000.00, 'Sedan', 'Novo', 10);
	
	-- AVALIACAO
	INSERT INTO AVALIACAO (id, nota, comentario, FK_PESSOA_FK_USUARIO_id) VALUES 
	(1, 4.5, 'Ótima experiência!', 1),
	(2, 3.2, 'Poderia ser melhor.', 2),
	(3, 4.0, 'Muito satisfeito.', 3),
	(4, 3.7, 'Algumas melhorias necessárias.', 4),
	(5, 4.8, 'Excelente atendimento.', 5),
	(6, 3.5, 'Boa experiência no geral.', 6),
	(7, 4.2, 'Recomendo.', 7),
	(8, 3.9, 'Satisfeito com a compra.', 8),
	(9, 4.6, 'Bom serviço.', 9),
	(10, 3.8, 'Satisfeito com o carro.', 10);
	
	-- MOTOR
	INSERT INTO MOTOR (id, tipo) VALUES 
	(1, 'MotorX'),
	(2, 'MotorY'),
	(3, 'MotorZ'),
	(4, 'MotorA'),
	(5, 'MotorB'),
	(6, 'MotorC'),
	(7, 'MotorD'),
	(8, 'MotorE'),
	(9, 'MotorF'),
	(10, 'MotorG');
	
	-- TRANSMISSAO
	INSERT INTO TRANSMISSAO (id, tipo) VALUES 
	(1, 'TransmissaoX'),
	(2, 'TransmissaoY'),
	(3, 'TransmissaoZ'),
	(4, 'TransmissaoA'),
	(5, 'TransmissaoB'),
	(6, 'TransmissaoC'),
	(7, 'TransmissaoD'),
	(8, 'TransmissaoE'),
	(9, 'TransmissaoF'),
	(10, 'TransmissaoG');
	
	-- TRACAO
	INSERT INTO TRACAO (id, tipo) VALUES 
	(1, 'TracaoX'),
	(2, 'TracaoY'),
	(3, 'TracaoZ'),
	(4, 'TracaoA'),
	(5, 'TracaoB'),
	(6, 'TracaoC'),
	(7, 'TracaoD'),
	(8, 'TracaoE'),
	(9, 'TracaoF'),
	(10, 'TracaoG');
	
	-- SUSPENSAO
	INSERT INTO SUSPENSAO (id, tipo) VALUES 
	(1, 'SuspensaoX'),
	(2, 'SuspensaoY'),
	(3, 'SuspensaoZ'),
	(4, 'SuspensaoA'),
	(5, 'SuspensaoB'),
	(6, 'SuspensaoC'),
	(7, 'SuspensaoD'),
	(8, 'SuspensaoE'),
	(9, 'SuspensaoF'),
	(10, 'SuspensaoG');
	
	-- INFO_TECNICAS
	INSERT INTO INFO_TECNICAS (id, potencia, freio_abs, direcao_hidraulica, dimensoes, FK_MOTOR_id, FK_TRANSMISSAO_id, FK_TRACAO_id, FK_SUSPENSAO_id) VALUES 
	(1, 150, true, true, 'Dimensoes1', 1, 1, 1, 1),
	(2, 200, true, false, 'Dimensoes2', 2, 2, 2, 2),
	(3, 180, true, true, 'Dimensoes3', 3, 3, 3, 3),
	(4, 170, false, true, 'Dimensoes4', 4, 4, 4, 4),
	(5, 190, true, false, 'Dimensoes5', 5, 5, 5, 5),
	(6, 160, false, true, 'Dimensoes6', 6, 6, 6, 6),
	(7, 210, true, false, 'Dimensoes7', 7, 7, 7, 7),
	(8, 220, false, true, 'Dimensoes8', 8, 8, 8, 8),
	(9, 195, true, true, 'Dimensoes9', 9, 9, 9, 9),
	(10, 185, false, false, 'Dimensoes10', 10, 10, 10, 10);
	
	-- TIPO_CARROCERIA
	INSERT INTO TIPO_CARROCERIA (id, tipo, descricao) VALUES 
	(1, 'TipoX', 'DescricaoX'),
	(2, 'TipoY', 'DescricaoY'),
	(3, 'TipoZ', 'DescricaoZ'),
	(4, 'TipoA', 'DescricaoA'),
	(5, 'TipoB', 'DescricaoB'),
	(6, 'TipoC', 'DescricaoC'),
	(7, 'TipoD', 'DescricaoD'),
	(8, 'TipoE', 'DescricaoE'),
	(9, 'TipoF', 'DescricaoF'),
	(10, 'TipoG', 'DescricaoG');
	
	-- CARRO
	INSERT INTO CARRO (id, preco, eh_novo, FK_INFO_TECNICAS_id, FK_MARCA_id, FK_MODELO_id, FK_TIPO_CARROCERIA_id) VALUES 
	(1, 35000.00, true, 1, 1, 1, 1),
	(2, 28000.00, false, 2, 2, 2, 2),
	(3, 38000.00, true, 3, 3, 3, 3),
	(4, 27000.00, false, 4, 4, 4, 4),
	(5, 32000.00, true, 5, 5, 5, 5),
	(6, 30000.00, true, 6, 6, 6, 6),
	(7, 40000.00, false, 7, 7, 7, 7),
	(8, 31000.00, true, 8, 8, 8, 8),
	(9, 33000.00, true, 9, 9, 9, 9),
	(10, 29500.00, true, 10, 10, 10, 10);
	
	-- Compra
	INSERT INTO Compra (FK_PESSOA_FK_USUARIO_id, FK_CARRO_id) VALUES 
	(1, 1),
	(2, 2),
	(3, 3),
	(4, 4),
	(5, 5),
	(6, 6),
	(7, 7),
	(8, 8),
	(9, 9),
	(10, 10);
	
	-- AGENDAMENTO
	INSERT INTO AGENDAMENTO (codigo, data, hora, FK_PESSOA_FK_USUARIO_id, FK_CONCESSIONARIA_FK_USUARIO_id) VALUES 
	(1, '2023-10-25', '10:00', 1, 1),
	(2, '2023-11-05', '14:30', 2, 2),
	(3, '2023-11-10', '11:00', 3, 3),
	(4, '2023-11-15', '15:00', 4, 4),
	(5, '2023-11-20', '13:30', 5, 5),
	(6, '2023-11-25', '12:00', 6, 6),
	(7, '2023-11-30', '16:00', 7, 7),
	(8, '2023-12-05', '09:30', 8, 8),
	(9, '2023-12-10', '17:00', 9, 9),
	(10, '2023-12-15', '08:30', 10, 10);
	
	
	-- Tabela MODELO
	SELECT * FROM MODELO;
	
	-- Tabela MARCA
	SELECT * FROM MARCA;
	
	-- Tabela USUARIO
	SELECT * FROM USUARIO;
	
	-- Tabela CONCESSIONARIA
	SELECT * FROM CONCESSIONARIA;
	
	-- Tabela PESSOA
	SELECT * FROM PESSOA;
	
	-- Tabela AVALIACAO
	SELECT * FROM AVALIACAO;
	
	-- Tabela MOTOR
	SELECT * FROM MOTOR;
	
	-- Tabela TRANSMISSAO
	SELECT * FROM TRANSMISSAO;
	
	-- Tabela TRACAO
	SELECT * FROM TRACAO;
	
	-- Tabela SUSPENSAO
	SELECT * FROM SUSPENSAO;
	
	-- Tabela INFO_TECNICAS
	SELECT * FROM INFO_TECNICAS;
	
	-- Tabela TIPO_CARROCERIA
	SELECT * FROM TIPO_CARROCERIA;
	
	-- Tabela CARRO
	SELECT * FROM CARRO;
	
	-- Tabela Compra
	SELECT * FROM Compra;
	
	-- Tabela AGENDAMENTO
	SELECT * FROM AGENDAMENTO;



### 9. TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Usa template da disciplina disponibilizado no Colab.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>

#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>

#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas

#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.

># Marco de Entrega 02: Do item 6. até o item 9.1 (5 PTS) <br>

#### 9.5	INSTRUÇÕES APLICANDO ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
    a) Criar minimo 3 de exclusão
    b) Criar minimo 3 de atualização

#### 9.6	CONSULTAS COM INNER JOIN E ORDER BY (Mínimo 6)<br>
    a) Uma junção que envolva todas as tabelas possuindo no mínimo 2 registros no resultado
    b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho

#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
    a) Criar minimo 2 envolvendo algum tipo de junção

#### 9.8	CONSULTAS COM LEFT, RIGHT E FULL JOIN (Mínimo 4)<br>
    a) Criar minimo 1 de cada tipo

#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join (caso não ocorra na base justificar e substituir por uma view)
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho

#### 9.10	SUBCONSULTAS (Mínimo 4)<br>
     a) Criar minimo 1 envolvendo GROUP BY
     b) Criar minimo 1 envolvendo algum tipo de junção

># Marco de Entrega 03: Do item 9.2 até o ítem 9.10 (10 PTS)<br>

### 10. RELATÓRIOS E GRÁFICOS

#### a) análises e resultados provenientes do banco de dados desenvolvido (usar modelo disponível)
#### b) link com exemplo de relatórios será disponiblizado pelo professor no AVA
#### OBS: Esta é uma atividade de grande relevância no contexto do trabalho. Mantenha o foco nos 5 principais relatórios/resultados visando obter o melhor resultado possível.

    

### 11. AJUSTES DA DOCUMENTAÇÃO, CRIAÇÃO DOS SLIDES E VÍDEO PARA APRESENTAÇAO FINAL <br>

#### a) Modelo (pecha kucha)<br>
#### b) Tempo de apresentação 6:40 

># Marco de Entrega 04: Itens 10 e 11 (20 PTS) <br>
<br>
<br>




### 12. FORMATACAO NO GIT:<br> 
https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
    
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/
#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

    
### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. <strong>Caso existam arquivos com conteúdos sigilosos<strong>, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário do git "profmoisesomena", para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://www.sis4.com/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


