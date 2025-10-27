# 📊 Dashboard de Vendas – Power BI

![Capa do Dashboard](./assets/Paginas-BI.png)

## 🧠 Visão Geral
Projeto de **Business Intelligence** para monitorar desempenho comercial, funil e ciclo de vendas. 
Este repositório contém documentação, imagens e um dataset de **exemplo**, além do passo a passo para conectar a base real no Google Sheets.

> Autor: **Higor Maia** — Analista de TI (BI & Data Analytics)

---

## ⚙️ Principais Recursos do Dashboard
- **Visão Geral**: Total de Leads, Vendas Concluídas, Taxa de Conversão, Receita Total.
- **Funil de Vendas**: Prospecção → Proposta → Contato → Fechamento (com conversão por origem).
- **Análise por Vendedor**: Evolução de vendas, ticket médio, origem do lead por vendedor.
- **Ciclo de Vendas**: Tempo médio, maior/menor ciclo, % no prazo, tempo por etapa e produto.
- **Detalhamento de Leads**: Tabela completa com filtros dinâmicos (status, origem, vendedor).

---

## 🧩 Modelagem de Dados (conceito)
Tabelas principais:
- `Leads` (fato)
- `ProdutosServicos` (dimensão)
- `Vendedores` (dimensão)
- `Calendario` (dimensão de tempo)

Relacionamentos **1:N** das dimensões para a fato, com direção única para garantir desempenho.

---

## 📐 Métricas DAX (exemplo)
| Medida | DAX (pseudo) | Descrição |
|---|---|---|
| **Total de Leads** | `COUNTROWS(Leads)` | Quantidade de leads cadastrados |
| **Vendas Concluídas** | `CALCULATE(COUNTROWS(Leads), Leads[Status]="Concluído")` | Leads convertidos em venda |
| **Taxa de Conversão %** | `DIVIDE([Vendas Concluídas], [Total de Leads])` | Conversão do funil |
| **Receita Total** | `SUM(Leads[Valor])` | Soma de valores fechados |
| **Ticket Médio** | `DIVIDE([Receita Total], [Vendas Concluídas])` | Valor médio por venda |
| **Tempo Médio de Fechamento (dias)** | `AVERAGE(Leads[DiasFechamento])` | Ciclo médio de venda |

> As medidas reais variam conforme seu modelo. Este arquivo será ajustado conforme o `.pbix` final.

---

## 🔗 Base de Dados (Google Sheets)
Este dashboard pode ser conectado diretamente à planilha:
**https://docs.google.com/spreadsheets/d/1LJ29I5mlXayyns2aMnS0aGoJ-cINJ4rUBzqvwo47xOE/edit?usp=sharing**

### Como conectar no Power BI Desktop
1. **Obter Dados** → **Web**.  
2. Cole a URL **de exportação CSV** do Google Sheets (Arquivo → Compartilhar → Qualquer pessoa com o link / publicar na web ou use o link de CSV do GSheets).  
3. Use o **Power Query** para tratamento (tipos, datas, colunas calculadas, filtros).  
4. Atualize as relações e medidas no modelo.

> Alternativa: Conectar via **Google Sheets Connector** (se disponível) ou publicar a planilha como CSV público e usar essa URL.

---

## 🗂 Estrutura deste Repositório
```
dashboard-vendas-powerbi/
├─ assets/                    # Imagens do dashboard
├─ dataset/                   # Dados de exemplo + link da base
├─ documentos/                # Diagramas e PDFs de documentação
└─ README.md                  # Este arquivo
```

---

## 📁 Arquivos Importantes
- `assets/Paginas-BI.png`: print principal do relatório.
- `dataset/leads_vendas_exemplo.csv`: dataset fictício para demonstração/local.
- `dataset/google_sheet_link.txt`: link da base real no Google Sheets.
- `documentos/estrutura_modelo_dados.png`: (adicione seu diagrama de modelo aqui).

---

## ▶️ Como Executar (passo a passo)
1. Baixe o arquivo **PBIX** (adicione-o a este repositório ou disponibilize um link de download).
2. Abra no **Power BI Desktop**.
3. No **Power Query**, troque a fonte para o Google Sheets indicado em `dataset/google_sheet_link.txt`.
4. Verifique as credenciais de acesso.
5. Atualize as tabelas, confirme as relações e teste as medidas.
6. Publique no **Power BI Service** (opcional) e configure atualização agendada, se necessário.

---

## 🧰 Stack Tecnológica
- **Power BI Desktop** (Power Query + DAX)
- **Google Sheets** (fonte de dados)
- **Excel/CSV** (dados locais de exemplo)
- **Figma** (opcional, para layouts e UI)

---

## 📈 Resultados Esperados
- Visibilidade sobre taxa de conversão e funil.
- Entendimento do ciclo de vendas e gargalos por etapa/produto.
- Ranking de vendedores e origens de lead mais eficientes.
- Base para previsões/otimizações com ML (futuro).

---

## 👤 Autor
**Higor Maia** — BI & Data Analytics  
🌐 Blog: https://datamarketingdigital.com.br/blog  
💼 LinkedIn: https://www.linkedin.com/in/higor-maia/  
🐙 GitHub: https://github.com/higormaia  
📧 E-mail: higormaia.data@gmail.com

---

## 📝 Licença
Distribuído sob licença **MIT**. Veja `LICENSE`.
