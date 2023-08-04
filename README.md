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
Ao decidir mudar o tcc, primeiro olhei uma primeira planilha que peguei e procurei soluções que estariam usando-a na internet para evitar desenvolver o mesmo modelo. Como existiam algumas usando já umas ideias que eu tive além de Regressão não linear (séries temporais e assemble models) faltava outra tentativa: predizer Weekly_sales com o modelo de dados de contagem. No site que usou regressão não linear já tinha os gráficos e ainda bem que rolei para baixo e tive uma grande supresa: há uma estrutura hierárquica e há heterocedasticidade entre o que seria a variável dependente com a de contexto do nível 3.
A tabela então tem uma estrutura hierárquica: tempo nível 1, departamento nível 2 e lojas nível 3, mas departemanto não tem variável de contexto, só a dependente e uma que não varia no nível 3. As outras variáveis pareciam ser do nível 3 mas variam com o tempo, ou seja, foram para o nível 1.
Concluindo: o nível 2 tem uma aparência de modelo nulo mas nível 3 não, e a dúvida ficou na variável dependente que muda a cada observação que é de semana em semana e o gráfico de frequência dela sugere o uso de modelo Poisson. Mesmo sendo este nível um modelo nulo não posso usar GLMM3 linear? Já vi que não no seu livro, mas o modelo é nulo e restou uma preditiva cuja a frequência sugere uma superdispersão (notei um fenómeno típico de modelos que usam planilhas com data e vendas: uma superdispersão de compras com valores baixos).
