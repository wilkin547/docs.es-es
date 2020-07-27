---
title: Subprocesamiento administrado y no administrado en Windows
ms.date: 10/24/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], unmanaged
- threading [.NET Framework], managed
- threading [.NET], managed
- threads and fibers [.NET]
- managed threading
ms.assetid: 4fb6452f-c071-420d-9e71-da16dee7a1eb
ms.openlocfilehash: de823297540d5ce3740a26614dbb9a82881decf3
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924388"
---
# <a name="managed-and-unmanaged-threading-in-windows"></a>Subprocesamiento administrado y no administrado en Windows

La administración de todos los subprocesos se realiza mediante la clase <xref:System.Threading.Thread> , incluidos los subprocesos creados por Common Language Runtime y los creados fuera del runtime que entran en el entorno administrado para ejecutar código. El runtime supervisa todos los subprocesos del proceso que han ejecutado alguna vez código en el entorno de ejecución administrado. No realiza un seguimiento de ningún otro subproceso. Los subprocesos pueden acceder al entorno de ejecución administrado a través de la interoperabilidad COM (porque el runtime expone los objetos administrados como objetos COM a los entornos no administrados), la función COM [DllGetClassObject](/windows/desktop/api/combaseapi/nf-combaseapi-dllgetclassobject) y la invocación de plataforma.  
  
 Cuando un subproceso no administrado entra en el runtime a través de, por ejemplo, un contenedor CCW, el sistema comprueba el almacén local del subproceso para buscar un objeto <xref:System.Threading.Thread> administrado interno. Si se encuentra uno, el runtime ya tiene en cuenta este subproceso. Si no lo encuentra, el runtime compila un nuevo objeto <xref:System.Threading.Thread> y lo instala en el almacén local de ese subproceso.  
  
 En los subprocesos administrados, <xref:System.Threading.Thread.GetHashCode%2A?displayProperty=nameWithType> es la identificación del subproceso administrado estable. En cuanto a la duración de su subproceso, no estará en conflicto con el valor de ningún otro subproceso, independientemente del dominio de la aplicación del que obtiene este valor.  
  
## <a name="mapping-from-win32-threading-to-managed-threading"></a>Asignación de subprocesos de Win32 a subprocesos administrados

 En la tabla siguiente se asignan elementos de subproceso de Win32 a sus equivalentes de runtime aproximados. Tenga en cuenta que esta asignación no representa una funcionalidad idéntica. Por ejemplo, **TerminateThread** no ejecuta cláusulas **finally** ni libera recursos, y no se puede evitar. No obstante, <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> ejecuta todo su código de reversión, recupera todos los recursos y se puede denegar con <xref:System.Threading.Thread.ResetAbort%2A>. Asegúrese de leer detenidamente la documentación y no realice suposiciones sobre la funcionalidad.  
  
|En Win32|En Common Language Runtime|  
|--------------|------------------------------------|  
|**CreateThread**|Combinación de **Thread** y <xref:System.Threading.ThreadStart>|  
|**TerminateThread**|<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>|  
|**SuspendThread**|<xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>|  
|**ResumeThread**|<xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>|  
|**Sleep**|<xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>|  
|**WaitForSingleObject** en el identificador de subproceso|<xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>|  
|**ExitThread**|No equivalente|  
|**GetCurrentThread**|<xref:System.Threading.Thread.CurrentThread%2A?displayProperty=nameWithType>|  
|**SetThreadPriority**|<xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType>|  
|No equivalente|<xref:System.Threading.Thread.Name%2A?displayProperty=nameWithType>|  
|No equivalente|<xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>|  
|Cercano a **CoInitializeEx** (OLE32.DLL)|<xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType>|  
  
## <a name="managed-threads-and-com-apartments"></a>Subprocesos administrados y apartamentos COM

