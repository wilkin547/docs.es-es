---
title: Agrupación de conexiones de OLE DB, ODBC y Oracle
ms.date: 03/30/2017
ms.assetid: 2bd83b1e-3ea9-43c4-bade-d9cdb9bbbb04
ms.openlocfilehash: 7c17863facd962583e0da03e810c9a8150cda0a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772039"
---
# <a name="ole-db-odbc-and-oracle-connection-pooling"></a>Agrupación de conexiones de OLE DB, ODBC y Oracle
La agrupación de conexiones puede mejorar de forma considerable el rendimiento y la escalabilidad de la aplicación. En esta sección se describe la agrupación de conexiones en los proveedores de datos .NET Framework para OLE DB, ODBC y Oracle.  
  
## <a name="connection-pooling-for-oledb"></a>Agrupación de conexiones para OLE DB  
 El proveedor de datos .NET Framework para OLE DB agrupa automáticamente las conexiones mediante la agrupación de sesiones OLE DB. Se pueden utilizar argumentos de cadena de conexión para habilitar o deshabilitar servicios OLE DB, incluida la agrupación. Por ejemplo, la siguiente cadena de conexión deshabilita la agrupación de sesiones OLE DB y la inscripción automática de transacciones.  
  
```  
Provider=SQLOLEDB;OLE DB Services=-4;Data Source=localhost;Integrated Security=SSPI;  
```  
  
 Se recomienda cerrar siempre o eliminar una conexión cuando termine de utilizarla, para que la conexión pueda regresar al grupo. Es posible que las conexiones que no se cierran explícitamente no puedan regresar al grupo. Por ejemplo, una conexión que se ha salido del ámbito pero que no se ha cerrado explícitamente solo se devolverá al grupo de conexión si se ha alcanzado el tamaño máximo del grupo y la conexión aún es válida.  
  
 Para obtener más información acerca de la sesión de OLE DB o agrupación de recursos, así como cómo deshabilitar la agrupación invalidando los valores predeterminados de servicio de proveedor OLE DB, consulte el [Guía del programador de OLE DB](https://go.microsoft.com/fwlink/?linkid=45232).  
  
## <a name="connection-pooling-for-odbc"></a>Agrupación de conexiones para ODBC  
 La agrupación de conexiones para el proveedor de datos .NET Framework para ODBC se administra a través del Administrador de controladores ODBC que se utiliza en la conexión, y que no está influido por dicho proveedor.  
  
 Para habilitar o deshabilitar la agrupación de conexiones, abra **Administrador de orígenes de datos ODBC** en la carpeta Herramientas administrativas del Panel de Control. El **agrupación de conexiones** pestaña le permite especificar los parámetros para cada controlador ODBC instalado de agrupación de conexiones. Tenga en cuenta que los cambios en la agrupación de conexiones de un controlador ODBC específico afectarán a todas las aplicaciones que utilicen dicho controlador.  
  
## <a name="connection-pooling-for-oracleclient"></a>Agrupación de conexiones para OracleClient  
 El proveedor de datos .NET Framework para Oracle ofrece agrupación automática de conexiones para la aplicación cliente de ADO.NET. También puede suministrar varios modificadores de cadena de conexión para controlar el comportamiento de agrupación de conexiones (vea "Control de la agrupación de conexiones con palabras clave de cadena de conexión", más adelante en este tema).  
  
### <a name="pool-creation-and-assignment"></a>Creación y asignación del grupo  
 Cuando se abre una conexión, se crea un grupo de conexión basado en un algoritmo de coincidencia exacta que asocia el grupo con la cadena de conexión de la conexión. Cada grupo de conexión se asocia con una cadena de conexión distinta. Si se abre una nueva conexión y la cadena de conexión no coincide exactamente con un grupo existente, se crea un nuevo grupo.  
  
 Una vez creados, los grupos de conexión no se destruyen hasta que finaliza el proceso activo. Mantener grupos inactivos o vacíos consume muy pocos recursos del sistema.  
  
### <a name="connection-addition"></a>Adición de conexiones  
 Para cada cadena de conexión única se crea un grupo de conexión. Cuando se crea un grupo, se crean y agregan al grupo varios objetos de conexión y se satisface así el requisito de tamaño mínimo del grupo. Las conexiones se agregan al grupo cuando es necesario, hasta el tamaño máximo del grupo.  
  
 Cuando se solicita un objeto <xref:System.Data.OracleClient.OracleConnection>, se obtiene del grupo si se encuentra disponible una conexión que se pueda utilizar. Una conexión de este tipo debe estar sin utilizar en ese momento, tener un contexto de transacción coincidente o no estar asociada con ningún contexto de transacción, y tener un vínculo válido al servidor.  
  
 Si se ha alcanzado el tamaño máximo del grupo y no hay disponible ninguna conexión que se pueda utilizar, la solicitud se pone en la cola. El concentrador de conexión satisface estas solicitudes al reasignar las conexiones conforme se liberan de nuevo en el grupo, lo cual ocurre y se liberan de nuevo en el grupo cuando se cierran o eliminan.  
  
### <a name="connection-removal"></a>Eliminación de conexiones  
 El concentrador de conexión quita una conexión del grupo después de que ha estado inactiva durante un período de tiempo prolongado o si detecta que se ha roto la conexión al servidor. Tenga en cuenta que esto solo puede detectarse después de intentar comunicarse con el servidor. Si se encuentra que una conexión ya no está conectada al servidor, se marca como no válida. El concentrador de conexión analiza periódicamente los grupos en busca de objetos que se han liberado en el grupo y marcado como no válidos. Luego, estas conexiones se quitan de forma permanente.  
  
 Si existe una conexión a un servidor que ha desaparecido, se puede extraer del grupo si el concentrador de conexión no ha detectado la conexión rota y la ha marcado como no válida. Cuando esto se produce, se genera una excepción. No obstante, aun así deberá cerrar la conexión para liberarla de nuevo en el grupo.  
  
 No llame a `Close` o a `Dispose` en un objeto `Connection`, un objeto `DataReader` o cualquier otro objeto administrado en el método `Finalize` de la clase. En un finalizador, libere solo los recursos no administrados que pertenezcan directamente a su clase. Si la clase no dispone de recursos no administrados, no incluya un método `Finalize` en la definición de clase. Para obtener más información, consulte [recolección](../../../../docs/standard/garbage-collection/index.md).  
  
### <a name="transaction-support"></a>Compatibilidad con transacciones  
 Las conexiones se extraen del grupo y se asignan en función del contexto de transacción. Es necesario que el subproceso solicitante y la conexión asignada coincidan. Por lo tanto, cada grupo de conexiones se divide realmente en conexiones ningún contexto de transacción asociada a ellos y en *N* subdivisiones que contienen conexiones con un contexto de transacción particular.  
  
 Cuando se cierra una conexión, se libera de nuevo en el grupo y en la subdivisión adecuada en función de su contexto de transacción. Por lo tanto, puede cerrar la conexión sin generar un error, incluso aunque aún haya pendiente una transacción distribuida. Esto le permite confirmar o anular la transacción distribuida más adelante.  
  
### <a name="controlling-connection-pooling-with-connection-string-keywords"></a>Control de la agrupación de conexiones con palabras clave de cadena de conexión  
 La propiedad <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> del objeto <xref:System.Data.OracleClient.OracleConnection> admite pares clave-valor de cadena de conexión que se pueden utilizar para ajustar el comportamiento de la lógica de agrupación de conexiones.  
  
 En la siguiente tabla se describen los valores <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> que puede utilizar para ajustar el comportamiento de agrupación de conexiones.  
  
|Name|Default|Descripción|  
|----------|-------------|-----------------|  
|`Connection Lifetime`|0|Cuando una conexión se devuelve al grupo, su hora de creación se compara con la hora actual y, si ese marco temporal (en segundos) supera el valor especificado por `Connection Lifetime`, la conexión se destruye. Esto resulta de utilidad en configuraciones agrupadas para forzar el equilibrio de carga entre un servidor en ejecución y uno que acaba de conectarse.<br /><br /> Un valor de cero (0) hará que las conexiones agrupadas tengan el tiempo de espera máximo.|  
|`Enlist`|'true'|Cuando es `true`, el concentrador inscribe automáticamente la conexión en el contexto de transacción actual del subproceso de creación, si existe un contexto de transacción.|  
|`Max Pool Size`|100|El número máximo de conexiones permitido en el grupo.|  
|`Min Pool Size`|0|El número mínimo de conexiones mantenido en el grupo.|  
|`Pooling`|'true'|Cuando es `true`, la conexión se extrae del grupo adecuado o, si es necesario, se crea y agrega al grupo correcto.|  
  
## <a name="see-also"></a>Vea también

- [Agrupación de conexiones](../../../../docs/framework/data/adonet/connection-pooling.md)
- [Contadores de rendimiento](../../../../docs/framework/data/adonet/performance-counters.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
