---
title: "(Visual Basic) de sincronización de subprocesos | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 04f485d1-8333-4510-9e72-c334e7427e7e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ec8fa89c8921eadee428a90971d9ae4ce305a109
ms.lasthandoff: 03/13/2017

---
# <a name="thread-synchronization-visual-basic"></a>Sincronización de subprocesos (Visual Basic)
Las secciones siguientes describen las características y clases que pueden utilizar para sincronizar el acceso a los recursos en aplicaciones multiproceso.  
  
 Una de las ventajas de usar varios subprocesos en una aplicación es que cada subproceso se ejecuta de forma asincrónica. Aplicaciones para Windows, esto permite que las tareas largas que se realice en segundo plano mientras la ventana de la aplicación y controles siguen respondiendo. Servidor de aplicaciones, subprocesamiento múltiple proporciona la capacidad de controlar cada solicitud entrante con un subproceso diferente. De lo contrario, podría no obtener atiende cada nueva solicitud hasta que se hubiera satisfecho totalmente la solicitud anterior.  
  
 Sin embargo, la naturaleza asincrónica de los subprocesos significa que el acceso a recursos como identificadores de archivos, conexiones de red y memoria debe ser coordinada. De lo contrario, dos o más subprocesos podrían acceso al mismo recurso al mismo tiempo, cada uno desprevenido de las acciones del otro. El resultado es impredecible datos dañados.  
  
 Para las operaciones simples en tipos de datos numéricos enteros, sincronización de subprocesos se puede lograr con miembros de la <xref:System.Threading.Interlocked>clase.</xref:System.Threading.Interlocked> Para todos los demás datos de tipos y recursos no es seguro para subprocesos, subprocesamiento múltiple sólo pueden segura realizarse utilizando las estructuras de este tema.  
  
 Para obtener información general sobre la programación multiproceso, vea:  
  
