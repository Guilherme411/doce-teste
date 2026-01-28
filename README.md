- Contexto e descrição do sistema
Texto (pronto).

- Diagrama ER (DER)
Colocar imagem do DER (pronto)

## Dicionário de Dados do banco

[cite_start]Este dicionário descreve a estrutura das tabelas do banco de dados para o sistema de adoção de pets[cite: 1].

### 🧍 Gestão de Pessoas e Endereços

#### [cite_start]Tabela: PESSOA_ADOTADOR [cite: 2]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_pessoa | INT | Identificador único do adotador | [cite_start]PK [cite: 3] |
| cpf | VARCHAR(11) | Cadastro de Pessoa Física (apenas números) | [cite_start]- [cite: 3] |
| nome | VARCHAR(100) | Nome completo do adotador | [cite_start]- [cite: 3] |
| email | VARCHAR(100) | Endereço de correio eletrônico | [cite_start]- [cite: 3] |
| id_endereco_pessoa | INT | Referência ao endereço do adotador | [cite_start]FK [cite: 3] |

#### [cite_start]Tabela: ENDERECO_PESSOA [cite: 6]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_endereco_pessoa | INT | Identificador único do endereço da pessoa | [cite_start]PK [cite: 7] |
| rua | VARCHAR(100) | Nome do logradouro | [cite_start]- [cite: 7] |
| bairro | VARCHAR(50) | Bairro de residência | [cite_start]- [cite: 7] |
| cidade | VARCHAR(50) | Cidade de residência | [cite_start]- [cite: 7] |
| numero | VARCHAR(10) | Número da residência ou complemento | [cite_start]- [cite: 7] |

#### [cite_start]Tabela: TELEFONE [cite: 4]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_telefone | INT | Identificador único do registro de telefone | [cite_start]PK [cite: 5] |
| telefone | VARCHAR(15) | Número de telefone com DDD | [cite_start]- [cite: 5] |
| id_pessoa | INT | Referência ao dono do telefone | [cite_start]FK [cite: 5] |

---

### 🐾 Gestão de Pets e Espécies

#### [cite_start]Tabela: PETS [cite: 8]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_pet | INT | Identificador único do animal | [cite_start]PK [cite: 9] |
| nome | VARCHAR(50) | Nome do pet | [cite_start]- [cite: 9] |
| descricao | VARCHAR(150) | Breve resumo sobre o pet (comportamento, etc) | [cite_start]- [cite: 9] |
| peso | DECIMAL(5,2) | Peso do animal em kg | [cite_start]- [cite: 9] |
| data_nascimento | DATE | Data de nascimento aproximada ou exata | [cite_start]- [cite: 9] |
| sexo | ENUM | Gênero do animal (Macho/Fêmea) | [cite_start]- [cite: 9] |
| porte | ENUM | Tamanho (Pequeno, Médio, Grande) | [cite_start]- [cite: 9] |
| id_tipo_especie | INT | Referência à espécie (Cão, Gato, etc) | [cite_start]FK [cite: 9] |
| id_endereco_pet | INT | Referência ao local onde o pet foi encontrado | [cite_start]FK [cite: 9] |
| id_vacina_pet | INT | Referência ao histórico de vacinação | [cite_start]FK [cite: 9] |

#### [cite_start]Tabela: TIPO_ESPECIE [cite: 10]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_tipo_especie | INT | Identificador único da espécie | [cite_start]PK [cite: 11] |
| nome_especie | ENUM | Classificação da espécie do animal | [cite_start]- [cite: 11] |

#### [cite_start]Tabela: ENDERECO_PET_ENCONTRADO [cite: 12]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_endereco_pet | INT | Identificador único do local de resgate | [cite_start]PK [cite: 13] |
| rua | VARCHAR(100) | Logradouro onde o pet foi visto/resgatado | [cite_start]- [cite: 13] |
| bairro | VARCHAR(50) | Bairro do resgate | [cite_start]- [cite: 13] |
| cidade | VARCHAR(50) | Cidade do resgate | [cite_start]- [cite: 13] |
| numero | VARCHAR(10) | Número aproximado do local de resgate | [cite_start]- [cite: 13] |

---

### Vacinação e Processos

#### [cite_start]Tabela: ADOCAO [cite: 14]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_adocao | INT | Identificador único do processo de adoção | [cite_start]PK [cite: 15] |
| data_adocao | DATE | Data em que a adoção foi formalizada | [cite_start]- [cite: 15] |
| id_pet | INT | Referência ao pet adotado | [cite_start]FK [cite: 15] |
| id_pessoa | INT | Referência ao adotador responsável | [cite_start]FK [cite: 15] |

#### [cite_start]Tabela: VACINA_PET [cite: 16]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_vacina_pet | INT | Identificador único da aplicação da vacina | [cite_start]PK [cite: 17] |
| id_catalago_vacina | INT | Referência ao tipo de vacina no catálogo | [cite_start]FK [cite: 17] |

#### [cite_start]Tabela: CATALAGO_VACINA [cite: 18]
| Campo | Tipo | Descrição | Chave |
| :--- | :--- | :--- | :---: |
| id_catalago_vacina | INT | Identificador único da vacina no sistema | [cite_start]PK [cite: 19] |
| nome_vacina | VARCHAR(50) | Nome comercial ou técnico da vacina | [cite_start]- [cite: 19] |

- Script SQL (DDL + DML)
script (adicionar aqui)

- Consultas SQL (JOIN, agregação, GROUP BY, HAVING)
Consultas (quase pronto)

- Demonstração prática do banco funcionando
Adicionar passo a passo de rodar o codigo pelo xampp (Nao pronto)