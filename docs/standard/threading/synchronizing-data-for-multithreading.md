---
title: "Synchronizing Data for Multithreading | Microsoft Docs"
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
  - "synchronization, threads"
  - "threading [.NET Framework], synchronizing threads"
  - "managed threading"
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Synchronizing Data for Multithreading
Cuando varios subprocesos pueden llamar a las propiedades y métodos de un solo objeto, es fundamental sincronizar las llamadas.  En caso contrario, un subproceso puede interrumpir la ejecución de otro subproceso, y el objeto puede terminar teniendo un estado no válido.  Se dice que una clase es segura para subprocesos cuando sus miembros están protegidos contra este tipo de interrupciones.  
  
 La infraestructura de Common Language proporciona diversas estrategias para sincronizar el acceso a instancias y miembros estáticos:  
  
-   Regiones de código sincronizado.  Puede utilizar la clase <xref:System.Threading.Monitor> o la compatibilidad del compilador de esta clase para sincronizar sólo el bloque de código necesario y así mejorar el rendimiento.  
  
-   Sincronización manual.  Puede utilizar los objetos de sincronización proporcionados por la biblioteca de clases de .NET Framework.  Vea [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md), que incluye una discusión de la clase <xref:System.Threading.Monitor>.  
  
-   Contextos sincronizados.  Puede utilizar <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> para habilitar la sincronización automática y simple de objetos <xref:System.ContextBoundObject>.  
  
-   Clases de colección del espacio de nombres <xref:System.Collections.Concurrent?displayProperty=fullName>.  Estas clases proporcionan operaciones integradas sincronizadas de agregar y quitar.  Para obtener más información, vea [Colecciones seguras para subprocesos](../../../docs/standard/collections/thread-safe/index.md).  
  
 Common Language Runtime proporciona un modelo de subproceso en el que las clases pertenecen a un número de categorías que pueden sincronizarse de varias formas diferentes en función de los requisitos.  En la tabla siguiente se muestra la compatibilidad de sincronización proporcionada para campos y métodos con una categoría de sincronización dada.  
  
|Categoría|Campos globales|Campos estáticos|Métodos estáticos|Campos de instancia|Métodos de instancia|Bloques de código específico|  
|---------------|---------------------|----------------------|-----------------------|-------------------------|--------------------------|----------------------------------|  
|Sin sincronización|No|No|No|No|No|No|  
|Contexto sincronizado|No|No|No|Sí|Sí|No|  
|Regiones de código sincronizado|No|No|Sólo si se marca|No|Sólo si se marca|Sólo si se marca|  
|Sincronización manual|Manual|Manual|Manual|Manual|Manual|Manual|  
  
## Sin sincronización  
 Ésta es la opción predeterminada para objetos.  Cualquier subproceso puede tener acceso a un método o campo en cualquier momento.  Sólo debería tener acceso a estos objetos un subproceso cada vez.  
  
## Sincronización manual  
 La biblioteca de clases de .NET Framework proporciona una serie de clases para sincronizar los subprocesos.  Vea [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## Regiones de código sincronizado  
 Puede utilizar la clase <xref:System.Threading.Monitor> o una palabra clave del compilador para sincronizar bloques de código, métodos de instancia y métodos estáticos.  No se admiten los campos estáticos sincronizados.  
  
 Visual Basic y C\# admiten el marcado de bloques de código con una determinada palabra clave de lenguaje, la instrucción `lock` en C\# o la instrucción `SyncLock` en Visual Basic.  Cuando un subproceso ejecuta el código, se realiza un intento de bloqueo.  Si otro subproceso ha realizado ya el bloqueo, el subproceso se bloquea hasta que esté disponible el bloqueo.  Cuando el subproceso sale del bloque sincronizado de código, el bloqueo se libera, independientemente de cómo salga del bloque el subproceso.  
  
> [!NOTE]
>  Las instrucciones `lock` y `SyncLock` se implementan mediante <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName> y <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName>, por lo que se pueden utilizar otros métodos de <xref:System.Threading.Monitor> con ellas en el área sincronizada.  
  
 También puede decorar un método con **MethodImplAttribute** y **MethodImplOptions.Synchronized**, lo que tiene el mismo efecto que utilizar **Monitor** o una de las palabras clave del compilador para bloquear todo el cuerpo del método.  
  
 Se puede utilizar <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> para que un subproceso salga de operaciones de bloqueo, por ejemplo, de la espera para tener acceso a una región de código sincronizado.  También se utiliza **Thread.Interrupt** para que los subprocesos salgan de operaciones como <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  No bloquee el tipo, es decir, `typeof(MyType)` en C\#, `GetType(MyType)` en Visual Basic o `MyType::typeid` en C\+\+, para proteger los métodos `static` \(métodos `Shared` en Visual Basic\).  Utilice en su lugar un objeto estático privado.  De igual forma, no utilice `this` en C\# \(`Me` en Visual Basic\) para bloquear los métodos de instancia.  Utilice en su lugar un objeto privado.  Una clase o instancia se puede bloquear por código distinto del suyo propio, produciendo potenciales interbloqueos o problemas de rendimiento.  
  
### Compatibilidad del compilador  
 Visual Basic y C\# admiten una palabra clave que utiliza <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName> y <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName> para bloquear el objeto.  Visual Basic admite la instrucción [SyncLock](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md) y C\# admite la instrucción [lock](../Topic/lock%20Statement%20\(C%23%20Reference\).md).  
  
 En ambos casos, si se inicia una excepción en el bloque de código, el bloqueo adquirido por **lock** o **SyncLock** se libera automáticamente.  Los compiladores de C\# y de Visual Basic emiten un bloque **try**\/**finally** con **Monitor.Enter** al principio de try y **Monitor.Exit** en el bloque **finally**.  Si se inicia una excepción dentro del bloque **lock** o **SyncLock**, se ejecuta el controlador **finally** para permitir realizar cualquier trabajo de limpieza.  
  
## Contexto sincronizado  
 Puede utilizar el atributo **SynchronizationAttribute** en cualquier objeto **ContextBoundObject** para sincronizar todos los métodos y campos de instancia.  Todos los objetos del mismo dominio de contexto comparten el mismo bloqueo.  Varios subprocesos pueden tener acceso a los métodos y campos, pero sólo uno al mismo tiempo.  
  
## Vea también  
 <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)   
 [SyncLock \(Instrucción\)](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md)   
 [lock \(Instrucción\)](../Topic/lock%20Statement%20\(C%23%20Reference\).md)