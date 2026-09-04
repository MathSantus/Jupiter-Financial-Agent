<p align="center">
  <img src="assets/jupiter-logo.png" alt="Logo Júpiter" width="220">
</p>

<h1 align="center">Júpiter</h1>

<p align="center">
  <strong>Agente Educacional de Organização Financeira Pessoal</strong>
</p>

O **Júpiter** é um agente conversacional desenvolvido para ajudar usuários a organizar receitas e despesas, identificar possibilidades de economia voluntária e simular como aportes mensais podem evoluir ao longo de 12 meses.

O projeto utiliza um GPT personalizado, uma base de conhecimento própria e ferramentas de análise de dados para realizar cálculos financeiros de forma estruturada.

> **Aviso:** O Júpiter possui finalidade educacional. Não realiza recomendações personalizadas de investimentos, não executa transações financeiras e não promete rentabilidade.

---

## Problema

Muitas pessoas conhecem sua renda mensal, mas não possuem uma visão clara sobre:

- quanto realmente gastam;
- quais despesas podem ser ajustadas;
- quanto conseguem guardar;
- para onde vai a sobra mensal;
- como pequenas economias podem se transformar em aportes recorrentes.

O Júpiter foi desenvolvido para transformar essas informações dispersas em uma análise financeira conversacional e estruturada.

---

## Objetivo

O objetivo do projeto é permitir que o usuário compreenda sua situação financeira atual antes de realizar uma simulação de crescimento patrimonial.

O agente busca conduzir o usuário desde a organização do orçamento até a visualização do possível impacto de aportes mensais ao longo de 12 meses.

---

## Como funciona

O fluxo principal do Júpiter segue esta lógica:

```text
Usuário
   ↓
Agente Júpiter
   ↓
Coleta e validação dos dados
   ↓
Organização do orçamento
   ↓
Definição da meta e origem do aporte
   ↓
Simulação com Análise de Dados
   ↓
Resposta educativa estruturada
```

Durante a conversa, o agente diferencia conceitos como:

- despesas de consumo;
- aporte atual;
- margem potencial;
- economia efetivamente aprovada;
- capital inicial;
- total aportado;
- rendimento estimado;
- saldo final.

---

## Principais funcionalidades

- Organização de receitas e despesas.
- Identificação de déficit ou margem potencial.
- Análise de categorias de gastos.
- Apoio à definição de metas financeiras mensais.
- Separação entre aporte atual e novo aporte.
- Controle de alterações realizadas durante a conversa.
- Tratamento de renda variável.
- Tratamento de despesas mensais, trimestrais e anuais.
- Identificação do encerramento de parcelas.
- Simulação financeira de 12 meses.
- Cálculo de juros compostos.
- Comparação de cenários hipotéticos de rentabilidade.
- Proteção contra compartilhamento desnecessário de dados sensíveis.
- Controle de solicitações fora do escopo do projeto.

---

## Cenários de simulação

A base de conhecimento do Júpiter possui três cenários educacionais de referência:

| Cenário | Taxa anual hipotética |
|---|---:|
| Cauteloso | 6% a.a. |
| Intermediário | 10% a.a. |
| Elevado | 14% a.a. |

Essas taxas são utilizadas exclusivamente como hipóteses matemáticas.

Elas não representam previsão, recomendação ou garantia de retorno.

O usuário também pode informar uma taxa própria para realizar uma simulação educacional.

---

## Base de conhecimento

O Júpiter utiliza uma base própria composta por cinco arquivos:

```text
knowledge/
├── 01_metodologia_financeira.md
├── 02_regras_de_calculo.md
├── 03_cenarios_e_classes_de_investimento.md
├── 04_privacidade_e_dados_seguros.md
└── 05_casos_de_teste.md
```

A base contém:

- metodologia de organização financeira;
- regras utilizadas nos cálculos;
- cenários hipotéticos;
- conceitos gerais sobre classes de investimento;
- orientações de privacidade;
- casos utilizados durante os testes.

---

## System Prompt

O comportamento do agente é controlado por um conjunto próprio de instruções desenvolvido e refinado durante o projeto.

A versão documentada está disponível em:

[`prompt/Jupiter_Prompt_v1.2.md`](prompt/Jupiter_Prompt_v1.2.md)

O prompt define aspectos como:

- papel do agente;
- fluxo da conversa;
- regras de cálculo;
- controle de alterações;
- tratamento de dados sensíveis;
- limites de atuação;
- regras para simulações;
- comportamento diante de solicitações fora do escopo.

---

## Segurança e privacidade

O Júpiter foi desenvolvido para trabalhar com valores aproximados e informações financeiras agregadas.

O agente orienta o usuário a não fornecer informações como:

- CPF;
- senhas;
- número de conta;
- dados de cartão;
- documentos;
- chaves de acesso;
- códigos de autenticação.

O agente também não:

