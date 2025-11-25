# Projeto de ETL e Business Intelligence: Dashboard de Vendas

Este projeto demonstra a implementação de um pipeline completo de **ETL (Extract, Transform, Load)** utilizando **Talend Open Studio** e a criação de um **Dashboard de Vendas** interativo no **Power BI**, com o **SQL Server** atuando como o banco de dados transacional (OLTP) e o Data Warehouse (OLAP).

## Tecnologias Utilizadas

| Categoria | Tecnologia | Uso no Projeto |
| :--- | :--- | :--- |
| **ETL** | Talend Open Studio for Data Integration | Extração, transformação e carga de dados. |
| **Banco de Dados** | SQL Server | Armazenamento dos dados transacionais (OLTP) e do Data Warehouse (OLAP). |
| **Business Intelligence** | Power BI | Criação do modelo de dados, medidas DAX e visualização do Dashboard de Vendas. |
| **Linguagem** | SQL (T-SQL) | Criação de tabelas, views e manipulação de dados. |
| **Conceitos** | Modelagem Dimensional (Star Schema), Surrogate Keys, SCD (Slowly Changing Dimensions) | Estruturação do Data Warehouse. |

## Arquitetura do Projeto

O projeto segue uma arquitetura clássica de Business Intelligence, dividida em três grandes etapas:

1.  **Extração e Staging:** O Talend extrai dados da fonte OLTP (SQL Server) e os carrega em tabelas de Staging no ambiente OLAP.
2.  **Transformação e Carga (Data Warehouse):** Os dados são transformados, aplicando regras de negócio, e carregados nas tabelas de Dimensão e Fato, seguindo o modelo dimensional (Star Schema).
3.  **Visualização e Análise:** O Power BI se conecta ao Data Warehouse (OLAP) para modelar os dados, criar medidas e gerar o Dashboard de Vendas.

## Etapas do Desenvolvimento

O projeto foi estruturado nas seguintes fases principais:

### 1. Preparação e Staging
*   **Conexões:** Configuração das conexões OLTP e OLAP no Talend.
*   **Carga de Staging:** Carga inicial de todas as entidades de dados (Clientes, Produtos, Vendas, Metas, etc.) para a área de Staging.

### 2. Modelagem Dimensional e Carga do Data Warehouse
*   **Criação de Dimensões:** Implementação de tabelas de Dimensão (e.g., `DimUF`, `DimCidade`, `DimCliente`, `DimMaterial`) com a aplicação de **Surrogate Keys** e tratamento de **Slowly Changing Dimensions (SCD)**.
*   **Criação de Fatos:** Implementação das tabelas de Fato (`FatoMetaVendas`, `FatoVenda`) para armazenar as métricas e chaves estrangeiras das dimensões.

### 3. Orquestração e Automação
*   **Criação de Jobs Gerais:** Desenvolvimento de Jobs mestres no Talend para orquestrar a sequência de carga (Staging -> Dimensões -> Fatos).
*   **Automação:** Configuração da automação do Job Geral para execução programada.

### 4. Business Intelligence com Power BI
*   **Conexão e Importação:** Conexão ao Data Warehouse (OLAP) e importação das tabelas de Fato e Dimensão.
*   **Modelagem de Dados:** Configuração de relacionamentos (Star Schema) e criação de uma tabela de **Calendário** para análise temporal.
*   **Criação de Medidas (DAX):** Desenvolvimento de um conjunto robusto de medidas DAX para cálculo de métricas de vendas, metas, rentabilidade e tendências.
*   **Visualização:** Criação de um Dashboard de Vendas com diversos visuais (Gauge, Tabela, Cartão Múltiplo, Sunburst, Gráficos de Barras/Linhas) para análise de Mês Atual, Ano e Tendência.
*   **Publicação:** Publicação do dashboard na nuvem do Power BI e configuração de **Segurança de Linha (RLS)**.

## Dashboard de Vendas (Power BI)


O dashboard final permite uma análise completa do desempenho de vendas, incluindo:

*   **Indicadores-chave de Desempenho (KPIs):** Vendas, Metas, Rentabilidade.
*   **Análise Temporal:** Comparação de desempenho por Mês Atual e Ano.
*   **Análise de Tendência:** Visualização da evolução das vendas ao longo do tempo.
*   **Análise Detalhada:** Top 5 Clientes e Produtos, distribuição geográfica (UF e Cidade).

### Link para o Dashboard
<p>
📊 <a href="https://app.powerbi.com/view?r=eyJrIjoiYzYwYzdjYjEtNDk4ZS00ODBhLThmMTAtMTQ3ZmIzNmY4MDVhIiwidCI6IjY1OWNlMmI4LTA3MTQtNDE5OC04YzM4LWRjOWI2MGFhYmI1NyJ9" target="_blank">Visualizar Dashboard no Power BI</a>
</p>
