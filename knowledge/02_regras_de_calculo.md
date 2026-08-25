# Regras de cálculo do Júpiter

## Convenções

- Utilizar valores monetários com duas casas decimais.
- Preservar a moeda informada pelo usuário.
- Se nenhuma moeda for indicada, utilizar reais.
- Considerar 12 meses como prazo padrão.
- Informar se os aportes ocorrem no início ou no fim de cada mês.
- Apresentar resultados brutos, salvo quando taxas, impostos ou inflação forem explicitamente fornecidos.

## Orçamento mensal

Considere:

- `R`: renda mensal líquida;
- `D`: despesas mensais de consumo, sem incluir aportes;
- `A_atual`: aporte mensal já realizado;
- `E`: economia aprovada pelo usuário;
- `S_escolhida`: parcela do saldo livre que o usuário escolheu simular.

Fórmulas:

- `despesas_totais = soma das despesas de consumo`
- `saldo_livre = R - D - A_atual`
- `percentual_comprometido = (D / R) × 100`, quando `R > 0`
- `aporte_total = A_atual + E + S_escolhida`

Condições:

- `E` não pode superar a soma das reduções aprovadas.
- `S_escolhida` não pode superar o saldo livre positivo.
- Não contar o aporte atual novamente como despesa de consumo.
- Não contar a mesma economia em mais de uma categoria.
- Quando houver déficit, não criar novo aporte sem confirmação explícita do usuário.

## Conversão da taxa anual

Para uma taxa anual efetiva `i_a`, calcular a taxa mensal equivalente:

`i_m = (1 + i_a)^(1/12) - 1`

A taxa deve ser convertida de percentual para decimal antes do cálculo.

Exemplo:

- 10% ao ano = 0,10
- `i_m = (1 + 0,10)^(1/12) - 1`

## Evolução com aporte no fim do mês

Para cada mês:

`saldo_mês = saldo_anterior × (1 + i_m) + aporte_total`

O capital inicial rende durante o mês. O aporte entra ao final do mês.

## Evolução com aporte no início do mês

Para cada mês:

`saldo_mês = (saldo_anterior + aporte_total) × (1 + i_m)`

O aporte do mês também participa do rendimento daquele período.

## Resultado final

- `total_colocado = capital_inicial + aporte_total × número_de_meses`
- `rendimento_estimado = saldo_final - total_colocado`
- `saldo_final = total_colocado + rendimento_estimado`

Sempre apresentar separadamente:

1. capital inicial;
2. total de aportes;
3. total colocado;
4. rendimento bruto estimado;
5. saldo final projetado.

## Limitações matemáticas

A simulação não incorpora automaticamente:

- imposto de renda;
- IOF;
- taxas administrativas;
- taxas de custódia;
- inflação;
- variação de preços;
- risco de crédito;
- oscilações de mercado;
- resgates antecipados.

Esses elementos só devem ser incluídos quando houver dados claros e método definido.
