# Projeto Integrador - Padaria e Confeitaria Wonder Bakery

Um modelo para o desenvolvimento do Projeto Integrador do Curso de Técnico em Desenvolvimento de Sistemas para a Internet Integrado ao Ensino Médio do IFC - Campus Araquari.

Equipe: [João Otávio Bento](https://github.com/MsHapen) e [Davy Moreira Sebold](https://github.com/Rascro)

Professores: [Marco André Mendes](github.com/marcoandre) e [Alann Perini](https://github.com/AlannKPerini).

Links do projeto:

-   [Documentação (esse documento)](https://github.com/MsHapen/pi_modelo.git)
-   [Backend](github.com/marcoandre/pi-backend)
-   [Frontend](github.com/marcoandre/pi-frontend)

![Wonder_Bakery](docs/Wonder-Bakery.webp "Wonder Bakery")

A Wonder Bakery é uma padaria e confeitaria temática do universo de Pokemon. Ela tem seu foco em deixar suas receitas únicas e atrativas, prezando não só o sabor mas também a apresentação. Fundada em 2013, vem se aperfeiçoando até hoje. Seu dono é Satoshi Tajiri e possui 12 funcionários: 4 Padeiros, 2 caixas, 3 atendentes e 3 entregadores.

Atualmente a padaria funciona de forma presencial. Seus pedidos podem ser feitos no  caixa ou por meio de algum atendente no local, mas recentemente isso se tornou um problema pois, mesmo as vendas estando ótimas, eles se sentem limitados em questão de área de vendas.

Foi pedido que o site tivesse grande destaque na aparência dos confeitos pois essa é uma importante parte do negócio, solicitando que ficassem à vista e com “imagens grandes”.

Eles necessitam de um sistema que facilite para o cliente na hora de fazer seu pedido e os funcionários em sua organização.

# Descrição da proposta

Visamos fazer um sistema simples para quem maneja e atrativo para quem usa, priorizando a parte visual. Seguiremos com um sistema de cadastro para registrar dados do usuário como endereço, formas de pagamento, etc. O sistema será focado no atendimento e gerenciamento, por isso precisará transmitir os pedidos para os confeiteiros após serem finalizados pelos clientes. Também faremos um sistema de pesquisa para facilitar a busca pelos produtos e um para marcar os que estão indisponíveis e registrar promoções e cupons. 

# Regras de Negócio 

- **RN01** – *Criação Comanda:* Para iniciar um atendimento no balcão, é necessário primeiro abrir uma nova comanda.
- **RN02** – *Inserir Produtos Comanda:* Para inserir um produto na comanda, é necessário que o produto esteja cadastrado no sistema e que a quantia comprada seja acima de zero.
- **RN03** – *Relatório de Fluxo de Caixa:* O relatório de fluxo de caixa será permitido somente para o administrador.
- **RN04** – *Estoque:* O Sistema deve manter a entrada e saída de itens do estoque com data e quantidade registrando um relatório de fluxo para o administrador.
- **RN05** – *Produtos:* O sistema deve manter o registro dos produtos em estoque.
- **RN06** – *Compra:* O sistema deve registrar cada venda efetuada.

# Requisitos Funcionais

**ENTRADA**

- **R.F.01 - Registro de Usuário:** O sistema deve manter os usuários registrados e seus devidos níveis após o primeiro cadastro deles, usando seu nome de usuário, senha e CPF.
    - **Dados necessários:** Nome, Senha, CPF e Nível de Usuário.
    - **Nível de Usuário:** Gerente
- **R.F.02 - Registro de Produtos:** Todos os produtos vendidos devem estar devidamente registrados no estoque.
    - **Dados necessários:** Nome do Produto, Categoria, Código do Produto, Valor e Quantidade.
    - **Nível de Usuário:** Gerente.

**PROCESSOS**

- **R.F.03 - Autenticação de Usuário:** O sistema deve ser capaz de autentificar o usuário que o está acessando com base no Registro de Usuário para checar seu nível e sua autenticidade.
    - **Dados necessários:** Nome de Usuário, CPF e Nível de Usuário.
    - **Nível de Usuário:** Gerente
- **R.F.04 - Emissão de Comandas:** Após a confirmação de cada pedido, uma comanda deve ser gerada, podendo ser marcada como finalizada quando o pedido for entregue.
    - **Dados necessários:** Nome do Produto, Quantidade, Horário do Pedido e validação.
    - **Nível de Usuário:** Atendente, Gerente.
- **R.F.05 - Cálculo de Vendas:** O sistema deve calcular o valor dos itens adicionados pelo usuário na venda.
    - **Dados necessários:** Usuário, Código do Produto, Valor.
    - **Nível de Usuário:** Caixa, Gerente.
- **R.F.06 - Gerenciamento de Venda:** Toda compra feita no caixa deve emitir uma nota e só poderá ser efetuada mediante a confirmação do pagamento.
    - **Dados necessários:** Nome do Produto, Código do produto, Valor, Quantidade Comprada
    - **Nível de Usuário:** Caixa, Gerente
- **R.F.07 - Reposição:** Se os produtos do estoque estiverem em baixa quantidade (20) deve ser enviado um aviso de reposição pelo sistema.
    - **Dados necessários:** Código do Produto, Quantidade.
    - **Nível de Usuário:** Gerente

**SAÍDA**

- **R.F.08 - Relatório de Vendas da semana:** Toda semana deve ser emitido um relatório com o valor das vendas da semana e os produtos mais vendidos.
    - **Dados necessários:** Período (Data Inicial e Final).
    - **Nível de Usuário:** Gerente.

- **R.F.09 - Relatório de Estoque:** Deve ser emitido um relatório diariamente listando os produtos disponíveis no estoque e sua quantidade. 
    - **Dados necessários:** Período (Data Inicial e Final).
    - **Nível de Usuário:** Gerente.

# Requisitos Não Funcionais

- **N.F.R.01 - Manutenção:** O sistema deve receber uma manutenção sempre que necessário.

- **N.F.R.02 - Portabilidade:** O sistema deve ser capaz de rodar nos navegadores Chrome, Opera e Microsoft Edge.

- **N.F.R.03 - Compatibilidade:** O sistema deve ser compativel com Linux e Windows.

- **N.F.R.04 - Banco de Dados:** O banco de dados do sistema deverá ser feito em MySQL ou PostgreSQL.

- **N.F.R.05 - Atuação:** O sistema deve ser capaz de lidar com ao menos 10 usuários simultâneos.

- **N.F.R.07 - Segurança:** O sistema deve possuir uma forma de autenticar o usuário, utilizando criptografia de senha md5. Além disso o sistema deve possuir um firewall de inspeção de dados

- **N.F.R.08 - Disponibilidade:** O sistema deve funcionar durante o periodo de funcionamento da padaria.
