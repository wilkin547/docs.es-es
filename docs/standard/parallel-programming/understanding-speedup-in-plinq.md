---
title: "Introducción a la velocidad en PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, performance tuning
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3373cb6a2c535bd7d42eb062e1f9727952f7cfb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="understanding-speedup-in-plinq"></a>Introducción a la velocidad en PLINQ
El objetivo principal de PLINQ es acelerar la ejecución de LINQ a consultas de objetos mediante la ejecución de los delegados de consulta en paralelo en equipos de varios núcleos. PLINQ funciona mejor cuando el procesamiento de cada elemento de una colección de origen es independiente, sin ningún estado compartido implicado entre los delegados individuales. Estas operaciones son comunes en LINQ to Objects y PLINQ y a menudo se denominan "*perfectamente paralelas*" porque prestan fácilmente a la programación en varios subprocesos. Sin embargo, no todas las consultas constan únicamente de operaciones paralelas perfectas; en la mayoría de los casos, una consulta incluye a operadores que no se puede paralelizar cualquiera o que ralentizan la ejecución en paralelo. E incluso con las consultas que son perfectamente paralelas, PLINQ debe crear particiones del origen de datos y programar el trabajo en los subprocesos y generalmente tiene que combinar los resultados cuando finaliza la consulta. Todas estas operaciones aumentan el costo computacional de la paralelización; se llaman a estos costos de agregar paralelización *sobrecarga*. Para lograr un rendimiento óptimo en una consulta PLINQ, el objetivo es maximizar las partes que son perfectamente paralelas y minimizar las partes que producir una sobrecarga. Este artículo proporciona información que le ayudará a escribir consultas PLINQ que son tan eficaces como sea posible mientras se sigue produciendo resultados correctos.  
  
## <a name="factors-that-impact-plinq-query-performance"></a>Factores que afectan el rendimiento de las consultas PLINQ  
 En las siguientes secciones se enumeran algunos de los factores más importantes que afectan al rendimiento consultas en paralelo. Estas son las instrucciones generales que por sí mismos no son suficientes para predecir el rendimiento de las consultas en todos los casos. Como siempre, es importante medir el rendimiento real de consultas específicas en equipos con una variedad de cargas y configuraciones representativas.  
  
1.  Costo computacional del trabajo total.  
  
     Para lograr una velocidad, una consulta PLINQ debe tener suficiente trabajo perfectamente en paralelo para compensar la sobrecarga. El trabajo se puede expresar como el costo computacional de cada delegado multiplicado por el número de elementos de la colección de origen. Suponiendo que una operación puede paralelizar, cuanto más procesamiento costoso es, mayor será la posibilidad de aumentar la velocidad. Por ejemplo, si una función tarda un milisegundo en ejecutarse, una consulta secuencial de más de 1000 elementos tardará un segundo para realizar esa operación, mientras que una consulta paralela en un equipo con cuatro núcleos puede tardar sólo 250 milisegundos. Esto da como resultado una velocidad de 750 milisegundos. Si la función requiere un segundo ejecutar para cada elemento, la velocidad sería 750 segundos. Si el delegado es muy caro, PLINQ podría proporcionar un aumento significativo con solo unos pocos elementos de la colección de origen. Por el contrario, las colecciones de origen pequeñas con delegados triviales generalmente no son buenas candidatas para PLINQ.  
  
     En el ejemplo siguiente, queryA es probablemente una buena candidata para PLINQ, suponiendo que su función Select implica mucho trabajo. queryB no es probablemente una buena candidata porque no hay suficiente trabajo en la instrucción Select y la sobrecarga de la paralelización compensará la mayoría o la totalidad de la velocidad.  
  
    ```vb  
    Dim queryA = From num In numberList.AsParallel()  
                 Select ExpensiveFunction(num); 'good for PLINQ  
  
    Dim queryB = From num In numberList.AsParallel()  
                 Where num Mod 2 > 0  
                 Select num; 'not as good for PLINQ  
    ```  
  
    ```csharp  
    var queryA = from num in numberList.AsParallel()  
                 select ExpensiveFunction(num); //good for PLINQ  
  
    var queryB = from num in numberList.AsParallel()  
                 where num % 2 > 0  
                 select num; //not as good for PLINQ  
    ```  
  
