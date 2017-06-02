---
title: "Understanding Speedup in PLINQ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "PLINQ queries, performance tuning"
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Understanding Speedup in PLINQ
El objetivo principal de PLINQ es acelerar la ejecución de LINQ to Objects mediante la ejecución de los delegados de consulta en paralelo en equipos multiprocesador.  El rendimiento de PLINQ es óptimo cuando el procesamiento de cada elemento de una colección de origen es independiente, y no se comparte el estado entre los delegados individuales.  Esas operaciones son comunes en LINQ to Objects y PLINQ, y se prestan con facilidad a la programación en varios subprocesos, por lo que se conocen como "*perfectamente paralelas*".  Sin embargo, no todas las consultas se componen de operaciones paralelas perfectas; en la mayoría de los casos, una consulta incluye operadores que no se pueden paralelizar o que ralentizan la ejecución en paralelo.  Incluso con consultas que son perfectamente paralelas, PLINQ debe crear particiones del origen de datos y programar el trabajo en los subprocesos, y generalmente tiene que combinar los resultados cuando la consulta se completa.  Todas estas operaciones aumentan el costo computacional de la paralelización; el costo de agregar paralelización se denomina *sobrecarga*.  Para lograr el rendimiento óptimo en una consulta PLINQ, el objetivo es maximizar las partes que son perfectamente paralelas y minimizar las que requieren sobrecarga.  En este artículo se proporciona información que le ayudará a escribir consultas PLINQ lo más eficaces posible y que además produzcan resultados correctos.  
  
## Factores que afectan al rendimiento de las consultas PLINQ  
 En las siguientes secciones se enumeran algunos de los factores más importantes que influyen en el rendimiento de las consultas en paralelo.  Son instrucciones generales que por sí solas no bastan para predecir el rendimiento de las consultas en todos los casos.  Como siempre, es importante medir el rendimiento real de consultas concretas en equipos con una gama de cargas y configuraciones representativas.  
  
1.  Costo computacional del trabajo total.  
  
     Para lograr velocidad, una consulta PLINQ debe tener bastante trabajo perfectamente en paralelo como para compensar la sobrecarga.  El trabajo se puede expresar como el costo computacional de cada delegado multiplicado por el número de elementos de la colección de origen.  Suponiendo que una operación se pueda paralelizar, cuanto más cara sea computacionalmente, más oportunidad hay de aumentar la velocidad.  Por ejemplo, si una función tarda un milisegundo en ejecutarse, una consulta secuencial de más de 1000 elementos tardará un segundo en realizar esa operación, mientras que una consulta paralela en un equipo con cuatro núcleos solo tardaría 250 milisegundos.  Esto supone 750 milisegundos menos.  Si la función tardara un segundo en ejecutar cada elemento, el aumento sería de 750 segundos.  Si el delegado resulta muy caro, PLINQ podría proporcionar un aumento significativo con solo unos elementos de la colección de origen.  A la inversa, las colecciones de origen pequeñas con delegados triviales no son, en general, buenas candidatas para PLINQ.  
  
     En el siguiente ejemplo, queryA es probablemente buena candidata para PLINQ, suponiendo que su función select implica mucho trabajo. queryB no es probablemente buena candidata porque no hay bastante trabajo en la instrucción select, y la sobrecarga de la paralelización compensará la mayoría o todo\).  
  
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
  
2.  Número de núcleos lógicos del sistema \(grado de paralelismo\).  
  
     Este punto es un corolario obvio de la sección anterior. Las consultas que están perfectamente en paralelo se ejecutan más rápidamente en equipos con más núcleos porque se puede dividir el trabajo entre más subprocesos simultáneos.  La cantidad total de aumento de velocidad depende del porcentaje del trabajo total de la consulta que se puede paralelizar.  Sin embargo, no se debe dar por supuesto que todas las consultas se ejecutarán el doble de rápido en un equipo de ocho núcleos que en uno de cuatro.  Al refinar las consultas para lograr el rendimiento óptimo, es importante medir los resultados reales en equipos con varios núcleos.  Este punto se relaciona con el punto 1: se necesitan conjuntos de datos mayores para aprovechar los grandes recursos informáticos.  
  
