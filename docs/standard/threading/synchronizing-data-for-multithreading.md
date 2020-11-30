---
title: Sincronizar datos para subprocesamiento múltiple
description: Aprenda a sincronizar datos para multithreading en .NET. Elija estrategias tales como regiones de código sincronizado, sincronización manual o contextos sincronizados.
ms.date: 03/30/2017
helpviewer_keywords:
- synchronization, threads
- threading [.NET], synchronizing threads
- managed threading
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
ms.openlocfilehash: e1b90bdc5657c1fd22c6e77e31890ff63c3cc3ea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727463"
---
# <a name="synchronizing-data-for-multithreading"></a>Sincronizar datos para multithreading

Cuando varios subprocesos pueden realizar llamadas a las propiedades y los métodos de un objeto individual, es fundamental sincronizarlas. De lo contrario, un subproceso puede interrumpir lo que esté realizando otro y el objeto podría quedar en un estado no válido. La clase cuyos miembros están protegidos de tales interrupciones se conoce como segura para subprocesos.  
  
.NET proporciona diversas estrategias para sincronizar el acceso a miembros estáticos y de instancia:  
  
- Regiones de código sincronizado. Puede usar la clase <xref:System.Threading.Monitor> o la compatibilidad de compilador para esta clase para sincronizar solo el bloque de código que lo necesite y mejorar así el rendimiento.  
  
- Sincronización manual. Puede usar los objetos de sincronización que proporciona la biblioteca de clases de .NET. Consulte [Información general sobre los primitivos de sincronización](overview-of-synchronization-primitives.md), que incluye una explicación de la clase <xref:System.Threading.Monitor>.  
  
- Contextos sincronizados. Solo en el caso de las aplicaciones de .NET Framework y Xamarin, puede usar <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> para habilitar la sincronización automática y simple de objetos <xref:System.ContextBoundObject>.  
  
- Clases de colección del espacio de nombres <xref:System.Collections.Concurrent?displayProperty=nameWithType>. Estas clases proporcionan operaciones de incorporación y eliminación sincronizadas incorporadas. Para obtener más información, consulte [Colecciones seguras para subprocesos](../collections/thread-safe/index.md).  
  
 Common Language Runtime proporciona un modelo de subprocesos en el que las clases se dividen en varias categorías que se pueden sincronizar de distintas maneras (según sea necesario). En la siguiente tabla se muestra la compatibilidad de sincronización que se proporciona para los campos y los métodos de determinadas categorías de sincronización.  
  
|Categoría|Campos generales|Campos estáticos|Métodos estáticos|Campos de instancia|Métodos de instancia|Bloques de código específicos|  
|--------------|-------------------|-------------------|--------------------|---------------------|----------------------|--------------------------|  
|Sin sincronización|No|No|No|No|No|No|  
|Contexto sincronizado|No|No|No|Sí|Sí|No|  
|Regiones de código sincronizado|No|No|Solo si se marcan|No|Solo si se marcan|Solo si se marcan|  
|Sincronización manual|Manual|Manual|Manual|Manual|Manual|Manual|  
  
## <a name="no-synchronization"></a>Sin sincronización  

 Este es el valor predeterminado para los objetos. Todos los subprocesos pueden acceder a cualquier método o campo en cualquier momento. Solo puede acceder a estos objetos un subproceso a la vez.  
  
## <a name="manual-synchronization"></a>Sincronización manual  

 La biblioteca de clases de .NET proporciona una serie de clases para sincronizar subprocesos. Consulte [Overview of Synchronization Primitives](overview-of-synchronization-primitives.md) (Introducción a los primitivos de sincronización).  
  
## <a name="synchronized-code-regions"></a>Regiones de código sincronizado  

 Puede usar la clase <xref:System.Threading.Monitor> o una palabra clave del compilador para sincronizar bloques de código, métodos de instancia y métodos estáticos. No se admiten los campos estáticos sincronizados.  
  
 Visual Basic y C# admiten el marcado de bloques de código con una palabra clave de lenguaje concreta, la instrucción `lock` de C# o la instrucción `SyncLock` de Visual Basic. Cuando se ejecuta el código en un subproceso, se realiza un intento de adquirir el bloqueo. Si otro subproceso ya lo ha adquirido, el subproceso se bloquea hasta que el bloqueo vuelva a estar disponible. Cuando el subproceso sale del bloque de código sincronizado, el bloqueo se libera, independientemente de la manera en que lo haga.  
  
> [!NOTE]
> Las instrucciones `lock` y `SyncLock` se implementan con <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>, por lo que se pueden usar otros métodos de <xref:System.Threading.Monitor> junto con ellas en la región sincronizada.  
  
 También puede decorar un método con <xref:System.Runtime.CompilerServices.MethodImplAttribute> con un valor de <xref:System.Runtime.CompilerServices.MethodImplOptions.Synchronized?displayProperty=nameWithType>, que tiene el mismo efecto que usar <xref:System.Threading.Monitor> o una de las palabras clave del compilador para bloquear todo el cuerpo del método.  
  
 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> puede utilizarse para que un subproceso salga de operaciones de bloqueo, como esperar para acceder a una región de código sincronizado. **Thread.Interrupt** también se utiliza para que los subprocesos salgan de operaciones como <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> No bloquee el tipo, es decir, `typeof(MyType)` en C#, `GetType(MyType)` en Visual Basic o `MyType::typeid` en C++, para proteger los métodos `static` (métodos `Shared` en Visual Basic). Utilice en su lugar un objeto estático privado. Asimismo, no utilice `this` en C# (`Me` en Visual Basic) para bloquear los métodos de instancia. Utilice en su lugar un objeto privado. Una clase o instancia se puede bloquear por código distinto del suyo, lo que puede producir interbloqueos o problemas de rendimiento.  
  
### <a name="compiler-support"></a>Compatibilidad del compilador  

 Visual Basic y C# admiten una palabra clave del lenguaje que utiliza <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> y <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> para bloquear el objeto. Visual Basic admite la instrucción [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md); C# admite la instrucción [lock](../../csharp/language-reference/keywords/lock-statement.md).  
  
 En ambos casos, si se produce una excepción en el bloque de código, el bloqueo de **lock** o **SyncLock** se anula automáticamente. Los compiladores de C# y Visual Basic emiten un bloque **try**/**finally** con **Monitor.Enter** al principio de try, y **Monitor.Exit** en el bloque **finalmente**. Si se produce una excepción en el bloque **lock** o **SyncLock**, el controlador **finally** se ejecuta para que realice los trabajos de limpieza.  
  
## <a name="synchronized-context"></a>Contexto sincronizado  

Solo en aplicaciones de .NET Framework y Xamarin, puede usar <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> en cualquier <xref:System.ContextBoundObject> para sincronizar todos los campos y métodos de instancia. Todos los objetos del mismo dominio de contexto comparten la misma instrucción lock. Varios subprocesos pueden acceder a los métodos y los campos, pero solo se permite uno a la vez.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>
- [Subprocesos y subprocesamiento](threads-and-threading.md)
- [Información general sobre las primitivas de sincronización](overview-of-synchronization-primitives.md)
- [SyncLock (instrucción)](../../visual-basic/language-reference/statements/synclock-statement.md)
- [lock (instrucción)](../../csharp/language-reference/keywords/lock-statement.md)
