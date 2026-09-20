# 🛡️ Vigil Summit Agent — Agente Autônomo de Funil de Eventos B2B

Solução de IA que gerencia o **funil completo de um evento corporativo B2B** — da captação do lead à reunião comercial agendada — atacando os três gargalos clássicos desses eventos: **geração de leads qualificados**, **no-show** e **follow-up frio**.

> **Contexto:** Case AI Engineer — cliente fictício **Vigil.AI** (cibersegurança), evento **Vigil Summit — Segurança para a Era da IA**. Projeto de TCC do MBA em Inteligência Artificial.

---

## 🎯 O que o agente faz

| Fase | Descrição |
|------|-----------|
| **1. Captação** | Landing page + formulário → webhook → grava o lead |
| **2. Enriquecimento** | Lusha (empresa + contato) + Claude geram o perfil e o ângulo de personalização |
| **3. Engajamento pré-evento** | Régua proativa (E1–E5) por e-mail e WhatsApp para reduzir no-show |
| **4. Follow-up pós-evento** | Régua comercial (P1–P6) para agendar reunião via Cal.com |
| **Agente reativo** | Responde o lead no WhatsApp com memória de contexto |

---

## 🧱 Arquitetura

- **Orquestração:** n8n (4 workflows independentes que compartilham estado)
- **LLM:** Claude (Anthropic) via OpenRouter — `anthropic/claude-sonnet-4.6`
- **Enriquecimento:** Lusha (Enrich Company + Enrich Contact)
- **Dados / painel:** Google Sheets
- **Memória conversacional:** Redis (janela de contexto)
- **Canais:** Gmail API (e-mail) + WhatsApp Cloud API
- **Agendamento:** Cal.com
- **Captação:** Landing
