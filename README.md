# ACIDENTES – Assistente de atendimento de Acidentes

**Acidentes** é um protótipo de aplicação web desenvolvida para coletar e organizar dados sobre acidentes de trânsito. Por meio de uma interface de chat interativa (via WebSocket) e integração com a API da OpenAI, o sistema gera automaticamente narrativas estruturadas e um JSON contendo todos os detalhes do sinistro, facilitando a elaboração de relatórios e o registro formal dos eventos.

## Funcionalidades

### Coleta Interativa de Dados
- Através de um diálogo orientado, o sistema coleta informações essenciais do acidente, como:
  - Data, hora
  - Localização (BR, km, cidade, UF)
  - Tipo de acidente
  - Detalhes dos veículos
  - Dados do condutor  
  - E muito mais.

### Geração de Narrativas e JSON
Utiliza modelos de linguagem (GPT-3.5-turbo e GPT-4) para:
- Estruturar as informações coletadas em um JSON padronizado.
- Refinar e melhorar a narrativa do acidente, garantindo clareza, concisão e organização cronológica dos fatos.

### Gerenciamento de Tokens
- Implementa um sistema para contar e deduzir tokens usados nas chamadas à API, ajudando a controlar o custo e a otimizar as requisições.

### Uso de Cache e Persistência
- Armazena temporariamente os dados coletados em cache durante a sessão para evitar múltiplos salvamentos no banco.
- O salvamento final é realizado apenas ao término da interação, reduzindo operações de I/O.

### Integração com Django Channels e Daphne
- Permite comunicação assíncrona via WebSocket, oferecendo uma experiência de chat em tempo real para o usuário.

## Tecnologias Utilizadas

- **Python** – Linguagem principal do projeto.
- **Django** – Framework web para o backend.
- **Django Channels** – Suporte a WebSockets e comunicação assíncrona.
- **Daphne** – Servidor ASGI para execução da aplicação.
- **OpenAI API** – Geração e aprimoramento das narrativas de acidentes.
- **tiktoken** – Contagem e otimização de tokens para as chamadas à API.
- **Cache (Redis)** – Armazenamento temporário dos dados durante a sessão.
