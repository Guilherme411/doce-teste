### Gestão de Pessoas e Endereços

#### Tabela: PESSOA_ADOTADOR
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_pessoa | INT | Identificador único do adotador | PK |
| cpf | VARCHAR(11) | Cadastro de Pessoa Física (apenas números) | - |
| nome | VARCHAR(100) | Nome completo do adotador | - |
| email | VARCHAR(100) | Endereço de correio eletrônico | - |
| id_endereco_pessoa | INT | Referência ao endereço do adotador | FK |

#### Tabela: ENDERECO_PESSOA
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_endereco_pessoa | INT | Identificador único do endereço da pessoa | PK |
| rua | VARCHAR(100) | Nome do logradouro | - |
| bairro | VARCHAR(50) | Bairro de residência | - |
| cidade | VARCHAR(50) | Cidade de residência | - |
| numero | VARCHAR(10) | Número da residência ou complemento | - |

#### Tabela: TELEFONE
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_telefone | INT | Identificador único do registro de telefone | PK |
| telefone | VARCHAR(15) | Número de telefone com DDD | - |
| id_pessoa | INT | Referência ao dono do telefone | FK |

---

### Gestão de Pets e Espécies

#### Tabela: PETS
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_pet | INT | Identificador único do animal | PK |
| nome | VARCHAR(50) | Nome do pet | - |
| descricao | VARCHAR(150) | Breve resumo sobre o pet (comportamento, etc) | - |
| peso | DECIMAL(5,2) | Peso do animal em kg | - |
| data_nascimento | DATE | Data de nascimento aproximada ou exata | - |
| sexo | ENUM | Gênero do animal (Macho/Fêmea) | - |
| porte | ENUM | Tamanho (Pequeno, Médio, Grande) | - |
| id_tipo_especie | INT | Referência à espécie (Cão, Gato, etc) | FK |
| id_endereco_pet | INT | Referência ao local onde o pet foi encontrado | FK |
| id_vacina_pet | INT | Referência ao histórico de vacinação | FK |

#### Tabela: TIPO_ESPECIE
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_tipo_especie | INT | Identificador único da espécie | PK |
| nome_especie | ENUM | Classificação da espécie do animal | - |

#### Tabela: ENDERECO_PET_ENCONTRADO
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_endereco_pet | INT | Identificador único do local de resgate | PK |
| rua | VARCHAR(100) | Logradouro onde o pet foi visto/resgatado | - |
| bairro | VARCHAR(50) | Bairro do resgate | - |
| cidade | VARCHAR(50) | Cidade do resgate | - |
| numero | VARCHAR(10) | Número aproximado do local de resgate | - |

---

### Vacinação e Processos

#### Tabela: ADOCAO
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_adocao | INT | Identificador único do processo de adoção | PK |
| data_adocao | DATE | Data em que a adoção foi formalizada | - |
| id_pet | INT | Referência ao pet adotado | FK |
| id_pessoa | INT | Referência ao adotador responsável | FK |

#### Tabela: VACINA_PET
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_vacina_pet | INT | Identificador único da aplicação da vacina | PK |
| id_catalago_vacina | INT | Referência ao tipo de vacina no catálogo | FK |

#### Tabela: CATALAGO_VACINA
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_catalago_vacina | INT | Identificador único da vacina no sistema | PK |
| nome_vacina | VARCHAR(50) | Nome comercial ou técnico da vacina | - |
