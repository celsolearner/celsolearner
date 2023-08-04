### Hi there 👋

<!--
**celsolearner/celsolearner** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

## Stepwise e overdisp no Python:
em overdisp de statstests.tests e em stepwise de stepwise_process.statsmodels
try:
        formula = model.model.data.ynames + " ~ " + \
            ' + '.join(model.model.data.xnames[1:])

        df = pd.concat([model.model.data.orig_endog,
                       model.model.data.orig_exog], axis=1)
        
        #estas 3 linhas, estavam sem o caracter '\' e provocavam os erros:
        # adjust column names with special characters from categorical columns
        df.columns = df.columns.str.replace('\[', '', regex=True)
        df.columns = df.columns.str.replace('\.', '_', regex=True)
        df.columns = df.columns.str.replace('\]', '', regex=True)

## Dúvidas
Professor, vou tentar simplificar bem: em uma estrutura hierárquica tempo em semanas nível 1, departamento nível 2 e lojas nível 3, mas departemanto não tem variável de contexto, só a dependente Vendas Semanais. Lojas tem variável de contexto e o resto varia com o tempo e entrou no nível um. O gráfico de frequência de Vendas semanais sugere o uso de modelo Poisson. Mesmo sendo este nível 2 um modelo nulo não posso usar hlm3 linear ao invés de multinível para dados de contagem?
