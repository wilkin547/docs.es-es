---
title: "Reliability Best Practices | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "marking locks"
  - "rebooting databases"
  - "denial of service attacks"
  - "back-out code"
  - "SQL Server [.NET Framework], reliability"
  - "synchronization, reliability"
  - "single-threaded COM components"
  - "slow leaks"
  - "suspending threads"
  - "asynchronous exception handling"
  - "leaked resources [.NET Framework]"
  - "unmanaged memory"
  - "memory, reliability"
  - "threading [.NET Framework], reliability"
  - "process-wide domain shared states"
  - "shared states"
  - "SafeHandle class, reliability"
  - "reliability contracts [.NET Framework]"
  - "cleanup operations"
  - "constrained execution regions"
  - "CERs"
  - "finalizers, reliability"
  - "reliability [.NET Framework]"
  - "blocks, reliability"
  - "finally clauses"
  - "cross-application domain shared states"
  - "catch blocks"
  - "identifying locks"
  - "writing reliable code"
  - "impersonation"
  - "GC.KeepAlive method"
  - "managed threading"
  - "locks, reliability"
  - "STA-dependent features"
  - "fibers"
ms.assetid: cf624c1f-c160-46a1-bb2b-213587688da7
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# Reliability Best Practices
Las reglas de confiabilidad siguientes están orientadas a SQL Server; sin embargo, también se aplican a cualquier aplicación de servidor basada en host.  Es sumamente importante que los servidores como SQL Server no malgasten recursos y no se apaguen.  Sin embargo, esto no se puede hacer escribiendo código de retroceso para todos los métodos que alteran el estado de un objeto.  La meta es no escribir código administrado confiable al cien por cien que se recuperará de cualquier error en todas las ubicaciones mediante código de retroceso.  Ésa sería una abrumadora tarea con pocas oportunidades de realizarse correctamente.  Common Language Runtime \(CLR\) no puede proporcionar con facilidad garantías al código administrado lo bastante seguras para que sea factible escribir código perfecto.  Tenga en cuenta que, a diferencia de ASP.NET, SQL Server utiliza sólo un proceso que no se puede reciclar sin dejar inactiva una base de datos durante un tiempo inaceptablemente largo.  
  
 Con estas garantías más débiles y ejecutando un único proceso, la confiabilidad se basa en finalizar los subprocesos o reciclar dominios de aplicación cuando sea necesario, y tomar precauciones para garantizar que no se malgastan recursos del sistema operativo como identificadores o memoria.  Incluso con esta restricción de confiabilidad más simple, sigue habiendo un requisito de confiabilidad significativo:  
  
-   Nunca malgastar los recursos del sistema operativo.  
  
-   Indicar a CLR todos los bloqueos administrados en todas las formas.  
  
-   Nunca interrumpir el estado compartido del dominio entre aplicaciones, permitiendo que el reciclaje <xref:System.AppDomain> funcione sin problemas.  
  
 Aunque teóricamente es posible escribir código administrado para controlar las excepciones <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> y <xref:System.OutOfMemoryException>, no es razonable esperar que los desarrolladores escriban un código tan robusto en toda una aplicación.  Por esa razón, las excepciones fuera de banda provocan que finalice el subproceso que se está ejecutando y, si el subproceso finalizado estaba editando en el estado compartido, lo que se puede determinar si el subproceso mantiene un bloqueo, se descarga el dominio <xref:System.AppDomain>.  Cuando se hace terminar un método que estaba editando el código compartido, el estado quedará dañado porque no es posible escribir código de retroceso confiable para las actualizaciones al estado compartido.  
  
 En la versión 2.0 de .NET Framework, el único host que requiere confiabilidad es SQL Server.  Si su ensamblado se va a ejecutar en SQL Server debería realizar el trabajo de confiabilidad para todas las partes de ese ensamblado, incluso si hay características específicas que están deshabilitadas al ejecutarse en la base de datos.  Esto es necesario porque el motor de análisis de código examina el código en el nivel de ensamblado y no puede diferenciar el código deshabilitado.  Otra consideración de programación para SQL Server es que SQL Server ejecuta todo en un proceso y el reciclaje de <xref:System.AppDomain> se utiliza para limpiar todos los recursos, como la memoria y los identificadores del sistema operativo.  
  
 No puede depender de finalizadores, destructores ni bloques `try/finally` para el código de retroceso.  Se podrían interrumpir o no ser llamados.  
  
 Las excepciones asincrónicas se pueden iniciar en ubicaciones inesperadas, posiblemente cada instrucción máquina: <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> y <xref:System.OutOfMemoryException>.  
  
 Los subprocesos administrados no son necesariamente subprocesos Win32 en SQL; podrían ser fibras.  
  
 El estado compartido mutable de todo el proceso o entre aplicaciones es extremadamente difícil de modificar con seguridad y debería evitarse siempre que sea posible.  
  
 Las condiciones de memoria insuficiente no son raras en SQL Server.  
  
 Si las bibliotecas hospedadas en SQL Server no actualizan correctamente su estado compartido, es muy posible que el código no se recupere hasta que se haya reiniciado la base de datos.  Además, en algunos casos extremos, es posible que esta situación provocara errores en el proceso de SQL Server, haciendo que se reiniciara la base de datos.  Reiniciar la base de datos puede dejar inactivo un Sitio Web o puede afectar a las operaciones de la empresa, afectando negativamente a la disponibilidad.  Una pequeña pérdida de recursos del sistema operativo, como memoria o identificadores, pueden provocar que finalmente el servidor no pueda asignar los identificadores sin posibilidad de recuperación o, posiblemente, el rendimiento del servidor podría ir degradándose lentamente y reducir la disponibilidad de la aplicación cliente.  Está claro que es deseable evitar estos escenarios.  
  
