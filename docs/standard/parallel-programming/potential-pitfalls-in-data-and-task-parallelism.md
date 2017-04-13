---
title: "Potential Pitfalls in Data and Task Parallelism | Microsoft Docs"
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
  - "parallel programming, pitfalls"
ms.assetid: 1e357177-e699-4b8f-9e49-56d3513ed128
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Potential Pitfalls in Data and Task Parallelism
En muchos casos, <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> pueden proporcionar mejoras de rendimiento significativas en comparación con los bucles secuenciales normales.  Sin embargo, el trabajo de paralelizar el bucle aporta una complejidad que puede llevar a problemas que, en código secuencial, no son tan comunes o que no se producen en absoluto.  En este tema se indican algunas prácticas que se deben evitar al escribir bucles paralelos.  
  
## No se debe suponer que la ejecución en paralelo es siempre más rápida  
 En algunos casos, un bucle paralelo se podría ejecutar más lentamente que su equivalente secuencial.  La regla básica es que no es probable que los bucles en paralelo que tienen pocas iteraciones y delegados de usuario rápidos aumenten gran cosa la velocidad.  Sin embargo, como son muchos los factores implicados en el rendimiento, recomendamos siempre medir los resultados reales.  
  
## Evitar la escritura en ubicaciones de memoria compartidas  
 En código secuencial, no es raro leer o escribir en variables estáticas o en campos de clase.  Sin embargo, cuando varios subprocesos tienen acceso a estas variables de forma simultánea, hay grandes posibilidades de que se produzcan condiciones de carrera.  Aunque se pueden usar bloqueos para sincronizar el acceso a la variable, el costo de la sincronización puede afectar negativamente al rendimiento.  Por tanto, se recomienda evitar, o al menos limitar, el acceso al estado compartido en un bucle en paralelo en la medida de lo posible.  La manera mejor de hacerlo es mediante las sobrecargas de <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> y <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> que utilizan una variable <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> para almacenar el estado local del subproceso durante la ejecución del bucle.  Para obtener más información, vea [How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) y [How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md).  
  
## Evitar la paralelización excesiva  
 Si usa bucles en paralelo, incurrirá en costos de sobrecarga al crear particiones de la colección de origen y sincronizar los subprocesos de trabajo.  El número de procesadores del equipo reduce también las ventajas de la paralelización.  Si se ejecutan varios subprocesos enlazados a cálculos en un único procesador, no se gana en velocidad.  Por tanto, debe tener cuidado para no paralelizar en exceso un bucle.  
  
 El escenario más común en el que se puede producir un exceso de paralelización son los bucles anidados.  En la mayoría de los casos, es mejor paralelizar únicamente el bucle exterior, a menos que se cumplan una o más de las siguientes condiciones:  
  
-   Se sabe que el bucle interno es muy largo.  
  
-   Se realiza un cálculo caro en cada pedido. \(La operación que se muestra en el ejemplo no es cara.\)  
  
-   Se sabe que el sistema de destino tiene suficientes procesadores como para controlar el número de subprocesos que se producirán al paralelizar la consulta de `cust.Orders`.  
  
 En todos los casos, la mejor manera de determinar la forma óptima de la consulta es mediante la prueba y la medición.  
  
