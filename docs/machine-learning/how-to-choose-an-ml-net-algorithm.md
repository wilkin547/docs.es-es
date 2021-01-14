---
title: Cómo elegir un algoritmo de ML.NET
description: Aprenda a elegir un algoritmo de ML.NET para su modelo de Machine Learning
ms.topic: overview
ms.date: 06/05/2019
ms.openlocfilehash: 04cf191401c7c25f1fa341acaf9312dc19752260
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593095"
---
# <a name="how-to-choose-an-mlnet-algorithm"></a>Cómo elegir un algoritmo de ML.NET

Para cada [tarea de ML.NET](resources/tasks.md), existen varios algoritmos de entrenamiento de donde elegir. La elección depende del problema que intenta resolver, las características de los datos y los recursos de proceso y almacenamiento que tiene a su disposición. Es importante tener en cuenta que entrenar un modelo de Machine Learning es un proceso iterativo. Es posible que deba probar varios algoritmos para encontrar el que mejor funcione.

Los algoritmos funcionan con **características**. Las características son valores numéricos calculados a partir de los datos de entrada. Son entradas óptimas para los algoritmos de aprendizaje automático. Transforme sus datos de entrada sin formato en características mediante una o varias de las [transformaciones de datos](resources/transforms.md). Por ejemplo, los datos de texto se transforman en un conjunto de recuentos de palabras y recuentos de combinación de palabras. Una vez extraídas las características de un tipo de datos sin formato mediante transformaciones de datos, se dice que están **caracterizadas**. Por ejemplo, texto caracterizado o datos de imagen caracterizados.

## <a name="trainer--algorithm--task"></a>Instructor = algoritmo + tarea

Un algoritmo es la expresión matemática que se ejecuta para generar un **modelo**. Diferentes algoritmos generan modelos con diferentes características.

Con ML.NET, se puede aplicar el mismo algoritmo a distintas tareas. Por ejemplo, se puede usar el ascenso coordinado dual estocástico para la clasificación binaria, la clasificación multiclase y la regresión. La diferencia radica en cómo se interpreta la salida del algoritmo para que coincida con la tarea.

Para cada combinación de tarea o algoritmo, ML.NET proporciona un componente que ejecuta el algoritmo de entrenamiento y hace la interpretación. Estos componentes se denominan instructores. Por ejemplo, <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer> usa el algoritmo **StochasticDualCoordinatedAscent** que se aplica a la tarea de **regresión**.

## <a name="linear-algorithms"></a>Algoritmos lineales

Los algoritmos lineales generan un modelo que calcula **puntuaciones** desde una combinación lineal de los datos de entrada y un conjunto de **pesos**. Los pesos son parámetros del modelo estimado durante el entrenamiento.