## Reglas de procedimientos recomendados  
 La introducción se centraba en qué debería interceptar la revisión del código administrado que se ejecuta en el servidor con el fin de incrementar la estabilidad y la confiabilidad del marco de trabajo.  Todas estas comprobaciones son en general prácticas recomendadas y absolutamente obligatorias en el servidor.  
  
 Si se presenta un interbloqueo o una restricción de recursos, SQL Server anulará un subproceso o interrumpirá un <xref:System.AppDomain>.  Cuando esto ocurre, sólo se garantiza la ejecución del código de retroceso en un área de ejecución restringida \(CER\).  
  
### Utilice SafeHandle para evitar las pérdidas de recursos  
 En el caso de una descarga de <xref:System.AppDomain>, no se puede depender de la ejecución de bloques `finally` o finalizadores, por lo que es importante abstraer todo el acceso a los recursos del sistema operativo a través de la clase <xref:System.Runtime.InteropServices.SafeHandle> en lugar de las clases <xref:System.IntPtr>, <xref:System.Runtime.InteropServices.HandleRef> o similares.  Esto permite a CLR siga y cerrar los identificadores utiliza incluso en el caso de desmontaje de <xref:System.AppDomain> .  <xref:System.Runtime.InteropServices.SafeHandle> utilizará un finalizador crítico que siempre ejecutará CLR.  
  
 El identificador del sistema operativo se almacena en el identificador seguro desde el momento en que se crea y hasta el momento que se libera.  No hay ningún intervalo temporal durante el que puede producirse una <xref:System.Threading.ThreadAbortException> para producir la pérdida de un identificador.  Además, la invocación de la plataforma asignará un recuento de referencia al identificador, que permite un seguimiento estricto del período de duración del controlador, impidiendo que se produzca un problema de seguridad con una condición de carrera entre `Dispose` y un método que esté utilizando el identificador en cada momento.  
  
 La mayoría de las clases que actualmente tienen un finalizador para simplemente limpiar un identificador del sistema operativo ya no necesitarán el finalizador.  En su lugar, el finalizador estará en la clase derivada <xref:System.Runtime.InteropServices.SafeHandle>.  
  
 Observe que <xref:System.Runtime.InteropServices.SafeHandle> no es un reemplazo para <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>.  Hay todavía posibilidad de obtener contención de recursos y ventajas de rendimiento para disponer explícitamente de recursos del sistema operativo.  Simplemente debe estar al tanto de que los bloques `finally` que disponen explícitamente de recursos pueden no ejecutarse hasta su finalización.  
  
 <xref:System.Runtime.InteropServices.SafeHandle> permite implementar un método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> propio que realiza el trabajo necesario para liberar el identificador, como pasar el estado a una rutina de liberación de identificadores del sistema operativo o liberar un conjunto de identificadores en un bucle.  CLR garantiza que se ejecuta este método.  Es responsabilidad del autor de la implementación de <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> garantizar que el identificador se libera en todas las circunstancias.  No hacerlo así provocará que se pierda el identificador, lo que a menudo produce la pérdida de recursos nativos asociados con el identificador.  Por consiguiente, es fundamental estructurar las clases derivadas <xref:System.Runtime.InteropServices.SafeHandle> de manera que la implementación de <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> no requiera la asignación de ningún recurso que podría no estar disponible en el momento de la invocación.  Tenga en cuenta que es permisible llamar a métodos que podrían fallar con la implementación de <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>, con la condición de que el código pueda controlar esos errores y finalizar el contrato para liberar el identificador nativo.  A efectos de depuración, <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> tiene un valor devuelto de tipo <xref:System.Boolean> que puede establecerse en `false` si se encuentra un error catastrófico que impida la liberación del recurso.  Al hacerlo así, se activará el MDA [releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md), si está habilitado, para ayudar a identificar el problema.  Esta operación no afecta de ninguna otra manera al motor en tiempo de ejecución; no se volverá a llamar a <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> para el mismo recurso y, por lo tanto, el identificador se perderá.  
  
 <xref:System.Runtime.InteropServices.SafeHandle> no es adecuado en ciertos contextos.  Dado que el método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> puede ejecutarse en un subproceso finalizador <xref:System.GC>, los identificadores que se deben liberar en un subproceso concreto no deben estar contenidos en un <xref:System.Runtime.InteropServices.SafeHandle>.  
  
 CLR puede limpiar los contenedores invocables en tiempo de ejecución \(RCW\) sin necesidad de código adicional.  Para el código que utiliza la invocación de plataforma y trata los objetos COM como `IUnknown*` o <xref:System.IntPtr>, se debe volver a escribir el código para utilizar un RCW.  <xref:System.Runtime.InteropServices.SafeHandle> puede no ser adecuado para este escenario debido a la posibilidad de que un método no administrado de liberación a código administrado.  
  
