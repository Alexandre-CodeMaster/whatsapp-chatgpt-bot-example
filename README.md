# whatsapp-chatgpt-bot-example
Exemplo de automação de respostas no WhatsApp usando Python + OpenAI API.

```markdown
# 🤖 WhatsApp + ChatGPT Bot 
*Automação Inteligente de Atendimento*

```bash
# Menu Rápido
1. Sobre o Projeto
2. Configuração Inicial
3. Exemplos de Uso
4. Solução de Problemas
5. Estrutura do Projeto
```

---

## 🌟 Sobre o Projeto
**Criador**: [Alexandre-CodeMaster](https://github.com/Alexandre-CodeMaster)  
**Desenvolvimento**:  
- Ideia original e implementação por Alexandre  
- Uso de GPT-3.5 Turbo (OpenAI) como assistente de código  
- Integração com Twilio API  

*(Projeto desenvolvido com apoio de IA generativa como ferramenta complementar)*

---

## 🛠️ Configuração Inicial
**Pré-requisitos**:
- Python 3.10+
- Conta no [Twilio](https://www.twilio.com/)
- Chave da [OpenAI](https://platform.openai.com/)

```bash
# Clone o projeto
git clone https://github.com/Alexandre-CodeMaster/whatsapp-bot.git
cd whatsapp-bot

# Instale dependências
pip install -r requirements.txt
```

---

## 💡 Exemplos de Uso
### 1. Resposta Automática Básica
```python
# Trecho do bot.py
@app.route('/webhook', methods=['POST'])
def whatsapp_bot():
    user_msg = request.values.get('Body', '')
    resposta = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[{"role": "user", "content": user_msg}]
    )
    return resposta.choices[0].message['content']
```

### 2. Fluxo Completo
```bash
# Terminal 1 (Backend)
python bot.py

# Terminal 2 (Teste)
curl -X POST http://localhost:5000/webhook -d "Body=Olá"
```

---

## ⚠️ Solução de Problemas
**Erro Comum** | **Solução**
--- | ---
`ModuleNotFoundError` | `pip install --upgrade -r requirements.txt`
Twilio não responde | Verifique webhooks no [Console Twilio](https://www.twilio.com/console)

---

## 📂 Estrutura do Projeto
```
whatsapp-bot/
├── bot.py               # Código principal
├── requirements.txt     # Dependências
├── .env.example         # Modelo de configuração
└── README.md            # Este arquivo
```

---

## 📜 Licença
MIT License © 2025 - Alexandre (@Alexandre-CodeMaster)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
```
