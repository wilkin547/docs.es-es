---
title: Procedimientos recomendados para la confiabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- marking locks
- rebooting databases
- denial of service attacks
- back-out code
- SQL Server [.NET Framework], reliability
- synchronization, reliability
- single-threaded COM components
- slow leaks
- suspending threads
- asynchronous exception handling
- leaked resources [.NET Framework]
- unmanaged memory
- memory, reliability
- threading [.NET Framework], reliability
- process-wide domain shared states
- shared states
- SafeHandle class, reliability
- reliability contracts [.NET Framework]
- cleanup operations
- constrained execution regions
- CERs
- finalizers, reliability
- reliability [.NET Framework]
- blocks, reliability
- finally clauses
- cross-application domain shared states
- catch blocks
- identifying locks
- writing reliable code
- impersonation
- GC.KeepAlive method
- managed threading
- locks, reliability
- STA-dependent features
- fibers
ms.assetid: cf624c1f-c160-46a1-bb2b-213587688da7
ms.openlocfilehash: bd51ea1b79ac1dbd89a862f3961cc8508a87f301
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715983"
---
# <a name="reliability-best-practices"></a>Procedimientos recomendados para la confiabilidad

Las siguientes reglas de confiabilidad están orientadas a SQL Server, pero también se aplican a cualquier aplicación de servidor basada en host. Es extremadamente importante que los servidores como SQL Server no pierdan recursos ni se interrumpan.  Pero eso no se puede realizar mediante la escritura de código devuelto para todos los métodos que modifican el estado de un objeto.  El objetivo no es escribir código administrado confiable al 100 por cien que se recupere de los errores en todas las ubicaciones con código devuelto.  Eso sería una tarea desalentadora con escasa probabilidad de éxito.  El Common Language Runtime (CLR) no puede proporcionar fácilmente garantías lo bastante seguras para el código administrado para que la escritura de código perfecto sea viable.  Tenga en cuenta que, a diferencia de ASP.NET, SQL Server solo usa un proceso que no se puede reciclar sin cerrar una base de datos durante un período inaceptablemente prolongado.

Con estas garantías más débiles y al ejecutarse en un único proceso, la confiabilidad se basa en terminar subprocesos o reciclar dominios de aplicación cuando es necesario, y en tomar precauciones para asegurarse de que no se pierden recursos del sistema operativo como identificadores o memoria.  Incluso con esta restricción de confiabilidad más simple, sigue habiendo un requisito de confiabilidad significativo:

- No perder nunca recursos del sistema operativo.

- Identificar todos los tipos de bloqueos administrados para el CLR.

- No interrumpir nunca el estado compartido entre dominios de aplicación, lo que permite que el reciclaje de <xref:System.AppDomain> funcione sin problemas.

Aunque teóricamente sea posible escribir código administrado para controlar excepciones <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> y <xref:System.OutOfMemoryException>, no es razonable esperar que los desarrolladores escriban este tipo de código sólido a lo largo de toda una aplicación.  Por ese motivo, las excepciones fuera de banda hacen que se finalice el subproceso en ejecución; y si el subproceso finalizado estaba editando el estado compartido, lo que se puede determinar si el subproceso mantiene un bloqueo, entonces se descarga el <xref:System.AppDomain>.  Cuando se finaliza un método que está editando el estado compartido, el estado quedará dañado porque no es posible escribir código devuelto confiable para las actualizaciones del estado compartido.

En la versión 2.0 de .NET Framework, el único host que requiere confiabilidad es SQL Server.  Si el ensamblado se va a ejecutar en SQL Server, debe realizar el trabajo de confiabilidad para todos los elementos de ese ensamblado, incluso si hay características específicas que están deshabilitadas cuando se ejecutan en la base de datos.  Esto es obligatorio porque el motor de análisis de código examina el código en el nivel de ensamblado y no puede diferenciar el código deshabilitado. Otra consideración a la hora de programar es que SQL Server ejecuta todo el contenido en un proceso y el reciclaje de <xref:System.AppDomain> se usa para limpiar todos los recursos, como los identificadores de memoria y del sistema operativo.

No puede depender de los finalizadores, destructores ni de bloques `try/finally` para el código devuelto. Es posible que se interrumpan o que no se llamen.

Se pueden iniciar excepciones asincrónicas en ubicaciones inesperadas, posiblemente en cada instrucción del equipo: <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> y <xref:System.OutOfMemoryException>.

Los subprocesos administrados no son necesariamente subprocesos Win32 en SQL; pueden ser fibras.

El estado compartido mutable de todo el proceso o del dominio de varias aplicaciones es muy difícil de modificar de forma segura y debe evitarse siempre que sea posible.

Las condiciones de memoria insuficiente son frecuentes en SQL Server.