#### Regla de análisis de código  
 Utilice <xref:System.Runtime.InteropServices.SafeHandle> para encapsular los recursos del sistema operativo.  No utilice <xref:System.Runtime.InteropServices.HandleRef> ni campos de tipo <xref:System.IntPtr>.  
  
### Asegúrese de que los finalizadores no se tienen que ejecutar para evitar la pérdida de recursos del sistema operativo  
 Revise cuidadosamente sus finalizadores para asegurarse de que, aun cuando no ejecutan, no se pierde ningún recurso crítico del sistema operativo.  A diferencia de una descarga de <xref:System.AppDomain> normal cuando la aplicación se ejecuta en un estado estable o cuando se cierra un servidor como SQL Server, los objetos no se terminan durante una descarga abrupta de <xref:System.AppDomain>.  Asegúrese de que no se pierden recursos en caso de una descarga abrupta, puesto que no se puede garantizar la corrección de una aplicación, sino que la integridad del servidor se debe mantener sin pérdida de recursos.  Utilice <xref:System.Runtime.InteropServices.SafeHandle> para liberar recursos del sistema operativo.  
  
### Asegúrese de que las cláusulas Finally no se tienen que ejecutar para evitar la pérdida de recursos del sistema operativo  
 Las cláusulas `finally` no tienen garantía de ejecución fuera de las CER, lo que requiere que los desarrolladores de bibliotecas no se basen en código contenido en bloques `finally` para liberar recursos no administrados.  La solución recomendada es utilizar <xref:System.Runtime.InteropServices.SafeHandle>.  
  
#### Regla de análisis de código  
 Utilice <xref:System.Runtime.InteropServices.SafeHandle> para limpiar los recursos del sistema operativo en lugar de `Finalize`.  No utilice <xref:System.IntPtr>; use <xref:System.Runtime.InteropServices.SafeHandle> para encapsular los recursos.  Si la cláusula Finally debe ejecutarse, colóquela en un área CER.  
  
### Todos los bloqueos deben pasar por el código de bloqueo administrado existente  
 CLR debe saber cuándo el código está en un bloqueo, de forma que sepa cómo romper el <xref:System.AppDomain> en lugar de limitarse a anular el subproceso.  Anular el subproceso podría ser peligroso ya que los datos con los que opera el subproceso podrían quedar en un estado incoherente.  Por consiguiente, se debe reciclar todo el <xref:System.AppDomain>.  Las consecuencias de no identificar un bloqueo pueden ser interbloqueos o resultados incorrectos.  Utilice los métodos <xref:System.Threading.Thread.BeginCriticalRegion%2A> y <xref:System.Threading.Thread.EndCriticalRegion%2A> para identificar las regiones del bloqueo.  Son métodos estáticos de la clase <xref:System.Threading.Thread> que sólo se refieren al subproceso actual, ayudando así a impedir que un subproceso edite el recuento de bloqueos de otro subproceso.  
  
 <xref:System.Threading.Monitor.Enter%2A> y <xref:System.Threading.Monitor.Exit%2A> llevan integrada esta notificación a CLR, por lo que se recomienda su utilización, así como el uso de [lock \(Instrucción\)](../Topic/lock%20Statement%20\(C%23%20Reference\).md), que utiliza estos métodos.  
  
 Otros mecanismos de bloqueo como bloqueos de iteración y <xref:System.Threading.AutoResetEvent> deben llamar a estos métodos para notificar CLR que se está entrando en una sección crítica.  Estos métodos no toman ningún bloqueo; informan a CLR que el código se está ejecutando en una sección crítica y anular el subproceso podría dejar el procesamiento en un estado compartido incoherente.  Si ha definido su propio tipo de bloqueo, como una clase <xref:System.Threading.ReaderWriterLock> personalizada, utilice estos métodos de recuento de bloqueo.  
  
#### Regla de análisis de código  
 Marque e identifique todos los bloqueos mediante <xref:System.Threading.Thread.BeginCriticalRegion%2A> y <xref:System.Threading.Thread.EndCriticalRegion%2A>.  No utilice <xref:System.Threading.Interlocked.CompareExchange%2A>, <xref:System.Threading.Interlocked.Increment%2A> ni <xref:System.Threading.Interlocked.Decrement%2A> en los bucles.  No haga una invocación de plataforma de las variantes de Win32 de estos métodos.  No utilice <xref:System.Threading.Thread.Sleep%2A> en los bucles.  No utilice campos volátiles.  
  
