# tempo-de-tela-sono-e-estresse
Análise exploratória de 3.000 perfis estudantis simulados para investigar as relações entre tempo de tela, duração do sono e nível de estresse.
# Tempo de tela, duração do sono e estresse em perfis estudantis simulados

**Autor:** Murillo Preto Cardoso Junior

## Sobre o projeto

Perfis com maior tempo de tela tendem a apresentar menor duração média do sono? Como os escores de estresse se distribuem entre perfis com diferentes durações de sono? Essas duas perguntas orientam a análise exploratória desenvolvida neste projeto em Python.

A base reúne 3.000 perfis estudantis simulados e 15 variáveis. Segundo o autor da base, os dados foram gerados para fins educacionais, com relações estatísticas planejadas. Os resultados descrevem os padrões encontrados na simulação e não permitem estabelecer efeitos causais em estudantes reais.

## Fonte dos dados

A base foi disponibilizada no Kaggle sob licença CC0: [Student Sleep, Screen Time & Mental Health 2026](https://www.kaggle.com/datasets/uditjain13/student-sleep-screen-time-and-mental-health-2026).

## Arquivos do projeto

- [Notebook com as análises, os gráficos e as conclusões](./Projeto_Final_Programacao_e_Ciencia_de_Dados_em_Saude.ipynb)
- [Base de dados original em CSV](./student_sleep_mental_health_2026.csv)

## Como a análise foi organizada

O notebook começa com o dicionário das variáveis e a verificação de valores ausentes, duplicatas e possíveis inconsistências. Em 42 perfis, o tempo de redes sociais superava o tempo de tela. Adotando a premissa de que as duas medidas se referem ao mesmo período, utilizamos o tempo de tela como limite superior para o uso de redes sociais. A transformação foi feita no notebook, com preservação dos valores originais para conferência.

Em seguida, os perfis foram agrupados em três faixas de duração média do sono: menos de 6 horas, de 6 a menos de 8 horas e 8 horas ou mais. Esses intervalos foram usados para comparar os grupos. Duas funções próprias auxiliaram a análise: uma calcula a distribuição dos escores de estresse dentro de cada faixa e a outra calcula a correlação de Spearman entre duas variáveis.

## Principais resultados

- **Tempo de tela e sono:** a correlação de Spearman foi de −0,572. Nos perfis simulados, mais horas de tela tenderam a acompanhar menos horas de sono. Entre os 62 perfis com exatamente 6,5 horas de tela, a duração do sono variou de 5,6 a 9,2 horas.
- **Sono e estresse:** as medianas dos escores de estresse foram 9, 7 e 6, da faixa de menor para a de maior duração do sono. Houve sobreposição entre os grupos: os escores de 5 a 10 apareceram nas três faixas.

## Como executar o notebook

1. Na página do repositório, selecione **Code → Download ZIP** e extraia os arquivos.
2. Mantenha o notebook e o arquivo `student_sleep_mental_health_2026.csv` na mesma pasta. O código utiliza esse nome para localizar a base.
3. Com o Python 3 instalado, abra um terminal nessa pasta e instale as dependências:

   ```bash
   python -m pip install jupyterlab pandas matplotlib scipy jinja2
   ```

4. Inicie o JupyterLab:

   ```bash
   jupyter lab
   ```

5. Abra o arquivo `.ipynb`. No menu **Kernel**, escolha **Restart Kernel and Run All Cells** para reproduzir as tabelas, os quatro gráficos e as análises a partir do CSV original.
