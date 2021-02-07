---
description: 'Más información acerca de: seguimiento de datos en ADO.NET'
title: Seguimiento de datos
ms.date: 03/30/2017
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
ms.openlocfilehash: 7fc4407e76ea34bacc97177d6342730a8263b5c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663747"
---
# <a name="data-tracing-in-adonet"></a>Traza de datos en ADO.NET

ADO.NET incluye la funcionalidad de seguimiento de datos integrada que admiten los proveedores de datos de .NET para SQL Server, Oracle, OLE DB y ODBC, así como los <xref:System.Data.DataSet> protocolos de red de SQL Server y ADO.net.

Las llamadas API de acceso a datos de traza ayudan a diagnosticar los siguientes problemas:

- Falta de coincidencia de esquemas entre el programa cliente y la base de datos.

- Inoperabilidad de la base de datos o problemas con las bibliotecas de red.

- SQL incorrecto, tanto si está incluido en el código como si lo ha generado una aplicación.

- Lógica de programación incorrecta.

- Problemas derivados de la interacción entre varios componentes de ADO.NET o entre ADO.NET y sus propios componentes.

Para garantizar la compatibilidad entre diferentes tecnologías de traza, éste es ampliable, de manera que un programador puede realizar un seguimiento de un problema en cualquier nivel de la pila de la aplicación. A pesar de que el seguimiento no es una característica exclusiva de ADO.NET, los proveedores de Microsoft aprovechan la ventaja de el seguimiento generalizada y las API de instrumental.

Para obtener más información sobre cómo establecer y configurar el seguimiento administrado en ADO.NET, vea [seguimiento de acceso a datos](/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10)).

## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Obtener acceso a información de diagnóstico en el registro de eventos extendidos

En el proveedor de datos de .NET Framework para SQL Server, el seguimiento de acceso a datos ([seguimiento de acceso a datos](/previous-versions/sql/sql-server-2012/hh880086(v=msdn.10))) se ha actualizado para facilitar la correlación de eventos de cliente con información de diagnóstico, como errores de conexión, desde el búfer de anillo de Conectividad del servidor y la información de rendimiento de la aplicación en el registro de eventos extendidos. Para obtener información sobre la lectura del registro de eventos extendidos, vea [Ver datos de sesión de evento](/previous-versions/sql/sql-server-2012/hh710068(v=sql.110)).

Para las operaciones de conexión, ADO.NET enviará un identificador de conexión de cliente. Si se produce un error en la conexión, puede tener acceso al búfer de anillo de conectividad ([Solución de problemas de conectividad en SQL Server 2008 con el búfer de anillo de conectividad](/archive/blogs/sql_protocols/connectivity-troubleshooting-in-sql-server-2008-with-the-connectivity-ring-buffer)) y buscar el campo `ClientConnectionID` para obtener información de diagnóstico acerca del error de conexión. Los identificadores de conexión del cliente se registran en el búfer de anillo únicamente si se produce un error. (Si se produce un error en una conexión antes de enviar el paquete de inicio de sesión previo, no se generará un identificador de conexión del cliente). El identificador de conexión del cliente es un GUID de 16 bytes. También puede buscar el identificador de la conexión de cliente en la salida de destino de los eventos extendidos si la acción `client_connection_id` se agregó a los eventos en una sesión de eventos extendidos. Puede habilitar el seguimiento de acceso a datos y volver a ejecutar el comando de conexión y observar el campo `ClientConnectionID` en el seguimiento de acceso a datos, si necesita ayuda adicional de diagnóstico del controlador del cliente.

Puede obtener el identificador de la conexión de cliente mediante programación con la propiedad `SqlConnection.ClientConnectionID`.

`ClientConnectionID` está disponible para un objeto <xref:System.Data.SqlClient.SqlConnection> que establezca correctamente una conexión. Si se produce un error en un intento de conexión, `ClientConnectionID` puede estar disponible a través de `SqlException.ToString`.

ADO.NET también envía un identificador de actividad específico del subproceso El identificador de actividad se captura en las sesiones de eventos extendidos si las sesiones se inician con la opción TRACK_CAUSAILITY habilitada. Con respecto a los problemas de rendimiento con una conexión activa, puede obtener el identificador de actividad a partir del seguimiento de acceso a datos del cliente (campo `ActivityID`) y, posteriormente, buscar el identificador de actividad en la salida de eventos extendidos. El identificador de actividad de los eventos extendidos es un GUID de 16 bytes (no es igual que el GUID del identificador de la conexión de cliente) anexado con un número de secuencia de cuatro bytes. El número de secuencia representa el orden de una solicitud en un subproceso e indica el orden relativo del lote, así como las instrucciones RPC para el subproceso. `ActivityID` se envía actualmente opcionalmente para instrucciones por lotes de SQL y solicitudes RPC cuando el seguimiento de acceso a datos está habilitado y el decimoctavo bit de la palabra de configuración de seguimiento de acceso a datos está activado.

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
- [Información general de ADO.NET](ado-net-overview.md)