### El código de limpieza debe estar en un bloque Finally o Catch, no a continuación de una detección catch  
 El código de limpieza nunca ir a continuación de un bloque `catch`; debería estar en un bloque `finally` o en el propio bloque `catch`.  Ésta es una práctica recomendada normal.  Normalmente es preferible usar un bloque `finally` porque ejecuta el mismo código tanto cuando se produce una excepción como cuando se encuentra normalmente final del bloque `try`.  En caso de que se produzca una excepción inesperada, por ejemplo una <xref:System.Threading.ThreadAbortException>, no se ejecutará el código de limpieza.  Lo ideal sería que los recursos no administrados que se limpiarían en un bloque `finally` estuvieran contenidos en un <xref:System.Runtime.InteropServices.SafeHandle> para evitar pérdidas.  Tenga en cuenta que la palabra clave `using` de C\# se puede utilizar eficazmente para desechar objetos, incluso identificadores.  
  
 Aunque el reciclaje de <xref:System.AppDomain> puede limpiar los recursos en el subproceso finalizador, sigue siendo importante colocar código de limpieza en el lugar correcto.  Tenga en cuenta que, si un subproceso recibe una excepción asincrónica sin mantener un bloqueo, CLR intenta terminar el propio subproceso sin tener que reciclar el <xref:System.AppDomain>.  Asegurarse de que los recursos se limpian antes en lugar de más tarde ayuda a liberar más recursos y administrar mejor su período de duración.  Si no cierra explícitamente un identificador a un archivo en alguna ruta de código de error, espere a que lo limpie el finalizador <xref:System.Runtime.InteropServices.SafeHandle>; la próxima vez que el código lo ejecute, podría no obtener acceso a exactamente el mismo archivo si el finalizador aún no se ha ejecutado.  Por este motivo, asegurarse de que existe código de limpieza y de que funciona correctamente, ayudará a la recuperación de errores más limpia y rápidamente, incluso aunque no sea estrictamente necesario.  
  
#### Regla de análisis de código  
 Código de limpieza situado después de `catch` debe estar incluido en un bloque `finally`.  Sitúe las llamadas a dispose en un bloque finally.  los bloques de `catch` deben finalizar en un inicio o un reinicio.  Aunque habrá excepciones, como cuando el código detecta si se puede establecer una conexión de red cuando podría producirse una de un gran número de excepciones, cualquier código que requiera la detección de una serie de excepciones en circunstancias normales debería dar signos de que el código debería probarse para ver si finalizará correctamente.  
  
### El estado compartido mutable para todo el proceso situado en dominios de aplicación debe eliminarse o utilizarse en un área de ejecución restringida  
 Como se explica en la introducción, puede resultar muy difícil escribir código administrado que supervise estado compartido en todo el proceso entre dominios de aplicación de una manera confiable.  El estado compartido durante el proceso es cualquier tipo de estructura de datos compartido entre dominios de aplicación, ya sea en código Win32, dentro de CLR o en el código administrado que utilice la comunicación remota.  Es muy difícil que cualquier estado compartido mutable escriba correctamente en código administrado, y cualquier estado compartido estático podría hacerse extremando las precauciones.  Si posee estado compartido en el proceso o en el equipo, busque alguna manera de eliminarlo o de proteger el estado compartido utilizando un área de ejecución restringida \(CER\).  Tenga en cuenta de que cualquier biblioteca con estado compartido que no esté identificada y corregida podría provocar que se bloqueara un host, como SQL Server, que requiera la descarga de <xref:System.AppDomain>.  
  
 Si el código utiliza un objeto COM, evite compartir ese objeto COM entre dominios de aplicación.  
  
### Los bloqueos no funcionan en los procesos o entre dominios de aplicación.  
 En el pasado, <xref:System.Threading.Monitor.Enter%2A> y [lock \(Instrucción\)](../Topic/lock%20Statement%20\(C%23%20Reference\).md) se han utilizado para crear bloqueos de proceso globales.  Por ejemplo, esto ocurre al establecer bloqueos en clases ágiles <xref:System.AppDomain>, como instancias de <xref:System.Type> de ensamblados no compartidos, objetos <xref:System.Threading.Thread>, cadenas a las que se ha aplicado el método Intern, y algunas cadenas compartidas entre dominios de aplicación mediante la comunicación remota.  Estos bloqueos ya son de todo el proceso.  Para identificar la presencia de un bloqueo de dominio entre aplicaciones de todo el proceso, determine si el código incluido en el bloque utiliza algún recurso externo persistente, como un archivo guardado en disco o, probablemente, una base de datos.  
  
 Tenga en cuenta que tomar un bloqueo dentro de un <xref:System.AppDomain> podría provocar problemas si el código protegido utiliza un recurso externo porque ese código podría ejecutarse simultáneamente en varios dominios de aplicación.  Éste puede ser un problema cuando escribiendo en el un archivo de registro o enlazándose a un socket para el proceso completo.  Estos cambios significan que no hay ninguna sencilla, usando código administrado, de obtener un bloqueo global para todo el proceso, salvo utilizar una instancia con nombre de <xref:System.Threading.Mutex> o <xref:System.Threading.Semaphore>.  Cree código que no se ejecute simultáneamente en dos dominios de aplicación o utilice las clases <xref:System.Threading.Mutex> o <xref:System.Threading.Semaphore>.  Si no se puede cambiar el código existente, no utilice una exclusión mutua con nombre de Win32 para conseguir esta sincronización porque ejecutarlo en modo fibra significa que no se puede garantizar que será el mismo subproceso del sistema operativo el que adquiera y libere la exclusión mutua.  Debe utilizar la clase administrada <xref:System.Threading.Mutex>, un <xref:System.Threading.ManualResetEvent>, un <xref:System.Threading.AutoResetEvent> o un <xref:System.Threading.Semaphore> para sincronizar el código del bloqueo de tal forma que CLR esté informado de este hecho en lugar de bloquearlo usando código no administrado.  
  
