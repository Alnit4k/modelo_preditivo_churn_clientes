# Modelo Preditivo de Churn de Clientes

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas&logoColor=white)
![Status](https://img.shields.io/badge/Status-Concluído-brightgreen)
![License](https://img.shields.io/badge/Licença-MIT-blue)

Projeto de ciência de dados desenvolvido durante o curso **Profissão: Cientista de Dados (EBAC)**, com o objetivo de identificar padrões de comportamento associados ao cancelamento (*churn*) de clientes em uma empresa de telecomunicações, a partir do tratamento e análise exploratória da base de dados.

---

## Sobre o projeto

Churn é a taxa de clientes que deixam de utilizar um serviço em um determinado período. Para empresas de assinatura — como as de telecomunicações — reter um cliente é significativamente mais barato do que conquistar um novo, o que torna a previsão de churn um problema de alto valor para times de dados e negócio.

Este projeto parte de uma base bruta fornecida por uma operadora de telecomunicações e percorre as etapas iniciais (e essenciais) de qualquer pipeline preditivo: **entendimento, limpeza e tratamento dos dados**, preparando o terreno para a etapa de modelagem.

## Problema de negócio

> Como identificar, a partir de dados cadastrais e de consumo, quais clientes possuem maior propensão a cancelar o serviço?

Responder a essa pergunta permite que a empresa direcione ações de retenção (descontos, contato proativo, ajustes de plano) para os clientes certos, otimizando custo e efetividade da campanha.

## Sobre os dados

O dataset contém informações cadastrais, contratuais e de consumo de clientes de uma operadora de telecomunicações, incluindo variáveis como:

| Coluna | Descrição |
|---|---|
| `Idoso` | Indica se o cliente é idoso (booleano) |
| `Casado` | Indica se o cliente é casado (booleano) |
| `Dependents` | Indica se o cliente possui dependentes (booleano) |
| `PhoneService` | Indica se o cliente possui serviço de telefonia |
| `Pagamento_Mensal` | Valor da mensalidade paga pelo cliente |
| `genero` | Gênero do cliente |
| `Churn` | Variável-alvo: indica se o cliente cancelou o serviço (booleano) |

> A base completa está disponível em [`CHURN_TELECON_MOD08_TAREFA (1).csv`](./CHURN_TELECON_MOD08_TAREFA%20(1).csv).

## 🔧 Metodologia

O tratamento dos dados seguiu as seguintes etapas:

1. **Importação e visualização inicial** — carregamento do dataset e checagem estrutural (linhas, colunas, tipos).
2. **Ajuste de tipos de dados** — colunas booleanas (`Idoso`, `Casado`, `Dependents`, `Churn`) estavam tipadas como `object` e foram convertidas para facilitar cálculos estatísticos e a plotagem de gráficos.
3. **Tratamento de valores nulos** — cada coluna com dados ausentes foi avaliada individualmente:
   - `PhoneService`: descartada por concentrar um volume alto de nulos com baixo valor analítico agregado.
   - `Pagamento_Mensal`: preenchida pela média, por se tratar de uma variável numérica contínua.
   - `genero`: as poucas linhas nulas (12 no total, valor irrisório frente ao tamanho da base) foram removidas.
4. **Padronização de categorias** — normalização dos valores da coluna `genero` para garantir consistência na análise.

> 🔜 **Próxima etapa (a completar):** aplicação de algoritmo(s) de classificação — ex. Regressão Logística, Random Forest, XGBoost — treino/teste, e avaliação via métricas como acurácia, precisão, recall e matriz de confusão. *Atualize esta seção com o modelo escolhido e os resultados obtidos no notebook.*

## 🛠️ Tecnologias utilizadas

- **Python** — linguagem principal do projeto
- **Pandas** — manipulação e tratamento de dados
- **Jupyter Notebook** — ambiente de desenvolvimento e documentação do processo
- *(adicionar aqui bibliotecas de visualização e modelagem efetivamente usadas, ex. Matplotlib/Seaborn/Scikit-learn)*

## Como executar o projeto

```bash
# Clone o repositório
git clone https://github.com/Alnit4k/modelo_preditivo_churn_clientes.git

# Acesse a pasta do projeto
cd modelo_preditivo_churn_clientes

# Instale as dependências
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# Execute o notebook
jupyter notebook "Profissao Cientista de Dados M14 Pratique.ipynb"
```

## Estrutura do repositório

```
modelo_preditivo_churn_clientes/
├── CHURN_TELECON_MOD08_TAREFA (1).csv     # Base de dados bruta
├── Profissao Cientista de Dados M14 Pratique.ipynb   # Notebook com todo o desenvolvimento
└── README.md
```

## 📈 Próximos passos

- [ ] Adicionar análise exploratória visual (distribuições, correlações com churn)
- [ ] Documentar o(s) modelo(s) de classificação utilizados e as métricas obtidas
- [ ] Incluir matriz de confusão e interpretação dos resultados
- [ ] Discutir principais variáveis preditoras (feature importance)

## Autor

**Misael** — Estudante de Ciência de Dados na EBAC
[GitHub](https://github.com/Alnit4k)

---

<p align="center"><i>Projeto desenvolvido para fins educacionais no curso Profissão: Cientista de Dados — EBAC.</i></p>
