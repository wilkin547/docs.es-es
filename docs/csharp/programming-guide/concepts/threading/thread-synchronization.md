---
title: "Sincronización de subprocesos (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e42b1be6-c93c-479f-a148-be0759f1a4e1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 31b206eb01d778b67acc1a25d3c69e2e1dfd553d
ms.lasthandoff: 03/13/2017

---
# <a name="thread-synchronization-c"></a>Sincronización de subprocesos (C#)
En las secciones siguientes se describen las características y clases que se pueden usar para sincronizar el acceso a recursos en aplicaciones multiproceso.  
  
 Una de las ventajas de usar varios subprocesos en una aplicación es que cada subproceso se ejecuta de manera asincrónica. En las aplicaciones para Windows, esto permite realizar las tareas que exigen mucho tiempo en segundo plano mientras la ventana de la aplicación y los controles siguen respondiendo. En las aplicaciones de servidor, el multithreading proporciona la capacidad de controlar cada solicitud de entrada con un subproceso diferente. De lo contrario, no se atendería cada nueva solicitud hasta que se hubiera satisfecho totalmente la solicitud anterior.  
  
 En cambio, la naturaleza asincrónica de los subprocesos significa que el acceso a recursos como identificadores de archivos, conexiones de red y memoria se deben coordinar. De lo contrario, dos o más subprocesos podrían tener acceso al mismo tiempo al mismo recurso, cada uno desprevenido de las acciones del otro. El resultado serían daños imprevisibles en los datos.  
  
 Para las operaciones simples en tipos de datos numéricos enteros, la sincronización de subprocesos se puede lograr con miembros de la clase <xref:System.Threading.Interlocked>. Para todos los demás tipos de datos y los recursos no seguros para subprocesos, el multithreading solo se puede realizar de manera segura con las construcciones de este tema.  
  
 Para obtener información general sobre la programación multiproceso, vea:  
  