-   [Conceptos básicos del subprocesamiento administrado](http://msdn.microsoft.com/library/b2944911-0e8f-427d-a8bb-077550618935)  
  
-   [Utilizar subprocesos y subprocesamiento](http://msdn.microsoft.com/library/9b5ec2cd-121b-4d49-b075-222cf26f2344)  
  
-   [Procedimientos recomendados para el subprocesamiento administrado](http://msdn.microsoft.com/library/e51988e7-7f4b-4646-a06d-1416cee8d557)  
  
## <a name="the-lock-and-synclock-keywords"></a>El bloqueo de palabras clave y SyncLock  
 Visual Basic `SyncLock` instrucción puede utilizarse para asegurarse de que un bloque de código se ejecuta hasta completarse sin interrupción por otros subprocesos. Esto se logra obteniendo un bloqueo de exclusión mutua para un objeto determinado para la duración del bloque de código.  
  
 Un `SyncLock` instrucción se le asigna un objeto como argumento y va seguido de un bloque de código que se ejecuta sólo un subproceso a la vez. Por ejemplo:  
  
```vb  
Public Class TestThreading  
    Dim lockThis As New Object  
  
    Public Sub Process()  
        SyncLock lockThis  
            ' Access thread-sensitive resources.  
        End SyncLock  
    End Sub  
End Class  
```  
  
 El argumento proporcionado para el `SyncLock` palabra clave debe ser un objeto basado en un tipo de referencia y se utiliza para definir el ámbito del bloqueo. En el ejemplo anterior, el ámbito del bloqueo se limita a esta función porque no hay referencias al objeto `lockThis` existe fuera de la función. Si dicha referencia existía, ámbito del bloqueo se extendería a ese objeto. Estrictamente, el objeto proporcionado se utiliza únicamente para identificar el recurso que se comparte entre varios subprocesos, por lo que puede ser una instancia de clase arbitraria. En la práctica, sin embargo, este objeto normalmente representa el recurso para el subproceso que la sincronización es necesaria. Por ejemplo, si es un objeto contenedor que va a usar varios subprocesos, a continuación, se puede pasar el contenedor para bloquear y el bloque de código sincronizado sigue el bloqueo podría tener acceso al contenedor. Siempre que otros subprocesos bloqueen el mismo contenedor antes de tener acceso y acceso al objeto se sincroniza de forma segura.  
  
 Generalmente, es mejor evitar el bloqueo en un `public` tipo, o en instancias de objeto más allá del control de la aplicación. Por ejemplo, `lockThis` puede ser problemática si la instancia es accesible públicamente, porque podría impedir el código fuera de su control en el objeto. Esto podría crear situaciones de interbloqueo que esperan a que dos o más subprocesos para la versión del mismo objeto. El bloqueo de un tipo de datos público, en lugar de un objeto, puede producir problemas por la misma razón. Bloqueo de cadenas literales es especialmente arriesgado porque las cadenas literales *aplicado el método Intern* por common language runtime (CLR). Esto significa que hay una instancia de una cadena determinada literal para todo el programa, exactamente el mismo objeto representa el literal en todos con dominios de aplicación, todos los subprocesos. Como resultado, colocar un bloqueo en una cadena con el mismo contenido en cualquier parte en los bloqueos de procesos de aplicación todas las instancias de esa cadena en la aplicación. Como resultado, es mejor bloquear a un miembro privado o protegido que se aplica el método Intern no. Algunas clases proporcionan a miembros específicamente para bloquear. El <xref:System.Array>tipo, por ejemplo, proporciona <xref:System.Array.SyncRoot%2A>.</xref:System.Array.SyncRoot%2A> </xref:System.Array> Muchos tipos de colección proporcionan un `SyncRoot` miembro también.  
  
 Para obtener más información acerca de la `SyncLock` instrucción, vea los temas siguientes:  
  
-   [SyncLock (instrucción)](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a>Monitores  
 Como el `SyncLock` (palabra clave), los monitores evitan que bloques de código de ejecución simultánea de varios subprocesos. El <xref:System.Threading.Monitor.Enter%2A>método permite que un solo subproceso continuar con las instrucciones siguientes; todos los demás subprocesos se bloquean hasta que el subproceso de ejecución llama a <xref:System.Threading.Monitor.Exit%2A>.</xref:System.Threading.Monitor.Exit%2A> </xref:System.Threading.Monitor.Enter%2A> Esto es similar a utilizar el `SyncLock` (palabra clave). Por ejemplo:  
  
```vb  
SyncLock x  
    DoSomething()  
End SyncLock  
```  
  
 Esto es equivalente a:  
  
```vb  
Dim obj As Object = CType(x, Object)  
System.Threading.Monitor.Enter(obj)  
Try  
    DoSomething()  
Finally  
    System.Threading.Monitor.Exit(obj)  
End Try  
```  
  
 Mediante la `SyncLock` palabra clave normalmente es preferible usar respecto al uso de la <xref:System.Threading.Monitor>clase directamente, ambos porque `SyncLock` es más conciso y porque `SyncLock` garantiza que se libera el monitor subyacente aunque el código protegido produzca una excepción.</xref:System.Threading.Monitor> Esto se logra con la `Finally` (palabra clave), que ejecuta su bloque de código asociado independientemente de si se produce una excepción.  
  
## <a name="synchronization-events-and-wait-handles"></a>Eventos de sincronización y controladores de espera  
 Uso de un bloqueo o un monitor es útil para evitar la ejecución simultánea de subproceso de bloques de código, pero estas construcciones no permiten que un subproceso comunique un evento a otro. Esto requiere *eventos de sincronización*, que son objetos que tienen uno de dos Estados, señalizado y no señalizado, que se puede utilizar para activar y suspender subprocesos. Subprocesos se pueden suspender haciendo que esperen en un evento de sincronización que está señalado y se pueden activar cambiando el estado del evento en señalado. Si un subproceso intenta esperar en un evento que se ha señalado, el subproceso se sigue ejecutando sin retraso.  
  
 Hay dos tipos de eventos de sincronización: <xref:System.Threading.AutoResetEvent>y <xref:System.Threading.ManualResetEvent>.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent> Sólo se diferencian en que <xref:System.Threading.AutoResetEvent>cambios de señalen a no señalizado automáticamente cada vez que se activa un subproceso.</xref:System.Threading.AutoResetEvent> Por el contrario, un <xref:System.Threading.ManualResetEvent>permite cualquier número de subprocesos esté activado si su estado es señalizado y sólo vuelve a una no señalizado estado cuando su <xref:System.Threading.EventWaitHandle.Reset%2A>se llama al método.</xref:System.Threading.EventWaitHandle.Reset%2A> </xref:System.Threading.ManualResetEvent>  
  
 Pueden hacer que los subprocesos esperen en eventos llamando a una de los métodos de espera, como <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, o <xref:System.Threading.WaitHandle.WaitAll%2A>.</xref:System.Threading.WaitHandle.WaitAll%2A> </xref:System.Threading.WaitHandle.WaitAny%2A> </xref:System.Threading.WaitHandle.WaitOne%2A> <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName>hace que el subproceso debe esperar hasta que se señalice un único evento, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName>bloquea un subproceso hasta que se señalen uno o más eventos, y <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName>bloquea el subproceso hasta que todos los eventos indicados se señalen.</xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> </xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName></xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName> Un evento se señaliza cuando su <xref:System.Threading.EventWaitHandle.Set%2A>se llama al método.</xref:System.Threading.EventWaitHandle.Set%2A>  
  
 En el ejemplo siguiente, se crea un subproceso y se inicia por la `Main` (función). El nuevo subproceso espera en un evento utilizando la <xref:System.Threading.WaitHandle.WaitOne%2A>método.</xref:System.Threading.WaitHandle.WaitOne%2A> Se suspende el subproceso hasta que se señaliza el evento por el subproceso principal que se está ejecutando el `Main` (función). Una vez que se señala el evento, se devuelve el subproceso auxiliar. En este caso, como el evento sólo se utiliza para la activación de un subproceso, o bien el <xref:System.Threading.AutoResetEvent>o <xref:System.Threading.ManualResetEvent>clases podrían utilizarse.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent>  
  
```vb  
Imports System.Threading  
  
Module Module1  
    Dim autoEvent As AutoResetEvent  
  
    Sub DoWork()  
        Console.WriteLine("   worker thread started, now waiting on event...")  
        autoEvent.WaitOne()  
        Console.WriteLine("   worker thread reactivated, now exiting...")  
    End Sub  
  
    Sub Main()  
        autoEvent = New AutoResetEvent(False)  
  
        Console.WriteLine("main thread starting worker thread...")  
        Dim t As New Thread(AddressOf DoWork)  
        t.Start()  
  
        Console.WriteLine("main thread sleeping for 1 second...")  
        Thread.Sleep(1000)  
  
        Console.WriteLine("main thread signaling worker thread...")  
        autoEvent.Set()  
    End Sub  
End Module  
```  
  
## <a name="mutex-object"></a>Objeto de exclusión mutua  
 Un *mutex* es similar a un monitor; impide la ejecución simultánea de un bloque de código por más de un subproceso a la vez. De hecho, el nombre "mutex" es una forma abreviada del término "mutuamente exclusivo". A diferencia de los monitores, sin embargo, una exclusión mutua puede utilizarse para sincronizar los subprocesos entre los procesos. Una exclusión mutua se representa mediante la <xref:System.Threading.Mutex>clase.</xref:System.Threading.Mutex>  
  
 Cuando se utiliza para la sincronización entre proceso, una exclusión mutua se denomina un *exclusión mutua con nombre* porque es para su uso en otra aplicación y, por tanto, no se puede compartir por medio de una variable global o estática. Se le debe proporcionar un nombre para que ambas aplicaciones pueden tener acceso al mismo objeto de exclusión mutua.  
  
 Aunque una exclusión mutua se puede utilizar para la sincronización de subprocesos dentro de un proceso, utilizando <xref:System.Threading.Monitor>normalmente, es preferible, porque los monitores se diseñaron específicamente para .NET Framework y, por tanto, hacer un mejor uso de recursos.</xref:System.Threading.Monitor> En cambio, la <xref:System.Threading.Mutex>clase es un contenedor para una construcción de Win32.</xref:System.Threading.Mutex> Aunque es más eficaz que un monitor, una exclusión mutua requiere transiciones de interoperabilidad que son más costosas que el requerido por la <xref:System.Threading.Monitor>clase.</xref:System.Threading.Monitor> Para obtener un ejemplo del uso de una exclusión mutua, vea [exclusiones mutuas](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).  
  
## <a name="interlocked-class"></a>Interlocked (clase)  
 Puede utilizar los métodos de la <xref:System.Threading.Interlocked>clase para evitar problemas que pueden producirse cuando varios subprocesos intentan actualizar o comparar el mismo valor simultáneamente.</xref:System.Threading.Interlocked> Los métodos de esta clase permiten segura incremento, disminuir, intercambian y comparan valores desde cualquier subproceso.  
  
## <a name="readerwriter-locks"></a>Bloqueos ReaderWriterLock  
 En algunos casos, puede bloquear un recurso sólo cuando se escriben los datos y permitir que múltiples clientes puedan leer datos simultáneamente cuando no se está actualizando datos. La <xref:System.Threading.ReaderWriterLock>clase exija el acceso exclusivo a un recurso mientras un subproceso modificando el recurso, pero permite el acceso no exclusivo al leer el recurso.</xref:System.Threading.ReaderWriterLock> Bloqueos ReaderWriterLock son una alternativa útil a los bloqueos exclusivos que hacen otros subprocesos en espera, incluso cuando esos subprocesos no necesitan actualizar datos.  
  
## <a name="deadlocks"></a>Interbloqueos  
 Sincronización de subprocesos es muy valiosa en las aplicaciones multiproceso, pero siempre existe el peligro de crear un `deadlock`, donde varios subprocesos están esperando mutuamente y la aplicación se detenga. Un interbloqueo es análogo a una situación en la que automóviles parados en un delimitador de cuatro vías y cada persona está esperando la otra ir. Evitar los interbloqueos es importante; la clave es una planeación cuidadosa. A menudo puede predecir las situaciones de interbloqueo creando diagramas de aplicaciones multiproceso antes de empezar a codificar.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread></xref:System.Threading.Thread>   
 <xref:System.Threading.WaitHandle.WaitOne%2A></xref:System.Threading.WaitHandle.WaitOne%2A>   
 <xref:System.Threading.WaitHandle.WaitAny%2A></xref:System.Threading.WaitHandle.WaitAny%2A>   
 <xref:System.Threading.WaitHandle.WaitAll%2A></xref:System.Threading.WaitHandle.WaitAll%2A>   
 <xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A>   
 <xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A>   
 <xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A>   
 <xref:System.Threading.Monitor></xref:System.Threading.Monitor>   
 <xref:System.Threading.Mutex></xref:System.Threading.Mutex>   
 <xref:System.Threading.AutoResetEvent></xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent></xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Interlocked></xref:System.Threading.Interlocked>   
 <xref:System.Threading.WaitHandle></xref:System.Threading.WaitHandle>   
 <xref:System.Threading.EventWaitHandle></xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading></xref:System.Threading>   
 <xref:System.Threading.EventWaitHandle.Set%2A></xref:System.Threading.EventWaitHandle.Set%2A>   
 [Aplicaciones multiproceso (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [SyncLock (instrucción)](../../../../visual-basic/language-reference/statements/synclock-statement.md)   
 [Exclusiones mutuas](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)   
 @System.Threading.Monitor   
 [Operaciones de bloqueo](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b)   
 [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18)   
 [Sincronizar datos para subprocesamiento múltiple](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)