Si las bibliotecas hospedadas en SQL Server no actualizan correctamente su estado compartido, hay una probabilidad alta de que el código no se recupere hasta que se haya reiniciado la base de datos.  Además, en algunos casos extremos, es posible que esto pueda provocar un error en el proceso de SQL Server, haciendo que la base de datos se reinicie.  Reiniciar la base de datos puede dejar fuera de servicio a un sitio web o afectar a las operaciones de la empresa, lo que afecta negativamente a la disponibilidad.  Una pérdida lenta de recursos del sistema operativo, como la memoria o los identificadores, puede hacer que se acabe produciendo un error en la asignación de identificadores por parte del servidor sin posibilidad de recuperación, o posiblemente que se degrade el rendimiento del servidor de forma lenta y se reduzca la disponibilidad de las aplicaciones de un cliente.  Es evidente que estos escenarios se deben evitar.

## <a name="best-practice-rules"></a>Reglas de procedimientos recomendados

En la introducción nos centramos en qué tendría que detectar la revisión del código administrado que se ejecuta en el servidor para aumentar la estabilidad y confiabilidad de la plataforma. Todas estas comprobaciones son recomendables en general y absolutamente necesarias en el servidor.

En el caso de un interbloqueo o de una restricción de recursos, SQL Server anulará un subproceso o un <xref:System.AppDomain>.  Cuando esto sucede, solo se garantiza la ejecución de código devuelto en una región de ejecución restringida (CER).

### <a name="use-safehandle-to-avoid-resource-leaks"></a>Usar SafeHandle para evitar pérdidas de recursos

En el caso de una descarga de <xref:System.AppDomain>, no se puede depender de la ejecución de bloques `finally` o finalizadores, por lo que es importante abstraer el acceso a todos los recursos del sistema operativo a través de la clase <xref:System.Runtime.InteropServices.SafeHandle> en lugar de <xref:System.IntPtr>, <xref:System.Runtime.InteropServices.HandleRef> o clases similares. Esto permite que el CLR realice el seguimiento y cierre los identificadores usados incluso en el caso de anulación de <xref:System.AppDomain>.  <xref:System.Runtime.InteropServices.SafeHandle> usará un finalizador crítico que el CLR ejecutará siempre.

El identificador del sistema operativo se almacena en el controlador seguro desde el momento en que se crea hasta el momento en que se libera.  No hay ninguna período de tiempo durante el que una excepción <xref:System.Threading.ThreadAbortException> pueda provocar la pérdida de un identificador.  Además, la invocación de plataforma realizará el recuento de referencias del identificador, lo que permite un seguimiento estricto de la duración del identificador, evitando un problema de seguridad con una condición de carrera entre `Dispose` y un método que actualmente use el identificador.

La mayoría de las clases que actualmente tienen un finalizador simplemente para limpiar un identificador del sistema operativo ya no lo necesitarán. En su lugar, el finalizador estará en la clase derivada <xref:System.Runtime.InteropServices.SafeHandle>.

Tenga en cuenta que <xref:System.Runtime.InteropServices.SafeHandle> no es un sustituto de <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>.  Todavía hay posibles ventajas de contención de recursos y rendimiento a la eliminación explícita de recursos del sistema operativo.  Simplemente tenga en cuenta que es posible que los bloques `finally` que eliminan explícitamente de los recursos no se ejecuten hasta su finalización.

<xref:System.Runtime.InteropServices.SafeHandle> permite implementar su propio método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> que realiza el trabajo necesario para liberar el identificador, como pasar el estado a una rutina de liberación de identificadores del sistema operativo o liberar un conjunto de identificadores en un bucle.  El CLR garantiza que este método se ejecute.  Es responsabilidad del autor de la implementación de <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> asegurarse de que el identificador se libera en todas las circunstancias. Si no lo hace, se producirá la pérdida del identificador, lo que a menudo produce la pérdida de recursos nativos asociados al identificador. Por tanto, es fundamental estructurar las clases derivadas de <xref:System.Runtime.InteropServices.SafeHandle> para que la implementación de <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> no requiera la asignación de ningún recurso que pueda no estar disponible en el momento de la invocación. Tenga en cuenta que se permite llamar a métodos que pueden producir un error en la implementación de <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> siempre que el código pueda controlar esos errores y finalizar el contrato para liberar el identificador nativo. Para la depuración, <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> tiene un valor devuelto de <xref:System.Boolean>, que se puede establecer en `false` si se produce un error catastrófico que impida la liberación del recurso. Si se hace esto, se activará el MDA [releaseHandleFailed](../debug-trace-profile/releasehandlefailed-mda.md), si está habilitado, para ayudar a identificar el problema. No afecta el tiempo de ejecución de ninguna otra forma; no se volverá a llamar a <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> para el mismo recurso y, por tanto, el identificador se perderá.

<xref:System.Runtime.InteropServices.SafeHandle> no es adecuado en ciertos contextos.  Como el método <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> se puede ejecutar en un subproceso de finalizador de <xref:System.GC>, los identificadores que deban liberarse en un subproceso concreto no deben estar contenidos en <xref:System.Runtime.InteropServices.SafeHandle>.