2.  El número de núcleos lógicos del sistema (grado de paralelismo).  
  
     Este punto es un corolario obvio a la sección anterior, las consultas que son perfectamente paralelas ejecutan más rápido en equipos con varios núcleos porque se puede dividir el trabajo entre más subprocesos simultáneos. La cantidad total de velocidad depende de en qué porcentaje del trabajo total de la consulta puede paralelizar. Sin embargo, no se da por supuesto que todas las consultas se ejecutarán dos veces más rápido en un equipo de ocho núcleos como un equipo de cuatro núcleos. Al optimizar las consultas para un rendimiento óptimo, es importante medir los resultados reales en equipos con varios números de núcleos. Este punto se relaciona con el punto #1: conjuntos de datos grandes deben aprovechar las ventajas de la mayor cantidad de recursos informáticos.  
  
3.  El número y tipo de operaciones.  
  
     PLINQ proporciona el operador AsOrdered para situaciones en las que es necesario mantener el orden de los elementos de la secuencia de origen. Hay un costo asociado con la ordenación, pero este costo es normalmente moderado. Operaciones GroupBy y Join también incurren en sobrecarga. PLINQ se comporta mejor si se permite para procesar elementos en la colección de origen en cualquier orden y pasarlos al operador siguiente en cuanto estén listas. Para más información, consulte cómo [conservar el orden en PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
4.  La forma de ejecución de la consulta.  
  
     Si va a almacenar los resultados de una consulta llamando a ToArray o ToList, los resultados de todos los subprocesos paralelos deben combinarse en la estructura de datos único. Esto implica un costo computacional inevitable. Asimismo, si recorrer en iteración los resultados mediante el uso de un bucle foreach (For Each en Visual Basic), los resultados de los subprocesos de trabajo deben serializarse en el subproceso del enumerador. Pero si desea realizar alguna acción en función del resultado de cada subproceso, puede utilizar el método ForAll para realizar este trabajo en varios subprocesos.  
  
5.  El tipo de opciones de combinación.  
  
     PLINQ puede configurarse para ser almacenan en búfer su salida y generar en fragmentos o a la vez después de que el conjunto de resultados completo se genera, o bien en secuencias los resultados individuales se generan. El primer resultado es un menor tiempo de ejecución total y el segundo disminuye la latencia entre los elementos producidos.  Mientras que las opciones de combinación no siempre tienen una repercusión importante en el rendimiento general de las consultas, pueden afectar al rendimiento percibido porque controlan el tiempo que un usuario debe esperar a ver los resultados. Para más información, consulte las [opciones de combinación en PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
6.  El tipo de partición.  
  
     En algunos casos, una consulta PLINQ sobre una colección de origen indizable puede producir en una carga de trabajo desequilibrada. Cuando esto ocurre, es posible que pueda aumentar el rendimiento de las consultas creando un particionador personalizado. Para más información, consulte [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md) (Particionadores personalizados para PLINQ y TPL).  
  
## <a name="when-plinq-chooses-sequential-mode"></a>Cuando elige PLINQ el modo secuencial  
 PLINQ siempre intentará ejecutar una consulta al menos tan rápida como la consulta se ejecutara secuencialmente. Aunque PLINQ no observar computacionalmente son costosas de los delegados de usuario, o tamaño el origen de entrada, buscar para determinada consulta "formas". En concreto, busca operadores de consulta o combinaciones de operadores que normalmente provocan una consulta se ejecute más lentamente en modo paralelo. Cuando encuentra esas formas, PLINQ predeterminada vuelve al modo secuencial.  
  
 Sin embargo, después de medir el rendimiento de una consulta concreta, puede determinar que realmente se ejecuta más rápido en modo paralelo. En tales casos puede usar el <xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType> marca a través de la <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> método para indicar a PLINQ para paralelizar la consulta. Para más información, consulte [Especificación del modo de ejecución en PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
 En la lista siguiente se describe las formas de consulta PLINQ de forma predeterminada se ejecutará en modo secuencial:  
  
-   Las consultas que contienen una instrucción Select, Where indizado, SelectMany indizado o una cláusula ElementAt después de un operador de ordenación o filtrado que ha quitado o reorganizado los índices originales.  
  
-   Consultas que contienen un Take, TakeWhile, Skip, SkipWhile (operador) y donde índices en la secuencia de origen no están en el orden original.  
  
-   Las consultas que contienen Zip o SequenceEquals, a menos que uno de los orígenes de datos tiene un índice ordenado inicialmente y el otro origen de datos sea indizable (es decir, una matriz o IList(T)).  
  
-   Consultas que contienen Concat, a menos que se aplica a los orígenes de datos indizables.  
  
-   Invertir las consultas que contienen, a menos que aplique a un origen de datos indizables.  
  
## <a name="see-also"></a>Vea también  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