#### Evite usar lock\(typeof \(MyType\)\)  
 Los objetos <xref:System.Type> privados y públicos en ensamblados compartidos con sólo una copia del código compartido por todos los dominios de aplicación también presentan problemas.  Para los ensamblados compartidos, sólo hay una instancia de un <xref:System.Type> por proceso, lo que significa que varios dominios de aplicación comparten exactamente la misma instancia de <xref:System.Type>.  Al tomar un bloqueo en una instancia <xref:System.Type>, se toma un bloqueo que afecta a todo el proceso, no sólo a <xref:System.AppDomain>.  Si un <xref:System.AppDomain> toma un bloqueo en un objeto <xref:System.Type>, ese subproceso se anula abruptamente y no liberará el bloqueo.  Este bloqueo puede hacer entonces que se interbloqueen otros dominios de aplicación.  
  
 Una manera buena de tomar los bloqueos de métodos estáticos implica agregar al código un objeto de sincronización interno estático.  Esto se podría inicializar en el constructor de clase si existe pero, si no es así, se puede inicializar de esta manera:  
  
```  
private static Object s_InternalSyncObject;  
private static Object InternalSyncObject   
{  
    get   
    {  
        if (s_InternalSyncObject == null)   
        {  
            Object o = new Object();  
            Interlocked.CompareExchange(  
                ref s_InternalSyncObject, o, null);  
        }  
        return s_InternalSyncObject;  
    }  
}  
```  
  
 Después, al tomar un bloqueo, utilice la propiedad `InternalSyncObject` para obtener un objeto que bloquear.  No es necesario usar la propiedad si ha inicializado el objeto de sincronización interno en su constructor de clase.  El código de inicialización de bloqueo de doble comprobación debe ser parecido a este ejemplo:  
  
```  
public static MyClass SingletonProperty   
{  
    get   
    {  
        if (s_SingletonProperty == null)   
        {  
            lock(InternalSyncObject)   
            {  
                // Do not use lock(typeof(MyClass))   
                if (s_SingletonProperty == null)   
                {  
                    MyClass tmp = new MyClass(…);     
                    // Do all initialization before publishing  
                    s_SingletonProperty = tmp;  
                }  
            }  
        }  
        return s_SingletonProperty;  
    }  
}  
```  
  
#### Una nota sobre Lock\(this\)  
 Por lo general, es aceptable tomar un bloqueo en un objeto concreto que es de acceso público.  Sin embargo, si el objeto es un objeto singleton que podría producir que se interbloqueara todo un subsistema completo, plantéese utilizar también el modelo de diseño anterior.  Por ejemplo, un bloqueo en el objeto <xref:System.Security.SecurityManager> podría producir un interbloqueo dentro de <xref:System.AppDomain>, dejando inutilizable todo el <xref:System.AppDomain>.  Es una práctica recomendable no tomar bloqueos en un objeto de acceso público de este tipo.  Sin embargo, un bloqueo en una colección o matriz concreta generalmente no debería presentar ningún problema.  
  
#### Regla de análisis de código  
 No tome los bloqueos en tipos que se podrían utilizar entre dominios de aplicación o no tienen un sentido fuerte de identidad.  No llame a <xref:System.Threading.Monitor.Enter%2A> en un objeto <xref:System.Type>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.PropertyInfo>, <xref:System.String>, <xref:System.ValueType>, <xref:System.Threading.Thread> ni en ningún objeto que se derive de <xref:System.MarshalByRefObject>.  
  
### Quite las llamadas de GC.KeepAlive  
 Una cantidad significativa de código existente no utiliza <xref:System.GC.KeepAlive%2A> cuando debe o lo utiliza cuando no es adecuado.  Después de la conversión a <xref:System.Runtime.InteropServices.SafeHandle>, las clases no tienen que llamar a <xref:System.GC.KeepAlive%2A>, suponiendo que no tienen un finalizador pero se basan en <xref:System.Runtime.InteropServices.SafeHandle> para finalizar los identificadores del sistema operativo.  Aunque el costo de rendimiento de mantener una llamada a <xref:System.GC.KeepAlive%2A> puede ser inapreciable, la percepción de que una llamada a <xref:System.GC.KeepAlive%2A> es necesaria o suficiente para solucionar un problema de duración que puede no existir hace que el código sea más difícil de mantener.  Sin embargo, al utilizar los contenedores de CLR invocables \(RCW\) de la interoperabilidad COM, el código sigue requiriendo usar <xref:System.GC.KeepAlive%2A>.  
  
