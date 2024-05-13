# Estrutura do Banco de Dados

## Tabelas

### User

- **id**: Identificação única do usuário.
- **age**: Idade do usuário.
- **phone_number**: Número de telefone do usuário.
- **gender**: Gênero do usuário.
- **nationality**: Nacionalidade do usuário.
- **email**: Endereço de email do usuário.
- **name**: Nome do usuário.
- **password**: Senha do usuário.

### Student

- **id**: Identificação única do estudante.
- **social_media**: Informações sobre redes sociais do estudante.
- **one_word**: Descrição do estudante em uma palavra.
- **about_me**: Breve descrição sobre o estudante.
- **id_university**: Chave estrangeira para a universidade à qual o estudante pertence.
- **id_country**: Chave estrangeira para o país do estudante.
- **id_user**: Chave estrangeira para o usuário correspondente.
- **id_answers**: Chave estrangeira para as respostas do estudante.

### Tutor

- **id**: Identificação única do tutor.
- **id_country**: Chave estrangeira para o país do tutor.
- **id_user**: Chave estrangeira para o usuário correspondente.

### University

- **id**: Identificação única da universidade.
- **name**: Nome da universidade.
- **id_country**: Chave estrangeira para o país onde a universidade está localizada.

### Country

- **id**: Identificação única do país.
- **country**: Nome do país.
- **city**: Nome da cidade.

### Team

- **id**: Identificação única da equipe.
- **color**: Cor associada à equipe.
- **universe**: Universo da equipe.
- **id_cesim_game**: Chave estrangeira para o jogo Cesim associado.
- **id_student_team**: Chave estrangeira para a equipe de estudantes associada.
- **id_tutor_team**: Chave estrangeira para a equipe de tutores associada.
- **ativa**: Identifica se o time está ativo.

### Cesim_game

- **id**: Identificação única do jogo Cesim.
- **startdate**: Data de início do jogo.
- **enddate**: Data de término do jogo.

### Round

- **id**: Identificação única da rodada.
- **startdate**: Data de início da rodada.
- **enddate**: Data de término da rodada.
- **round_number**: Número da rodada.
- **id_cesim_game**: Chave estrangeira para o jogo Cesim associado.

### Questionnaire

- **id**: Identificação única do questionário.
- **name**: Nome do questionário.
- **quest_category**: Categoria do questionário.

### Questions

- **id**: Identificação única da pergunta.
- **description**: Descrição da pergunta.
- **id_questionnaire**: Chave estrangeira para o questionário associado.

### Alternative

- **id**: Identificação única da alternativa.
- **description**: Descrição da alternativa.
- **id_questions**: Chave estrangeira para a pergunta associada.

### questionnaire_round

- **id**: Identificação única da associação entre questionário e rodada.
- **id_questionnaire**: Chave estrangeira para o questionário associado.
- **id_round**: Chave estrangeira para a rodada associada.

### Answers

- **id**: Identificação única da resposta.
- **id_questions**: Chave estrangeira para a pergunta associada.
- **id_round**: Chave estrangeira para a rodada associada.
- **id_alternative**: Chave estrangeira para a alternativa associada.

### Student_team

- **id**: Identificação única da associação entre estudante e equipe.
- **id_team**: Chave estrangeira para a equipe associada.
- **id_student**: Chave estrangeira para o estudante associado.

### Tutor_team

- **id**: Identificação única da associação entre tutor e equipe.
- **id_tutor**: Chave estrangeira para o tutor associado.
- **id_team**: Chave estrangeira para a equipe associada.

### questionnaire_student

- **id**: Identificação única da associação entre questionário e estudante.
- **id_studentSender**: Chave estrangeira para o estudante remetente.
- **id_studentReceiver**: Chave estrangeira para o estudante destinatário.
- **id_questionnaire**: Chave estrangeira para o questionário associado.

## Relacionamentos

- **Chaves Primárias**: Cada tabela possui uma chave primária que identifica exclusivamente cada registro.
- **Chaves Estrangeiras**: Algumas tabelas têm chaves estrangeiras que estabelecem relações com outras tabelas.

**Link para visualização:** (https://github.com/kauanmassuia/bancodedadosponderadakizzy.git)

