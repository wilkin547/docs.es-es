---
ms.openlocfilehash: 4ffef401c07dbb27db7c0225acdc6817d95bfe11
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2020
ms.locfileid: "91451372"
---
## <a name="available-counters"></a>Contadores disponibles

En los distintos paquetes de .NET, las métricas básicas sobre la recolección de elementos no utilizados (GC), Just-in-Time (JIT), los ensamblados, las excepciones, los subprocesos, las redes y las solicitudes web se publican mediante EventCounters.

### <a name="systemruntime-counters"></a>Contadores "System.Runtime"

Los siguientes contadores se publican como parte del entorno de ejecución de .NET y se mantienen en [`RuntimeEventSource.cs`](https://github.com/dotnet/coreclr/blob/master/src/System.Private.CoreLib/src/System/Diagnostics/Eventing/RuntimeEventSource.cs).

| Contador | Descripción |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | Porcentaje de tiempo de GC desde la última GC |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | Tasa de asignación en bytes |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | Porcentaje de uso de CPU del proceso |
| :::no-loc text="Exception Count"::: (`exception-count`) | Número de excepciones que se han producido |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | Número de bytes que se considera que están asignados según <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType> |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | Número de veces que se ha producido una GC para Gen 0 |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | Número de bytes para la GC de Gen 0 |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | Número de veces que se ha producido una GC para Gen 1 |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | Número de bytes para la GC de Gen 1 |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | Número de veces que se ha producido una GC para Gen 2 |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | Número de bytes para la GC de Gen 2 |
| :::no-loc text="LOH Size"::: (`loh-size`) | Número de bytes para la GC de Gen 3 |
| :::no-loc text="POH Size"::: (`poh-size`) | Número de bytes del montón de objetos anclados (disponible en .NET 5 y versiones posteriores) |
| :::no-loc text="GC Fragmentation"::: (`gc-fragmentation`) | Fragmentación de montones de recolección de elementos no utilizados (disponible en .NET 5 y versiones posteriores) |
| :::no-loc text="Monitor Lock Contention Count"::: (`monitor-lock-contention-count`) | Número de veces que ha habido contención al intentar tomar el bloqueo del monitor, según <xref:System.Threading.Monitor.LockContentionCount?displayProperty=nameWithType> |
| :::no-loc text="Number of Active Timers"::: (`active-timer-count`) | Número de instancias de <xref:System.Threading.Timer> que están activas actualmente, según <xref:System.Threading.Timer.ActiveCount?displayProperty=nameWithType> |
| :::no-loc text="Number of Assemblies Loaded"::: (`assembly-count`) | Número de instancias de <xref:System.Reflection.Assembly> cargadas en un proceso en un momento dado |
| :::no-loc text="ThreadPool Completed Work Item Count"::: (`threadpool-completed-items-count`) | Número de elementos de trabajo que se han procesado hasta ahora en <xref:System.Threading.ThreadPool> |
| :::no-loc text="ThreadPool Queue Length"::: (`threadpool-queue-length`) | Número de elementos de trabajo que se encuentran actualmente en cola para procesarse en <xref:System.Threading.ThreadPool> |
| :::no-loc text="ThreadPool Thread Count"::: (`threadpool-thread-count`) | Número de subprocesos del grupo de subprocesos que existen actualmente en <xref:System.Threading.ThreadPool>, según <xref:System.Threading.ThreadPool.ThreadCount?displayProperty=nameWithType> |
| :::no-loc text="Working Set"::: (`working-set`) | Cantidad de memoria física asignada al contexto del proceso en un momento dado según <xref:System.Environment.WorkingSet?displayProperty=nameWithType> |
| :::no-loc text="IL Bytes Jitted"::: (`il-bytes-jitted`) | Tamaño total (en bytes) de IL que tienen compilación JIT (disponible en .NET 5 y versiones posteriores) |
| :::no-loc text="Method Jitted Count"::: (`method-jitted-count`) | Número de métodos que tienen compilación JIT (disponible en .NET 5 y versiones posteriores) |

### <a name="microsoftaspnetcorehosting-counters"></a>Contadores "Microsoft.AspNetCore.Hosting"

Los siguientes contadores se publican como parte de [ASP.NET Core](/aspnet/core) y se mantienen en [`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Hosting/Hosting/src/Internal/HostingEventSource.cs).

| Contador | Descripción |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | Número total de solicitudes que se han iniciado, pero que aún no se han detenido |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | Número total de solicitudes erróneas que se han producido durante la vida de la aplicación |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | Número de solicitudes que se han producido por segundo |
| :::no-loc text="Total Requests"::: (`total-requests`) | Número total de solicitudes que se han producido durante la vida de la aplicación |

### <a name="microsoftaspnetcorehttpconnections-counters"></a>Contadores "Microsoft.AspNetCore.Http.Connections"

Los siguientes contadores se publican como parte de [ASP.NET Core SignalR](/aspnet/core/signalr/introduction) y se mantienen en [`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs).

| Contador | Descripción |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | Duración media de una conexión en milisegundos |
| :::no-loc text="Current Connections"::: (`current-connections`) | Número de conexiones activas que se han iniciado, pero que aún no se han detenido |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | Número total de conexiones que se han iniciado |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | Número total de conexiones que se han detenido |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | Número total de conexiones cuyo tiempo de espera se ha agotado |

### <a name="microsoft-aspnetcore-server-kestrel-counters"></a>Contadores "Microsoft-AspNetCore-Server-Kestrel"

Los siguientes contadores se publican como parte del [servidor web Kestrel de ASP.NET Core](/aspnet/core/fundamentals/servers/kestrel) y se mantienen en [`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs).

| Contador | Descripción |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | Longitud actual de la cola de conexión |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | Número de conexiones por segundo al servidor web |
| :::no-loc text="Current Connections"::: (`current-connections`) | Número actual de conexiones activas al servidor web |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | Número actual de protocolos de enlace TLS |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | Número actual de solicitudes actualizadas (WebSockets) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | Número total de protocolos de enlace TLS erróneos |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | Longitud actual de la cola de solicitudes |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | Número de protocolos de enlace TLS por segundo |
| :::no-loc text="Total Connections"::: (`total-connections`) | Número total de conexiones al servidor web |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | Número total de protocolos de enlace TLS con el servidor web |
