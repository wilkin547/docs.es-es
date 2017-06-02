---
title: "Ejecuci&#243;n en paralelo en ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Ejecuci&#243;n en paralelo en ADO.NET
La ejecución en paralelo en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] es la posibilidad de ejecutar una aplicación en un equipo que tiene instaladas varias versiones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], utilizando exclusivamente la versión para la que se ha compilado la aplicación.  Para obtener más información sobre la configuración de la ejecución en paralelo, vea [Ejecución simultánea](../../../../docs/framework/deployment/side-by-side-execution.md).  
  
 Una aplicación compilada mediante una versión de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se puede ejecutar en otra versión distinta de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  No obstante, se recomienda compilar una versión de la aplicación por cada versión instalada de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y ejecutarlas por separado.  En cualquier caso, debe tener en cuenta los cambios entre las diferentes versiones de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] que pueden afectar a la compatibilidad con versiones posteriores o anteriores de la aplicación.  
  
## Compatibilidad con versiones anteriores y posteriores  
 La compatibilidad con versiones posteriores implica que una aplicación se puede compilar con una versión anterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], aunque se podrá ejecutar asimismo correctamente en una versión posterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  El código [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] escrito para [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.1 es compatible con versiones posteriores.  
  
 La compatibilidad con versiones anteriores significa que una aplicación compilada para una versión posterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se ejecuta también en versiones anteriores de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], sin que su funcionalidad se vea afectada.  Por supuesto, no será así en el caso de las características incluidas en una versión nueva de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## Proveedor de datos .NET Framework para ODBC  
 A partir de la versión 1.1, el proveedor de datos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para ODBC \(<xref:System.Data.Odbc>\) se incluye como parte de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  El proveedor de datos de ODBC está disponible para los programadores de la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] mediante descarga en el sitio web del [Centro para programadores de acceso a datos y almacenamiento](http://go.microsoft.com/fwlink/?linkid=4173).  El espacio de nombres del proveedor de datos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para ODBC descargado es **Microsoft.Data.Odbc**.  
  
 Si ha programado una aplicación para la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que usa el proveedor de datos de ODBC para conectarse al origen de datos y desea ejecutar dicha aplicación en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.1 o posteriores, debe actualizar el espacio de nombres del proveedor de datos de ODBC a **System.Data.Odbc**.  A continuación, debe compilarla de nuevo para la nueva versión de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Si ha programado una aplicación para la versión 2.0 o posterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que usa el proveedor de datos de ODBC para conectarse al origen de datos y desea ejecutar dicha aplicación en la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], debe descargar el proveedor de datos de ODBC e instalarlo en el sistema de la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  A continuación debe cambiar el espacio de nombres del proveedor de datos de ODBC a **Microsoft.Data.Odbc** y recompilar la aplicación para la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## Proveedor de datos .NET Framework para Oracle  
 A partir de la versión 1.1, el proveedor de datos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para Oracle \(<xref:System.Data.OracleClient>\) se incluye como parte de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  El proveedor de datos está disponible para los programadores de la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] mediante descarga en el sitio web del [Centro para programadores de acceso a datos y almacenamiento](http://go.microsoft.com/fwlink/?linkid=4173).  
  
 Si ha programado una aplicación para la versión 2.0 o posterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que usa el proveedor de datos para conectarse al origen de datos y desea ejecutar esta aplicación en la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], debe descargar el proveedor de datos e instalarlo en el sistema de la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## Seguridad de acceso del código  
 En la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], se requiere que los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] \(<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>\) se ejecuten con un permiso FullTrust.  Si se intentan utilizar los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] con la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] en una zona con un permiso inferior a FullTrust, se produce una excepción <xref:System.Security.SecurityException>.  
  
 Sin embargo, desde la versión 2.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se pueden usar todos los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] en zonas de confianza parcial.  Además, se ha agregado una nueva característica de seguridad a los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1.  Esta característica le permite restringir las cadenas de conexión que se pueden utilizar en una zona de seguridad determinada.  Es posible también deshabilitar el uso de contraseñas en blanco para una zona de seguridad determinada.  Para obtener más información, consulta [Seguridad de acceso del código y ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
 Debido a que cada instalación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] tiene un archivo Security.config independiente, no existen problemas de compatibilidad con la configuración de la seguridad.  Sin embargo, si la aplicación depende de las capacidades de seguridad adicionales de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] incluidas en la versión 1.1 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y posteriores, no podrá distribuir la aplicación a un sistema de la versión 1.0.  
  
## Ejecución de SqlCommand  
 A partir de la versión 1.1 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], se ha cambiado la forma en que <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ejecuta los comandos en el origen de datos.  
  
 En la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ejecuta todos los comandos en el contexto del procedimiento almacenado **sp\_executesql**.  Como resultado, los comandos que influyen en el estado de la conexión \(Activar NOCOUNT, por ejemplo\) sólo se aplican a la ejecución del comando actual.  Mientras la conexión permanece abierta, los comandos que se ejecutan posteriormente no modifican el estado de la conexión.  
  
 En la versión 1.1 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y posteriores, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> solo ejecuta un comando en el contexto del procedimiento almacenado **sp\_executesql** si dicho comando contiene parámetros, ya que de esta forma mejora el rendimiento.  Como consecuencia, si un comando que influye en el estado de la conexión se incluye en un comando sin parámetros, modifica el estado de la conexión de todos los comandos posteriores que se ejecuten mientras la conexión esté abierta.  
  
 Tomemos como ejemplo el siguiente lote de comandos, que se ejecuta en una llamada a <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 En la versión 1.1 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y posteriores, NOCOUNT permanecerá en ON para los comandos que se ejecuten posteriormente, mientras la conexión esté abierta.  En el caso de la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], NOCOUNT solo permanece en ON para la ejecución actual de comandos.  
  
 Este cambio puede afectar a la compatibilidad con versiones posteriores y anteriores de la aplicación si depende del comportamiento de <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> para cualquiera de las versiones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Para las aplicaciones que se ejecutan en versiones anteriores y posteriores de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], puede escribir el código para asegurarse de que el comportamiento sea el mismo independientemente de la versión que se esté ejecutando.  Si desea asegurarse de que un comando modifica el estado de la conexión para todos los comandos que se ejecuten posteriormente, se recomienda ejecutar el comando usando <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>.  Si desea asegurarse de que un comando no modifica el estado de la conexión para todos los comandos que se ejecuten posteriormente, se recomienda incluir los comandos para restablecer el estado de la conexión en el comando.  Por ejemplo:  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## Vea también  
 [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [Recuperación y modificación de datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)