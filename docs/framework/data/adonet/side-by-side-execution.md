---
title: Ejecución en paralelo en ADO.NET
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: 7435f64afa9ce45a29f4d0a537219f31968eb3f5
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042158"
---
# <a name="side-by-side-execution-in-adonet"></a>Ejecución en paralelo en ADO.NET
La ejecución en paralelo en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] es la posibilidad de ejecutar una aplicación en un equipo que tiene instaladas varias versiones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], utilizando exclusivamente la versión para la que se ha compilado la aplicación. Para obtener información detallada sobre la configuración de ejecución en paralelo, vea [ejecución Side-by-Side](../../../../docs/framework/deployment/side-by-side-execution.md).  
  
 Una aplicación compilada mediante una versión de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se puede ejecutar en otra versión distinta de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. No obstante, se recomienda compilar una versión de la aplicación por cada versión instalada de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y ejecutarlas por separado. En cualquier caso, debe tener en cuenta los cambios entre las diferentes versiones de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] que pueden afectar a la compatibilidad con versiones posteriores o anteriores de la aplicación.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Compatibilidad con versiones anteriores y posteriores  
 La compatibilidad con versiones posteriores implica que una aplicación se puede compilar con una versión anterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], aunque se podrá ejecutar asimismo correctamente en una versión posterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. El código [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] escrito para [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.1 es compatible con versiones posteriores.  
  
 La compatibilidad con versiones anteriores significa que una aplicación compilada para una versión posterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se ejecuta también en versiones anteriores de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], sin que su funcionalidad se vea afectada. Por supuesto, no será así en el caso de las características incluidas en una versión nueva de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Proveedor de datos .NET Framework para ODBC  
 A partir de la versión 1.1, el proveedor de datos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para ODBC (<xref:System.Data.Odbc>) se incluye como parte de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. El proveedor de datos ODBC está disponible para [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] descargar los programadores de la versión 1.0 como un sitio Web desde el [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173). El espacio de nombres para los datos descargados [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proveedor de datos de ODBC es **Microsoft.Data.Odbc**.  
  
 Si tiene una aplicación desarrollada para la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] version 1.0 que usa el proveedor de datos ODBC para conectarse al origen de datos y desea ejecutar dicha aplicación en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.1 o una versión posterior, debe actualizar el espacio de nombres para ODBC proveedor de datos que **System.Data.Odbc**. A continuación, debe compilarla de nuevo para la nueva versión de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Si ha programado una aplicación para la versión 2.0 o posterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que usa el proveedor de datos de ODBC para conectarse al origen de datos y desea ejecutar dicha aplicación en la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], debe descargar el proveedor de datos de ODBC e instalarlo en el sistema de la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. A continuación, debe cambiar el espacio de nombres para el proveedor de datos ODBC a **Microsoft.Data.Odbc**y vuelva a compilar la aplicación para la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.0.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Proveedor de datos .NET Framework para Oracle  
 A partir de la versión 1.1, el proveedor de datos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para Oracle (<xref:System.Data.OracleClient>) se incluye como parte de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. El proveedor de datos está disponible para [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] descargar los programadores de la versión 1.0 como un sitio Web desde el [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173).  
  
 Si tiene una aplicación desarrollada para la [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 2.0 o posterior que usa el proveedor de datos para conectarse al origen de datos y desea ejecutar dicha aplicación en el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.0, debe descargar el proveedor de datos e instalarlo en el < C4 > [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]  sistema versión 1.0.  
  
## <a name="code-access-security"></a>Seguridad de acceso del código  
 En la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], se requiere que los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>) se ejecuten con un permiso FullTrust. Cualquier intento de utilizar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proveedores de datos desde el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.0 de una zona con menos de causas de permiso de plena confianza un <xref:System.Security.SecurityException>.  
  
 Sin embargo, desde la versión 2.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se pueden usar todos los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] en zonas de confianza parcial. Además, se ha agregado una nueva característica de seguridad a los proveedores de datos de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1. Esta característica le permite restringir las cadenas de conexión que se pueden utilizar en una zona de seguridad determinada. Es posible también deshabilitar el uso de contraseñas en blanco para una zona de seguridad determinada. Para obtener más información, consulta [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
 Debido a que cada instalación de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] tiene un archivo Security.config independiente, no existen problemas de compatibilidad con la configuración de la seguridad. Sin embargo, si la aplicación depende de las capacidades de seguridad adicionales de [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] incluidas en la versión 1.1 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y posteriores, no podrá distribuir la aplicación a un sistema de la versión 1.0.  
  
## <a name="sqlcommand-execution"></a>Ejecución de SqlCommand  
 A partir de la versión 1.1 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], se ha cambiado la forma en que <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ejecuta los comandos en el origen de datos.  
  
 En el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.0, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ejecuta todos los comandos en el contexto de la **sp_executesql** procedimiento almacenado. Como resultado, los comandos que influyen en el estado de la conexión (Activar NOCOUNT, por ejemplo) sólo se aplican a la ejecución del comando actual. Mientras la conexión permanece abierta, los comandos que se ejecutan posteriormente no modifican el estado de la conexión.  
  
 En el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versión 1.1 y versiones posterior, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> sólo ejecuta un comando en el contexto de la **sp_executesql** procedimiento almacenado si el comando contiene parámetros, que proporciona una mejora del rendimiento. Como consecuencia, si un comando que influye en el estado de la conexión se incluye en un comando sin parámetros, modifica el estado de la conexión de todos los comandos posteriores que se ejecuten mientras la conexión esté abierta.  
  
 Tomemos como ejemplo el siguiente lote de comandos, que se ejecuta en una llamada a <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 En la versión 1.1 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y posteriores, NOCOUNT permanecerá en ON para los comandos que se ejecuten posteriormente, mientras la conexión esté abierta. En el caso de la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], NOCOUNT solo permanece en ON para la ejecución actual de comandos.  
  
 Este cambio puede afectar a la compatibilidad con versiones posteriores y anteriores de la aplicación si depende del comportamiento de <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> para cualquiera de las versiones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Para las aplicaciones que se ejecutan en versiones anteriores y posteriores de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], puede escribir el código para asegurarse de que el comportamiento sea el mismo independientemente de la versión que se esté ejecutando. Si desea asegurarse de que un comando modifica el estado de la conexión para todos los comandos que se ejecuten posteriormente, se recomienda ejecutar el comando usando <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>. Si desea asegurarse de que un comando no modifica el estado de la conexión para todos los comandos que se ejecuten posteriormente, se recomienda incluir los comandos para restablecer el estado de la conexión en el comando. Por ejemplo:  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