El CLR puede limpiar los contenedores RCW sin ningún código adicional.  Para el código que usa invocación de plataforma y trata un objeto COM como un `IUnknown*` o <xref:System.IntPtr>, el código debe reescribirse para usar un contenedor RCW.  Es posible que <xref:System.Runtime.InteropServices.SafeHandle> no sea adecuado para este escenario debido a la posibilidad de que un método de liberación no administrado se vuelva a llamar en código administrado.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Use <xref:System.Runtime.InteropServices.SafeHandle> para encapsular los recursos del sistema operativo. No use <xref:System.Runtime.InteropServices.HandleRef> o campos de tipo <xref:System.IntPtr>.

### <a name="ensure-finalizers-do-not-have-to-run-to-prevent-leaking-operating-system-resources"></a>Asegurarse de que los finalizadores no tienen que ejecutarse para evitar la pérdida de recursos del sistema operativo

Revise cuidadosamente los finalizadores para asegurarse de que, incluso si no se ejecutan, no se produzca una pérdida de recursos críticos del sistema operativo.  A diferencia de una descarga normal de <xref:System.AppDomain> cuando se está ejecutando la aplicación en un estado estable o cuando un servidor (como por ejemplo SQL Server) se apaga, los objetos no se finalizan durante un descarga inesperada de <xref:System.AppDomain>.  Asegúrese de que no se pierden recursos en caso de una descarga inesperada, ya que no se puede garantizar la exactitud de la aplicación, pero se debe mantener la integridad del servidor sin que haya pérdida de recursos.  Use <xref:System.Runtime.InteropServices.SafeHandle> para liberar los recursos del sistema operativo.

### <a name="ensure-that-finally-clauses-do-not-have-to-run-to-prevent-leaking-operating-system-resources"></a>Asegúrese de que no es necesario que las cláusulas finally se ejecuten para evitar la pérdida de recursos del sistema operativo

No se garantiza que las cláusulas `finally` se ejecuten fuera de las CER, lo que obliga a los desarrolladores de bibliotecas a no confiar en el código de un bloque `finally` para liberar recursos no administrados.  La solución recomendada es usar <xref:System.Runtime.InteropServices.SafeHandle>.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Use <xref:System.Runtime.InteropServices.SafeHandle> para limpiar los recursos del sistema operativo en lugar de `Finalize`. No use <xref:System.IntPtr>; use <xref:System.Runtime.InteropServices.SafeHandle> para encapsular los recursos. Si se tiene que ejecutar la cláusula finally, colóquela en una CER.

### <a name="all-locks-should-go-through-existing-managed-locking-code"></a>Todos los bloqueos deben pasar por el código de bloqueo administrado existente

El CLR debe saber cuándo el código está en un bloqueo para saber que debe anular el <xref:System.AppDomain> en lugar de limitarse a anular el subproceso.  Anular el subproceso podría ser peligroso dado que los datos en los que opera el subproceso podrían quedar en un estado incoherente. Por tanto, tendría que reciclarse <xref:System.AppDomain> por completo.  Las consecuencias de no poder identificar un bloqueo pueden ser interbloqueos o resultados incorrectos. Use los métodos <xref:System.Threading.Thread.BeginCriticalRegion%2A> y <xref:System.Threading.Thread.EndCriticalRegion%2A> para identificar regiones de bloqueo.  Son métodos estáticos de la clase <xref:System.Threading.Thread> que solo se aplican al subproceso actual, lo que ayuda a impedir que un subproceso edite el recuento de bloqueos de otro.

<xref:System.Threading.Monitor.Enter%2A> y <xref:System.Threading.Monitor.Exit%2A> tienen integrada esta notificación al CLR, por lo que se recomienda su uso, así como el uso de la [instrucción lock](../../csharp/language-reference/keywords/lock-statement.md), que usa estos métodos.

Otros mecanismos de bloqueo, como los bloqueos por subproceso y <xref:System.Threading.AutoResetEvent>, deben llamar a estos métodos para notificar al CLR que se está entrando en una sección crítica.  Estos métodos no toman ningún bloqueo; informan al CLR que se está ejecutando código en una sección crítica y la anulación del subproceso podría dejar un estado compartido incoherente.  Si ha definido su propio tipo de bloqueo, como un clase <xref:System.Threading.ReaderWriterLock> personalizada, use estos métodos de recuento de bloqueos.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Marque e identifique todos los bloqueos mediante <xref:System.Threading.Thread.BeginCriticalRegion%2A> y <xref:System.Threading.Thread.EndCriticalRegion%2A>. No use <xref:System.Threading.Interlocked.CompareExchange%2A>, <xref:System.Threading.Interlocked.Increment%2A> y <xref:System.Threading.Interlocked.Decrement%2A> en un bucle.  No realice una invocación de plataforma de las variantes de Win32 de estos métodos.  No use <xref:System.Threading.Thread.Sleep%2A> en un bucle.  No use campos volátiles.

