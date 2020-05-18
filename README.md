## Data App - Prevendo Valores de Imóveis
> ##### Um App utilizado para exibir a solução de Machine Learning para o problema de predição de valores de imóveis de Boston
> ##### Usamos ``` 80% ``` de base de dados para treino e ```20%``` para teste
####  Semana de Data Science do [Minerando Dados](https://minerandodados.com.br/)
### Processo de Data Science 
### Etapas:

1. *Coleta de Dados*
2. *Limpeza e Formatação*
3. *Análise e Exploração* 
4. *Criação de Modelo*
5. *Interpretação de Resultado de Modelo*

Vou pular algumas etapas e ir logo para a etapa ```4 ``` que tem foco na escolha de algoritmo vencedor.
Nessa etapa, aplicamos os algorimtos que se adequam com o nosso problema. Lembrando que nesse caso, nosso problema é prever valor de um imóvel baseado nos valores dos dados que já temos. Esse é um problema para *algoritmo de aprendizado supervisionado*

#### Definição da Baseline
> É importante definir uma base line para termos marco no nosso projeto 
###### Nossa Baseline foi definida da seguinte forma:
``` def retorna_baseline(num_quartos):
  if num_quartos <= 4:
    return dic_baseline.get('Pequeno')
  elif num_quartos < 7:
    return dic_baseline.get('Medio')
  else:
    return dic_baseline.get('Grande') 
```

> desta forma, clasificamos assim os imoveis em três categorias definido no código em cima

###### Apos o treinamento, obtemos :
![predict_baseline](https://user-images.githubusercontent.com/19332627/82248838-2f034200-991f-11ea-9ac1-69cf2b4a77a9.PNG)
> Performance do modelo avaliado com os dados de teste

> erro quadrático: **6.205816494411828**

Obs: esse modelo erra ```+6 ou -6 ```

#### Regressão Linear
![rl](https://user-images.githubusercontent.com/19332627/82250696-50196200-9922-11ea-8137-68749949d93e.PNG)
> Performance do modelo avaliado com os dados de teste.

> erro quadrático de: **4.460277295153906**

#### Decision Tree 
![decision tree](https://user-images.githubusercontent.com/19332627/82252671-cff4fb80-9925-11ea-9b61-dcc083f38b7f.PNG)
> Performance do modelo avaliado com os dados de teste

> erro quadrático de: **4.643988873055277**

Por último, mas nao menos importanbte, testamos o nosso 
#### Random Forest
![random_forest](https://user-images.githubusercontent.com/19332627/82253900-409d1780-9928-11ea-89ce-4133f7ab5945.PNG)
> Performance do modelo avaliado com os dados de teste.

> erro quadrático de: **3.3218209875713334**

Note-se claramente que o Random Forest se saiu melhor que os demais algoritmos testados para o nosso problema
Desta forma, é com ele que terminamos a etapa 5 e decidimos.


> Psiu!!! essa escolha não quer dizer que o Random Forest é melhor que todos ou se sairá melhor que os restantes algoritmos. Mas, para esse problema ele se saí melhor que os os demais testados. Aliás,  poderíamos usar o ``` GridSearchCV ``` com seus famosos hiperparâmetros o que provavelmente seria um braço de ferro bem interessante.
