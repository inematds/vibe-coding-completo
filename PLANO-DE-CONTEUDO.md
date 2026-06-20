# Plano de Conteúdo — **Vibe Coding: Domínio Completo**

> **De zero a agentes de IA em produção — fundamentos, técnica e prática.**
> Curso original INEMA.CLUB, formato **v2** (dark premium + camada de aprendizagem). Conteúdo técnico próprio; **nenhuma** fonte, comunidade, plataforma ou autor original é citado. Baseado no acervo já processado (48 aulas → `concept-map.md`), porém **reorganizado por ABORDAGEM** (não por fase): o aluno escolhe entrar pela teoria, pela técnica, pelos prompts, pelos agentes ou pelos projetos.

- **courseId:** `vibe-coding-completo`
- **Diferença para o curso anterior (`vibe-coding`):** aquele seguia as 4 fases na ordem original. Este é **muito mais completo e didático**: tem trilha de **glossário**, trilha **técnica** de aprofundamento, **biblioteca de prompts** copy-run, trilha dedicada a **skills & agentes**, e trilha de **projetos end-to-end**. Aplica as regras didáticas novas do formato (visual-first ilimitado #29, exemplos copy-run #30, fundamento define termos inline #31).
- **Público:** de iniciante total (entra por T1) a quem já constrói e quer dominar técnica/agentes (entra por T2/T4).
- **Promessa:** entender os conceitos, dominar a técnica, ter uma biblioteca de prompts/skills pronta, e construir agentes e apps reais que rodam em produção.

---

## Visão geral — 6 trilhas, 21 módulos, ~150 tópicos

| Trilha | Cor | Foco | Módulos | Tópicos |
|--------|-----|------|---------|---------|
| **T1 — Fundamentos & Glossário** | Emerald 🟢 | Mentalidade, como o ecossistema se encaixa, glossário A–Z que define cada termo | 4 | 26 |
| **T2 — Técnica: Arquitetura & Engenharia** | Blue 🔵 | Como tudo funciona por dentro + disciplina de engenharia | 5 | 32 |
| **T3 — Prompts & Padrões de Conversa** | Purple 🟣 | A arte do prompt + **biblioteca de prompts prontos (copy-run)** | 3 | 22 |
| **T4 — Skills & Agentes** | Amber 🟡 | Empacotar workflows em skills e construir agentes (locais, agendados, por evento) | 3 | 22 |
| **T5 — Projetos Práticos (End-to-End)** | Teal 🟦 | Os builds completos, passo a passo, com os prompts reais | 3 | 24 |
| **T6 — Produção, Deploy & Segurança** | Rose 🌹 | Hospedar, dar confiabilidade, proteger e monetizar | 3 | 22 |

**Arco:** Entender (T1) → Dominar a técnica (T2) → Conversar bem (T3) → Reutilizar via skills/agentes (T4) → Construir de ponta a ponta (T5) → Colocar em produção com segurança (T6). As trilhas são **independentes mas referenciadas** entre si (links cruzados), então cada uma é uma porta de entrada.

> **Didática aplicada em todo módulo:** cada conceito-chave ganha apoio visual (SVG inline / imagem / animação) com legenda que ensina (#29); todo módulo prático traz ≥1 exemplo **copy-run** real (prompt/comando/código + objetivo + como verificar) (#30); em módulos de fundamento, **todo termo é definido inline na 1ª aparição** estilo "Novo aqui?" (#31).

---

## Trilha 1 — Fundamentos & Glossário 🟢 *(Emerald)*

> Objetivo: dar a base conceitual e a linguagem. Sai daqui entendendo o que é cada coisa e como se encaixam — sem jargão órfão.

### Módulo 1.1 — A Mentalidade do Vibe Coding *(7 tópicos)*
1. O que é vibe coding — construir descrevendo o **resultado** em linguagem natural.
2. Descrever o resultado, não os passos (e por que isso muda tudo).
3. Determinístico vs não-determinístico — por que a mesma instrução gera saídas diferentes.
4. Trust but verify — a IA erra; *green ≠ correto*.
5. Iterar em camadas — uma mudança por vez, testar a cada passo.
6. A IA como ferramenta de aprendizado — perguntar "por quê" pra fixar.
7. Quem faz o quê — você é o gerente; a IA é o desenvolvedor.

### Módulo 1.2 — O Ecossistema: Como as Peças se Encaixam *(6 tópicos)*
1. O assistente de código (lê arquivos, escreve, roda comandos, conecta ferramentas).
2. n8n — o construtor visual de workflows (nós conectando apps e dados).
3. MCP — o protocolo que dá ferramentas externas ao agente.
4. Skills & workflows — instruções reutilizáveis em markdown.
5. Agentes — o que muda quando o sistema "decide" sozinho.
6. Local vs hospedado — rodar na sua máquina vs rodar sozinho na nuvem.

### Módulo 1.3 — Glossário Essencial (Parte 1: IA, Claude Code, n8n) *(7 tópicos)*
*Cada tópico = um cluster de termos definidos com exemplo concreto.*
1. **Conceitos de IA:** LLM, prompt, system prompt, contexto/context window, token, context rot.
2. **Modos do assistente:** plan mode, bypass permissions, permission modes, `/clear`, `/compact`.
3. **Arquivos-chave:** CLAUDE.md, `.env`, `.gitignore`, `.mcp.json`, SKILL.md.
4. **MCP:** MCP, MCP server, tool/ferramenta, descoberta de servers.
5. **n8n básico:** nó (node), trigger, workflow, credential, OAuth2.
6. **n8n IA:** AI agent node, text classifier, code node, IF node.
7. **Dados:** vector store, embeddings, document loader, text splitter.

### Módulo 1.4 — Glossário Essencial (Parte 2: Agêntico, RAG, Deploy, Segurança) *(6 tópicos)*
1. **Agêntico:** agente, agêntico, WAT (Workflows/Agent/Tools), loop de auto-melhoria, agentic gap.
2. **RAG:** RAG, knowledge base, retrieval, confidence score.
3. **Versionamento/cloud:** GitHub, repo, commit, push, gh CLI.
4. **Execução hospedada:** Trigger.dev, cron, webhook, payload, dev vs prod, trace, retry, alert.
5. **App/Frontend:** frontend, backend, request/response, Vercel, env var.
6. **Segurança & pagamento:** Supabase, RLS, migration, Stripe, checkout, price ID, webhook secret, freemium.

---

## Trilha 2 — Técnica: Arquitetura & Engenharia 🔵 *(Blue)*

> Objetivo: abrir o capô. Entender como cada peça funciona por dentro e adquirir a disciplina de engenharia que separa "funcionou uma vez" de "confiável".

### Módulo 2.1 — Engenharia de CLAUDE.md *(6 tópicos)*
1. O CLAUDE.md como system prompt persistente. 2. Anatomia (papel, contexto, regras, estilo, estrutura). 3. Regras operacionais (procurar tool existente, aprender ao falhar, manter atualizado). 4. Manter enxuto (< ~500 linhas) e por quê. 5. CLAUDE.md vs skills — o que vai onde. 6. Iterar o arquivo conversando.

### Módulo 2.2 — O Framework WAT a Fundo *(7 tópicos)*
1. Visão geral WAT. 2. **W** = Workflows (instruções markdown = SOP). 3. **A** = Agent (o coordenador que decide). 4. **T** = Tools (scripts Python de um trabalho cada). 5. O loop de auto-melhoria (errar → diagnosticar → consertar tool → atualizar workflow). 6. Estrutura de pastas (workflows/tools/temporary/.env). 7. Quando NÃO usar WAT (tarefa de uma frase).

### Módulo 2.3 — MCP por Dentro *(7 tópicos)*
1. O que o protocolo resolve. 2. Como o agente descobre/decide ferramentas. 3. `.mcp.json` e a chave manual (nunca no chat). 4. Project-level vs global. 5. Onde achar servers (diretórios, GitHub). 6. Verificar/diagnosticar (`/mcp`, reiniciar). 7. Custo de contexto — desligar servers não usados.

### Módulo 2.4 — Contexto & Tokens (não deixe o agente "apodrecer") *(6 tópicos)*
1. Context rot — degradação após ~60%. 2. Os limiares (0-50 / 50-70 / 70-85 / 85%+). 3. `/clear` vs `/compact`. 4. Uma tarefa por sessão. 5. Definir "pronto" (evita loop). 6. Economia: skills, desligar MCP, CLAUDE.md enxuto.

### Módulo 2.5 — RAG & Dados *(6 tópicos)*
1. O problema: a IA não sabe o que não está no contexto. 2. System prompt vs vector store (quando cada um). 3. Embeddings & vector store em linguagem simples. 4. Indexador (manual trigger → docs → vector store). 5. Classifier — rotear antes de gastar o agente. 6. Confidence score & fallback (não inventar).

---

## Trilha 3 — Prompts & Padrões de Conversa 🟣 *(Purple)*

> Objetivo: a craft do prompt + uma **biblioteca de prompts prontos** que o aluno copia e roda. Esta trilha é fortemente copy-run (#30).

### Módulo 3.1 — Os Padrões de Prompting *(7 tópicos)*
1. Definir o objetivo, não os passos. 2. Ser específico sobre a saída (formato, nome, local). 3. Plan Mode primeiro, executar depois. 4. Feedback, não correção ("gostei de X, mude Y"). 5. Tratar o agente como especialista. 6. Os erros que mais custam token. 7. Checklist das 12 dicas.

### Módulo 3.2 — O Ciclo Plan → Build → Troubleshoot → Optimize *(7 tópicos)*
1. Plan Mode (pesquisa + perguntas + plano). 2. Build (criar e validar). 3. O que a IA NÃO faz (credenciais, mapeamento). 4. Troubleshoot (devolver o erro com contexto). 5. Optimize (melhorar em linguagem natural). 6. Verificação & testes de verdade. 7. Backup antes de mudar (export JSON).

### Módulo 3.3 — Biblioteca de Prompts Prontos (copy-run) *(8 tópicos)*
*Cada tópico = um prompt real, completo, com partes variáveis `<assim>`, objetivo e como verificar.*
1. Setup & CLAUDE.md (criar o projeto e o system prompt). 2. Conectar uma ferramenta via MCP. 3. Criar um workflow do zero. 4. Debugar um erro (template de troubleshooting). 5. Os 6 enhancements (fallback, filtro de tempo, filtro de automáticos, tom, nome, confiança). 6. Criar uma skill / slash command. 7. Criar um agente agendado (cron → pesquisa → planilha). 8. Criar um frontend + auditoria de segurança.

---

## Trilha 4 — Skills & Agentes 🟡 *(Amber)*

> Objetivo: parar de reexplicar — empacotar workflows em **skills** reutilizáveis e construir **agentes** (locais, agendados, por evento). Copy-run pesado.

### Módulo 4.1 — Skills: Conceito & Anatomia *(7 tópicos)*
1. O que é uma skill (= workflow em markdown, chamável). 2. Onde vivem (`.claude/skills`) e como viram slash command. 3. Anatomia do SKILL.md (nome, descrição, argumentos, passos). 4. Skills podem chamar tools. 5. Quando usar skill vs digitar. 6. Skills vs CLAUDE.md (contexto sob demanda). 7. Compartilhar e versionar skills.

### Módulo 4.2 — Construindo Skills na Prática *(7 tópicos)*
1. Pedir uma skill no formato oficial. 2. Skill "rascunhar e-mail" (`/draft-email`) — build + teste. 3. Invocar sem argumentos (a skill pergunta). 4. Reutilizar com contexto limpo. 5. Skill "documento → slides". 6. Plugar uma skill de design pronta. 7. Biblioteca de skills do aluno (ideias prontas).

### Módulo 4.3 — Agentes: Locais, Agendados & por Evento *(8 tópicos)*
1. O que é um agente (raciocina, adapta, se auto-cura). 2. Agente sob demanda (local). 3. O loop de auto-melhoria na prática. 4. Agente agendado (cron) — anatomia. 5. Agente por evento (webhook) — anatomia. 6. O agentic gap (sem auto-cura em produção). 7. Inputs fixos, saída estruturada, erro & log desde o 1º prompt. 8. Quando um "agente" é só um script (e tudo bem).

---

## Trilha 5 — Projetos Práticos (End-to-End) 🟦 *(Teal)*

> Objetivo: construir de ponta a ponta, com os prompts reais e a verificação. Cada módulo é um projeto completo.

### Módulo 5.1 — Projeto: Agente de Suporte por E-mail com RAG *(8 tópicos)*
1. O escopo (ler políticas em PDF → classificar → rascunhar resposta). 2. Arquitetura (indexador + agente). 3. O prompt de abertura abrangente. 4. Build dos dois workflows. 5. Credenciais (Gmail OAuth, OpenAI). 6. Testes (devolução, garantia, fora de escopo = não inventar). 7. Os 6 enhancements aplicados. 8. Verificação final & checklist.

### Módulo 5.2 — Projeto: Agentes Hospedados (Agendado + Webhook) *(8 tópicos)*
1. Agente de pesquisa agendado (cron → Firecrawl → síntese → Sheets). 2. OAuth refresh token (e o fallback via terminal). 3. Debug que só aparece em produção. 4. Relatório por webhook (payload → `.docx` → Drive). 5. Webhook como "campainha digital" + auth Bearer. 6. Form no-code → webhook. 7. Pipeline GitHub → deploy automático. 8. Verificar runs, traces e o schedule.

### Módulo 5.3 — Projeto: App Full-Stack (Lead Qualifier) + Frontend pra n8n *(8 tópicos)*
1. Arquitetura (backend Trigger.dev + frontend Vercel). 2. Build do lead qualifier (do prompt ao app). 3. Conectar frontend ↔ backend (env vars). 4. Autenticação com Supabase + RLS. 5. Auditoria de segurança. 6. Pagamentos com Stripe (freemium). 7. Frontend pra um workflow n8n (form → webhook). 8. Iteração incremental (design → auth → pagamento).

---

## Trilha 6 — Produção, Deploy & Segurança 🌹 *(Rose)*

> Objetivo: a engenharia de produção — hospedar, dar confiabilidade, proteger segredos/dados e monetizar.

### Módulo 6.1 — GitHub & Trigger.dev *(7 tópicos)*
1. GitHub como armazenamento de código (commit/push/repo/histórico). 2. gh CLI & `.gitignore` (o `.env` nunca sobe). 3. Trigger.dev (sem timeout, retries, traces, alertas). 4. Inicializar projeto + MCP do Trigger.dev. 5. Cron (5 campos). 6. Anatomia do dashboard (runs, traces, schedules, dev vs prod). 7. Deploy a partir do 1º prompt.

### Módulo 6.2 — Secrets & Segurança *(8 tópicos)*
1. Variáveis de ambiente (segredo fora do código, injetado em runtime). 2. Local (`.env`) vs nuvem (dashboard). 3. `.env.example` e ler de `process.env`. 4. OAuth & refresh token. 5. Regras de ouro (nunca no chat, nunca commitar, rotacionar). 6. RLS — isolar dados no próprio banco. 7. Auditoria de segurança (rotas, chaves, env, RLS). 8. App aberto = risco (alguém gasta seus tokens).

### Módulo 6.3 — Confiabilidade & Monetização *(7 tópicos)*
1. O agentic gap revisitado. 2. Logging significativo em cada passo. 3. try/catch nas chamadas externas. 4. Retries com backoff (vs bugs de lógica). 5. Alertas (e-mail/Slack/webhook). 6. O loop humano de debug (trace → IA → fix → redeploy). 7. Monetização com Stripe (produto, webhook, assinaturas, freemium).

---

## Recursos transversais (entram nas páginas)

- **Glossário vivo:** T1 define ~55 termos; demais trilhas usam tip box "O que é X?" na 1ª aparição (#31).
- **Biblioteca de prompts copy-run:** concentrada em T3.3, espalhada em todos os módulos práticos (T4, T5, T6) — todo prompt real, completo, com `<variáveis>` e "como verificar" (#30).
- **Skills & agentes catalogados:** `/draft-email`, `documento→slides`, skill de design; agentes de suporte, pesquisa, relatório, lead qualifier.
- **Apoio visual por conceito (#29):** SVG futurista inline em cada conceito-chave + heros; opção de PNG (inemaimg) e animações onde o movimento ensina.

---

## Estrutura de arquivos

```
vibe-coding-completo/
├── PLANO-DE-CONTEUDO.md
├── index.html                         # Landing (jornada + aparência + continuar)
├── assets/  learn.css · learn.js      # camada de aprendizagem (reaproveitada do curso anterior)
└── curso/
    ├── trilha1/ index + modulo-1-1..1-4   (Fundamentos & Glossário)
    ├── trilha2/ index + modulo-2-1..2-5   (Técnica)
    ├── trilha3/ index + modulo-3-1..3-3   (Prompts)
    ├── trilha4/ index + modulo-4-1..4-3   (Skills & Agentes)
    ├── trilha5/ index + modulo-5-1..5-3   (Projetos)
    └── trilha6/ index + modulo-6-1..6-3   (Produção)
```

**Total a construir:** 1 landing + 6 índices de trilha + 21 módulos = **28 páginas HTML** (+ assets já prontos). Cada módulo: nav completo (6 trilhas), ≥1 SVG por conceito-chave, ≥6 tópicos (3 seções cada), manifesto idêntico, camada de aprendizagem, e — nos práticos — exemplos copy-run.