### <a name="cleanup-code-must-be-in-a-finally-or-a-catch-block-not-following-a-catch"></a>El código de limpieza debe estar en un bloque Finally o Catch, no después de un Catch

El código de limpieza nunca debe seguir un bloqueo `catch`; debe estar en `finally` o en el propio bloque `catch`. Esto debería ser una buena práctica normal. Normalmente es preferible un bloque `finally`, porque ejecuta el mismo código tanto cuando se produce una excepción como cuando se llega al final del bloque `try`.  Si se produce una excepción inesperada, por ejemplo <xref:System.Threading.ThreadAbortException>, el código de limpieza no se ejecutará.  Todos los recursos no administrados que limpiaría en `finally`, se deberían incluir en <xref:System.Runtime.InteropServices.SafeHandle> para evitar pérdidas.  Tenga en cuenta que se puede usar la palabra clave `using` de C# de manera eficaz para desechar objetos, incluidos los identificadores.

Aunque el reciclaje de <xref:System.AppDomain> puede limpiar los recursos en el subproceso de finalizador, sigue siendo importante colocar el código de limpieza en el lugar correcto. Tenga en cuenta que si un subproceso recibe una excepción asincrónica sin mantener un bloqueo, el CLR intenta terminar el subproceso por sí mismo, sin necesidad de reciclar el <xref:System.AppDomain>.  Asegurarse de que los recursos se limpian lo antes posible ayuda a que haya más recursos disponibles y a administrar mejor la duración. Si no cierra explícitamente un identificador a un archivo en alguna ruta de acceso del código de error y después espera a que el finalizador de <xref:System.Runtime.InteropServices.SafeHandle> lo limpie, la próxima vez que ejecute el código se puede producir un error al intentar obtener acceso al mismo archivo si todavía no se ha ejecutado el finalizador.  Por este motivo, asegurarse de que el código de limpieza existe y funciona correctamente ayudará a recuperarse de errores de una forma más limpia y rápida, aunque no sea estrictamente necesario.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

El código de limpieza después de `catch` debe estar en un bloque `finally`. Coloque las llamadas al método dispose en un bloque finally. Los bloques `catch` deben terminar con throw o rethrow. Aunque habrá excepciones, como el código que detecta si se puede establecer una conexión de red donde es posible que se obtenga cualquiera de un gran número de excepciones, el código que requiera la detección de un número de excepciones en circunstancias normales debe proporcionar una indicación de que el código se debe probar para ver si va a ser correcto.

### <a name="process-wide-mutable-shared-state-between-application-domains-should-be-eliminated-or-use-a-constrained-execution-region"></a>El estado compartido mutable de todo el proceso entre dominios de aplicación se debe eliminar o utilizar una región de ejecución restringida

Como se describe en la introducción, puede ser muy difícil escribir código administrado que supervise el estado compartido de todo el proceso entre dominios de aplicación de una forma confiable.  El estado compartido de todo el proceso es cualquier tipo de estructura de datos compartida entre dominios de aplicación, ya sea en código Win32, dentro del CLR o en código administrado mediante la comunicación remota.  Cualquier estado compartido mutable es muy difícil de escribir correctamente en código administrado, y cualquier estado compartido estático solo puede hacerse con sumo cuidado.  Si tiene un estado compartido de todo el proceso o todo el equipo, busque alguna forma de eliminarlo o proteja el estado compartido con una región de ejecución restringida (CER).  Tenga en cuenta que cualquier biblioteca con estado compartido que no se identifique y corrija puede producir el bloqueo de un host, como SQL Server, que requiera que se limpie la descarga de <xref:System.AppDomain>.

Si el código usa un objeto COM, evite el uso compartido de ese objeto COM entre dominios de aplicación.

### <a name="locks-do-not-work-process-wide-or-between-application-domains"></a>Los bloqueos no funcionan en todo el proceso o entre dominios de aplicación.

En el pasado, <xref:System.Threading.Monitor.Enter%2A> y la [instrucción lock](../../csharp/language-reference/keywords/lock-statement.md) se han usado para crear bloqueos de proceso globales.  Por ejemplo, esto se produce al bloquear en clases ágiles de <xref:System.AppDomain>, como instancias de <xref:System.Type> de ensamblados no compartidos, objetos <xref:System.Threading.Thread>, cadenas internadas y algunas cadenas compartidas entre dominios de aplicación mediante comunicación remota.  Estos bloqueos ya no son de todo el proceso.  Para identificar la presencia de un bloqueo de dominios entre aplicaciones de todo el proceso, determine si el código dentro del bloqueo usa algún recurso persistente externo, como un archivo en disco o, posiblemente, una base de datos.