#### Regla de análisis de código  
 Quite <xref:System.GC.KeepAlive%2A>.  
  
### Utilice el atributo de protección de host  
 El <xref:System.Security.Permissions.HostProtectionAttribute> \(HPA\) proporciona el uso de acciones de seguridad declarativa para determinar los requisitos de protección de host, permitiendo al host impedir que incluso el código de plena confianza llame a determinados métodos que no son adecuados para el host dado, como <xref:System.Environment.Exit%2A> o <xref:System.Windows.Forms.MessageBox.Show%2A> para SQL Server.  
  
 El atributo HPA sólo afecta a las aplicaciones no administradas que hospedan Common Language Runtime e implementan esa protección de host, como SQL Server.  Cuando se aplica, la acción de seguridad produce la creación de una petición de vínculo basada en los recursos del host expuestos por la clase o el método.  Si se ejecuta el código en una aplicación cliente o en un servidor que no tiene protección de host, el atributo "se evapora"; no se detecta y, por tanto, no se aplica.  
  
> [!IMPORTANT]
>  El propósito de este atributo es forzar el cumplimiento de las directrices del modelo de programación específica del host, no el comportamiento de seguridad.  Aunque se  utiliza una petición de vínculo para comprobar la conformidad con respecto a los requisitos del modelo de programación, <xref:System.Security.Permissions.HostProtectionAttribute> no es un permiso de seguridad.  
  
 Si el host no tiene ningún requisito del modelo de programación, no se produce ninguna petición de vínculo.  
  
 Este atributo identifica lo siguiente:  
  
-   Métodos o clases que no son conformes al modelo de programación del host pero que, por lo demás, no causan daño alguno.  
  
-   Métodos o clases que no son conformes al modelo de programación del host y podrían desestabilizar el código de usuario administrado por servidor.  
  
-   Métodos o clases que no son conformes al modelo de programación del host y podrían desestabilizar el propio proceso de servidor.  
  
> [!NOTE]
>  Si está creando una biblioteca de clases a la que llamarán determinadas aplicaciones que pueden ejecutarse en un entorno con protección de host, este atributo se deberá aplicar a los miembros que expongan categorías de recursos <xref:System.Security.Permissions.HostProtectionResource>.  Los miembros de la biblioteca de clases de .NET Framework con este atributo hacen que sólo se compruebe el llamador inmediato.  Su miembro de biblioteca también debe producir una comprobación de su llamador inmediato de la misma manera.  
  
 Encontrará más información sobre el atributo HPA en <xref:System.Security.Permissions.HostProtectionAttribute>.  
  
#### Regla de análisis de código  
 Para SQL Server, todos los métodos utilizados para introducir la sincronización o el subprocesamiento se deben identificar con el atributo HPA.  Esto incluye métodos que comparten el estado, están sincronizados o administran los procesos externos.  Los valores <xref:System.Security.Permissions.HostProtectionResource> que afectan a SQL Server son <xref:System.Security.Permissions.HostProtectionResource>, <xref:System.Security.Permissions.HostProtectionResource> y <xref:System.Security.Permissions.HostProtectionResource>.  Sin embargo, cualquier método que exponga cualquier <xref:System.Security.Permissions.HostProtectionResource> debe identificarse mediante un atributo HPA, no sólo esos recursos que afectan a SQL.  
  
### No bloquee indefinidamente en código no administrado  
 Bloquear en código no administrado en lugar de en código administrado puede provocar un ataque de denegación de servicio porque CLR no puede anular el subproceso.  Un subproceso bloqueado impide a CLR descargar el dominio <xref:System.AppDomain>, por lo menos sin hacer algunas operaciones sumamente no seguras.  Bloquear utilizando un primitivo de sincronización de Win32 es un claro ejemplo de algo que no se puede permitir.  Si es posible, debe evitarse bloquear en una llamada a `ReadFile` en un socket, idealmente la API Win32 debería proporcionar un mecanismo en tiempo de espera para una operación como esta.  
  
 Cualquier método que llama en el nativo debería utilizar idealmente una llamada de Win32 con un tiempo de espera razonable y finito.  Si se permite al usuario especificar el tiempo de espera, éste no debería tener la posibilidad de especificar un tiempo de espera infinito sin algunos permisos de seguridad específicos.  Como pauta general, si un método va a estar bloqueado durante más de 10 segundos, aproximadamente, es necesario utilizar una versión que admita tiempos de espera o contar con un soporte adicional de CLR.  
  
 A continuación se enumeran algunos ejemplos de API problemáticas.  Se pueden crear canalizaciones \(tanto anónimas como con nombre\) con tiempos de espera; sin embargo, el código se debe asegurar de que nunca se llama a `CreateNamedPipe` ni a `WaitNamedPipe` con NMPWAIT\_WAIT\_FOREVER.  Además, puede producirse un bloqueo inesperado incluso aunque se especifique un tiempo de espera.  Llamar a `WriteFile` en una canalización anónima producirá un bloqueo hasta que se hayan escrito todos los bytes, lo que significa que si el búfer contiene datos no leídos, la llamada a `WriteFile` se bloqueará hasta que el lector haya liberado espacio en el búfer de la canalización.  Los sockets siempre deberían utilizar alguna API que obedezca a un mecanismo en tiempo de espera.  
  
