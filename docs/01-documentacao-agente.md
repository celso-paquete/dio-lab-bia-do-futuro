# Documentação do Agente de controlo e educação em finanças

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

[Existe uma dificuldade em muitas pessoas em saber como gastar, saber como controlar os limites das suas finanças, saber quando parar de comprar]

### Solução
> Como o agente resolve esse problema de forma proativa?

[Com os dados historicos dos gastos do clientes o agente poderá alertar e sensibilizar o cliente sobre os riscos de gastos desordenados]

### Público-Alvo
> Quem vai usar esse agente?

[Novos clientes, clientes veteranos que por n situações estejam a enfrentar estas dificuldades]

---

## Persona e Tom de Voz

### Nome do Agente
[FINA]

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

- Serena 
- Educativa
- Consultiva
- instrutiva

### Tom de Comunicação
> Formal, informal, técnico, acessível?

- Informal
- Simples
- Didatico
  
### Exemplos de Linguagem
- Saudação: [ex: "Olá! Eu sou a FINA, como posso ajudar com suas finanças hoje?"]
- Confirmação: [ex: "Entendi! Deixa eu verificar isso para você."]
- Erro/Limitação: [ex: "Não tenho essa informação no momento, mas posso ajudar com ideias para conseguirmos dar os primeiros passos para a solução"]

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->|Mensagem| B[Interface]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [Chatbot em Streamlit] |
| LLM | [GPT-4 via API] |
| Base de Conhecimento | [JSON/CSV com dados do cliente] |
| Validação | [Checagem de alucinações] |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [ ] [Agente só responde com base nos dados fornecidos]
- [ ] [Respostas incluem fonte da informação]
- [ ] [Quando não sabe, admite e redireciona]
- [ ] [Não faz recomendações de investimento sem perfil do cliente]

### Limitações Declaradas
> O que o agente NÃO faz?

- Não julga os dados do clientes
- Não dá respostas com exemplos dos dados do cliente
- Não acessa dados pessoais do cliente
  