Tenga en cuenta que tomar un bloqueo en un <xref:System.AppDomain> es posible que cause problemas si el código protegido usa un recurso externo, dado que ese código podría ejecutarse simultáneamente en varios dominios de aplicación.  Esto puede ser un problema al escribir en un archivo de registro o al enlazar a un socket para todo el proceso.  Estos cambios significan que no hay ninguna manera fácil, mediante código administrado, de obtener un bloqueo global del proceso que no sea usar una instancia de <xref:System.Threading.Mutex> o <xref:System.Threading.Semaphore> con nombre.  Cree código que no se ejecute simultáneamente en dos dominios de aplicación, o use las clases <xref:System.Threading.Mutex> o <xref:System.Threading.Semaphore>.  Si no se puede cambiar el código existente, no use una exclusión mutua con nombre de Win32 para conseguir esta sincronización, dado que la ejecución en modo de fibra significa que no se puede garantizar que el mismo subproceso de sistema operativo vaya a adquirir y liberar una exclusión mutua.  Debe usar la clase administrada <xref:System.Threading.Mutex>, <xref:System.Threading.ManualResetEvent> con nombre, <xref:System.Threading.AutoResetEvent> o <xref:System.Threading.Semaphore> para sincronizar el bloqueo de código de forma que el CLR lo sepa en lugar de sincronizar el bloqueo con código no administrado.

#### <a name="avoid-locktypeofmytype"></a>Evitar lock(typeof(MyType))

Los objetos <xref:System.Type> públicos y privados en ensamblados compartidos con solo una copia del código que se comparte entre todos los dominios de aplicación también presentan problemas.  Para los ensamblados compartidos, solo hay una instancia de un <xref:System.Type> por proceso, lo que significa que varios dominios de aplicación comparten la misma instancia de <xref:System.Type>.  Tomar un bloqueo en una instancia de <xref:System.Type> toma un bloqueo que afecta a todo el proceso, no solo al <xref:System.AppDomain>.  Si <xref:System.AppDomain> toma un bloqueo en un objeto <xref:System.Type> y después ese subproceso se anula abruptamente, no liberará el bloqueo.  Después, este bloqueo, puede provocar el interbloqueo de otros dominios de aplicación.

Una buena manera de tomar bloqueos en métodos estáticos implica agregar un objeto de sincronización interno estático al código.  Esto se podría inicializar en el constructor de clase si existe, pero si no, se puede inicializar de esta forma:

```csharp
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

Después, al tomar un bloqueo, use la propiedad `InternalSyncObject` para obtener un objeto para bloquear.  No es necesario usar la propiedad si el objeto de sincronización interno se ha inicializado en el constructor de la clase.  El código de inicialización de bloqueo de comprobación debe ser similar a este ejemplo:

```csharp
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

#### <a name="a-note-about-lockthis"></a>Una nota acerca del bloqueo (this)

Normalmente resulta aceptable tomar un bloqueo en un objeto individual que es accesible públicamente.  Pero si es un objeto Singleton que es posible que provoque el interbloqueo de un subsistema completo, considere la posibilidad de usar el modelo de diseño anterior.  Por ejemplo, un bloqueo en el objeto <xref:System.Security.SecurityManager> podría causar un interbloqueo en el <xref:System.AppDomain> inutilizando todo el <xref:System.AppDomain>. Es recomendable no tomar un bloqueo en un objeto accesible públicamente de este tipo.  No obstante, un bloqueo en una colección o matriz concreta generalmente no debería suponer un problema.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

No tome bloqueos en tipos que es posible que se usen en dominios de aplicación o no tengan un sentido fuerte de identidad. No llame a <xref:System.Threading.Monitor.Enter%2A> en un objeto <xref:System.Type>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.PropertyInfo>, <xref:System.String>, <xref:System.ValueType>, <xref:System.Threading.Thread> o cualquier otro que se derive de <xref:System.MarshalByRefObject>.

### <a name="remove-gckeepalive-calls"></a>Quitar GC. Llamadas KeepAlive

Una cantidad significativa del código existente no usa <xref:System.GC.KeepAlive%2A> cuando debe o lo usa cuando no es adecuado.  Después de convertir a <xref:System.Runtime.InteropServices.SafeHandle>, no es necesario que las clases llamen a <xref:System.GC.KeepAlive%2A>, suponiendo que no tienen un finalizador sino que se basan en <xref:System.Runtime.InteropServices.SafeHandle> para finalizar los identificadores de sistema operativo.  Mientras que el costo de rendimiento de mantener una llamada a <xref:System.GC.KeepAlive%2A> puede ser insignificante, la percepción de que una llamada a <xref:System.GC.KeepAlive%2A> es necesaria o suficiente para solucionar un problema de duración que puede que ya no exista hace que el código sea más difícil de mantener.  Aun así, cuando se usan contenedores RCW de interoperabilidad COM, el código sigue necesitando <xref:System.GC.KeepAlive%2A>.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Quite <xref:System.GC.KeepAlive%2A>.