-   [Principios básicos del subprocesamiento administrado](http://msdn.microsoft.com/library/b2944911-0e8f-427d-a8bb-077550618935)  
  
-   [Usar subprocesos y subprocesamiento](http://msdn.microsoft.com/library/9b5ec2cd-121b-4d49-b075-222cf26f2344)  
  
-   [Procedimientos recomendados para el subprocesamiento administrado](http://msdn.microsoft.com/library/e51988e7-7f4b-4646-a06d-1416cee8d557)  
  
## <a name="the-lock-keyword"></a>La palabra clave lock  
 La instrucción `lock` de C# se puede usar para garantizar que un bloque de código se ejecuta hasta el final sin que lo interrumpan otros subprocesos. Esto se logra obteniendo un bloqueo de exclusión mutua para un objeto determinado durante la ejecución de un bloque de código.  
  
 Una instrucción `lock` consiste en dar un objeto como argumento, seguido de un bloque de código que solo un subproceso puede ejecutar simultáneamente. Por ejemplo:  
  
```csharp  
public class TestThreading  
{  
    private System.Object lockThis = new System.Object();  
  
    public void Process()  
    {  
  
        lock (lockThis)  
        {  
            // Access thread-sensitive resources.  
        }  
    }  
  
}  
```  
  
 El argumento suministrado a la palabra clave `lock` debe ser un objeto basado en un tipo de referencia y se usa para definir el ámbito del bloqueo. En el ejemplo anterior, el ámbito del bloqueo se limita a esta función porque no existe ninguna referencia al objeto `lockThis` fuera de la función. Si existiese una referencia de ese tipo, el ámbito del bloqueo se extendería a ese objeto. Estrictamente, el objeto suministrado solo se usa para identificar únicamente el recurso que varios subprocesos comparten, de modo que puede ser una instancia de clase arbitraria. En cambio, en la práctica, este objeto normalmente representa el recurso para el que la sincronización de subprocesos es necesaria. Por ejemplo, si varios subprocesos van a usar un objeto contenedor, se puede pasar el contenedor para bloquearlo. Entonces, el bloque de código sincronizado que sigue al bloqueo tendría acceso al contenedor. Con tal de que otros subprocesos bloqueen el mismo contenedor antes de tener acceso a él, el acceso al objeto se sincroniza de manera segura.  
  
 Generalmente, es mejor evitar el bloqueo en un tipo `public` o en instancias de objeto que estén fuera del control de la aplicación. Por ejemplo, `lock(this)` puede ser problemático si se puede tener acceso a la instancia públicamente, ya que el código que está fuera de su control también puede bloquear el objeto. Esto podría crear situaciones del interbloqueo, en las que dos o más subprocesos esperan a que se libere el mismo objeto. El bloqueo de un tipo de datos público, como opuesto a un objeto, puede crear problemas por la misma razón. El bloqueo de cadenas literales es especialmente arriesgado porque Common Language Runtime (CLR) *interna* las cadenas literales. Esto significa que hay una instancia de un literal de cadena determinado para todo el programa, exactamente el mismo objeto representa el literal en todos los dominios de la aplicación en ejecución, en todos los subprocesos. Como resultado, un bloqueo sobre una cadena que tiene el mismo contenido en cualquier parte del proceso de la aplicación bloquea todas las instancias de esa cadena en la aplicación. Por tanto, es mejor bloquear un miembro privado o protegido que no esté internado. Algunas clases proporcionan específicamente los miembros para bloquear. Por ejemplo, el tipo <xref:System.Array> proporciona <xref:System.Array.SyncRoot%2A>. Muchos tipos de colección también proporcionan un miembro `SyncRoot`.  
  
 Vea los siguientes temas para obtener más información sobre la instrucción `lock`:  
  
-   [lock (instrucción)](../../../../csharp/language-reference/keywords/lock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a>Monitores  
 Como la palabra clave `lock`, los monitores evitan que varios subprocesos ejecuten simultáneamente bloques de código. El método <xref:System.Threading.Monitor.Enter%2A> permite que un subproceso, y solo uno, continúe con las instrucciones siguientes; todos los demás subprocesos se bloquean hasta que el subproceso en ejecución llama a <xref:System.Threading.Monitor.Exit%2A>. Esto es similar a usar la palabra clave `lock`. Por ejemplo:  
  
```csharp  
lock (x)  
{  
    DoSomething();  
}  
```  
  
 Esto equivale a:  
  
```csharp  
System.Object obj = (System.Object)x;  
System.Threading.Monitor.Enter(obj);  
try  
{  
    DoSomething();  
}  
finally  
{  
    System.Threading.Monitor.Exit(obj);  
}  
```  
  
 Normalmente, es preferible usar la palabra clave `lock` en vez de usar directamente la clase <xref:System.Threading.Monitor>, porque `lock` es más conciso y porque `lock` garantiza que se libera el monitor subyacente, aunque el código protegido produzca una excepción. Esto se logra con la palabra clave `finally`, que ejecuta su bloque de código asociado independientemente de que se produzca una excepción.  
  
## <a name="synchronization-events-and-wait-handles"></a>Eventos de sincronización y controladores de espera  
 El uso de un bloqueo o un monitor es útil para evitar la ejecución simultánea de bloques de código usados por varios subprocesos, pero estas construcciones no permiten que un subproceso comunique un evento a otro. Esto requiere *eventos de sincronización*, que son objetos que tienen uno de dos estados, señalizado y no señalizado, que se pueden usar para activar y suspender subprocesos. Los subprocesos se pueden suspender haciendo que esperen a que se produzca un evento de sincronización que no esté señalizado y se pueden activar cambiando el estado del evento a señalizado. Si un subproceso intenta esperar a que se produzca un evento que ya está señalizado, el subproceso se sigue ejecutando sin retraso.  
  
 Hay dos tipos de eventos de sincronización: <xref:System.Threading.AutoResetEvent> y <xref:System.Threading.ManualResetEvent>. Solo difieren en que <xref:System.Threading.AutoResetEvent> cambia automáticamente de señalizado a no señalizado siempre que activa un subproceso. A la inversa, <xref:System.Threading.ManualResetEvent> permite que cualquier número de subprocesos esté activado si su estado es señalizado y solo vuelve al estado no señalizado cuando se llama a su método <xref:System.Threading.EventWaitHandle.Reset%2A>.  
  
 Se puede hacer que los subprocesos esperen en eventos llamando a uno de los métodos de espera, como <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> o <xref:System.Threading.WaitHandle.WaitAll%2A>. <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName> hace que el subproceso espere hasta que se señalice un único evento, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName> bloquea un subproceso hasta que se señalicen uno o varios eventos especificados y <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> bloquea el subproceso hasta que se señalicen todos los eventos indicados. Un evento se señaliza cuando se llama a su método <xref:System.Threading.EventWaitHandle.Set%2A>.  
  
 En el ejemplo siguiente, la función `Main` crea e inicia un subproceso. El nuevo subproceso espera a que se produzca un evento mediante el método <xref:System.Threading.WaitHandle.WaitOne%2A>. Se suspende el subproceso hasta que el evento sea señalizado por el subproceso primario que está ejecutando la función `Main`. Cuando el evento se señaliza, el subproceso auxiliar se devuelve. En este caso, como el evento solo se usa para una activación del subproceso, se podrían usar las clases <xref:System.Threading.AutoResetEvent> o <xref:System.Threading.ManualResetEvent>.  
  
```csharp  
using System;  
using System.Threading;  
  
class ThreadingExample  
{  
    static AutoResetEvent autoEvent;  
  
    static void DoWork()  
    {  
        Console.WriteLine("   worker thread started, now waiting on event...");  
        autoEvent.WaitOne();  
        Console.WriteLine("   worker thread reactivated, now exiting...");  
    }  
  
    static void Main()  
    {  
        autoEvent = new AutoResetEvent(false);  
  
        Console.WriteLine("main thread starting worker thread...");  
        Thread t = new Thread(DoWork);  
        t.Start();  
  
        Console.WriteLine("main thread sleeping for 1 second...");  
        Thread.Sleep(1000);  
  
        Console.WriteLine("main thread signaling worker thread...");  
        autoEvent.Set();  
    }  
}  
```  
  
## <a name="mutex-object"></a>Objeto Mutex  
 Una *exclusión mutua* es similar a un monitor; impide la ejecución simultánea de un bloque de código por más de un subproceso a la vez. De hecho, el nombre "mutex" es una manera abreviada del término "mutuamente exclusivo". En cambio, a diferencia de los monitores, una exclusión mutua se puede usar para sincronizar los subprocesos entre varios procesos. Una exclusión mutua se representa mediante la clase <xref:System.Threading.Mutex>.  
  
 Cuando se usa para la sincronización entre procesos, una exclusión mutua se denomina una *exclusión mutua con nombre* porque va a usarla otra aplicación y, por tanto, no se puede compartir por medio de una variable global o estática. Se debe asignar un nombre para que ambas aplicaciones puedan tener acceso al mismo objeto de exclusión mutua.  
  
 Aunque se puede usar una exclusión mutua para la sincronización de subprocesos dentro de un proceso, normalmente es preferible usar <xref:System.Threading.Monitor> porque los monitores se diseñaron específicamente para .NET Framework y, por tanto, hacen un mejor uso de los recursos. Por el contrario, la clase <xref:System.Threading.Mutex> es un contenedor para una construcción de Win32. Aunque es más eficaz que un monitor, una exclusión mutua requiere transiciones de interoperabilidad que son más costosas a nivel computacional que las requeridas por la clase <xref:System.Threading.Monitor>. Para obtener un ejemplo de uso de la exclusión mutua, vea [Exclusiones mutuas (mutex)](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).  
  
## <a name="interlocked-class"></a>Clase Interlocked  
 Puede usar los métodos de la clase <xref:System.Threading.Interlocked> para evitar problemas que pueden producirse cuando varios subprocesos intentan actualizar o comparar simultáneamente el mismo valor. Los métodos de esta clase le permiten incrementar, reducir, intercambiar y comparar valores, de manera segura, desde cualquier subproceso.  
  
## <a name="readerwriter-locks"></a>Bloqueos ReaderWriter  
 En algunos casos, quizá quiera bloquear un recurso solo mientras se están escribiendo los datos y permitir que varios clientes puedan leer datos simultáneamente cuando no se estén actualizando los datos. La clase <xref:System.Threading.ReaderWriterLock> fuerza el acceso exclusivo a un recurso mientras hay un subproceso modificando el recurso, pero permite el acceso no exclusivo al leer el recurso. Los bloqueos de ReaderWriter son una alternativa útil a los bloqueos exclusivos que hacen esperar a otros subprocesos, incluso cuando esos subprocesos no necesitan actualizar datos.  
  
## <a name="deadlocks"></a>Interbloqueos  
 La sincronización de subprocesos resulta de un valor incalculable en aplicaciones multiproceso, pero siempre existe el peligro de crear un `deadlock`, en el que varios subprocesos están esperando unos a otros y la aplicación se bloquea. Un interbloqueo es una situación análoga a otra en la que hay automóviles parados en un cruce con cuatro señales de stop y cada uno de los conductores está esperando a que los otros se pongan en marcha. Evitar los interbloqueos es importante; la clave se planea cuidadosamente. A menudo es posible predecir situaciones de interbloqueo mediante la creación de diagramas de las aplicaciones multiproceso, antes de empezar a escribir código.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.WaitHandle.WaitOne%2A>   
 <xref:System.Threading.WaitHandle.WaitAny%2A>   
 <xref:System.Threading.WaitHandle.WaitAll%2A>   
 <xref:System.Threading.Thread.Join%2A>   
 <xref:System.Threading.Thread.Start%2A>   
 <xref:System.Threading.Thread.Sleep%2A>   
 <xref:System.Threading.Monitor>   
 <xref:System.Threading.Mutex>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Interlocked>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading>   
 <xref:System.Threading.EventWaitHandle.Set%2A>   
 [Aplicaciones multiproceso (C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)   
 [lock (Instrucción)](../../../../csharp/language-reference/keywords/lock-statement.md)   
 [Exclusiones mutuas (mutex)](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)   
 @System.Threading.Monitor   
 [Operaciones de bloqueo](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b)   
 [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18)   
 [Sincronizar datos para subprocesamiento múltiple](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)
