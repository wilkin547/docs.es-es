---
title: Ejecución en paralelo en ADO.NET
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: d20d8e81d76284509d6fe733e4f283a9ab39cb00
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877094"
---
# <a name="side-by-side-execution-in-adonet"></a>Ejecución en paralelo en ADO.NET
Ejecución en paralelo en .NET Framework es la capacidad de ejecutar una aplicación en un equipo que tiene varias versiones de .NET Framework instalada, utilizando exclusivamente la versión para el que se compiló la aplicación. Para obtener información detallada sobre la configuración de ejecución en paralelo, vea [ejecución Side-by-Side](../../../../docs/framework/deployment/side-by-side-execution.md).  
  
 Puede ejecutar una aplicación compilada con una versión de .NET Framework en una versión diferente de .NET Framework. Sin embargo, recomendamos que compile una versión de la aplicación para cada versión instalada de .NET Framework y ejecutarlas por separado. En cualquier caso, debe ser consciente de los cambios en ADO.NET entre las versiones que pueden afectar a la compatibilidad con versiones posteriores o la compatibilidad con versiones anteriores de la aplicación.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Compatibilidad con versiones anteriores y posteriores  
 Compatibilidad con versiones posteriores significa que una aplicación se puede compilar con una versión anterior de .NET Framework, pero se podrá ejecutar correctamente en una versión posterior de .NET Framework. Código ADO.NET escrito para .NET Framework versión 1.1 es compatible con versiones posteriores.  
  
 Compatibilidad con versiones anteriores significa que una aplicación se compila una versión más reciente de .NET Framework, pero continúa ejecutándose en versiones anteriores de .NET Framework sin ninguna pérdida de funcionalidad. Por supuesto, esto no será el caso de las características incluidas en una nueva versión de .NET Framework.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Proveedor de datos .NET Framework para ODBC  
 Comenzando con la versión 1.1, el proveedor de datos de .NET Framework para ODBC (<xref:System.Data.Odbc>) se incluye como parte de .NET Framework. El proveedor de datos ODBC está disponible para los programadores de la versión 1.0 de .NET Framework como una descarga Web desde el [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173). El espacio de nombres del proveedor de datos de .NET Framework para ODBC descargado es **Microsoft.Data.Odbc**.  
  
 Si tiene una aplicación desarrollada para .NET Framework versión 1.0 que usa el proveedor de datos ODBC para conectarse al origen de datos y desea ejecutar dicha aplicación en la versión de .NET Framework 1.1 o una versión posterior, debe actualizar el espacio de nombres dat ODBC un proveedor de **System.Data.Odbc**. A continuación, debe compilarla de nuevo para la versión más reciente de .NET Framework.  
  
 Si tiene una aplicación desarrollada para .NET Framework versión 2.0 o posterior que usa el proveedor de datos ODBC para conectarse al origen de datos y desea ejecutar dicha aplicación en la versión 1.0 de .NET Framework, debe descargar el proveedor de datos ODBC e instalarlo en el sistema de .NET Framework versión 1.0. A continuación, debe cambiar el espacio de nombres para el proveedor de datos ODBC a **Microsoft.Data.Odbc**y vuelva a compilar la aplicación para la versión 1.0 de .NET Framework.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Proveedor de datos .NET Framework para Oracle  
 Comenzando con la versión 1.1, el proveedor de datos de .NET Framework para Oracle (<xref:System.Data.OracleClient>) se incluye como parte de .NET Framework. El proveedor de datos está disponible para los programadores de la versión 1.0 de .NET Framework como una descarga Web desde el [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173).  
  
 Si tiene una aplicación desarrollada para .NET Framework versión 2.0 o posterior que usa el proveedor de datos para conectarse al origen de datos y desea ejecutar dicha aplicación en la versión 1.0 de .NET Framework, debe descargar el proveedor de datos e instalarlo en el .NET Sistema de T Framework versión 1.0.  
  
## <a name="code-access-security"></a>Seguridad de acceso del código  
 Los proveedores de datos de .NET Framework en la versión 1.0 de .NET Framework (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>) son necesarios para ejecutar con permisos de plena confianza. Cualquier intento de utilizar los proveedores de datos de .NET Framework k desde la versión 1.0 de .NET Framework en una zona con menos de causas de permiso de plena confianza un <xref:System.Security.SecurityException>.  
  
 Sin embargo, a partir de la versión 2.0 de .NET Framework, todos los proveedores de datos de .NET Framework pueden usarse en zonas de confianza parcial. Además, se ha agregado una nueva característica de seguridad a los proveedores de datos de .NET Framework en la versión 1.1 de .NET Framework. Esta característica le permite restringir las cadenas de conexión que se pueden utilizar en una zona de seguridad determinada. Es posible también deshabilitar el uso de contraseñas en blanco para una zona de seguridad determinada. Para obtener más información, consulta [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
 Dado que cada instalación de .NET Framework tiene un archivo Security.config independiente, no hay ningún problema de compatibilidad con la configuración de seguridad. Sin embargo, si la aplicación depende de las capacidades de seguridad adicionales de ADO.NET incluye en la versión de .NET Framework 1.1 y versiones posteriores, no podrá distribuir la aplicación a un sistema de la versión 1.0.  
  
## <a name="sqlcommand-execution"></a>Ejecución de SqlCommand  
 A partir de .NET Framework versión 1.1, la forma en que <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ejecuta comandos en los datos de origen se ha cambiado.  
  
 En .NET Framework versión 1.0, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> ejecuta todos los comandos en el contexto de la **sp_executesql** procedimiento almacenado. Como resultado, los comandos que influyen en el estado de la conexión (Activar NOCOUNT, por ejemplo) sólo se aplican a la ejecución del comando actual. Mientras la conexión permanece abierta, los comandos que se ejecutan posteriormente no modifican el estado de la conexión.  
  
 En .NET Framework versión 1.1 y versiones posterior, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> sólo ejecuta un comando en el contexto de la **sp_executesql** procedimiento almacenado si el comando contiene parámetros, que proporciona una mejora del rendimiento. Como consecuencia, si un comando que influye en el estado de la conexión se incluye en un comando sin parámetros, modifica el estado de la conexión de todos los comandos posteriores que se ejecuten mientras la conexión esté abierta.  
  
 Tomemos como ejemplo el siguiente lote de comandos, que se ejecuta en una llamada a <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 En .NET Framework versión 1.1 y versiones posterior, NOCOUNT permanecerá en ON para los comandos que se ejecuten mientras la conexión esté abierta. En la versión 1.0 de .NET Framework, NOCOUNT es sólo ON para la ejecución del comando actual.  
  
 Este cambio puede afectar a la compatibilidad de versiones anteriores y de la aplicación si depende del comportamiento de <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> para cualquier versión de .NET Framework.  
  
 Para las aplicaciones que se ejecutan en versiones anteriores y posteriores de .NET Framework, puede escribir el código para asegurarse de que el comportamiento es el mismo independientemente de la versión que se ejecutan en. Si desea asegurarse de que un comando modifica el estado de la conexión para todos los comandos que se ejecuten posteriormente, se recomienda ejecutar el comando usando <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>. Si desea asegurarse de que un comando no modifica el estado de la conexión para todos los comandos que se ejecuten posteriormente, se recomienda incluir los comandos para restablecer el estado de la conexión en el comando. Por ejemplo:  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