### <a name="use-the-hostprotection-attribute"></a>Usar el atributo HostProtection

El <xref:System.Security.Permissions.HostProtectionAttribute> (HPA) proporciona el uso de acciones de seguridad declarativa para determinar los requisitos de protección del host, lo que permite que el host evite que incluso el código de plena confianza llame a determinados métodos que no son apropiados para el host dado, como <xref:System.Environment.Exit%2A> o <xref:System.Windows.Forms.MessageBox.Show%2A> para SQL Server.

El HPA solo afecta a las aplicaciones no administradas que hospedan el CLR e implementan protección de host, como SQL Server. Cuando se aplica, la acción de seguridad crea como resultado una petición de vínculo que se basa en los recursos de host que expone la clase o el método. Si el código se ejecuta en una aplicación cliente o en un servidor que no está protegido por el host, el atributo "se evapora"; no se detecta y, por tanto, no se aplica.

> [!IMPORTANT]
> El propósito de este atributo es aplicar las directrices del modelo de programación específico del host, no el comportamiento de seguridad.  Aunque se usa una petición de vínculo para comprobar el cumplimiento de los requisitos del modelo de programación, el <xref:System.Security.Permissions.HostProtectionAttribute> no es un permiso de seguridad.

Si el host no tiene requisitos de modelo de programación, no se producen peticiones de vínculo.

Este atributo identifica lo siguiente:

- Métodos o clases que no se ajustan al modelo de programación del host, pero que son inofensivos.

- Métodos o clases que no se ajustan al modelo de programación del host y que podrían desestabilizar el código de usuario administrado por el servidor.

- Métodos o clases que no se ajustan al modelo de programación del host y que podrían desestabilizar el propio proceso de servidor.

> [!NOTE]
> Si va a crear una biblioteca de clases que va a ser llamada por aplicaciones que se pueden ejecutar en un entorno de host protegido, debe aplicar este atributo a los miembros que exponen categorías de recursos de <xref:System.Security.Permissions.HostProtectionResource>. Los miembros de la biblioteca de clases .NET Framework con este atributo hacen que solo se compruebe el llamador inmediato.  El miembro de biblioteca también debe provocar una comprobación de su llamador inmediato de la misma manera.

Encontrará más información sobre HPA en <xref:System.Security.Permissions.HostProtectionAttribute>.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Para SQL Server, todos los métodos que se usan para introducir la sincronización o subprocesos deben identificarse con el atributo HPA. Esto incluye los métodos que comparten el estado, se sincronizan o administran procesos externos. Los valores de <xref:System.Security.Permissions.HostProtectionResource> que afectan a SQL Server son <xref:System.Security.Permissions.HostProtectionResource.SharedState>, <xref:System.Security.Permissions.HostProtectionResource.Synchronization> y <xref:System.Security.Permissions.HostProtectionResource.ExternalProcessMgmt>. Sin embargo, cualquier método que expone cualquier <xref:System.Security.Permissions.HostProtectionResource> debe identificarse mediante un atributo HPA, no solo los recursos que afectan a SQL.

### <a name="do-not-block-indefinitely-in-unmanaged-code"></a>No bloquear indefinidamente en código no administrado

El bloqueo en código no administrado en lugar de en código administrado puede provocar un ataque por denegación de servicio porque el CLR no puede anular el subproceso.  Un subproceso bloqueado impide al CLR descargar <xref:System.AppDomain>, al menos sin tener que realizar algunas operaciones extremadamente no seguras.  El bloqueo mediante una primitiva de sincronización de Windows es un claro ejemplo de algo que no se puede permitir.  El bloqueo en una llamada a `ReadFile` en un socket debe evitarse si es posible; idealmente, la API de Windows debe proporcionar un mecanismo para que una operación como esta agote el tiempo de espera.

Cualquier método que realice llamadas nativas debería usar idealmente una llamada de Win32 con un tiempo de espera razonable y finito.  Si se permite al usuario especificar el tiempo de espera, el usuario no debería poder especificar un tiempo de espera infinito sin algunos permisos de seguridad específicos.  Como norma, si un método se va a bloquear durante más de 10 segundos, se debe usar una versión que admita tiempos de espera o necesitará soporte adicional del CLR.

Estos son algunos ejemplos de API problemáticas.  Se pueden crear canalizaciones (anónimas y con nombre) con un tiempo de espera, pero el código debe garantizar que nunca llama a `CreateNamedPipe` ni `WaitNamedPipe` con NMPWAIT_WAIT_FOREVER.  Además, puede haber un bloqueo inesperado incluso si se especifica un tiempo de espera.  La llamada a `WriteFile` en una canalización anónima se bloqueará hasta que se escriban todos los bytes, lo que significa que si el búfer contiene datos sin leer, la llamada a `WriteFile` se bloqueará hasta que el lector haya liberado espacio en el búfer de la canalización.  Los sockets siempre deberían usar alguna API que acepte un mecanismo de tiempo de espera.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Bloquear sin un tiempo de espera en código no administrado es un ataque por denegación de servicio. No realice llamadas de invocación de plataforma a `WaitForSingleObject`, `WaitForSingleObjectEx`, `WaitForMultipleObjects`, `MsgWaitForMultipleObjects` y `MsgWaitForMultipleObjectsEx`.  No use NMPWAIT_WAIT_FOREVER.

