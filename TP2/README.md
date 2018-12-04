# 7506 - Organización de Datos

Grupo 30: Datatouille

https://fdelmazo.github.io/7506-Datos/

---

Notebooks en orden de corrida y lectura:

0. [TP1](../TP1/TP1.ipynb) y su [anexo](../TP1/anexo.ipynb) --> Familiarización con el set de datos y exploración de estos.

1. [Investigación Previa](investigacion.ipynb) --> Con ayuda de lo trabajado en el TP1, se averiguan más cosas de las datos, en busqueda de que poder reutilizar.

2. [Creación de Dataframes](new_dataframes.ipynb) --> Como parte del feature engineering, se crean dataframes nuevos con información de los productos del sitio y de como se accede a este (marcas, sistemas operativos, etc).

3. [Feature Engineering](feature_engineering.html) --> Busqueda de atributos de los usuarios de los cuales se busca predecir la conversión.

4. [Feature Selection](feature_selection.ipynb) --> Busqueda de la combinación de features más favorable.

5. [Parameter Tuning](parameter_tuning.ipynb) --> Busqueda de los mejores hiper-parametros para cada algoritmo de ML.

6. [Submission Framework](submission_framework.ipynb) --> Pequeño framework para construir las postulaciones de labels. 

7. [TP2](TP2.ipynb) --> Teniendo todo en cuenta, usando los dataframes con todos los atributos buscados y encontrados, se definen y aplican los algoritmos de clasificación, se realizan los entrenamientos y posteriores predicciones de conversiones y finalmente se arman las postulaciones de labels.

---

Insights post entrega, fin de competencia y demás

- Entrenar el modelo final con todo X es... dudoso por decir poco. Lo que como grupo hacíamos era entrenar un modelo con X_train (un 34% separado del DF original) y luego la última llamada presubmit hacerlo con X total (todo el DF), con la teoría que eran más datos para entrenar y que la validación sería del lado de Kaggle. Lo que pasa con esto es que técnicamente estas usando un modelo ya pensado para unos datos, con otros. Se puede hacer (y nosotros vimos incrementos en nuestros resultados), pero al menos es un tema para debatir.

- Fallamos en hacer poco cross validation. Si bien el GridSearch en parameter tuning lo hace, deberíamos haber hecho más uso de esto.

- Hay un par de cosas que hubiese estado bueno tener más tiempo para aplicar. Blending y Voto por mayoría, por empezar.

- Hubiese estado bueno poder plotear nuestro AUC contra el AUC de kaggle, y luego crossreferenciarlo con nuestros commits, para ver la evolución de todos nuestros submits. Esto no es muy dificil, el AUC nuestro esta siempre al final del nombre del .csv que se submittea, y el de Kaggle se puede scrappear del sitio. Fue falta de tiempo.

- Fallamos en tan poco encoding. Mean encoding, one hot encoding, hashing trick, matrices dispersas, featureunion. Hay varios algoritmos que hacen muy buen uso de esto, y si bien hicimos un poco de pruebas, podrían haber sido más exhaustivas

- GridSearchCV devuelve un *modelo*. Nosotros siempre nos quedamos con sus mejores parametros y luego usamos esos para el modelo final. Tendríamos que haber usado el modelo directamente, porque es mejor que la suma de las partes.

- Un par de metodos para evitar overfitting no hubiesen estado mal, si bien atajamos bastante con el uso de bagging. Comparar test/train, hacer crossvalidation, dropouts, oversampling, regularización, perturbar los datos de entrada, etc.

- Leer nuestro TP1 y sacar aún más ideas de features hubiese estado bueno. También, ver de cada columna del DF original y pensar 'cómo puedo usar esto?'. Por ejemplo, nos quedamos con las ganas de utilizar los search terms.

- Usar el classification report de sklearn.

- Intentar plotear e identificar el bias y variance, ploteando el error del set de entrenamiento y el error de set de test en funcion de la cantidad de datos en el set de entrenamiento (en el mismo plot)

- Haber gastado más tiempo en el parameter tuning con grid search no modificado. Es verdad, consume un monton de tiempo, pero nos hubiese dado resultados más optimos que el 'GridSearchFede'.