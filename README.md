# 📊 Dashboard de Vendas — Power BI

Dashboard interativo desenvolvido para análise completa de vendas, acompanhamento de metas, lucratividade e desempenho por filial. O projeto cobre desde a exploração e tratamento dos dados até a entrega dos indicadores finais em painéis visuais e dinâmicos.

---

## 🖥️ Visões do Dashboard

- **Metas** — acompanhamento do faturamento realizado vs. meta, com diferença absoluta e percentual por filial
- **Visão Geral** — indicadores consolidados de vendas, pedidos, entregas, ticket médio e lucratividade

---

## 📈 Indicadores Principais

| Indicador | Valor |
|---|---|
| Faturamento Total | R$ 6,7M |
| Meta | R$ 6M |
| Diferença (Real - Meta) | +R$ 750 mil (+13%) |
| Lucro Total | R$ 2,8M |
| Margem de Lucro | ~41% |
| Ticket Médio | R$ 2,2 mil |
| Total de Pedidos | 3.000 |
| Total de Entregas | 3.000 |
| Tempo Médio de Entrega | ~45 horas |

<img width="1333" height="752" alt="image" src="https://github.com/user-attachments/assets/11b1dedc-920e-4dbb-9274-36cc43732c67" />
---

## 🏢 Desempenho por Filial

| Filial | Faturamento | % vs Meta |
|---|---|---|
| Matriz (RJ) | R$ 1,8M | +13% |
| Filial ES (Vitória) | R$ 1,7M | +15% ✅ melhor % |
| Filial SP (São Paulo) | R$ 1,6M | +11% |
| Filial MG (Belo Horizonte) | R$ 1,6M | +11% |

> Todas as filiais superaram a meta no período analisado.

---

## 🔍 O que o Dashboard permite analisar

- Evolução mensal do faturamento vs. meta acumulada
- Meses com maior e menor resultado de lucro
- Comparativo de desempenho entre filiais
- Participação por categoria no faturamento total
- Comportamento da margem de lucro ao longo do período
- Volume e prazo das entregas realizadas

<img width="1335" height="753" alt="image" src="https://github.com/user-attachments/assets/7fe11ac8-02e2-4393-a730-fba2f02490c0" />

---

## 🛠️ Stack

| Ferramenta | Uso no projeto |
|---|---|
| **Excel** | Fonte de dados brutos estruturada em cinco abas: `fVendas`, `fMetas`, `dLoja`, `dProdutos` e `dFuncionario` — cada uma representando uma entidade distinta do negócio |
| **Power Query** | Exploração, limpeza e transformação dos dados: promoção de cabeçalhos, ajuste de tipos, remoção de colunas irrelevantes, separação das colunas de data e hora em campos independentes, e unpivot da tabela de metas — que estava em formato horizontal — para estrutura relacional compatível com o modelo |
| **Modelagem Tabular** | Estruturação no modelo estrela com relacionamento entre tabelas fato (`fVendas`, `fMetas`) e dimensão (`dLoja`, `dProdutos`, `dCalendário`), incluindo relacionamento inativo para datas de entrega ativado via `USERELATIONSHIP` |
| **DAX** | Desenvolvimento de medidas para cobrir todo o ciclo analítico do dashboard: cálculo de faturamento via `SUMX`, apuração de lucro por linha com `SUMX`, ticket médio com `AVERAGEX`, tempo médio de entrega em horas com `AVERAGEX` + `DATEDIFF`, percentual vs. meta com `DIVIDE`, acumulado anual com `DATESYTD`, comparativo ano a ano com `SAMEPERIODLASTYEAR`, participação por filial com `ALL` e `ALLEXCEPT`, e formatação de tempo em `hh:mm:ss` via variáveis DAX |
| **Power BI** | Construção dos painéis interativos, visuais dinâmicos e entrega do relatório final |