### <a name="identify-any-sta-dependent-features"></a>Identificación de las características que dependen de STA

Identifique cualquier código que use contenedores uniproceso (STA) de COM.  Los STA están deshabilitados en el proceso de SQL Server.  Las características que dependen de `CoInitialize`, como los contadores de rendimiento o el Portapapeles, deben deshabilitarse en SQL Server.

### <a name="ensure-finalizers-are-free-of-synchronization-problems"></a>Asegurarse de que los finalizadores no tienen problemas de sincronización

Es posible que en futuras versiones de .NET existan varios subprocesos de finalizador, lo que significa que los finalizadores para distintas instancias del mismo tipo se ejecutan simultáneamente.  No es necesario que sean totalmente seguros para subprocesos; el recolector de elementos no utilizados garantiza que solo un subproceso ejecutará el finalizador de una instancia de objeto determinada.  No obstante, los finalizadores deben estar codificados para evitar interbloqueos y condiciones de carrera cuando se ejecutan simultáneamente en varias instancias de objeto distintas.  Cuando en un finalizador se usa un estado externo, como al escribir en un archivo de registro, los problemas de subprocesos se deben solucionar.  No confíe en la finalización para proporcionar seguridad para subprocesos. No use almacenamiento local de subprocesos, administrado o nativo, para almacenar el estado en el subproceso del finalizador.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Los finalizadores no deben presentar problemas de sincronización. No use un estado mudable estático en un finalizador.

### <a name="avoid-unmanaged-memory-if-possible"></a>Evitar la memoria no administrada si es posible

La memoria no administrada puede tener pérdidas, al igual que un identificador del sistema operativo. Si es posible, intente usar memoria de la pila mediante [stackalloc](../../csharp/language-reference/operators/stackalloc.md) o un objeto administrado anclado, como la [instrucción fixed](../../csharp/language-reference/keywords/fixed-statement.md) o un <xref:System.Runtime.InteropServices.GCHandle> mediante un byte []. El <xref:System.GC> acabará por limpiarlos. Pero si tiene que asignar memoria no administrada, considere el uso de una clase derivada de <xref:System.Runtime.InteropServices.SafeHandle> para encapsular la asignación de memoria.

Tenga en cuenta que al menos hay un caso en el que <xref:System.Runtime.InteropServices.SafeHandle> no resulta adecuado. Para las llamadas a métodos COM que asignan o liberan memoria, es común que un archivo DLL asigne memoria a través de `CoTaskMemAlloc` y después otro archivo DLL libere esa memoria con `CoTaskMemFree`.  Usar <xref:System.Runtime.InteropServices.SafeHandle> en estos casos no sería adecuado porque intentará unir la duración de la memoria no administrada a la duración del <xref:System.Runtime.InteropServices.SafeHandle> en lugar de permitir que el otro archivo DLL controle la duración de la memoria.

### <a name="review-all-uses-of-catchexception"></a>Revisar todos los usos de catch (excepción)

Los bloques catch que detectan todas las excepciones en lugar de una excepción concreta ahora también detectarán las excepciones asincrónicas. Examine todos los bloques catch(Exception) en busca de código devuelto o de liberación de recursos que no sea importante y que se haya podido pasar por alto, así como comportamientos potencialmente incorrectos dentro del propio bloque catch para controlar una excepción <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> u <xref:System.OutOfMemoryException>.  Tenga en cuenta que es posible que este código registre o asuma que solo puede ver determinadas excepciones, o que cada vez que se produce una excepción se produzca un error por un único motivo concreto.  Es posible que tenga que actualizar estas suposiciones para incluir <xref:System.Threading.ThreadAbortException>.

Considere la posibilidad de cambiar todos los lugares en que se detectan todas las excepciones por la detección de un tipo concreto de excepción que espera que se vaya producir, como una excepción <xref:System.FormatException> de métodos de formato de cadena.  Esto impide que el bloque catch se ejecute con excepciones inesperadas y ayuda a garantizar que el código no oculta errores detectando excepciones inesperadas.  Como norma general, no controle nunca una excepción en código de biblioteca (el código que requiere que se detecte una excepción puede indicar un problema de diseño en el código al que se está llamando).  En algunos casos es posible que quiera detectar una excepción e iniciar un tipo de excepción diferente para proporcionar más datos.  En este caso, use las excepciones anidadas, almacenando la causa real del error en la propiedad <xref:System.Exception.InnerException%2A> de la nueva excepción.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Revise todos los bloques catch en código administrado que detectan todos los objetos o todas las excepciones.  En C#, esto significa marcar ambos `catch` {} y `catch(Exception)` {}.  Considere la posibilidad de hacer que el tipo de excepción sea muy específico, o bien revise el código para asegurarse de que no actúa de forma incorrecta si detecta un tipo de excepción inesperada.

