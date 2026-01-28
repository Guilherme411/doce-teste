### Gestão de Pessoas e Endereços

#### Tabela: PESSOA_ADOTADOR
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_pessoa | INT | Identificador único do adotador | PK [cite: 3] |
| cpf | VARCHAR(11) | Cadastro de Pessoa Física (apenas números) | - [cite: 3] |
| nome | VARCHAR(100) | Nome completo do adotador | - [cite: 3] |
| email | VARCHAR(100) | Endereço de correio eletrônico | - [cite: 3] |
| id_endereco_pessoa | INT | Referência ao endereço do adotador | FK [cite: 3] |

#### Tabela: ENDERECO_PESSOA
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_endereco_pessoa | INT | Identificador único do endereço da pessoa | PK [cite: 7] |
| rua | VARCHAR(100) | Nome do logradouro | - [cite: 7] |
| bairro | VARCHAR(50) | Bairro de residência | - [cite: 7] |
| cidade | VARCHAR(50) | Cidade de residência | - [cite: 7] |
| numero | VARCHAR(10) | Número da residência ou complemento | - [cite: 7] |

#### Tabela: TELEFONE
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_telefone | INT | Identificador único do registro de telefone | PK [cite: 5] |
| telefone | VARCHAR(15) | Número de telefone com DDD | - [cite: 5] |
| id_pessoa | INT | Referência ao dono do telefone | FK [cite: 5] |

---

### Gestão de Pets e Espécies

#### Tabela: PETS
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_pet | INT | Identificador único do animal | PK [cite: 9] |
| nome | VARCHAR(50) | Nome do pet | - [cite: 9] |
| descricao | VARCHAR(150) | Breve resumo sobre o pet (comportamento, etc) | - [cite: 9] |
| peso | DECIMAL(5,2) | Peso do animal em kg | - [cite: 9] |
| data_nascimento | DATE | Data de nascimento aproximada ou exata | - [cite: 9] |
| sexo | ENUM | Gênero do animal (Macho/Fêmea) | - [cite: 9] |
| porte | ENUM | Tamanho (Pequeno, Médio, Grande) | - [cite: 9] |
| id_tipo_especie | INT | Referência à espécie (Cão, Gato, etc) | FK [cite: 9] |
| id_endereco_pet | INT | Referência ao local onde o pet foi encontrado | FK [cite: 9] |
| id_vacina_pet | INT | Referência ao histórico de vacinação | FK [cite: 9] |

#### Tabela: TIPO_ESPECIE
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_tipo_especie | INT | Identificador único da espécie | PK [cite: 11] |
| nome_especie | ENUM | Classificação da espécie do animal | - [cite: 11] |

#### Tabela: ENDERECO_PET_ENCONTRADO
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_endereco_pet | INT | Identificador único do local de resgate | PK [cite: 13] |
| rua | VARCHAR(100) | Logradouro onde o pet foi visto/resgatado | - [cite: 13] |
| bairro | VARCHAR(50) | Bairro do resgate | - [cite: 13] |
| cidade | VARCHAR(50) | Cidade do resgate | - [cite: 13] |
| numero | VARCHAR(10) | Número aproximado do local de resgate | - [cite: 13] |

---

### Vacinação e Processos

#### Tabela: ADOCAO
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_adocao | INT | Identificador único do processo de adoção | PK [cite: 15] |
| data_adocao | DATE | Data em que a adoção foi formalizada | - [cite: 15] |
| id_pet | INT | Referência ao pet adotado | FK [cite: 15] |
| id_pessoa | INT | Referência ao adotador responsável | FK [cite: 15] |

#### Tabela: VACINA_PET
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_vacina_pet | INT | Identificador único da aplicação da vacina | PK [cite: 17] |
| id_catalago_vacina | INT | Referência ao tipo de vacina no catálogo | FK [cite: 17] |

#### Tabela: CATALAGO_VACINA
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_catalago_vacina | INT | Identificador único da vacina no sistema | PK [cite: 19] |
| nome_vacina | VARCHAR(50) | Nome comercial ou técnico da vacina | - [cite: 19] |
