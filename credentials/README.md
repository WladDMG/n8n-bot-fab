# Credenciais do Projeto – Bot Fábrica de Apps

Este diretório contém **modelos genéricos** de credenciais utilizadas pelo workflow principal  
`workflows/bot-fab.json` do projeto **n8n-bot-fab**.

**Atenção:** Nenhum arquivo aqui deve conter dados reais.  
Use apenas exemplos e placeholders — este repositório é público e serve para versionamento seguro.

---

## Estrutura de Credenciais

| Integração | Nome no n8n | Função |
|-------------|--------------|--------|
| **OpenAI** | `OpenAI API` | Gera respostas e interpreta mensagens (IA Agent / GPT) |
| **Google Calendar** | `Google Calendar API` | Cria, lista e cancela eventos automaticamente |
| **Gmail** | `Gmail API` | Envia notificações e confirmações por e-mail |
| **Redis** | `Redis Chat Memory` | Armazena o contexto das conversas (memória do agente) |
| **Evolution API** | `Evolution API (WhatsApp)` | Envia e recebe mensagens de clientes via WhatsApp |

---

## Modelos de Credenciais

### OpenAI
Usado para o agente de IA (ChatGPT ou GPT-4o-mini).

```json
{
  "name": "OpenAI (modelo)",
  "data": {
    "apiKey": "SUA_CHAVE_OPENAI_AQUI"
  }
}
```
## Google Calendar
Permite criar e remover eventos no calendário da equipe.

```json
{
  "name": "Google Calendar (modelo)",
  "data": {
    "clientId": "SEU_CLIENT_ID_AQUI",
    "clientSecret": "SEU_CLIENT_SECRET_AQUI",
    "accessToken": "SEU_ACCESS_TOKEN_AQUI",
    "refreshToken": "SEU_REFRESH_TOKEN_AQUI"
  }
}
```
## Gmail
Responsável pelo envio de e-mails automáticos de confirmação.

```json
{
  "name": "Gmail (modelo)",
  "data": {
    "clientId": "SEU_CLIENT_ID_AQUI",
    "clientSecret": "SEU_CLIENT_SECRET_AQUI",
    "accessToken": "SEU_ACCESS_TOKEN_AQUI",
    "refreshToken": "SEU_REFRESH_TOKEN_AQUI"
  }
}
```
## Redis
Usado como memória de chat para manter o contexto da conversa entre mensagens.

```json
{
  "name": "Redis (modelo)",
  "data": {
    "host": "SEU_HOST_AQUI",
    "port": "6379",
    "password": "SENHA_DO_REDIS_AQUI"
  }
}
```
## Evolution API (WhatsApp)
Integração com o servidor do WhatsApp via Evolution API.

```json
{
  "name": "Evolution API (modelo)",
  "data": {
    "baseUrl": "https://api.evolution.whatsapp.dev",
    "instanceId": "SEU_INSTANCE_ID_AQUI",
    "token": "SEU_TOKEN_AQUI"
  }
}
```
## Exportar credenciais de exemplo
Para exportar credenciais (de forma segura, sem dados reais):

```bash
n8n export:credentials --output=./credentials/
```
Em seguida, edite os arquivos e substitua valores sensíveis pelos placeholders mostrados acima.

## Boas Práticas
Nunca suba credenciais reais (.env, tokens, senhas, etc.)

Sempre use placeholders e revise antes do commit

Prefira variáveis de ambiente no n8n ({{ $env.NOME_VARIAVEL }})

Garanta que o .gitignore esteja bloqueando arquivos sensíveis

##  Referência
Essas credenciais são usadas pelo workflow:

```bash
workflows/bot-fab.json
```
| Serviço         | Tipo de uso          |
|-----------------|----------------------|
| **OpenAI**      | IA conversacional    |
| **Google Calendar** | Agendamento      |
| **Gmail**       | Notificações         |
| **Redis**       | Memória de conversa  |
| **Evolution API** | WhatsApp           |


## Autor
Wladmir Silveira

Fábrica de Apps

https://fabricadeapps.dev

