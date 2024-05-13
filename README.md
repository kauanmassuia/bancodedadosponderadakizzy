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

**arquivo para visualização dos dados:**

<?xml version="1.0" encoding="utf-8" ?>
<!-- SQL XML created by WWW SQL Designer, https://github.com/ondras/wwwsqldesigner/ -->
<!-- Active URL: https://sql.toad.cz/ -->
<sql>
<datatypes db="mysql">
	<group label="Numeric" color="rgb(238,238,170)">
		<type label="Integer" length="0" sql="INTEGER" quote=""/>
	 	<type label="TINYINT" length="0" sql="TINYINT" quote=""/>
	 	<type label="SMALLINT" length="0" sql="SMALLINT" quote=""/>
	 	<type label="MEDIUMINT" length="0" sql="MEDIUMINT" quote=""/>
	 	<type label="INT" length="0" sql="INT" quote=""/>
		<type label="BIGINT" length="0" sql="BIGINT" quote=""/>
		<type label="Decimal" length="1" sql="DECIMAL" re="DEC" quote=""/>
		<type label="Single precision" length="0" sql="FLOAT" quote=""/>
		<type label="Double precision" length="0" sql="DOUBLE" re="DOUBLE" quote=""/>
	</group>

	<group label="Character" color="rgb(255,200,200)">
		<type label="Char" length="1" sql="CHAR" quote="'"/>
		<type label="Varchar" length="1" sql="VARCHAR" quote="'"/>
		<type label="Text" length="0" sql="MEDIUMTEXT" re="TEXT" quote="'"/>
		<type label="Binary" length="1" sql="BINARY" quote="'"/>
		<type label="Varbinary" length="1" sql="VARBINARY" quote="'"/>
		<type label="BLOB" length="0" sql="BLOB" re="BLOB" quote="'"/>
	</group>

	<group label="Date &amp; Time" color="rgb(200,255,200)">
		<type label="Date" length="0" sql="DATE" quote="'"/>
		<type label="Time" length="0" sql="TIME" quote="'"/>
		<type label="Datetime" length="0" sql="DATETIME" quote="'"/>
		<type label="Year" length="0" sql="YEAR" quote=""/>
		<type label="Timestamp" length="0" sql="TIMESTAMP" quote="'"/>
	</group>
	
	<group label="Miscellaneous" color="rgb(200,200,255)">
		<type label="ENUM" length="1" sql="ENUM" quote=""/>
		<type label="SET" length="1" sql="SET" quote=""/>
		<type label="Bit" length="0" sql="bit" quote=""/>
	</group>
</datatypes><table x="1539" y="1790" name="User">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="age " null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="phone_number" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="gender" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<row name="nationality" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<row name="email" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<row name="password" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1742" y="1703" name="Student">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="social_media" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="one_word" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="about_me" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="id_university" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="University" row="id" />
</row>
<row name="id_country" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Country" row="id" />
</row>
<row name="id_user" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="User" row="id" />
</row>
<row name="id_answers" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Answers" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1123" y="1587" name="Tutor">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_country" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Country" row="id" />
</row>
<row name="id_user" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="User" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1311" y="1763" name="University">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<row name="id_country" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Country" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1121" y="1727" name="Country">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="country" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<row name="city" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1533" y="1571" name="team">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="color" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<row name="universe" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_cesim_game" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Cesim_game" row="id" />
</row>
<row name="id_student_team" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_tutor_team" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Tutor_team" row="id" />
</row>
<row name="ativa" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1958" y="1580" name="Cesim_game">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="startdate" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="enddate" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="2231" y="1587" name="Round">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="startdate" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="enddate" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="round_number" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_cesim_game" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Cesim_game" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="2435" y="1792" name="Questionnaire">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="name" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<row name="quest_category" null="1" autoincrement="0">
<datatype>VARCHAR</datatype>
<default>NULL</default></row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="2230" y="1771" name="Questions">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="description" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="id_questionnaire" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Questionnaire" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="2060" y="1897" name="Alternative">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="description" null="1" autoincrement="0">
<datatype>MEDIUMTEXT</datatype>
<default>NULL</default></row>
<row name="id_questions" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Questions" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="2407" y="1587" name="questionnaire_round">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_questionnaire" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Questionnaire" row="id" />
</row>
<row name="id_round" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Round" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1990" y="1729" name="Answers">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_questions" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Questions" row="id" />
</row>
<row name="id_round" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Round" row="id" />
</row>
<row name="id_alternative" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Alternative" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1729" y="1571" name="Student_team">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_team" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="team" row="id" />
</row>
<row name="id_student" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Student" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="1305" y="1566" name="Tutor_team">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_tutor" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Tutor" row="id" />
</row>
<row name="id_team" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="team" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
<table x="2038" y="2048" name="questionnaire_student">
<row name="id" null="1" autoincrement="1">
<datatype>INTEGER</datatype>
<default>NULL</default></row>
<row name="id_studentSender" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Student" row="id" />
</row>
<row name="id_studentReceiver" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Student" row="id" />
</row>
<row name="id_questionnaire" null="1" autoincrement="0">
<datatype>INTEGER</datatype>
<default>NULL</default><relation table="Questionnaire" row="id" />
</row>
<key type="PRIMARY" name="">
<part>id</part>
</key>
</table>
</sql>

