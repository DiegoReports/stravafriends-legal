# 🏅 StvFriends – Competição Amistosa com Strava + WhatsApp + IA

O **StvFriends** é um projeto que cria uma competição esportiva amigável entre amigos, usando dados do **Strava**, banco de dados no **Supabase**, automações com **n8n**, mensagens personalizadas via **WhatsApp** (Evolution API) e incentivos motivacionais gerados por **IA (Gemini)**.

O objetivo é transformar atividades esportivas do dia a dia em um jogo interativo com pontuação, ranking e mensagens motivacionais automáticas enviadas para um grupo no WhatsApp.

---

## 🧩 **Funcionalidades**

- 🔄 Coleta automática de atividades dos participantes via **Strava API**
- 🧮 Cálculo de pontuação baseado em pesos de atividade:
  - Corrida – peso 3  
  - Caminhada – peso 1  
  - Bicicleta – peso 1  
  - Musculação – peso 4  
  - Pilates – peso 4
- 📊 Ranking diário/semanal dos participantes
- 🤖 IA (Gemini) gera mensagens de incentivo personalizadas
- 💬 Envio automático das mensagens para um **grupo no WhatsApp**
- 📦 Armazenamento seguro de dados com **Supabase**
- ⚙️ Fluxos automatizados 24/7 utilizando **n8n**

---

## 🏗️ **Arquitetura do Projeto**

STRAVA API → n8n → SUPABASE → n8n → GEMINI → n8n → EVOLUTION API → WHATSAPP (grupo)


### **Componentes principais:**

- **Strava API** – coleta de dados das atividades esportivas  
- **Supabase (PostgreSQL)** – armazenamento de usuários, atividades e pontuações  
- **n8n** – automação de todos os fluxos, webhooks e crons  
- **Gemini API** – geração de mensagens personalizadas  
- **Evolution API** – envio e recepção de mensagens no WhatsApp  
- **GitHub Pages** – hospedagem de Política de Privacidade e Termos de Uso  

---

## 🔐 **Requisitos e Credenciais**

Para rodar o projeto, você precisa gerar:

- **Strava Client ID / Client Secret**
- **Gemini API Key**
- **Supabase Service Role Key + URL**
- **Evolution API Instance + Token**
- **Webhook URLs (n8n)**

Após gerar as credenciais, configure-as como variáveis de ambiente no n8n.

---

## 📦 **Instalação e Setup**

### **1. Clone o repositório**
```bash
git clone https://github.com/SEU_USUARIO/StvFriends.git
cd StvFriends
```

### **2. Configure o n8n**

Você pode rodar:

- Localmente

- Railway (recomendado – gratuito)

- Render

- Fly.io

Exemplo local:
```bash
npm install -g n8n
n8n start
```

### 🧮 Regras de Pontuação

Cada atividade possui um peso fixo:

| Atividade  | Peso |
| ---------- | ---- |
| Corrida    | 3    |
| Caminhada  | 1    |
| Bicicleta  | 1    |
| Musculação | 4    |
| Pilates    | 4    |

### 💬 Fluxo de Mensagens no WhatsApp

- n8n recebe a atividade via Webhook
- Calcula pontuação
- Atualiza o ranking no Supabase
- Envia dados para o Gemini gerar motivação

n8n envia mensagem motivacional ao Grupo de WhatsApp via Evolution API

### 🔒 Privacidade e LGPD

Cada usuário autoriza o acesso via OAuth oficial do Strava

Nenhum dado é compartilhado publicamente

Apenas informações essenciais são coletadas

Termos de Uso e Política de Privacidade estão hospedados no GitHub Pages

### 🧪 Status do Projeto

- [x] ✔ Arquitetura definida
- [x] ✔ Modelagem do banco Supabase
- [x] ✔ Regras de pontuação finalizadas
- [ ] 🔄 Configuração da Strava como Public App (em andamento)
- [ ] 🔄 Criação dos workflows no n8n
- [ ] ⬜ Interface web (opcional – fase futura)

### 🤝 Contribuição

Sinta-se à vontade para:

- abrir issues

- sugerir melhorias

- enviar pull requests

### 🧑‍💻 Autor

<a href="https://www.linkedin.com/in/dh-goncalves/">Diego Henrique</a>
Instrutor e desenvolvedor em constante evolução 👨‍🏫⚙️
