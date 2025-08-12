# OdontoVida - Sistema de Atendimento Automatizado para Clínica Odontológica

## 1. Descrição do Projeto

Sistema de IA para atendimento automatizado de pacientes em uma clínica odontológica.  
O sistema responde dúvidas frequentes relacionadas a:

- Agendamentos  
- Serviços oferecidos  
- Convênios e formas de pagamento  
- Cuidados pós-procedimento  
- Informações gerais e contato  

---

## 2. Histórico de Prompts e Respostas

| Prompt | Resposta 1 | Resposta 2 | Resposta 3 | Resposta 4 | Resposta 5 |
|--------|------------|------------|------------|------------|------------|
| Explique claramente como o paciente pode agendar uma consulta (telefone, WhatsApp e site). | Você pode agendar por telefone (11) 1234-5678, WhatsApp (11) 91234-5678 ou site www.clinicaodonto.com/agendamento. | Ligue para (11) 1234-5678, envie mensagem para (11) 91234-5678 ou acesse www.clinicaodonto.com/agendamento. | Entre em contato via telefone, WhatsApp ou agende pelo site da clínica. | O agendamento pode ser feito pelo site www.clinicaodonto.com/agendamento, ou pelos telefones (11) 1234-5678 e (11) 91234-5678. | Atendemos agendamentos pelo nosso site, telefone fixo e WhatsApp comercial. |
| ... | ... | ... | ... | ... | ... |

---

## 3. Refinamento Interativo de Prompts

### 3.1 Agendamento de Consulta

**Prompt Original:**  
Explique claramente como o paciente pode agendar uma consulta (telefone, WhatsApp e site).

**Resposta Antiga:**  
Você pode agendar sua consulta pelo telefone (11) 1234-5678, pelo WhatsApp (11) 91234-5678 ou pelo nosso site www.clinicaodonto.com/agendamento.

**Prompt Refinado:**  
Você é assistente de uma clínica odontológica. Explique de forma clara e objetiva para o paciente como ele pode agendar uma consulta, indicando os canais disponíveis: telefone, WhatsApp e site. Use exemplos de números e endereço do site para facilitar a compreensão, e escreva em formato de lista com até 3 itens.

**Resposta Refinada:**  
Para agendar sua consulta, você pode:  
1. Ligar para (11) 1234-5678.  
2. Enviar uma mensagem pelo WhatsApp no número (11) 91234-5678.  
3. Acessar nosso site www.clinicaodonto.com/agendamento e reservar seu horário online.

**Justificativa do Refinamento:**  
Adicionar contexto e instruções específicas (formato de lista, exemplos claros) melhora a clareza e organização da resposta, facilitando a compreensão do paciente.

---

*(continua para os demais prompts)*

---

## 4. Perfis de Usuário

### 4.1 Usuário Iniciante

- Linguagem acessível  
- Evita jargões técnicos  
- Gosta de exemplos e instruções práticas  

**Exemplo de prompt:**  
"Como posso agendar uma consulta médica? Nunca fiz isso antes. Preciso de uma explicação fácil sobre como usar telefone, WhatsApp ou site."

**Resposta exemplo:**  
"Para agendar, você pode:  
1) Ligar para a clínica  
2) Usar o WhatsApp mandando 'Quero marcar consulta'  
3) Acessar o site e clicar em 'Agendar'."

### 4.2 Usuário Avançado

- Linguagem técnica  
- Prefere respostas objetivas e aprofundadas  
- Busca referências e automações  

**Exemplo de prompt:**  
"Quais APIs posso usar para automatizar o cancelamento de consultas médicas?"

**Resposta exemplo:**  
"Use Twilio, WhatsApp Business API ou Google Calendar API combinados com backend em Firebase ou Node.js para automação."

---

## 5. Exemplo de Código Python para Geração de Texto (Hugging Face Transformers)

```python
# -*- coding: utf-8 -*-
"""
Exemplo de uso do modelo de linguagem para geração de texto com Hugging Face Transformers
"""

!pip install transformers

from transformers import pipeline

def main():
    gerador = pipeline("text2text-generation", model="google/flan-t5-base")

    texto_resumo = """
    A inteligência artificial está transformando diversos setores, desde a saúde até o setor financeiro.
    ...
    """
    prompt1 = f"Resuma o seguinte texto: {texto_resumo}"
    prompt2 = "Recomende um filme para quem gosta de suspense psicológico com reviravoltas."
    prompt3 = "Crie um post de Instagram para divulgar uma nova academia no bairro..."

    resposta1 = gerador(prompt1, max_length=100)[0]['generated_text']
    resposta2 = gerador(prompt2, max_length=100)[0]['generated_text']
    resposta3 = gerador(prompt3, max_length=100)[0]['generated_text']

    print("Resumo:", resposta1)
    print("Recomendação:", resposta2)
    print("Peça de marketing:", resposta3)

if __name__ == "__main__":
    main()
