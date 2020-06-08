---
title: Semaphore y SemaphoreSlim
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- counting semaphores
- semaphores
- threading [.NET Framework], cross-process synchronization
- Semaphore class, about Semaphore class
- SemaphoreSlim class, about SemaphoreSlim class
- threading [.NET Framework], Semaphore class
ms.assetid: 7722a333-b974-47a2-a7c0-f09097fb644e
ms.openlocfilehash: 9a18a6517548bb402e1e3b9ac02e95aae32a8f4a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291141"
---
# <a name="semaphore-and-semaphoreslim"></a>Semaphore y SemaphoreSlim
La clase <xref:System.Threading.Semaphore?displayProperty=nameWithType> representa un semáforo local o con nombre (para todo el sistema). Se trata de un contenedor fino alrededor del objeto semáforo de Win32. Los semáforos de Win32 son semáforos de recuento, que se pueden utilizar para controlar el acceso a un grupo de recursos.  
  
 La clase <xref:System.Threading.SemaphoreSlim> representa un semáforo ligero y rápido que se puede usar para esperar en un único proceso cuando se supone que los tiempos de espera serán muy cortos. <xref:System.Threading.SemaphoreSlim> se basa en la medida de lo posible en las primitivas de sincronización proporcionadas por Common Language Runtime (CLR). Sin embargo, también proporciona identificadores de espera basados en kernel e inicializados de forma diferida a fin permitir la espera en varios semáforos. <xref:System.Threading.SemaphoreSlim> también admite el uso de tokens de cancelación, pero no los semáforos con nombre ni el uso de un identificador de espera para sincronización.  
  
## <a name="managing-a-limited-resource"></a>Administrar un recurso limitado  
 Los subprocesos entran en el semáforo mediante la llamada al método <xref:System.Threading.WaitHandle.WaitOne%2A>, heredado de la clase <xref:System.Threading.WaitHandle>, si se trata de un objeto <xref:System.Threading.Semaphore?displayProperty=nameWithType>, o al método <xref:System.Threading.SemaphoreSlim.Wait%2A?displayProperty=nameWithType> o <xref:System.Threading.SemaphoreSlim.WaitAsync%2A?displayProperty=nameWithType>, si se trata de un objeto <xref:System.Threading.SemaphoreSlim>. Cuando se devuelve la llamada, disminuye el recuento en el semáforo. Cuando un subproceso solicita la entrada y el recuento es cero, el subproceso se bloquea. Cuando los subprocesos liberan el semáforo mediante la llamada al método <xref:System.Threading.Semaphore.Release%2A?displayProperty=nameWithType> o <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType>, los subprocesos bloqueados pueden entrar. No hay ningún orden garantizado, como “primero en entrar, primero en salir” (FIFO) o “último en entrar, primero en salir” (LIFO), para que los subprocesos bloqueados entren en el semáforo.  
  
 Un subproceso puede entrar varias veces en el semáforo mediante la llamada al método <xref:System.Threading.Semaphore?displayProperty=nameWithType> del objeto <xref:System.Threading.WaitHandle.WaitOne%2A> o al método <xref:System.Threading.SemaphoreSlim> del objeto <xref:System.Threading.SemaphoreSlim.Wait%2A>. Para liberar el semáforo, el subproceso puede llamar el mismo número de veces a la sobrecarga de un método <xref:System.Threading.Semaphore.Release?displayProperty=nameWithType> o <xref:System.Threading.SemaphoreSlim.Release?displayProperty=nameWithType>, o llamar a la sobrecarga del método <xref:System.Threading.Semaphore.Release%28System.Int32%29?displayProperty=nameWithType> o <xref:System.Threading.SemaphoreSlim.Release%28System.Int32%29?displayProperty=nameWithType> y especificar el número de entradas que se liberan.  
  
### <a name="semaphores-and-thread-identity"></a>Los semáforos y la identidad del subproceso  
 Los dos tipos de semáforo no exigen la identidad del subproceso en las llamadas a los métodos <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.SemaphoreSlim.Wait%2A>, <xref:System.Threading.Semaphore.Release%2A> y <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType>. Por ejemplo, un escenario de uso común para semáforos implica un subproceso productor y un subproceso consumidor; uno de esos subprocesos siempre incrementa el recuento del semáforo y el otro siempre lo reduce.  
  
 Es responsabilidad del programador garantizar que un subproceso no libere el semáforo demasiadas veces. Por ejemplo, supongamos que un semáforo tiene un recuento máximo de dos y que los subprocesos A y B entran el semáforo. Si un error de programación en el subproceso B hace que llame a `Release` dos veces, ambas llamadas tendrán éxito. El recuento del semáforo está lleno y cuando el subproceso A finalmente llama a `Release`, se genera <xref:System.Threading.SemaphoreFullException>.  
  
## <a name="named-semaphores"></a>Semáforos con nombre  
 El sistema operativo Windows permite que los semáforos tengan nombres. Un semáforo con nombre abarca todo el sistema. Es decir, una vez creado el semáforo con nombre, es visible para todos los subprocesos de todos los procesos. Por lo tanto, el semáforo con nombre puede utilizarse para sincronizar tanto las actividades de procesos como las de subprocesos.  
  
 Puede crear un objeto <xref:System.Threading.Semaphore> que represente un semáforo de sistema con nombre mediante el uso de uno de los constructores que especifica un nombre.  
  
> [!NOTE]
> Dado que los semáforos con nombre abarcan todo el sistema, es posible tener varios objetos <xref:System.Threading.Semaphore> que representan el mismo semáforo con nombre. Cada vez que llama a un constructor o al método <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType>, se crea un nuevo objeto <xref:System.Threading.Semaphore>. Si se especifica el mismo nombre repetidamente, se crean varios objetos que representan el mismo semáforo con nombre.  
  
 Tenga cuidado al utilizar los semáforos con nombre. Dado que abarcan todo el sistema, otro proceso que utilice el mismo nombre puede entrar en el semáforo inesperadamente. Si hubiera código malintencionado ejecutándose en el mismo equipo, dicho código podría utilizar esto como base de un ataque de denegación de servicio.  
  
 Utilice la seguridad de control de acceso para proteger un objeto <xref:System.Threading.Semaphore> que representa un semáforo con nombre, a poder ser mediante un constructor que especifique un objeto <xref:System.Security.AccessControl.SemaphoreSecurity?displayProperty=nameWithType>. También puede aplicar la seguridad de control de acceso mediante el método <xref:System.Threading.Semaphore.SetAccessControl%2A?displayProperty=nameWithType>, pero esto deja una ventana de vulnerabilidad entre el momento en que se crea el semáforo y el momento en que se protege. Proteger los semáforos con seguridad de control de acceso ayuda a evitar ataques malintencionados, pero no soluciona el problema de conflictos involuntarios de nombres.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Semaphore>
- <xref:System.Threading.SemaphoreSlim>
- [Objetos y características de subprocesos](threading-objects-and-features.md)
