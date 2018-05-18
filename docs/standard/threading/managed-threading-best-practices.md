---
title: Procedimientos recomendados para el subprocesamiento administrado
ms.date: 11/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threading [.NET Framework], design guidelines
- threading [.NET Framework], best practices
- managed threading
ms.assetid: e51988e7-7f4b-4646-a06d-1416cee8d557
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15261291f40b6a41e0d6033fb92e1b23b4042019
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="managed-threading-best-practices"></a>Procedimientos recomendados para el subprocesamiento administrado
El multithreading requiere que la programación sea cuidadosa. La complejidad de muchas tareas se puede reducir poniendo las solicitudes de ejecución en cola por subprocesos del grupo de subprocesos. En este tema se tratan situaciones más complicadas, como coordinar el trabajo de múltiples subprocesos, o controlar los subprocesos que se bloquean.  
  
> [!NOTE]
> A partir de NET Framework 4, la biblioteca TPL y PLINQ proporcionan API que reducen parte de la complejidad y los riesgos que entraña la programación multiproceso. Para más información, consulte [Programación en paralelo en .NET](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="deadlocks-and-race-conditions"></a>Interbloqueos y condiciones de carrera  
 El multithreading resuelve problemas de rendimiento y de capacidad de respuesta, pero al hacerlo también crea nuevos problemas, como interbloqueos y condiciones de carrera.  
  
### <a name="deadlocks"></a>Interbloqueos  
 Un interbloqueo tiene lugar cuando dos subprocesos intentan bloquear un recurso que ya ha bloqueado uno de estos subprocesos. Ninguno de los subprocesos puede avanzar.  
  
 Muchos métodos de las clases del subprocesamiento administrado ofrecen tiempos de espera que se utilizan para detectar interbloqueos. Por ejemplo, con el siguiente código se intenta obtener un bloqueo en un objeto llamado `lockObject`. Si el bloqueo no se consigue en 300 milisegundos, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> devuelve el valor `false`.  
  
```vb  
If Monitor.TryEnter(lockObject, 300) Then  
    Try  
        ' Place code protected by the Monitor here.  
    Finally  
        Monitor.Exit(lockObject)  
    End Try  
Else  
    ' Code to execute if the attempt times out.  
End If  
```  
  
```csharp  
if (Monitor.TryEnter(lockObject, 300)) {  
    try {  
        // Place code protected by the Monitor here.  
    }  
    finally {  
        Monitor.Exit(lockObject);  
    }  
}  
else {  
    // Code to execute if the attempt times out.  
}  
```  
  
### <a name="race-conditions"></a>Condiciones de carrera  
 Una condición de carrera es un error que se produce cuando el resultado de un programa depende del primero de dos o más subprocesos que consiga llegar hasta un bloque específico de código. Ejecutar el programa muchas veces genera distintos resultados y no es posible predecir el resultado de una ejecución específica.  
  
 Un ejemplo sencillo de una condición de carrera es el incremento de un campo. Suponga una clase que tiene un campo privado **static** (**Shared** en Visual Basic) que se incrementa cada vez que se crea una instancia de la clase, mediante código como `objCt++;` (C#) o `objCt += 1` (Visual Basic). Esta operación requiere cargar el valor de `objCt` en un registro, incrementar el valor y almacenarlo en `objCt`.  
  
 En una aplicación multiproceso, un subproceso que realiza los tres pasos puede adelantar al subproceso que ha cargado e incrementado el valor; cuando el primer subproceso reanuda la ejecución y almacena su valor, sobrescribe `objCt` sin tener en cuenta el hecho de que el valor ha cambiado mientras tanto.  
  
 Para evitar fácilmente esta condición de carrera determinada, utilice los métodos de la clase <xref:System.Threading.Interlocked>, como <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>. Para más información sobre otras técnicas de sincronización de datos entre varios subprocesos, consulte [Sincronización de datos para multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md).  
  
 También se pueden producir condiciones de carrera al sincronizar las actividades de varios subprocesos. Siempre que escriba una línea de código, debe tener en cuenta qué puede ocurrir si otro subproceso adelanta a un subproceso antes de ejecutar la línea (o antes de cualquiera de las instrucciones máquina que forman la línea).  
  
## <a name="number-of-processors"></a>Número de procesadores  
 La mayoría de los equipos tienen ahora varios procesadores (también llamados núcleos), incluso los pequeños dispositivos como tabletas y teléfonos. Si está desarrollando software que también se ejecutará en equipos con un solo procesador, tenga en cuenta que el multithreading resuelve distintos problemas en equipos con varios procesadores y en equipos con un solo procesador.  
  
### <a name="multiprocessor-computers"></a>Equipos multiprocesador  
 El multithreading proporciona un mayor rendimiento. Diez procesadores pueden hacer diez veces el trabajo de uno, pero sólo si el trabajo se divide de forma que los diez trabajen al mismo tiempo; los subprocesos proporcionan una forma fácil de dividir el trabajo y de aprovechar la eficacia de procesamiento adicional. Si utiliza el multithreading en un equipo multiprocesador:  
  
-   El número de subprocesos que se pueden ejecutar de forma simultánea está limitado por el número de procesadores.  
  
-   Sólo se ejecuta un subproceso en segundo plano si el número de subprocesos que se ejecutan en primer plano es menor que el número de procesadores.  
  
-   Cuando se llama al método <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> en un subproceso, ese subproceso se puede ejecutar o no inmediatamente dependiendo del número de procesadores y de subprocesos en espera de ejecución.  
  
-   Las condiciones de carrera se pueden producir no sólo debido a las prioridades imprevistas de subprocesos, sino también porque dos subprocesos que se ejecutan en procesadores diferentes pueden competir para alcanzar el mismo bloque de código.  
  
### <a name="single-processor-computers"></a>Equipos de un solo procesador  
 El multithreading ofrece una gran capacidad de respuesta al usuario del equipo, y utiliza el tiempo de inactividad para realizar tareas en segundo plano. Si utiliza el multithreading en un equipo de un solo procesador:  
  
-   Sólo se ejecuta un subproceso cada vez.  
  
-   Se ejecuta un subproceso en segundo plano sólo cuando el subproceso principal del usuario está inactivo. Un subproceso en primer plano que se ejecuta continuamente agota el tiempo de procesador de los subprocesos en segundo plano.  
  
-   Cuando se llama al método <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> en un subproceso, ese subproceso no se ejecuta hasta que el subproceso en curso le cede la ejecución o es relegado por el sistema operativo.  
  
-   Generalmente, las condiciones de carrera se producen debido a que el programador no tuvo en cuenta el hecho de que un subproceso puede ser adelantado por otro en un momento difícil permitiendo, algunas veces, que otro subproceso llegue el primero al bloque de código.  
  
## <a name="static-members-and-static-constructors"></a>Miembros estáticos y constructores estáticos  
 No se inicializa una clase hasta que su constructor de clase (constructor`static` en C#, `Shared Sub New` en Visual Basic) haya terminado de ejecutarse. Para evitar la ejecución de código en un tipo no inicializado, Common Language Runtime bloquea todas las llamadas de otros subprocesos a los miembros `static` de la clase (miembros`Shared` en Visual Basic) hasta que el constructor de clase termina de ejecutarse.  
  
 Por ejemplo, si un constructor de clase inicia un nuevo subproceso, y el procedimiento del subproceso llama a un miembro `static` de la clase, el nuevo subproceso se bloquea hasta que el constructor de clase finalice.  
  
 Esto se aplica a cualquier tipo que pueda tener un constructor `static`.  
  
## <a name="general-recommendations"></a>Recomendaciones generales  
 Tenga en cuenta las siguientes instrucciones cuando utilice varios subprocesos:  
  
-   No utilice <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> para finalizar otros subprocesos. Una llamada a **Abort** en otro subproceso es similar a iniciar una excepción en ese subproceso, sin conocer qué punto ha alcanzado en su procesamiento.  
  
-   No utilice <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> ni <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType> para sincronizar las actividades de varios subprocesos. Utilice <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.Monitor>.  
  
-   No controle la ejecución de subprocesos de trabajo desde el programa principal (con eventos, por ejemplo). En su lugar, diseñe un programa de forma que los subprocesos de trabajo sean los que tengan que esperar hasta que haya trabajo disponible, lo ejecuten y notifiquen su finalización a otras partes del programa. Si los subprocesos de trabajo no se bloquean, puede ser conveniente usar subprocesos del grupo de subprocesos. <xref:System.Threading.Monitor.PulseAll%2A?displayProperty=nameWithType> resulta útil en aquellas situaciones en las que los subprocesos de trabajo se bloquean.  
  
-   No utilice los tipos como objetos de bloqueo. Es decir, evite código como `lock(typeof(X))` en C# o `SyncLock(GetType(X))` en Visual Basic o el uso de <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> con objetos <xref:System.Type>. Para un tipo determinado, hay sólo una instancia de <xref:System.Type?displayProperty=nameWithType> por el dominio de aplicación. Si el tipo que quiere bloquear es público, codifique uno que su tipo no pueda bloquear, para evitar interbloqueos. Para otros problemas, consulte [Procedimientos recomendados para la confiabilidad](../../../docs/framework/performance/reliability-best-practices.md).  
  
-   Tenga cuidado al efectuar bloqueos en instancias, por ejemplo `lock(this)` en C# o `SyncLock(Me)` en Visual Basic. Si otra parte del código de la aplicación, ajeno al tipo, bloquea el objeto, podrían producirse interbloqueos.  
  
-   Asegúrese de que un subproceso que entra en un monitor siempre sale de ese monitor, aun en el caso de que se produzca una excepción mientras el subproceso se encuentra en el monitor. La instrucción [lock](~/docs/csharp/language-reference/keywords/lock-statement.md) de C# y la instrucción [SyncLock](~/docs/visual-basic/language-reference/statements/synclock-statement.md) de Visual Basic ofrecen automáticamente este comportamiento mediante un bloque **finally** que garantiza la llamada a <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>. Si no está seguro de que se llamará a **Exit**, considere la posibilidad de cambiar el diseño con el fin de usar **Mutex**. Una zona de exclusión mutua se libera automáticamente cuando finaliza el subproceso al que pertenece.  
  
-   Utilice varios subprocesos para tareas que requieren recursos diferentes, y evite asignar varios subprocesos a un solo recurso. Por ejemplo, en tareas que impliquen beneficios de E/S por tener un subproceso propio, ya que ese subproceso se bloquea durante las operaciones de E/S y, de este modo, permite ejecutar otros subprocesos. Los datos proporcionados por el usuario son otro recurso que se beneficia de la utilización de un subproceso dedicado. En un equipo de un solo procesador, una tarea que implica un cálculo intensivo coexiste con los datos proporcionados por el usuario y con tareas que implican la E/S, pero varias tareas de cálculo intensivo compiten entre ellas.  
  
-   Considere la posibilidad de utilizar métodos de la clase <xref:System.Threading.Interlocked> para los cambios de estado simples, en lugar de utilizar la instrucción `lock` (`SyncLock` en Visual Basic). La instrucción `lock` es una buena herramienta de uso general, pero la clase <xref:System.Threading.Interlocked> genera mejor rendimiento para las actualizaciones que deben ser atómicas. Internamente, ejecuta un solo prefijo de bloqueo si no hay contención. En las revisiones de código, inspeccione código similar al que se muestra en los ejemplos siguientes. En el primer ejemplo, se incrementa una variable de estado:  
  
    ```vb  
    SyncLock lockObject  
        myField += 1  
    End SyncLock  
    ```  
  
    ```csharp  
    lock(lockObject)   
    {  
        myField++;  
    }  
    ```  
  
     Para mejorar el rendimiento, utilice el método <xref:System.Threading.Interlocked.Increment%2A> en lugar de la instrucción `lock`, de la siguiente manera:  
  
    ```vb  
    System.Threading.Interlocked.Increment(myField)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.Increment(myField);  
    ```  
  
    > [!NOTE]
    >  En la versión 2.0 de .NET Framework, el método <xref:System.Threading.Interlocked.Add%2A> proporciona actualizaciones atómicas en incrementos mayores que 1.  
  
     En el segundo ejemplo, se actualiza una variable de tipo de referencia sólo si es una referencia nula (`Nothing` en Visual Basic).  
  
    ```vb  
    If x Is Nothing Then  
        SyncLock lockObject  
            If x Is Nothing Then  
                x = y  
            End If  
        End SyncLock  
    End If  
    ```  
  
    ```csharp  
    if (x == null)  
    {  
        lock (lockObject)  
        {  
            if (x == null)  
            {  
                x = y;  
            }  
        }  
    }  
    ```  
  
     Se puede mejorar el rendimiento utilizando el método <xref:System.Threading.Interlocked.CompareExchange%2A> de la siguiente manera:  
  
    ```vb  
    System.Threading.Interlocked.CompareExchange(x, y, Nothing)  
    ```  
  
    ```csharp  
    System.Threading.Interlocked.CompareExchange(ref x, y, null);  
    ```  
  
    > [!NOTE]
    >  En la versión 2.0 de .NET Framework, el método <xref:System.Threading.Interlocked.CompareExchange%2A> tiene una sobrecarga genérica que se puede utilizar para el reemplazo con seguridad de tipos de cualquier tipo de referencia.  
  
## <a name="recommendations-for-class-libraries"></a>Recomendaciones para las bibliotecas de clases  
 Tenga en cuenta las instrucciones siguientes cuando diseñe bibliotecas de clases para el multithreading:  
  
-   Evite la necesidad de sincronización si es posible. Esto se aplica especialmente en el caso de código muy utilizado. Por ejemplo, se podría ajustar un algoritmo de modo que tolere una condición de carrera en lugar de eliminarla. La sincronización innecesaria disminuye el rendimiento y crea la posibilidad de interbloqueos y condiciones de carrera.  
  
-   Procure que los datos estáticos (`Shared` en Visual Basic) sean seguros para subprocesos de manera predeterminada.  
  
-   No convierta los datos de instancia en datos seguros para subprocesos de manera predeterminada. Al agregar bloqueos para crear código seguro para subprocesos, se reduce el rendimiento, se incrementa la contención de bloqueos y se crea la posibilidad de que se produzcan interbloqueos. En los modelos de aplicación comunes, sólo un subproceso a la vez ejecuta código de usuario, lo que minimiza la necesidad de la seguridad para subprocesos. Por esta razón, las bibliotecas de clases de .NET Framework no son seguras para subprocesos de forma predeterminada.  
  
-   Evite proporcionar métodos estáticos que alteren el estado estático. En escenarios de servidor comunes, el estado estático se comparte entre las solicitudes, lo que significa que varios subprocesos pueden ejecutar a la vez ese código. De este modo, se abre la posibilidad de errores de subprocesos. Considere la posibilidad de utilizar un modelo de diseño que encapsule los datos en instancias no compartidas por las solicitudes. Además, si se sincronizan los datos estáticos, las llamadas entre los métodos estáticos que modifican el estado pueden generar interbloqueos o sincronización redundante, lo que afecta negativamente al rendimiento.  
  
## <a name="see-also"></a>Vea también  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Subprocesos y subprocesamiento](../../../docs/standard/threading/threads-and-threading.md)
