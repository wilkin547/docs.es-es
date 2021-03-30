---
title: EventCounters conocidos de .NET
description: Revise los EventCounters publicados por las bibliotecas y el entorno de ejecución de .NET.
ms.topic: reference
ms.date: 12/17/2020
ms.openlocfilehash: aad4fa8b33ebf0dcb7803c77b11fb99a6b6d7b83
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872839"
---
# <a name="well-known-eventcounters-in-net"></a>EventCounters conocidos de .NET

Las bibliotecas y el entorno de ejecución de .NET implementan y publican varios [`EventCounter`](./event-counters.md) que se pueden usar para identificar y diagnosticar diversos problemas de rendimiento. Este documento hace referencia a los proveedores que se pueden usar para supervisar estos `EventCounters` y sus descripciones.

## <a name="systemruntime-counters"></a>Contadores "System.Runtime"

Los siguientes contadores se publican como parte del entorno de ejecución de .NET (CoreCLR) y se mantienen en [`RuntimeEventSource.cs`](https://github.com/dotnet/runtime/blob/main/src/libraries/System.Private.CoreLib/src/System/Diagnostics/Tracing/RuntimeEventSource.cs).

| Contador | Descripción |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | Porcentaje de tiempo de GC desde la última GC |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | Número de bytes asignados por intervalo de actualización |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | Porcentaje de uso de CPU del proceso en relación con todos los recursos de CPU del sistema |
| :::no-loc text="Exception Count"::: (`exception-count`) | Número de excepciones que se han producido |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | Número de bytes que se considera que están asignados según <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType> |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | Número de veces que se ha producido una GC para Gen 0 por intervalo de actualización |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | Número de bytes para la GC de Gen 0 |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | Número de veces que se ha producido una GC para Gen 1 por intervalo de actualización |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | Número de bytes para la GC de Gen 1 |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | Número de veces que se ha producido una GC para Gen 2 por intervalo de actualización |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | Número de bytes para la GC de Gen 2 |
| :::no-loc text="LOH Size"::: (`loh-size`) | Número de bytes para el montón de objetos grandes |
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

## <a name="microsoftaspnetcorehosting-counters"></a>Contadores "Microsoft.AspNetCore.Hosting"

Los siguientes contadores se publican como parte de [ASP.NET Core](/aspnet/core) y se mantienen en [`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/main/src/Hosting/Hosting/src/Internal/HostingEventSource.cs).

| Contador | Descripción |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | Número total de solicitudes que se han iniciado, pero que aún no se han detenido |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | Número total de solicitudes erróneas que se han producido durante la vida de la aplicación |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | Número de solicitudes que se han producido por intervalo de actualización |
| :::no-loc text="Total Requests"::: (`total-requests`) | Número total de solicitudes que se han producido durante la vida de la aplicación |

## <a name="microsoftaspnetcorehttpconnections-counters"></a>Contadores "Microsoft.AspNetCore.Http.Connections"

Los siguientes contadores se publican como parte de [ASP.NET Core SignalR](/aspnet/core/signalr/introduction) y se mantienen en [`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/main/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs).

| Contador | Descripción |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | Duración media de una conexión en milisegundos |
| :::no-loc text="Current Connections"::: (`current-connections`) | Número de conexiones activas que se han iniciado, pero que aún no se han detenido |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | Número total de conexiones que se han iniciado |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | Número total de conexiones que se han detenido |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | Número total de conexiones cuyo tiempo de espera se ha agotado |

## <a name="microsoft-aspnetcore-server-kestrel-counters"></a>Contadores "Microsoft-AspNetCore-Server-Kestrel"

Los siguientes contadores se publican como parte del [servidor web Kestrel de ASP.NET Core](/aspnet/core/fundamentals/servers/kestrel) y se mantienen en [`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/main/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs).

| Contador | Descripción |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | Longitud actual de la cola de conexión |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | Número de conexiones al servidor web por intervalo de actualización |
| :::no-loc text="Current Connections"::: (`current-connections`) | Número actual de conexiones activas al servidor web |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | Número actual de protocolos de enlace TLS |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | Número actual de solicitudes actualizadas (WebSockets) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | Número total de protocolos de enlace TLS erróneos |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | Longitud actual de la cola de solicitudes |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | Número de protocolos de enlace TLS por intervalo de actualización |
| :::no-loc text="Total Connections"::: (`total-connections`) | Número total de conexiones al servidor web |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | Número total de protocolos de enlace TLS con el servidor web |

## <a name="systemnethttp-counters"></a>Contadores "System.Net.Http"

Los siguientes contadores se publican en la pila HTTP.  Estos contadores solo están disponibles en .NET 5 y versiones posteriores.

| Contador | Descripción |
|--|--|
| :::no-loc text="Requests Started"::: (`requests-started`) | Número de solicitudes que se han iniciado desde que se inició el proceso |
| :::no-loc text="Requests Started Rate"::: (`requests-started-rate`) | Número de solicitudes que se han iniciado por intervalo de actualización |
| :::no-loc text="Requests Failed"::: (`requests-failed`) | Número de solicitudes con errores desde que se inició el proceso |
| :::no-loc text="Requests Failed Rate"::: (`requests-failed-rate`) | Número de solicitudes con errores por intervalo de actualización |
| :::no-loc text="Current Requests"::: (`current-requests`) | Número actual de solicitudes HTTP activas que se han iniciado, pero que aún no se han completado o tienen errores |
| :::no-loc text="Current HTTP 1.1 Connections"::: (`http11-connections-current-total`) | Número actual de conexiones HTTP 1.1 que se han iniciado, pero que aún no se han completado o tienen errores |
| :::no-loc text="Current HTTP 2.0 Connections"::: (`http20-connections-current-total`) | Número actual de conexiones HTTP 2.0 que se han iniciado, pero que aún no se han completado o tienen errores |
| :::no-loc text="HTTP 1.1 Requests Queue Duration"::: (`http11-requests-queue-duration`) | Tiempo medio que pasan las solicitudes HTTP 1.1 en la cola de solicitudes |
| :::no-loc text="HTTP 2.0 Requests Queue Duration"::: (`http20-requests-queue-duration`) | Tiempo medio que pasan las solicitudes HTTP 2.0 en la cola de solicitudes |

## <a name="systemnetnameresolution-counters"></a>Contadores "System.Net.NameResolution"

Los siguientes contadores realizan un seguimiento de las métricas relacionadas con las búsquedas de DNS. Estos contadores solo están disponibles en .NET 5 y versiones posteriores.

| Contador | Descripción |
|--|--|
| :::no-loc text="DNS Lookups Requested"::: (`dns-lookups-requested`) | Número de búsquedas de DNS que se han solicitado desde que se inició el proceso |
| :::no-loc text="Average DNS Lookup Duration"::: (`dns-lookups-duration`) | Tiempo medio empleado en una búsqueda de DNS |

## <a name="systemnetsecurity-counters"></a>Contadores "System.Net.Security"

Los siguientes contadores realizan un seguimiento de las métricas relacionadas con el protocolo de Seguridad de la capa de transporte.  Estos contadores solo están disponibles en .NET 5 y versiones posteriores.

| Contador | Descripción |
|--|--|
| :::no-loc text="TLS handshakes completed"::: (`tls-handshake-rate`) | Número de protocolos de enlace TLS completados por intervalo de actualización |
| :::no-loc text="Total TLS handshakes completed"::: (`total-tls-handshakes`) | Número total de protocolos de enlace TLS completados desde que se inició el proceso |
| :::no-loc text="Current TLS handshakes"::: (`current-tls-handshakes`) | Número actual de protocolos de enlace TLS que se han iniciado, pero que aún no se han completado |
| :::no-loc text="Total TLS handshakes failed"::: (`failed-tls-handshakes`) | Número total de protocolos de enlace TLS con errores desde que se inició el proceso |
| :::no-loc text="All TLS Sessions Active"::: (`all-tls-sessions-open`) | Número de sesiones activas de TLS de cualquier versión |
| :::no-loc text="TLS 1.0 Sessions Active"::: (`tls10-sessions-open`) | Número de sesiones activas de TLS 1.0 |
| :::no-loc text="TLS 1.1 Sessions Active"::: (`tls11-sessions-open`) | Número de sesiones activas de TLS 1.1 |
| :::no-loc text="TLS 1.2 Sessions Active"::: (`tls12-sessions-open`) | Número de sesiones activas de TLS 1.2 |
| :::no-loc text="TLS 1.3 Sessions Active"::: (`tls13-sessions-open`) | Número de sesiones activas de TLS 1.3 |
| :::no-loc text="TLS Handshake Duration"::: (`all-tls-handshake-duration`) | Duración media de todos los protocolos de enlace TLS |
| :::no-loc text="TLS 1.0 Handshake Duration"::: (`tls10-handshake-duration`) | Duración media de los protocolos de enlace TLS 1.0 |
| :::no-loc text="TLS 1.1 Handshake Duration"::: (`tls11-handshake-duration`) | Duración media de los protocolos de enlace TLS 1.1 |
| :::no-loc text="TLS 1.2 Handshake Duration"::: (`tls12-handshake-duration`) | Duración media de los protocolos de enlace TLS 1.2 |
| :::no-loc text="TLS 1.3 Handshake Duration"::: (`tls13-handshake-duration`) | Duración media de los protocolos de enlace TLS 1.3 |

## <a name="systemnetsockets-counters-available-on-net-5-and-later-versions"></a>Contadores "System.Net.Sockets" (disponibles en .NET 5 y versiones posteriores)

Los siguientes contadores realizan un seguimiento de las métricas relacionadas con <xref:System.Net.Sockets.Socket>.

| Contador | Descripción |
|--|--|
| :::no-loc text="Outgoing Connections Established"::: (`outgoing-connections-established`) | Número total de conexiones salientes establecidas desde que se inició el proceso |
| :::no-loc text="Incoming Connections Established"::: (`incoming-connections-established`) | Número total de conexiones entrantes establecidas desde que se inició el proceso |
| :::no-loc text="Bytes Received"::: (`bytes-received`) | Número total de bytes recibidos desde que se inició el proceso |
| :::no-loc text="Bytes Sent"::: (`bytes-sent`) | Número total de bytes enviados desde que se inició el proceso |
| :::no-loc text="Datagrams Received"::: (`datagrams-received`) | Número total de datagramas recibidos desde que se inició el proceso |
| :::no-loc text="Datagrams Sent"::: (`datagrams-sent`) | Número total de datagramas enviados desde que se inició el proceso |