Los algoritmos lineales funcionan bien para las características que se pueden [separar de manera lineal](https://en.wikipedia.org/wiki/Linear_separability).

Antes del entrenamiento con un algoritmo lineal, se deben normalizar las características. Esto evita que una característica tenga más influencia sobre el resultado que otros.

En general, los algoritmos lineales son escalables, rápidos y baratos de entrenar y predecir. Se escalan por el número de características y aproximadamente por el tamaño del conjunto de datos de entrenamiento.

Los algoritmos lineales realizan varios recorridos por los datos de entrenamiento. Si el conjunto de datos cabe en la memoria, la adición de un [punto de control de memoria caché](xref:Microsoft.ML.LearningPipelineExtensions.AppendCacheCheckpoint%2A) a la canalización de ML.NET antes de anexar el instructor hará que el entrenamiento se ejecute más rápidamente.

**Instructores lineales**

|Algoritmo|Propiedades|Instructores|
|---------|----------|--------|
|Perceptrón promedio|Ideal para la clasificación de textos|<xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>|
|Ascenso coordinado dual estocástico|No es necesario optimizar para obtener un buen rendimiento predeterminado|<xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer> <xref:Microsoft.ML.Trainers.SdcaNonCalibratedBinaryTrainer> <xref:Microsoft.ML.Trainers.SdcaMaximumEntropyMulticlassTrainer> <xref:Microsoft.ML.Trainers.SdcaNonCalibratedMulticlassTrainer> <xref:Microsoft.ML.Trainers.SdcaRegressionTrainer>|
|L-BFGS|Se utiliza cuando el número de características es grande. Genera estadísticas de entrenamiento de regresión logística, pero no se escala tan bien como AveragedPerceptronTrainer|<xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer> <xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer> <xref:Microsoft.ML.Trainers.LbfgsPoissonRegressionTrainer>|
|Descenso de gradiente estocástico simbólico|Instructor de clasificación binaria lineal más rápido y más preciso. Se escala bien con el número de procesadores|<xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>|

## <a name="decision-tree-algorithms"></a>Algoritmos de árbol de decisión

Los algoritmos de árbol de decisión crean un modelo que contiene una serie de decisiones: eficazmente un diagrama de flujo a través de los valores de datos.

Para usar este tipo de algoritmo, no es necesario poder separar las características de forma lineal. Tampoco es necesario normalizar las características, porque los valores individuales en el vector de la característica se usan de forma independiente en el proceso de toma de decisiones.

Los algoritmos de árbol de decisión normalmente son muy precisos.

Salvo por los modelos aditivos generalizados (GAM), los modelos de árbol carecen de explicación cuando el número de características es grande.

Los algoritmos de árbol de decisión consumen más recursos y no se escalan tan bien como los lineales. Se desempeñan bien en los conjuntos de datos que pueden caber en la memoria.

Los árboles de decisión potenciados son un conjunto de árboles pequeños, donde cada árbol asigna una puntuación a los datos de entrada y pasa la puntuación al árbol siguiente para generar una mejor puntuación y así sucesivamente, donde cada árbol en el conjunto mejora al anterior.

**Instructores para árbol de decisión**

|Algoritmo|Propiedades|Instructores|
|---------|----------|--------|
|Máquina potenciada de degradado ligero|Instructores de árbol de clasificación binaria más rápidos y más precisos. Altamente optimizable|<xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmMulticlassTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRegressionTrainer> <xref:Microsoft.ML.Trainers.LightGbm.LightGbmRankingTrainer>|
|Árbol rápido|Se usa para los datos de imagen caracterizados. Resistente a los datos no equilibrados. Altamente optimizable | <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeRegressionTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeTweedieTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastTreeRankingTrainer>|
|Bosque rápido|Funciona bien con datos ruidosos|<xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.FastForestRegressionTrainer>|
|Modelo aditivo generalizado (GAM)|Ideal para problemas que funcionan bien con los algoritmos de árbol, pero en los que la explicación es una prioridad|<xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer> <xref:Microsoft.ML.Trainers.FastTree.GamRegressionTrainer>|

## <a name="matrix-factorization"></a>Factorización matricial

|Propiedades|Instructores|
|----------|--------|
|Ideal para datos categóricos dispersos, con grandes conjuntos de datos|<xref:Microsoft.ML.Trainers.FieldAwareFactorizationMachineTrainer>|

## <a name="meta-algorithms"></a>Meta-algoritmos

Estos instructores crean un instructor multiclase a partir de un instructor binario. Usar con <xref:Microsoft.ML.Trainers.AveragedPerceptronTrainer>, <xref:Microsoft.ML.Trainers.LbfgsLogisticRegressionBinaryTrainer>, <xref:Microsoft.ML.Trainers.SymbolicSgdLogisticRegressionBinaryTrainer>, <xref:Microsoft.ML.Trainers.LightGbm.LightGbmBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.FastForestBinaryTrainer>, <xref:Microsoft.ML.Trainers.FastTree.GamBinaryTrainer>.

|Algoritmo|Propiedades|Instructores|
|---------|----------|--------|
|Uno frente a todos|Este clasificador multiclase entrena un clasificador binario para cada clase, que distingue esa clase de todas las demás. Está limitado en la escala por el número de clases para clasificar|[OneVersusAllTrainer\<BinaryClassificationTrainer>](xref:Microsoft.ML.Trainers.OneVersusAllTrainer) |
|Acoplamiento en pares|Este clasificador multiclase entrena un algoritmo de clasificación binaria en cada par de clases. Está limitado en la escala por el número de clases, ya que cada combinación de dos clases debe entrenarse.|[PairwiseCouplingTrainer\<BinaryClassificationTrainer>](xref:Microsoft.ML.Trainers.PairwiseCouplingTrainer)|

## <a name="k-means"></a>K-Means

|Propiedades|Instructores|
|----------|--------|
|Se usa para la agrupación en clústeres|<xref:Microsoft.ML.Trainers.KMeansTrainer>|

## <a name="principal-component-analysis"></a>Análisis de componentes principales

|Propiedades|Instructores|
|----------|--------|
|Se usa para la detección de anomalías|<xref:Microsoft.ML.Trainers.RandomizedPcaTrainer>|

## <a name="naive-bayes"></a>Bayes naive

|Propiedades|Instructores|
|----------|--------|
|Use este instructor de clasificación multiclase cuando las características sean independientes y el conjunto de datos de entrenamiento sea pequeño.|<xref:Microsoft.ML.Trainers.NaiveBayesMulticlassTrainer>|

## <a name="prior-trainer"></a>Instructor anterior

|Propiedades|Instructores|
|----------|--------|
|Use este instructor de clasificación binaria para marcar el rendimiento de otros instructores. Para ser eficaces, las métricas de los otros instructores deben ser mejores que el instructor anterior. |<xref:Microsoft.ML.Trainers.PriorTrainer>|