#### Regla de análisis de código  
 Bloquear sin un tiempo de espera en código no administrado es un ataque de denegación de servicio.  No realice llamadas de invocación de plataforma para `WaitForSingleObject`, `WaitForSingleObjectEx`, `WaitForMultipleObjects`, `MsgWaitForMultipleObjects` y `MsgWaitForMultipleObjectsEx`.  No utilice NMPWAIT\_WAIT\_FOREVER.  
  
### Identifique cualquier característica dependiente de STA.  
 Identifique cualquier código que utilice contenedores uniproceso COM \(STA\).  Los atributos STA están deshabilitados en el proceso SQL Server.  Las características que dependen de `CoInitialize`, como contadores de rendimiento o el portapapeles, se deben deshabilitar dentro de SQL Server.  
  
### Garantizar que los finalizadores no presentan problemas de sincronización  
 En versiones futuras de .NET Framework podrían existir varios subprocesos finalizadores, significando que los finalizadores de distintas instancias del mismo tipo se ejecutan simultáneamente.  No tienen por qué ser completamente seguros para subprocesos; el recolector de elementos no utilizados garantiza que sólo un subproceso ejecutará el finalizador de una instancia de objeto dada.  Sin embargo, los finalizadores deben estar codificados para evitar condiciones de carrera e interbloqueos al ejecutarse simultáneamente en varias instancias de objeto diferentes.  Al utilizar cualquier estado externo, como escribir en un archivo de registro, en un finalizador, se deben controlar los problemas de los subprocesos.  No confíe en la finalización para proporcionar seguridad para subprocesos.  No utilice almacenamiento local de subprocesos, administrados o nativos, para almacenar el estado en el subproceso finalizador.  
  
#### Regla de análisis de código  
 Los finalizadores no deben presentar problemas de sincronización.  No utilice un estado mudable estático en un finalizador.  
  
### Evite la memoria no administrada si es posible  
 Puede haber pérdidas de memoria no administrada, igual que con un identificador del sistema operativo.  Si es posible, intente utilizar memoria de la pila usando [stackalloc](../Topic/stackalloc%20\(C%23%20Reference\).md) o un objeto administrado anclado, como [fixed \(Instrucción\)](../Topic/fixed%20Statement%20\(C%23%20Reference\).md) o <xref:System.Runtime.InteropServices.GCHandle> usando byte\[\].  <xref:System.GC> los limpia finalmente.  Sin embargo, si debe asignar memoria no administrada, considere la posibilidad de utilizar una clase que se derive de <xref:System.Runtime.InteropServices.SafeHandle> para contener la asignación de memoria.  
  
 Observe que hay por lo menos un caso en el que <xref:System.Runtime.InteropServices.SafeHandle> no es adecuado.  Para las llamadas a métodos COM que asignan o liberan memoria, es frecuente que una DLL asigne la memoria mediante `CoTaskMemAlloc` y después otra DLL libere esa memoria con `CoTaskMemFree`.  Utilizar <xref:System.Runtime.InteropServices.SafeHandle> en estos lugares no sería adecuado porque intentará unir el período de duración de la memoria no administrada al período de duración del <xref:System.Runtime.InteropServices.SafeHandle> en lugar de permitir que la otra DLL controle el período de duración de la memoria.  
  
### Revise todos los usos de Catch\(Exception\)  
 Los bloques Catch que detectan todas las excepciones en lugar de una excepción concreta ahora detectan también las excepciones asincrónicas.  Examine todos los bloques catch\(Exception\) para buscar liberaciones de recursos no importantes o código de recuperación que podría omitirse, así como comportamiento potencialmente incorrecto dentro del propio bloque catch para controlar una <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> o <xref:System.OutOfMemoryException>.  Observe que puede que este código esté registrando o asumiendo que sólo puede ver determinadas excepciones, o que siempre que se produce una excepción, siempre falla exactamente por un motivo concreto.  Puede ser necesario actualizar estas asunciones para incluir <xref:System.Threading.ThreadAbortException>.  
  
 Plantéese cambiar todos los lugares que detectan todas las excepciones para detectar un tipo concreto de excepción que espera que se vaya a producir, como una <xref:System.FormatException> a partir de métodos de formato de cadenas.  Esto evita que el bloque catch se ejecute con excepciones inesperadas y ayudará a garantizar que el código no oculta los errores detectando excepciones inesperadas.  Como norma general, nunca controle una excepción en código de biblioteca \(el código que requiere que se detecte una excepción puede ser una indicación de un defecto de diseño en el código al que se está llamando\).  En algunos casos, puede que desee detectar una excepción e iniciar un tipo de excepción diferente para proporcionar más datos.  En estos casos, utilice las excepciones anidadas, almacenando la causa real del error en la propiedad <xref:System.Exception.InnerException%2A> de la nueva excepción.  
  