### <a name="do-not-assume-a-managed-thread-is-a-win32-thread--it-is-a-fiber"></a>No asuma que un subproceso administrado es un subproceso de Win32, es una fibra

El uso de almacenamiento local de subprocesos administrados sirve, pero no se puede usar el almacenamiento local de subprocesos no administrados ni suponer que el código se va a ejecutar de nuevo en el subproceso del sistema operativo actual. No cambie ajustes como la configuración regional del subproceso. No llame a `InitializeCriticalSection` o `CreateMutex` a través de la invocación de plataforma porque requieren que el subproceso del sistema operativo que entra en un bloqueo también salga del bloqueo. Como este no es el caso cuando se usan fibras, las secciones críticas de Win32 y las exclusiones mutuas no se pueden usar directamente en SQL.  Tenga en cuenta que la clase administrada <xref:System.Threading.Mutex> no controla estas consideraciones de afinidad de subprocesos.

Puede usar sin ningún riesgo la mayor parte del estado en un objeto <xref:System.Threading.Thread> administrado, incluido el almacenamiento local de subprocesos administrados y la referencia cultural de la interfaz de usuario actual del subproceso. También puede usar el <xref:System.ThreadStaticAttribute>, que hace que el valor de una variable estática existente solo sea accesible para el subproceso administrado actual (es otra manera de realizar almacenamiento local de fibras en el CLR). Por motivos del modelo de programación, no se puede cambiar la referencia cultural actual de un subproceso cuando se ejecuta en SQL.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

SQL Server se ejecuta en modo de fibra; no use almacenamiento local de subprocesos. Evite llamadas de invocación de plataforma a `TlsAlloc`, `TlsFree`, `TlsGetValue` y `TlsSetValue.`

### <a name="let-sql-server-handle-impersonation"></a>Permitir que SQL Server controle la suplantación

Dado que la suplantación opera en el nivel de subproceso y SQL se puede ejecutar en modo de fibra, el código administrado no debe suplantar a los usuarios y no debería llamar a `RevertToSelf`.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

Permita que SQL Server controle la suplantación. No use `RevertToSelf`, `ImpersonateAnonymousToken`, `DdeImpersonateClient`, `ImpersonateDdeClientWindow`, `ImpersonateLoggedOnUser`, `ImpersonateNamedPipeClient`, `ImpersonateSelf`, `RpcImpersonateClient`, `RpcRevertToSelf`, `RpcRevertToSelfEx` ni `SetThreadToken`.

### <a name="do-not-call-threadsuspend"></a>No llamar a Thread:: Suspend

La capacidad de suspender un subproceso parece una operación sencilla, pero puede producir interbloqueos.  Si un subproceso que mantiene un bloqueo queda suspendido por un segundo subproceso y, después, el segundo subproceso intenta tomar el mismo bloqueo, se produce un interbloqueo.  En la actualidad, <xref:System.Threading.Thread.Suspend%2A> puede interferir con la seguridad, la carga de clases, la comunicación remota y la reflexión.

#### <a name="code-analysis-rule"></a>Regla de análisis de código

No llame a <xref:System.Threading.Thread.Suspend%2A>. Considere el uso de una primitiva de sincronización real en su lugar, como un <xref:System.Threading.Semaphore> o <xref:System.Threading.ManualResetEvent>.

### <a name="protect-critical-operations-with-constrained-execution-regions-and-reliability-contracts"></a>Proteja las operaciones críticas con regiones de ejecución restringidas y contratos de confiabilidad

Al realizar una operación compleja que actualiza un estado compartido o que deba ser totalmente correcta o totalmente incorrecta de manera determinante, asegúrese de que está protegida por una región de ejecución restringida (CER). Esto garantiza que el código se ejecuta en todos los casos, incluso en una anulación abrupta del subproceso o una descarga abrupta de <xref:System.AppDomain>.

Una CER es un bloque `try/finally` concreto precedido inmediatamente por una llamada a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>.

Hacer esto indica al compilador Just-In-Time que prepare todo el código en el bloque finally antes de ejecutar el bloque `try`. Esto garantiza que el código en el bloque finally se compila y se ejecuta en todos los casos. No es raro que una CER tenga un bloque `try` vacío. El uso de una CER protege frente a anulaciones de subprocesos asincrónicos y excepciones de memoria insuficiente. Vea <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A> para obtener una forma de CER que además administra desbordamientos de pila para código excesivamente profundo.

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.ConstrainedExecution>
- [Programación en SQL Server y atributos de protección de host](sql-server-programming-and-host-protection-attributes.md)
