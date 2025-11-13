# 🧠 Mental Monitoring API

A **Mental Monitoring API** é uma aplicação desenvolvida em **Java com Spring Boot** que permite o **acompanhamento de pacientes e profissionais de saúde mental**, o **agendamento de consultas** e o **compartilhamento de recursos educativos** (como artigos e vídeos).

O objetivo é contribuir para o **ODS 3 – Saúde e Bem-Estar**, promovendo um sistema simples, acessível e eficiente de **monitoramento psicológico e apoio emocional**.

---

## 🎯 O que a aplicação faz?

A aplicação funciona como um **sistema de gerenciamento de saúde mental**, oferecendo quatro grandes funcionalidades:

1. **Pacientes:** cadastro, atualização, exclusão e consulta de informações.
2. **Profissionais de saúde:** registro de psicólogos, terapeutas e outros especialistas.
3. **Consultas:** agendamento e gerenciamento entre pacientes e profissionais.
4. **Recursos de apoio:** artigos e vídeos com orientações e dicas sobre bem-estar mental.

Tudo é feito por meio de uma **API REST**, que pode ser acessada e testada usando ferramentas como o **Insomnia**.

---

## 🧩 Estrutura do Projeto

mental-monitoring-api/

├── src/

│ ├── main/java/com.example.mental/

│ │ ├── controller/ → Endpoints da API (lógica de entrada)

│ │ ├── entity/ → Classes que representam as tabelas (modelos)

│ │ ├── repository/ → Comunicação com o banco de dados (JPA)

│ │ ├── service/ → Regras de negócio e validações

│ │ └── exception/ → Tratamento de erros e respostas amigáveis

│ └── resources/

│ ├── application.properties → Configurações da aplicação

│ └── data.sql (opcional) → Dados iniciais (seed)

├── pom.xml → Arquivo de dependências do Maven

├── MentalMonitoringAPI_Insomnia.json → Coleção para testes no Insomnia

└── README.md → Este arquivo


---

## ⚙️ Como rodar o projeto

### 🧰 Pré-requisitos

- **Java 17** ou superior
- **Maven** instalado
- **IntelliJ IDEA** (ou VSCode com suporte a Java)
- **Insomnia** (para testar os endpoints)

---

### 🚀 Passo a passo

```bash
1️⃣ **Baixe o projeto**

git clone https://github.com/YujiSam/Mental-Monitoring-API.git

2️⃣ Acesse a pasta

cd mental-monitoring-api

3️⃣ Rode o projeto

mvn spring-boot:run

4️⃣ Acesse a aplicação

http://localhost:8080

5️⃣ (Opcional) Abra o console do banco H2

http://localhost:8080/h2-console

    JDBC URL: jdbc:h2:mem:mentaldb

    User: sa

    Password: (deixe em branco)

🧪 Testando no Insomnia

O projeto já vem com uma coleção pronta de requisições para o Insomnia:
📄 MentalMonitoringAPI_Insomnia.json
Para importar:

    Abra o Insomnia

    Vá em Application → Preferences → Data → Import Data → From File

    Escolha o arquivo MentalMonitoringAPI_Insomnia.json

    Clique em Importar

Você verá 4 grupos:

    🧍 Pacientes

    👩‍⚕️ Profissionais de Saúde

    🩺 Consultas

    📚 Recursos de Apoio

Cada grupo contém os métodos:

GET (listar todos)
GET /{id} (buscar por ID)
POST (criar)
PUT /{id} (atualizar)
DELETE /{id} (remover)

💡 Exemplos de Requisições
👩 Paciente

POST /api/pacientes

{
  "nome": "Maria Souza",
  "email": "maria.souza@example.com",
  "dataNascimento": "1994-07-15"
}

👨‍⚕️ Profissional

POST /api/profissionais

{
  "nome": "Dr. João Mendes",
  "email": "joao.mendes@psicologia.com",
  "especialidade": "Psicologia Clínica"
}

🩺 Consulta

POST /api/consultas

{
  "dataHora": "2025-11-20T15:00:00",
  "status": "AGENDADA",
  "observacao": "Sessão inicial de avaliação psicológica",
  "pacienteId": 1,
  "profissionalId": 1
}

📚 Recurso

POST /api/recursos

{
  "titulo": "Como lidar com ansiedade",
  "tipo": "Artigo",
  "link": "https://saudemental.com/ansiedade",
  "descricao": "Artigo com técnicas práticas de respiração e foco."
}

🌱 ODS Relacionado
ODS 3 – Saúde e Bem-Estar

    Garantir o acesso à saúde de qualidade e promover o bem-estar para todos, em todas as idades.

A Mental Monitoring API apoia esse objetivo ao possibilitar:

    O acompanhamento digital de pacientes e profissionais;

    O incentivo à saúde mental através de recursos educativos;

    A organização de consultas e histórico de acompanhamento psicológico.

🧑‍💻 Autores

Gustavo Yuji Osugi - RM 555034

Renan Simões Gonçalves - RM 555584

Victor Hugo de Paula - RM 554787

📅 Global Solution 2025

✅ Resumo rápido
Entidade	Métodos Disponíveis	Endpoint base
Pacientes	GET / GET/{id} / POST / PUT / DELETE	/api/pacientes
Profissionais	GET / GET/{id} / POST / PUT / DELETE	/api/profissionais
Consultas	GET / GET/{id} / POST / PUT / DELETE	/api/consultas
Recursos	GET / GET/{id} / POST / PUT / DELETE	/api/recursos