#### Regla de análisis de código  
 Revise todos los bloques catch incluidos en código administrado que detectan todos los objetos o todas las excepciones.  En C\#, esto significa marcar tanto `catch` {} como `catch(Exception)` {}.  Piense en hacer que el tipo de la excepción sea muy específico o revise el código para que no actúe incorrectamente si detecta un tipo de excepción inesperado.  
  
### No presuponga que un subproceso administrado es un subproceso de Win32 \- Es una fibra  
 Utilizar almacenamiento local de subprocesos administrados funciona, pero no se puede utilizar el almacenamiento local de subprocesos no administrados ni presuponer que el código se ejecutará de nuevo en el subproceso actual del sistema operativo.  No cambie ajustes como la configuración regional del subproceso.  No llame a `InitializeCriticalSection` ni a `CreateMutex` a través de la invocación de plataforma porque requieren el subproceso del sistema operativo que escriba un bloqueo también salga del bloqueo.  Puesto que éste no será el caso al utilizar fibras, en SQL no se pueden usar directamente secciones críticas de Win32 y exclusiones mutuas.  Observe que la clase <xref:System.Threading.Mutex> administrada no controla estas consideraciones de afinidad de subprocesos.  
  
 Se puede utilizar sin ningún riesgo la mayor parte del estado en un objeto <xref:System.Threading.Thread> administrado, incluidos el almacenamiento local de subprocesos administrados y la referencia cultural de la interfaz de usuario actual del subproceso.  También puede utilizar el atributo <xref:System.ThreadStaticAttribute>, que hace que el valor de una variable estática existente sólo sea accesible por el subproceso administrado actual \(ésta es otra forma de realizar el almacenamiento local de fibras en CLR\).  Por motivos relacionados con el modelo de programación, no se puede cambiar la referencia cultural actual de un subproceso al ejecutarse en SQL.  
  
#### Regla de análisis de código  
 SQL Server se ejecuta en modo de fibra; no utilice el almacenamiento local de subprocesos.  Evite las llamadas de invocación de plataforma a `TlsAlloc`, `TlsFree`, `TlsGetValue` y `TlsSetValue.`  
  
### Deje que SQL Server controle la suplantación  
 Puesto que la suplantación actúa en el nivel de subproceso y SQL se puede ejecutar en modo de fibra, el código administrado no debería suplantar usuarios ni llamar a `RevertToSelf`.  
  
#### Regla de análisis de código  
 Deje que SQL Server controle la suplantación.  No utilice `RevertToSelf`, `ImpersonateAnonymousToken`, `DdeImpersonateClient`, `ImpersonateDdeClientWindow`, `ImpersonateLoggedOnUser`, `ImpersonateNamedPipeClient`, `ImpersonateSelf`, `RpcImpersonateClient`, `RpcRevertToSelf`, `RpcRevertToSelfEx` ni `SetThreadToken`.  
  
### No llame a Thread::Suspend  
 La capacidad de suspender un subproceso puede parecer una operación sencilla, pero puede producir interbloqueos.  Si un subproceso que tiene un bloqueo queda suspendido por un segundo subproceso y el segundo subproceso intenta tomar el mismo bloqueo, se produce un interbloqueo.  <xref:System.Threading.Thread.Suspend%2A> puede interferir con la seguridad, la carga de clases, la comunicación remota, y la reflexión.  
  
#### Regla de análisis de código  
 No llame a <xref:System.Threading.Thread.Suspend%2A>.  Plantéese utilizar un primitivo de sincronización real, como <xref:System.Threading.Semaphore> o <xref:System.Threading.ManualResetEvent>.  
  
### Proteja las operaciones críticas con áreas de ejecución restringida y contratos de confiabilidad  
 Al realizar una operación compleja que actualiza un estado compartido o que debe terminar de forma completamente correcta o completamente incorrecta de manera determinista, asegúrese de que está protegida por un área de ejecución restringida \(CER\).  Esto garantiza que el código se ejecuta en todos los casos, incluso en caso de anulación abrupta del subproceso o de una descarga abrupta de <xref:System.AppDomain>.  
  
 Una CER es un bloque `try/finally` concreto inmediatamente precedido por una llamada a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>.  
  
 Al hacerlo así se indica al compilador Just\-In\-Time que debe preparar todo el código incluido en el bloque finally antes de ejecutar el bloque `try`.  Esto garantiza que se compila el código en el bloque finally y que se ejecutará en todos los casos.  No es raro en una CER tenga un bloque `try` vacío.  Utilizar una CER protege contra las anulaciones asincrónicas de los subprocesos y las excepciones de memoria insuficiente.  Vea <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> para obtener una forma de CER que además controla los desbordamientos de pila para el código excesivamente profundo.  
  
## Vea también  
 <xref:System.Runtime.ConstrainedExecution>   
 [SQL Server Programming and Host Protection Attributes](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)