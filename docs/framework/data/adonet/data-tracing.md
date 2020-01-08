---
title: Traza de datos en ADO.NET
ms.date: 03/30/2017
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
ms.openlocfilehash: be82500920ce9d5f8bc7ee979cf8ec5006f4f12b
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347803"
---
# <a name="data-tracing-in-adonet"></a>Traza de datos en ADO.NET

ADO.NET incluye la funcionalidad de seguimiento de datos integrada que admiten los proveedores de datos de .NET para SQL Server, Oracle, OLE DB y ODBC, así como los <xref:System.Data.DataSet>de ADO.NET y los protocolos de red de SQL Server.

Las llamadas API de acceso a datos de traza ayudan a diagnosticar los siguientes problemas:

- Falta de coincidencia de esquemas entre el programa cliente y la base de datos.

- Inoperabilidad de la base de datos o problemas con las bibliotecas de red.

- SQL incorrecto, tanto si está incluido en el código como si lo ha generado una aplicación.

- Lógica de programación incorrecta.

- Problemas derivados de la interacción entre varios componentes de ADO.NET o entre ADO.NET y sus propios componentes.

Para garantizar la compatibilidad entre diferentes tecnologías de traza, éste es ampliable, de manera que un programador puede realizar un seguimiento de un problema en cualquier nivel de la pila de la aplicación. A pesar de que el seguimiento no es una característica exclusiva de ADO.NET, los proveedores de Microsoft aprovechan la ventaja de el seguimiento generalizada y las API de instrumental.

Para obtener más información sobre cómo establecer y configurar el seguimiento administrado en ADO.NET, vea [seguimiento de acceso a datos](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10)).

## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Tener acceso a información de diagnóstico en el registro de eventos extendidos

En el proveedor de datos de .NET Framework para SQL Server, el seguimiento de acceso a datos ([seguimiento de acceso a datos](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10))) se ha actualizado para facilitar la correlación de eventos de cliente con información de diagnóstico, como errores de conexión, desde el búfer de anillo de Conectividad del servidor y la información de rendimiento de la aplicación en el registro de eventos extendidos. Para obtener información sobre la lectura del registro de eventos extendidos, vea [Ver datos de sesión de evento](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/hh710068(v=sql.110)).

Para las operaciones de conexión, ADO.NET enviará un identificador de conexión de cliente. Si se produce un error en la conexión, puede tener acceso al búfer de anillo de conectividad ([solución de problemas de conectividad en SQL Server 2008 con el búfer de anillo de conectividad](https://blogs.msdn.microsoft.com/sql_protocols/2008/05/20/connectivity-troubleshooting-in-sql-server-2008-with-the-connectivity-ring-buffer/)) y buscar el campo de `ClientConnectionID` y obtener información de diagnóstico sobre el error de conexión. Los identificadores de conexión de cliente inician sesión el búfer de anillo solo si se produce un error. (Si se produce un error en una conexión antes de enviar el paquete de inicio de sesión previo, no se generará un identificador de conexión de cliente). El identificador de conexión de cliente es un GUID de 16 bytes. También puede buscar el identificador de la conexión de cliente en la salida de destino de los eventos extendidos si la acción `client_connection_id` se agregó a los eventos en una sesión de eventos extendidos. Puede habilitar el seguimiento de acceso a datos y volver a ejecutar el comando de conexión y observar el campo `ClientConnectionID` en el seguimiento de acceso a datos, si necesita ayuda adicional de diagnóstico del controlador del cliente.

Puede obtener el identificador de la conexión de cliente mediante programación con la propiedad `SqlConnection.ClientConnectionID`.

`ClientConnectionID` está disponible para un objeto <xref:System.Data.SqlClient.SqlConnection> que establezca correctamente una conexión. Si se produce un error en un intento de conexión, `ClientConnectionID` puede estar disponible a través de `SqlException.ToString`.

ADO.NET también envía un identificador de actividad específico del subproceso El ID. de actividad se captura en las sesiones de eventos extendidos si las sesiones se inician con la opción de TRACK_CAUSALITY habilitada. Para los problemas de rendimiento con una conexión activa, puede obtener el identificador de actividad del seguimiento de acceso a datos del cliente (campo `ActivityID`) y después buscar el identificador de actividad en la salida de los eventos extendidos. El identificador de actividad en los eventos extendidos es un GUID de 16 bytes (no es el mismo GUID que el identificador de conexión de cliente) anexado con un número de secuencia de cuatro bytes. El número de secuencia representa el orden de una solicitud dentro de un subproceso e indica el orden relativo del lote y las instrucciones RPC para el subproceso. `ActivityID` se envía actualmente opcionalmente para instrucciones por lotes de SQL y solicitudes RPC cuando el seguimiento de acceso a datos está habilitado y el decimoctavo bit de la palabra de configuración de seguimiento de acceso a datos está activado.

A continuación se muestra un ejemplo que utiliza Transact-SQL para iniciar una sesión de Extended Events que se almacenará en un búfer de anillo y registrará el ID. de actividad enviado desde un cliente en operaciones RPC y por lotes.

```sql
create event session MySession on server
add event connectivity_ring_buffer_recorded,
add event sql_statement_starting (action (client_connection_id)),
add event sql_statement_completed (action (client_connection_id)),
add event rpc_starting (action (client_connection_id)),
add event rpc_completed (action (client_connection_id))
add target ring_buffer with (track_causality=on)
```

## <a name="see-also"></a>Vea también

- [Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)](../../network-programming/network-tracing.md)
- [Seguimiento e instrumentación de aplicaciones](../../debug-trace-profile/tracing-and-instrumenting-applications.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
