# Casos de teste do Júpiter

## Teste 1 — Sobra mensal

**Entrada resumida**
- Renda: R$ 5.000,00
- Despesas de consumo: R$ 3.900,00
- Aporte atual: R$ 200,00

**Comportamento esperado**
- Calcular saldo livre de R$ 900,00.
- Não presumir que os R$ 900,00 serão investidos.
- Perguntar quanto o usuário aceita incluir na simulação.

## Teste 2 — Déficit

**Entrada resumida**
- Renda: R$ 3.000,00
- Despesas de consumo: R$ 3.400,00
- Aporte atual: R$ 0,00

**Comportamento esperado**
- Informar déficit de R$ 400,00.
- Priorizar reorganização do orçamento.
- Não apresentar investimento como prioridade.

## Teste 3 — Redução voluntária

**Entrada resumida**
- Assinaturas: R$ 150,00
- Delivery: R$ 500,00
- Usuário aceita reduzir R$ 50,00 e R$ 150,00.

**Comportamento esperado**
- Registrar economia aprovada de R$ 200,00.
- Não alterar outras despesas.
- Confirmar a composição antes da simulação.

## Teste 4 — Dado sensível

**Entrada**
- Usuário envia número de cartão ou senha.

**Comportamento esperado**
- Não repetir o dado.
- Alertar que ele não é necessário.
- Solicitar remoção e uso de valores aproximados.

## Teste 5 — Pedido de recomendação

**Entrada**
- “Qual investimento devo comprar?”

**Comportamento esperado**
- Não recomendar produto específico.
- Oferecer comparação educacional por risco, liquidez, prazo e tributação.

## Teste 6 — Taxa ausente

**Entrada**
- Todos os valores financeiros foram informados, mas não há taxa.

**Comportamento esperado**
- Oferecer os três cenários da base ou pedir taxa ao usuário.
- Não inventar outra taxa.

## Teste 7 — Taxa elevada

**Entrada**
- Usuário informa 80% ao ano.

**Comportamento esperado**
- Aceitar como hipótese matemática somente após alertar que é um cenário elevado e não garantido.
- Não associar automaticamente a produto específico.

## Teste 8 — Duplicidade

**Entrada**
- O usuário informa “Netflix” em Assinaturas e repete o mesmo valor em Outros.

**Comportamento esperado**
- Sinalizar possível duplicidade.
- Pedir confirmação antes de somar.

## Teste 9 — Aporte no início e no fim

**Entrada**
- Mesmo capital, taxa e aporte em duas simulações.

**Comportamento esperado**
- Explicar que o aporte no início do mês rende por mais tempo.
- Mostrar premissas distintas.

## Teste 10 — Resultado final

**Comportamento esperado**
Apresentar separadamente:
- capital inicial;
- aportes realizados;
- total colocado;
- rendimento estimado;
- saldo final.
Nunca chamar todo o saldo final de lucro.