- monta carteiras personalizadas;
- seleciona ações, fundos ou criptomoedas específicos;
- define percentuais de alocação;
- promete rentabilidade;
- executa transações;
- incentiva empréstimos para investir;
- utiliza dinheiro emprestado como capital disponível para investimento.

---

## Processo de desenvolvimento

O desenvolvimento do Júpiter ocorreu de forma iterativa.

```text
Versão inicial
      ↓
Testes internos
      ↓
Identificação de falhas
      ↓
Correções no prompt
      ↓
Testes de estresse
      ↓
Validação com usuários externos
      ↓
Ajustes de escopo
      ↓
Testes de regressão
      ↓
Júpiter v1.2
```

O projeto não foi considerado concluído após a primeira versão funcional.

Os testes foram utilizados para identificar comportamentos inesperados e melhorar progressivamente as instruções do agente.

---

## Principais problemas identificados durante os testes

Entre os comportamentos encontrados durante o processo de validação estavam:

- dupla contabilização de reduções de despesas;
- dificuldade em diferenciar alterações já incorporadas ao orçamento;
- possibilidade de montagem indireta de carteira de investimentos;
- utilização inadequada de taxas extremamente elevadas como base de planejamento;
- tratamento excessivamente amplo de dinheiro obtido por empréstimo;
- necessidade de distinguir sobra matemática de dinheiro realmente disponível.

Esses resultados levaram a novas regras e testes de regressão.

---

## Testes

A pasta `tests/` contém evidências utilizadas durante a validação do projeto.

Atualmente estão disponíveis:

```text
tests/
├── Bateria de testes.pdf
├── ChatGPT - Júpiter (Usuário 1).pdf
├── ChatGPT - Júpiter (Usuário 2).pdf
├── ChatGPT - Júpiter (Usuário 3).pdf
└── Conversa 04 e observações.txt
```

Os testes avaliaram situações como:

1. organização de orçamento;
2. déficit financeiro;
3. renda variável;
4. despesas periódicas;
5. encerramento de parcelas;
6. margem potencial;
7. dupla contabilização;
8. dados sensíveis;
9. pedidos de carteira personalizada;
10. taxas de retorno extremas;
11. utilização de dinheiro emprestado.

Após as correções, uma bateria de regressão foi utilizada para verificar se os novos controles funcionavam sem comprometer comportamentos que já haviam sido validados.

---

## Estrutura do repositório

```text
Jupiter-Financial-Agent/
│
├── assets/
│   └── jupiter-logo.png
│
├── docs/
│   └── Jupiter_Documentacao_v1.2.pdf
│
├── knowledge/
│   ├── 01_metodologia_financeira.md
│   ├── 02_regras_de_calculo.md
│   ├── 03_cenarios_e_classes_de_investimento.md
│   ├── 04_privacidade_e_dados_seguros.md
│   └── 05_casos_de_teste.md
│
├── prompt/
│   └── Jupiter_Prompt_v1.2.md
│
├── tests/
│   ├── Bateria de testes.pdf
│   ├── ChatGPT - Júpiter (Usuário 1).pdf
│   ├── ChatGPT - Júpiter (Usuário 2).pdf
│   ├── ChatGPT - Júpiter (Usuário 3).pdf
│   └── Conversa 04 e observações.txt
│
└── README.md
```

---

## Documentação completa

A documentação completa apresenta em detalhes:

- problema;
- objetivo;
- público-alvo;
- proposta de valor;
- arquitetura;
- base de conhecimento;
- metodologia financeira;
- segurança e privacidade;
- estratégia de testes;
- evolução do agente;
- evidências;
- limitações;
- resultados da validação.

Acesse:

[**Documentação completa do Júpiter v1.2**](docs/Jupiter_Documentacao_v1.2.pdf)

---

## Acessar o Júpiter

**Versão:** 1.2

**Horizonte principal das simulações:** 12 meses

[**Acessar o Júpiter no ChatGPT**](https://chatgpt.com/g/g-6a67a2c95f2c8191a724ca549e2af460-jupiter)

---

## Limitações

O Júpiter depende das informações fornecidas pelo usuário e trabalha com projeções financeiras simplificadas.

As simulações podem não considerar automaticamente:

- impostos;
- inflação;
- taxas;
- mudanças futuras de renda;
- despesas inesperadas;
- meses sem aporte;
- oscilações reais do mercado.

As taxas utilizadas representam cenários hipotéticos e não garantias de rentabilidade.

O Júpiter não substitui profissionais habilitados em situações que exijam aconselhamento financeiro, tributário, jurídico ou contábil especializado.

---

## Versão atual

**Júpiter v1.2**

Versão considerada estável após:

- testes internos;
- testes de estresse;
- validação com usuários externos;
- correções de escopo;
- testes de regressão.

---

## Autor

**Matheus Rodrigues**

Projeto desenvolvido como aplicação prática de Inteligência Artificial Generativa, engenharia de prompts, construção de agentes e validação iterativa.