## Evitar llamadas a métodos que no son seguros para subprocesos  
 La escritura en métodos de instancia que no son seguros para subprocesos de un bucle en paralelo puede producir daños en los datos, que pueden pasar o no inadvertidos para el programa.  También puede dar lugar a excepciones.  En el siguiente ejemplo, varios subprocesos estarían intentando llamar simultáneamente al método <xref:System.IO.FileStream.WriteByte%2A?displayProperty=fullName>, lo que no se admite en la clase.  
  
 [!code-csharp[TPL_Pitfalls#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#04)]
 [!code-vb[TPL_Pitfalls#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#04)]  
  
## Limitar las llamadas a métodos seguros para subprocesos  
 La mayoría de los métodos estáticos de .NET Framework son seguros para subprocesos y se les pueden llamar simultáneamente desde varios subprocesos.  Sin embargo, incluso en estos casos, la sincronización que esto supone puede conducir a una ralentización importante en la consulta.  
  
> [!NOTE]
>  Puede comprobarlo si inserta algunas llamadas a <xref:System.Console.WriteLine%2A> en las consultas.  Aunque este método se usa en los ejemplos de la documentación para fines de demostración, no debe usarlo en bucles paralelos a menos que sea necesario.  
  
## Ser consciente de los problemas de afinidad de los subprocesos  
 Algunas tecnologías, como la interoperabilidad COM para componentes STA \(contenedor uniproceso\), Windows Forms y Windows Presentation Foundation \(WPF\), imponen restricciones de afinidad de subprocesos que exigen que el código se ejecute en un subproceso determinado.  Por ejemplo, tanto en Windows Forms como en WPF, solo se puede tener acceso a un control en el subproceso donde se creó.  Por ejemplo, esto significa que no puede actualizar un control de lista desde un bucle paralelo a menos que configure el programador del subproceso para que programe trabajo solo en el subproceso de la interfaz de usuario.  Para obtener más información, vea [How to: Schedule Work on the User Interface \(UI\) Thread](../Topic/How%20to:%20Schedule%20Work%20on%20the%20User%20Interface%20\(UI\)%20Thread.md).  
  
## Tener precaución cuando se espera en delegados a los que llama Parallel.Invoke  
 En algunas circunstancias, Task Parallel Library incluirá una tarea, lo que significa que se ejecuta en la tarea del subproceso que se está ejecutando actualmente. \(Para obtener más información, vea [Task Schedulers](../Topic/Task%20Schedulers.md)\). Esta optimización de rendimiento puede acabar en interbloqueo en algunos casos.  Por ejemplo, dos tareas podrían ejecutar el mismo código de delegado, que señala cuándo se genera un evento, y después esperar a que la otra tarea señale.  Si la segunda tarea está alineada en el mismo subproceso que la primera y la primero entra en un estado de espera, la segunda tarea nunca podrá señalar su evento.  Para evitar que suceda, puede especificar un tiempo de espera en la operación de espera o utilizar constructores de subproceso explícitos para ayudar a asegurarse de que una tarea no puede bloquear la otra.  
  
## No se debe suponer que las iteraciones de ForEach, For y ForAll siempre se ejecutan en paralelo  
 Es importante tener presente que las iteraciones individuales de un bucle <xref:System.Threading.Tasks.Parallel.For%2A>, <xref:System.Threading.Tasks.Parallel.ForEach%2A> o <xref:System.Linq.ParallelEnumerable.ForAll%2A> tal vez no tengan que ejecutarse en paralelo.  Por consiguiente, se debe evitar escribir código cuya exactitud dependa de la ejecución en paralelo de las iteraciones o de la ejecución de las iteraciones en algún orden concreto.  Por ejemplo, es probable que este código lleve a un interbloqueo:  
  
 [!code-csharp[TPL_Pitfalls#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#01)]
 [!code-vb[TPL_Pitfalls#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#01)]  
  
 En este ejemplo, una iteración establece un evento y el resto de las iteraciones esperan el evento.  Ninguna de las iteraciones que esperan puede completarse hasta que se haya completado la iteración del valor de evento.  Sin embargo, es posible que las iteraciones que esperan bloqueen todos los subprocesos que se utilizan para ejecutar el bucle paralelo, antes de que la iteración del valor de evento haya tenido oportunidad de ejecutarse.  Esto produce un interbloqueo: la iteración del valor de evento nunca se ejecutará y las iteraciones que esperan nunca se activarán.  
  
 En concreto, una iteración de un bucle paralelo no debe esperar nunca otra iteración del bucle para progresar.  Si el bucle paralelo decide programar las iteraciones secuencialmente pero en el orden contrario, se producirá un interbloqueo.  
  
## Evitar la ejecución de bucles en paralelo en el subproceso de la interfaz de usuario  
 Es importante mantener la interfaz de usuario de la aplicación \(UI\) capaz de reaccionar.  Si una operación contiene bastante trabajo para garantizar la paralelización, no se debería ejecutar en el subproceso de la interfaz de usuario.  Conviene descargarla para que se ejecute en un subproceso en segundo plano.  Por ejemplo, si desea utilizar un bucle paralelo para calcular datos que después se presentarán en un control de IU, considere ejecutar el bucle dentro de una instancia de la tarea, en lugar de directamente en un controlador de eventos de IU.  Solo si el cálculo básico se ha completado se deberían calcular las referencias de la actualización de nuevo en el subproceso de la interfaz de usuario.  
  
 Si ejecuta bucles paralelos en el subproceso de la interfaz de usuario, tenga el cuidado de evitar la actualización de los controles de la interfaz de usuario desde el interior del bucle.  Si se intenta actualizar los controles de la interfaz de usuario desde dentro de un bucle paralelo que se está ejecutando en el subproceso de la interfaz de usuario, se puede llegar a dañar el estado, a producir excepciones, actualizaciones atrasadas e incluso interbloqueos, dependiendo de cómo se invoque la actualización de la interfaz de usuario.  En el siguiente ejemplo, el bucle paralelo bloquea el subproceso de la interfaz de usuario en el que se está ejecutando hasta que todas las iteraciones se completan.  Sin embargo, si se está ejecutando una iteración del bucle en un subproceso en segundo plano \(como puede hacer <xref:System.Threading.Tasks.Parallel.For%2A>\), la llamada a Invoke produce que se envíe un mensaje al subproceso de la interfaz de usuario, que se bloquea mientras espera a que ese mensaje se procese.  Puesto que se bloquea el subproceso de la interfaz de usuario cuando se ejecuta <xref:System.Threading.Tasks.Parallel.For%2A>, el mensaje no se procesa nunca y el subproceso de la interfaz de usuario se interbloquea.  
  
 [!code-csharp[TPL_Pitfalls#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#02)]
 [!code-vb[TPL_Pitfalls#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#02)]  
  
 En el siguiente ejemplo se muestra cómo evitar el interbloqueo mediante la ejecución del bucle dentro de una instancia de la tarea.  El bucle no bloquea el subproceso de la interfaz de usuario y se puede procesar el mensaje.  
  
 [!code-csharp[TPL_Pitfalls#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#03)]
 [!code-vb[TPL_Pitfalls#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#03)]  
  
## Vea también  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [Potential Pitfalls with PLINQ](../../../docs/standard/parallel-programming/potential-pitfalls-with-plinq.md)   
 [Modelos de programación paralela: Patrones de introducción y que aplican paralelas con .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=185142)