Un subproceso administrado se puede marcar para indicar que hospedará un contenedor [uniproceso](/windows/desktop/com/single-threaded-apartments) o [multiproceso](/windows/desktop/com/multithreaded-apartments) . (Para más información sobre la arquitectura de subprocesos COM, consulte [Procesos, subprocesos y contenedores](/windows/desktop/com/processes--threads--and-apartments)). Los métodos <xref:System.Threading.Thread.GetApartmentState%2A>, <xref:System.Threading.Thread.SetApartmentState%2A> y <xref:System.Threading.Thread.TrySetApartmentState%2A> de la clase <xref:System.Threading.Thread> devuelven y asignan el estado de contenedor de un subproceso. Si el estado no se ha establecido, <xref:System.Threading.Thread.GetApartmentState%2A> devuelve <xref:System.Threading.ApartmentState.Unknown?displayProperty=nameWithType>.  
  
 La propiedad solo se puede establecer cuando el estado del subproceso es <xref:System.Threading.ThreadState.Unstarted?displayProperty=nameWithType> y únicamente una vez por subproceso.  
  
 Si el estado de contenedor no se establece antes de que se inicie el subproceso, el subproceso se inicializa como un contenedor multiproceso (MTA). El subproceso de finalizador y todos los subprocesos controlados por <xref:System.Threading.ThreadPool> son MTA.  
  
> [!IMPORTANT]
> Para el código de inicio de aplicación, la única manera de controlar el estado de contenedor es aplicar <xref:System.MTAThreadAttribute> o <xref:System.STAThreadAttribute> al procedimiento de punto de entrada. En .NET Framework 1.0 y 1.1, la propiedad <xref:System.Threading.Thread.ApartmentState%2A> se puede establecer como la primera línea de código. Esto no está permitido en .NET Framework 2.0.  
  
 Los objetos administrados que están expuestos a COM se comportan como si tuviesen agregado el cálculo de referencias con subprocesamiento libre. En otras palabras, se pueden llamar desde cualquier apartamento COM en un modo de subprocesamiento libre. Los únicos objetos administrados que no muestran este comportamiento de subprocesamiento libre son aquellos que derivan de <xref:System.EnterpriseServices.ServicedComponent> o <xref:System.Runtime.InteropServices.StandardOleMarshalObject>.  
  
 En el ámbito de recursos administrados, <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> no se admite a menos que se usen contextos e instancias administradas asociadas a un contexto. Si usa Enterprise Services, entonces su objeto debe derivarse de <xref:System.EnterpriseServices.ServicedComponent> (que a su vez se deriva de <xref:System.ContextBoundObject>).  
  
 Cuando el código administrado llama a objetos COM, siempre sigue reglas COM. En otras palabras, el código llama a través de los proxy de apartamentos COM y contenedores de contexto COM+ 1.0, según lo dictado por OLE32.  
  
## <a name="blocking-issues"></a>Problemas de bloqueo  

Si un subproceso realiza una llamada no administrada al sistema operativo que ha bloqueado el subproceso en código no administrado, el runtime no tomará el control de él para <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> ni <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. En el caso de <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>, el runtime marca el subproceso para **Abort** y toma el control de él cuando vuelve a introducir código administrado. Lo preferible para usted es usar un bloqueo administrado en vez de no administrado. <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>,<xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType>, <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>, <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>, <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType>y demás responden todos a <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> y <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Además, si su subproceso está en un contenedor uniproceso, todas estas operaciones de bloqueo administrado suministrarán correctamente mensajes en su contenedor mientras el subproceso está bloqueado.  

## <a name="threads-and-fibers"></a>Subprocesos y fibras

El modelo de subprocesos de .NET no admite [fibras](/windows/desktop/procthread/fibers). No debe llamar a ninguna función no administrada que se implementa mediante fibras. Tales llamadas pueden producir un bloqueo de runtime de .NET.

## <a name="see-also"></a>Vea también

- <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType>
- <xref:System.Threading.ThreadState>
- <xref:System.EnterpriseServices.ServicedComponent>
- <xref:System.Threading.Thread>
- <xref:System.Threading.Monitor>
