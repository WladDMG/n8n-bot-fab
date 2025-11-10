## Descrição do Projeto

Este repositório armazena o **workflow principal do bot da Fábrica de Apps**, desenvolvido no **n8n**, que integra:

- **WhatsApp (Evolution API)**
- **OpenAI (GPT / Whisper)**
- **Google Calendar**
- **Gmail**
- **Redis Chat Memory** (para manter o contexto da conversa)

O fluxo é responsável por automatizar:
- Conversas inteligentes com clientes;
- Transcrição de áudios;
- Criação e cancelamento de eventos no Google Calendar;
- Envio de e-mails de confirmação;
- Retorno automático via WhatsApp.

---

## Exportar workflows do n8n

Para exportar todos os seus workflows em formato JSON e salvar na pasta `workflows/`:

```bash
n8n export:workflow --output=./workflows/
```
Para exportar apenas um workflow específico:

```bash
n8n export:workflow --id=<ID_DO_WORKFLOW> --output=./workflows/
```
📥 Importar workflows no n8n
Para importar um workflow salvo no repositório:

```bash
n8n import:workflow --input=./workflows/bot-fab.json
```

## Boas Práticas

Nunca suba credenciais reais (API keys, tokens, senhas)

Use placeholders nas credenciais exportadas ("API_KEY": "{{SUA_CHAVE_AQUI}}")

Descreva brevemente cada fluxo no README.md ou em comentários dentro do JSON

Versione com frequência para manter histórico de alterações no GitHub

## Exemplo de fluxo automatizado
Workflow bot-fab.json

## Estrutura do workflow

| Componente | Função |
|-------------|--------|
| **Webhook** | Recebe mensagens do Evolution API |
| **Switch** | Identifica se a mensagem é texto ou áudio |
| **Obter mídia em base64** | Baixa e converte áudios recebidos |
| **Transcribe a recording** | Converte o áudio em texto (OpenAI) |
| **AI Agent** | Interpreta, conversa e decide ações |
| **Google Calendar Tool** | Cria eventos quando há agendamento confirmado |
| **Gmail Tool** | Envia e-mails para cliente e equipe |
| **Redis Chat Memory** | Mantém contexto da conversa |
| **Evolution API (send)** | Retorna a resposta ao cliente no WhatsApp |

---
## Segurança
O diretório credentials/ existe apenas para referência.
Nunca armazene arquivos reais com dados sensíveis aqui.
Se precisar guardar modelos de credenciais, use nomes fictícios, por exemplo:


```json
{
  "name": "Google Calendar (modelo)",
  "data": {
    "clientId": "SEU_CLIENT_ID_AQUI",
    "clientSecret": "SEU_CLIENT_SECRET_AQUI"
  }
}
```
## Autor
Wladmir Silveira

Fábrica de Apps

https://fabricadeapps.dev

## Licença
Este projeto é distribuído sob a licença MIT — livre para uso, modificação e redistribuição.
