# 🧩 Modos do Copiloto (Ask, Edit, Plan, Agent e Study)
Créditos especiais ao Felipão da DIO (https://github.com/digitalinnovationone/my-first-copilot/commits?author=felipeAguiarCode).

![dio/me](https://img.shields.io/badge/dio-me-ff2d55)
![IA](https://img.shields.io/badge/IA-Assistente%20Inteligente-blue)
![Prompt](https://img.shields.io/badge/Prompt-engineering-yellow)

O Copiloto oferece diferentes modos de interação, cada um otimizado para um tipo específico de tarefa: análise, edição, planejamento, execução autônoma ou aprendizado.

Cada modo possui:
- um papel definido
- um nível de autonomia
- regras de comportamento
- formas diferentes de interagir com o código e com o usuário

A escolha do modo impacta diretamente:
- a profundidade da análise
- o grau de modificação no projeto
- a velocidade de execução
- o controle do usuário sobre as decisões

O objetivo é equilibrar produtividade, previsibilidade e clareza durante o desenvolvimento.

---

# 🧠 Como escolher o modo ideal

| Situação | Modo recomendado |
|---|---|
| Quero entender um erro ou conceito | ❓ Ask |
| Quero modificar um trecho específico | ✏️ Edit |
| Quero validar uma abordagem antes de implementar | 🧭 Plan |
| Quero delegar uma tarefa ampla | 🤖 Agent |
| Quero aprender enquanto resolvo o problema | 📚 Study |

---

# 📊 Comparação rápida entre os modos

| Modo | Modifica código | Explica | Planeja | Executa múltiplas etapas | Ensina |
|---|---|---|---|---|---|
| Ask | ❌ | ✅ | ⚠️ Parcial | ❌ | ⚠️ Básico |
| Edit | ✅ | ⚠️ Parcial | ❌ | ❌ | ❌ |
| Plan | ⚠️ Opcional | ✅ | ✅ | ⚠️ Parcial | ❌ |
| Agent | ✅ | ⚠️ Parcial | ✅ | ✅ | ❌ |
| Study | ⚠️ Opcional | ✅ | ✅ | ❌ | ✅ |

---

# ❓ Ask

## Objetivo
Responder dúvidas, analisar comportamentos e explicar conceitos sem modificar o projeto.

## Quando usar
- entender erros
- analisar stack traces
- compreender funções ou arquivos
- tirar dúvidas técnicas
- investigar comportamento de código

## Capacidades
- interpretar contexto do projeto
- explicar código existente
- responder perguntas técnicas
- sugerir possíveis causas de problemas

## Limitações
- não altera arquivos
- não executa ações
- não cria mudanças automaticamente

## Nível de autonomia
🔹 Muito baixo

## Tipo de interação
Analista técnico e mentor contextual.

## Exemplos de uso

```text
"Por que esta função está causando memory leak?"
```

```text
"Explique esta stack trace."
```

📄 **Prompt:** [prompts/prompt-ask.md](prompts/prompt-ask.md)

---

# ✏️ Edit

## Objetivo
Modificar código existente de forma direta e controlada.

## Quando usar
- refactors
- ajustes de lógica
- melhoria de performance
- mudança de estilo
- conversão de linguagem
- tratamento de erros
- adicionar logs

## Capacidades
- editar arquivos
- reescrever trechos
- aplicar melhorias pontuais
- adaptar código existente

## Limitações
- depende de instruções claras
- normalmente atua em escopo definido
- não deve tomar decisões arquiteturais amplas sozinho

## Nível de autonomia
🔹 Médio

## Tipo de interação
Editor técnico orientado a tarefas.

## Exemplos de uso

```text
"Refatore este método para usar async/await."
```

```text
"Adicione tratamento de exceções neste serviço."
```

📄 **Prompt:** [prompts/prompt-edit.md](prompts/prompt-edit.md)

---

# 🧭 Plan

## Objetivo
Planejar mudanças maiores antes da implementação.

## Quando usar
- criação de novas features
- mudanças estruturais
- validação de arquitetura
- migração de tecnologias
- tarefas complexas

## Capacidades
- dividir problemas em etapas
- avaliar impactos
- propor abordagens
- estruturar plano de execução

## Limitações
- não deve executar alterações automaticamente sem validação
- depende da qualidade do contexto fornecido

## Nível de autonomia
🔹 Médio-alto

## Tipo de interação
Arquiteto e estrategista técnico.

## Exemplos de uso

```text
"Planeje a migração de REST para GraphQL."
```

```text
"Defina os passos para implementar autenticação JWT."
```

📄 **Prompt:** [prompts/prompt-plan.md](prompts/prompt-plan.md)

---

# 🤖 Agent

## Objetivo
Executar tarefas amplas de forma mais autônoma e orientada a objetivos.

## Quando usar
- implementação de features completas
- alterações em múltiplos arquivos
- automação de tarefas complexas
- coordenação de mudanças encadeadas

## Capacidades
- navegar pelo projeto
- criar arquivos
- modificar múltiplos pontos
- manter contexto entre etapas
- adaptar decisões conforme o cenário

## Limitações
- pode gerar alterações extensas
- requer validação humana em tarefas críticas
- depende do contexto disponível

## Nível de autonomia
🔹 Alto

## Tipo de interação
Executor autônomo orientado a objetivos.

## Exemplos de uso

```text
"Implemente autenticação JWT completa."
```

```text
"Crie um sistema CRUD com validação e persistência."
```

📄 **Prompt:** [prompts/prompt-agent.md](prompts/prompt-agent.md)

---

# 📚 Study

## Objetivo
Promover aprendizado ativo durante a resolução de problemas.

## Quando usar
- estudar programação
- aprender novos conceitos
- praticar lógica
- desenvolver raciocínio técnico
- revisar fundamentos

## Capacidades
- ensinar passo a passo
- explicar trade-offs
- propor exercícios
- adaptar dificuldade gradualmente
- estimular pensamento crítico

## Limitações
- foco principal não é velocidade
- pode priorizar aprendizado em vez da solução final

## Nível de autonomia
🔹 Baixo

## Tipo de interação
Tutor técnico e guia educacional.

## Exemplos de uso

```text
"Me ensine closures em JavaScript com exercícios progressivos."
```

```text
"Explique orientação a objetos com exemplos práticos."
```

📄 **Prompt:** [prompts/prompt-study.md](prompts/prompt-study.md)

---

# 🔄 Fluxo recomendado de uso

Um fluxo comum de trabalho pode combinar diferentes modos:

```text
1. Ask   → entender o problema
2. Plan  → definir abordagem
3. Edit  → aplicar mudanças específicas
4. Agent → executar tarefas maiores
5. Study → consolidar aprendizado
```

---

# 🧠 Conceitos utilizados no projeto

Os modos do Copiloto podem operar com diferentes níveis de:

- leitura de contexto
- capacidade de ação
- autonomia decisória
- persistência de memória
- escopo operacional
- controle do usuário
- validação humana
- execução multi-etapas

Cada modo representa uma persona operacional especializada em um tipo de interação.

---

# 📁 Estrutura do projeto

```text
README.md

/prompts
  prompt-ask.md
  prompt-edit.md
  prompt-plan.md
  prompt-agent.md
  prompt-study.md
```

---

# 🧠 Resumo mental rápido

- ❓ Ask → entender algo
- ✏️ Edit → modificar código existente
- 🧭 Plan → validar abordagem antes de implementar
- 🤖 Agent → executar tarefas amplas com autonomia
- 📚 Study → aprender com acompanhamento guiado

---

# 🚀 Objetivo do projeto

Este projeto tem como objetivo demonstrar como diferentes modos de interação podem transformar um copiloto em um sistema mais:
- previsível
- modular
- contextual
- especializado
- útil para diferentes cenários de desenvolvimento

A proposta é explorar engenharia de prompts, definição de personas operacionais e níveis de autonomia aplicados a assistentes inteligentes voltados para programação.
