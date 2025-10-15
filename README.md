# Análise de Distribuição de Receita e Planos - Xbox Game Pass

Este projeto demonstra a análise da distribuição de receita e dos planos de assinatura de um serviço de games, focado em identificar padrões de consumo e a rentabilidade por tipo de assinatura (Mensal, Trimestral e Anual) em diferentes produtos.

## Objetivo do Projeto

O objetivo principal é transformar uma base de dados transacional de assinaturas em *insights* de negócio, respondendo a perguntas como:

1. Qual é o tipo de assinatura mais popular (Mensal, Trimestral ou Anual)?
2. Como a receita se distribui entre os diferentes níveis de planos (Core, Standard, Ultimate)?
3. Qual a distribuição percentual dos planos em produtos específicos (EA Play, Minecraft)?

## Dashboard e Resultados (Visualizações)

O dashboard em anexo `projetoDash.xlsx`  apresenta as seguintes visualizações principais:

1. **Distribuição Geral da Receita dos Planos (Gráfico de Colunas Agrupadas):** Compara a receita total de cada nível de plano (Core, Standard, Ultimate) segmentada por tipo de assinatura (Monthly, Quarterly, Annual).
2. **Distribuição de Planos por Produto (Gráficos de Pizza - EA Play e Minecraft):** Mostra a participação percentual de assinantes Anuais, Mensais e Trimestrais dentro de cada produto específico.

> **Insight Chave:** O dashboard aponta para uma forte predominância do **plano mensal (Monthly)** em todos os níveis e produtos, indicando uma preferência dos clientes por compromissos de curto prazo.

## Instruções para Reprodução (Passo a Passo)

Para reproduzir o *dashboard* a partir da tabela de dados brutos:

### 1. Preparação da Tabela Dinâmica Principal

O gráfico principal (Distribuição Geral da Receita) foi gerado a partir de uma Tabela Dinâmica que resume os dados da Coluna `Total Value`.

* **Fonte de Dados:** Tabela principal (Colunas `A:L` na Planilha 1).
* **Linhas (Rows):** `Plan` (Core, Standard, Ultimate).
* **Colunas (Columns):** `Subscription Type` (Monthly, Quarterly, Annual).
* **Valores (Values):** `SUM` de `Total Value`.
* **Filtro:** Não deve haver filtros, ou filtrar por assinaturas ativas se houver uma coluna de status.

### 2. Preparação das Tabelas Dinâmicas de Produto (EA Play/Minecraft)

Os gráficos de pizza (Distribuição dos Planos) foram gerados a partir de tabelas dinâmicas que filtram o produto.

* **Fonte de Dados:** Tabela principal.
* **Linhas (Rows):** `Subscription Type` (Annual, Monthly, Quarterly).
* **Colunas (Columns):** (Nenhuma).
* **Valores (Values):** `COUNT` de `Subscriber ID`.
* **Filtro:**
  * Para o gráfico **EA Play:** Adicionar um filtro em `EA Play Season Pass` onde o valor é **'Yes'**.
  * Para o gráfico **Minecraft:** Adicionar um filtro em `Minecraft Season Pass` onde o valor é **'Yes'**.

### 3. Geração dos Gráficos

* Selecione a Tabela Dinâmica desejada (ex: a de EA Play).
* Vá em **Inserir** > **Gráfico**.
* Escolha o tipo **Gráfico de Pizza** para as distribuições percentuais (EA Play/Minecraft).
* Escolha o tipo **Gráfico de Colunas Agrupadas** para a Receita Geral (Plano x Tipo de Assinatura).

---
