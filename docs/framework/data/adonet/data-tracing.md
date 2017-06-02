---
title: "Traza de datos en ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6a752a5-d2a9-4335-a382-b58690ccb79f
caps.latest.revision: 9
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 9
---
# Traza de datos en ADO.NET
ADO.NET 2.0 ofrece nueva funcionalidad integrada de seguimiento de datos compatible con los proveedores de datos de .NET para [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], Oracle, OLE DB y ODBC, así como <xref:System.Data.DataSet> de ADO.NET y los protocolos de red de [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)].  
  
 Las llamadas API de acceso a datos de traza ayudan a diagnosticar los siguientes problemas:  
  
-   Falta de coincidencia de esquemas entre el programa cliente y la base de datos.  
  
-   Inoperabilidad de la base de datos o problemas con las bibliotecas de red.  
  
-   SQL incorrecto, tanto si está incluido en el código como si lo ha generado una aplicación.  
  
-   Lógica de programación incorrecta.  
  
-   Problemas derivados de la interacción entre varios componentes de ADO.NET o entre ADO.NET y sus propios componentes.  
  
 Para garantizar la compatibilidad entre diferentes tecnologías de traza, éste es ampliable, de manera que un programador puede realizar un seguimiento de un problema en cualquier nivel de la pila de la aplicación.  A pesar de que el seguimiento no es una característica exclusiva de ADO.NET, los proveedores de Microsoft aprovechan la ventaja de el seguimiento generalizada y las API de instrumental.  
  
 Para obtener más información acerca de la instalación y configuración del seguimiento administrado en ADO.NET, consulte [Seguimiento del acceso a datos](http://msdn.microsoft.com/library/hh880086.aspx).  
  
## Tener acceso a información de diagnóstico en el registro de eventos extendidos  
 En el proveedor de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], el seguimiento del acceso a datos \([Seguimiento de acceso a datos](http://msdn.microsoft.com/library/hh880086.aspx)\)se actualizó para facilitar la correlación de eventos de cliente con la información de diagnóstico, como errores de conexión, de la información del búfer en anillo de conectividad y de rendimiento de la aplicación del servidor en el registro de eventos extendidos.  Para obtener información acerca de cómo leer el registro de eventos extendidos, consulte [Ver datos de sesiones de eventos](http://msdn.microsoft.com/library/hh710068\(SQL.110\).aspx).  
  
 Para las operaciones de conexión, ADO.NET enviará un identificador de conexión de cliente.  Si se produce un error en la conexión, puede tener acceso al búfer de anillo de conectividad \([Solucionar problemas de conectividad en SQL Server 2008 con el búfer en anillo de conectividad](http://go.microsoft.com/fwlink/?LinkId=207752)\) y buscar el campo `ClientConnectionID` y recopilar información de diagnóstico sobre el error de conexión.  Los identificadores de conexión de cliente inician sesión el búfer de anillo solo si se produce un error.  \(Si se produce un error en una conexión antes de enviar el paquete previo al inicio de sesión, no se generará un identificador de conexión de cliente.\) El identificador de la conexión de cliente es un GUID de 16 bytes.  También puede buscar el identificador de la conexión de cliente en la salida de destino de los eventos extendidos si la acción `client_connection_id` se agregó a los eventos en una sesión de eventos extendidos.  Puede habilitar el seguimiento de acceso a datos y volver a ejecutar el comando de conexión y observar el campo `ClientConnectionID` en el seguimiento de acceso a datos, si necesita ayuda adicional de diagnóstico del controlador del cliente.  
  
 Puede obtener el identificador de la conexión de cliente mediante programación con la propiedad `SqlConnection.ClientConnectionID`.  
  
 `ClientConnectionID` está disponible para un objeto <xref:System.Data.SqlClient.SqlConnection> que establezca correctamente una conexión.  Si se produce un error en un intento de conexión, `ClientConnectionID` puede estar disponible a través de `SqlException.ToString`.  
  
 ADO.NET también envía un identificador de actividad específico del subproceso  El identificador de actividad se captura en las sesiones de eventos extendidos si se inician las sesiones con la opción TRACK\_CAUSAILITY habilitada.  Para los problemas de rendimiento con una conexión activa, puede obtener el identificador de actividad del seguimiento de acceso a datos del cliente \(campo `ActivityID`\) y después buscar el identificador de actividad en la salida de los eventos extendidos.  El identificador de actividad de los eventos extendidos es un GUID de 16 bytes \(no es igual que el GUID del identificador de la conexión de cliente\) anexado con un número de secuencia de cuatro bytes.  El número de secuencia representa el orden de una solicitud dentro de un subproceso e indica el orden relativo del lote y las instrucciones RPC para el subproceso.  `ActivityID` se envía actualmente opcionalmente para instrucciones por lotes de SQL y solicitudes RPC cuando el seguimiento de acceso a datos está habilitado y el decimoctavo bit de la palabra de configuración de seguimiento de acceso a datos está activado.  
  
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
  
## Vea también  
 [Traza de la red en .NET Framework](../../../../docs/framework/network-programming/network-tracing.md)   
 [Tracing and Instrumenting Applications](../../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)