3.  Número y tipo de operaciones.  
  
     PLINQ proporciona el operador AsOrdered para las situaciones en las que es necesario mantener el orden de elementos de la secuencia de origen.  Hay un costo asociado a la ordenación, pero suele ser reducido.  Las operaciones GroupBy y Join también incurren en sobrecarga.  PLINQ rinde mejor cuando puede procesar los elementos de la colección de origen en cualquier orden y pasarlos al operador siguiente en cuanto están listos.  Para obtener más información, vea [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).  
  
4.  Forma de ejecución de la consulta.  
  
     Si se guardan los resultados de una consulta llamando a ToArray o ToList, los resultados de todos los subprocesos paralelos deben combinarse en la estructura de datos única.  Esto implica un costo computacional inevitable.  De igual modo, si se recorren los resultados con un bucle foreach \(For Each en Visual Basic\), hay que serializar los resultados de los subprocesos de trabajo en el subproceso del enumerador.  Pero si solo desea realizar una acción basada en el resultado de cada subproceso, puede utilizar el método ForAll para realizar este trabajo en varios subprocesos.  
  
5.  Tipo de opciones de combinación.  
  
     PLINQ se puede configurar para almacenar en búfer el resultado y producirlo en fragmentos o todo a la vez cuando el conjunto de resultados esté completo, o transmitir en secuencias los resultados individuales a medida que se van produciendo.  El primer resultado disminuye el tiempo de ejecución total y el segundo disminuye la latencia entre los elementos producidos.  Aunque las opciones de combinación no siempre tienen un efecto importante en el rendimiento global de las consultas, pueden influir en el rendimiento percibido, ya que controlan cuánto tiempo debe esperar un usuario para ver los resultados.  Para obtener más información, vea [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md).  
  
6.  Tipo de creación de particiones.  
  
     En algunos casos, una consulta PLINQ sobre una colección de origen indizable puede producir una carga de trabajo desequilibrada.  Cuando suceda, tal vez logre aumentar el rendimiento de las consultas creando un particionador personalizado.  Para obtener más información, vea [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md).  
  
## Cuándo elige PLINQ el modo secuencial  
 PLINQ siempre intentará ejecutar una consulta con la misma rapidez que si la consulta se ejecutara secuencialmente.  Aunque PLINQ no tenga en cuenta en el costo computacional de los delegados de usuario ni el tamaño del origen de entrada, sí busca ciertas "formas" de consulta.  Específicamente, busca operadores de consulta o combinaciones de operadores que hacen que normalmente una consulta se ejecute más despacio en modo paralelo.  Cuando encuentra esas formas, PLINQ vuelve de forma predeterminada al modo secuencial.  
  
 Sin embargo, después de medir el rendimiento de una consulta concreta, puede determinar que realmente se ejecuta más rápidamente en modo paralelo.  En casos así puede utilizar la marca <xref:System.Linq.ParallelExecutionMode?displayProperty=fullName> a través del método <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> para indicar a PLINQ que paralelice la consulta.  Para obtener más información, vea [How to: Specify the Execution Mode in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md).  
  
 La siguiente lista describe las formas de consulta que PLINQ ejecutará de forma predeterminada en modo secuencial:  
  
-   Consultas que contienen Select, Where indizado, SelectMany indizado o una cláusula ElementAt después de un operador de clasificación o de filtrado que ha quitado o reorganizado los índices originales.  
  
-   Consultas que contienen un operador Take, TakeWhile, Skip, SkipWhile y donde los índices de la secuencia de origen no están en el orden original.  
  
-   Consultas que contienen zip o SequenceEquals, a menos que uno de los orígenes de datos tenga un índice ordenado inicialmente y el otro origen de datos sea indizable \(es decir una matriz o IList \(T\)\).  
  
-   Consultas que contienen Concat, a menos que se apliquen a orígenes de datos indizables.  
  
-   Consultas que contienen Reverse, a menos que se apliquen a un origen de datos indizable.  
  
## Vea también  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)