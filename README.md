Link do BI - https://app.fabric.microsoft.com/view?r=eyJrIjoiYWU4MDJkMWYtYjk3ZS00NjhjLThjOTUtMjQzYWIyNWE2YTc4IiwidCI6ImI2ZDY3YjA2LTg3OWEtNGMxMy05OWY0LTRjN2ZmMTA4NTNkMyJ9

## - Objetivo

O objetivo principal do módulo de **Previsibilidade de Estoque** é antecipar a necessidade de compra de itens para abastecimento, permitindo planejar aquisições para diferentes horizontes de tempo (trimestre, semestre etc.). Essa estratégia visa:

- **Aproveitar condições de negociação** junto aos fornecedores (descontos por volume, prazos, etc.).
- **Evitar faltas ou excessos de produtos** no estoque, otimizando o capital de giro.
- **Aprimorar a precisão de forecast**, ajustando a taxa de crescimento da demanda com base em dados históricos e tendências de consumo.

## - Abordagem de Cálculo (Soma Aparada + Ajuste de Crescimento)

A metodologia de previsão adotada utiliza:

- **Soma aparada**: Uma forma de suavizar ou “limpar” outliers nos dados históricos, reduzindo o impacto de consumos atípicos que podem distorcer a projeção.
- **Ajuste de crescimento**: Aplicação de uma taxa de crescimento projetada sobre os dados já suavizados, de modo a refletir tendências de aumento ou redução no consumo ao longo do período analisado.
- Benefícios Esperados
- **Otimização do Nível de Estoque**: Maior assertividade no planejamento de compras, reduzindo custos de armazenagem e o risco de rupturas.
- **Negociação com Fornecedores**: Planejamento de compras para períodos mais longos, possibilitando negociação de melhores condições.
- **Visão Estratégica**: O acompanhamento do histórico e da previsão em um mesmo painel facilita a tomada de decisão baseada em dados confiáveis.

## - Fonte de Dados

- Todos os dados são obtidos a partir do **ERP ANALYSIS**, acessados via um usuário de consulta no **ORACLE**.
- As tabelas relevantes incluem informações de estoque, histórico de vendas/consumo e parâmetros de produtos.

## - Fluxo de Ingestão (Microsoft Fabric)

1. **Extração do ERP (ORACLE)**: As consultas são realizadas em tempo determinado (batch) ou em intervalos pré-definidos, utilizando credenciais de leitura.
2. **Transformação em Fluxo de Dados**: Dentro do **Microsoft Fabric**, são criados fluxos de dados (Dataflows) para efetuar a limpeza e a unificação das tabelas, além de possíveis joins com tabelas de parâmetros (ex.: cadastros de produtos, fornecedores, etc.).
3. **Lakehouse**: Os dados tratados são armazenados no **Lakehouse**, servindo como camada única de armazenamento (Data Lake) e facilitando o consumo por diferentes ferramentas de análise.
4. **Modelagem e Visualização**: A partir do Lakehouse, as informações são disponibilizadas para relatórios e dashboards, possivelmente via **Power BI** ou outras soluções de visualização dentro do Microsoft Fabric.

5. ![image](https://github.com/user-attachments/assets/cb0a6798-310d-4d9f-a117-43369cfb55ba)
