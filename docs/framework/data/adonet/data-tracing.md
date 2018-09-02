---
title: Traza de datos en ADO.NET
ms.date: 03/30/2017
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
ms.openlocfilehash: 037db6f4e5695e00401c81e1490953efe2fc9b99
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421104"
---
# <a name="data-tracing-in-adonet"></a>Traza de datos en ADO.NET
ADO.NET ofrece funcionalidad de seguimiento de datos integrado que es compatible con los proveedores de datos .NET para SQL Server, Oracle, OLE DB y ODBC, así como ADO.NET <xref:System.Data.DataSet>y los protocolos de red de SQL Server.  
  
 Las llamadas API de acceso a datos de traza ayudan a diagnosticar los siguientes problemas:  
  
-   Falta de coincidencia de esquemas entre el programa cliente y la base de datos.  
  
-   Inoperabilidad de la base de datos o problemas con las bibliotecas de red.  
  
-   SQL incorrecto, tanto si está incluido en el código como si lo ha generado una aplicación.  
  
-   Lógica de programación incorrecta.  
  
-   Problemas derivados de la interacción entre varios componentes de ADO.NET o entre ADO.NET y sus propios componentes.  
  
 Para garantizar la compatibilidad entre diferentes tecnologías de traza, éste es ampliable, de manera que un programador puede realizar un seguimiento de un problema en cualquier nivel de la pila de la aplicación. A pesar de que el seguimiento no es una característica exclusiva de ADO.NET, los proveedores de Microsoft aprovechan la ventaja de el seguimiento generalizada y las API de instrumental.  
  
 Para obtener más información sobre la configuración y la configuración del seguimiento administrado en ADO.NET, vea [Tracing Data Access](https://msdn.microsoft.com/library/hh880086.aspx).  
  
## <a name="accessing-diagnostic-information-in-the-extended-events-log"></a>Tener acceso a información de diagnóstico en el registro de eventos extendidos  
 En el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proveedor de datos para SQL Server, de acceso datos de seguimiento ([seguimiento de acceso a datos](https://msdn.microsoft.com/library/hh880086.aspx)) se ha actualizado para facilitar más fácil correlacionar eventos de cliente con la información de diagnóstico, como errores de conexión desde el información de rendimiento de búfer y la aplicación en el registro de eventos extendidos de anillo de conectividad del servidor. Para obtener información acerca de cómo leer el registro de eventos extendidos, consulte [ver datos de sesión de eventos](https://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx).  
  
 Para las operaciones de conexión, ADO.NET enviará un identificador de conexión de cliente. Si se produce un error en la conexión, puede tener acceso al búfer de anillo de conectividad ([solucionar problemas de conectividad en SQL Server 2008 con el búfer de anillo de conectividad](https://go.microsoft.com/fwlink/?LinkId=207752)) y busque el `ClientConnectionID` campo y obtener información de diagnóstico el Error de conexión. Los identificadores de conexión de cliente inician sesión el búfer de anillo solo si se produce un error. (Si se produce un error en una conexión antes de enviar el paquete previo al inicio de sesión, no se generará un identificador de conexión de cliente.) El identificador de la conexión de cliente es un GUID de 16 bytes. También puede buscar el identificador de la conexión de cliente en la salida de destino de los eventos extendidos si la acción `client_connection_id` se agregó a los eventos en una sesión de eventos extendidos. Puede habilitar el seguimiento de acceso a datos y volver a ejecutar el comando de conexión y observar el campo `ClientConnectionID` en el seguimiento de acceso a datos, si necesita ayuda adicional de diagnóstico del controlador del cliente.  
  
 Puede obtener el identificador de la conexión de cliente mediante programación con la propiedad `SqlConnection.ClientConnectionID`.  
  
 `ClientConnectionID` está disponible para un objeto <xref:System.Data.SqlClient.SqlConnection> que establezca correctamente una conexión. Si se produce un error en un intento de conexión, `ClientConnectionID` puede estar disponible a través de `SqlException.ToString`.  
  
 ADO.NET también envía un identificador de actividad específico del subproceso El identificador de actividad se captura en las sesiones de eventos extendidos si se inician las sesiones con la opción TRACK_CAUSAILITY habilitada. Para los problemas de rendimiento con una conexión activa, puede obtener el identificador de actividad del seguimiento de acceso a datos del cliente (campo `ActivityID`) y después buscar el identificador de actividad en la salida de los eventos extendidos. El identificador de actividad de los eventos extendidos es un GUID de 16 bytes (no es igual que el GUID del identificador de la conexión de cliente) anexado con un número de secuencia de cuatro bytes. El número de secuencia representa el orden de una solicitud dentro de un subproceso e indica el orden relativo del lote y las instrucciones RPC para el subproceso. `ActivityID` se envía actualmente opcionalmente para instrucciones por lotes de SQL y solicitudes RPC cuando el seguimiento de acceso a datos está habilitado y el decimoctavo bit de la palabra de configuración de seguimiento de acceso a datos está activado.  
  
 A continuación se muestra un ejemplo que usa [!INCLUDE[tsql](../../../../includes/tsql-md.md)] para iniciar una sesión de eventos extendidos que se almacenará en un búfer de anillo y registrará el identificador de actividad enviado desde un cliente en RPC y operaciones por lotes.  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
```  
  
## <a name="see-also"></a>Vea también  
 [Network Tracing in the .NET Framework (Seguimiento de red en .NET Framework)](../../../../docs/framework/network-programming/network-tracing.md)  
 [Seguimiento e instrumentación de aplicaciones](../../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
