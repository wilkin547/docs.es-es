---
title: Creación de reflejo de la base de datos en SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 89befaff-bb46-4290-8382-e67cdb0e3de9
ms.openlocfilehash: 90357b96d570ec1b2f80f8809ccfde69977bbc25
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509808"
---
# <a name="database-mirroring-in-sql-server"></a>Creación de reflejo de la base de datos en SQL Server
La creación de reflejo de base de datos de SQL Server permite mantener una copia, o reflejo, de una base de datos de SQL Server en un servidor en modo de espera. El reflejo garantiza que en todo momento existen dos copias distintas de los datos, lo que proporciona una alta disponibilidad y una completa redundancia de datos. El proveedor de datos .NET para SQL Server ofrece compatibilidad implícita con la creación de reflejo de base de datos; de modo que el desarrollador no tiene que realizar ninguna acción ni escribir ningún código una vez que se ha configurado para una base de datos de SQL Server. Además, el objeto <xref:System.Data.SqlClient.SqlConnection> admite un modo de conexión explícita que permita proporcionar el nombre de un servidor asociado de conmutación por error en la propiedad <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 La siguiente secuencia simplificada de eventos tiene lugar para un objeto <xref:System.Data.SqlClient.SqlConnection> que identifica una base de datos configurada para el reflejo:  
  
1.  La aplicación cliente se conecta correctamente a la base de datos principal y el servidor devuelve el nombre del servidor asociado, el cual se almacena en caché en el cliente.  
  
2.  Si el servidor que contiene la base de datos principal da error o se interrumpe la conectividad, se pierde el estado de la conexión y de la transacción. La aplicación cliente intenta restablecer la conexión a la base de datos principal pero no lo consigue.  
  
3.  La aplicación cliente intenta entonces de forma transparente establecer una conexión a la base de datos de reflejo del servidor asociado. Si lo consigue, la conexión se redirecciona a la base de datos de reflejo, que se convierte entonces en la nueva base de datos principal.  
  
## <a name="specifying-the-failover-partner-in-the-connection-string"></a>Especificación del asociado de conmutación por error en la cadena de conexión  
 Si proporciona el nombre de un servidor asociado de conmutación por error en la cadena de conexión, el cliente intenta una conexión al asociado de conmutación por error de forma transparente si la base de datos principal no está disponible cuando la aplicación cliente se conecta por primera vez.  
  
```  
";Failover Partner=PartnerServerName"  
```  
  
 Si omite el nombre del servidor asociado de conmutación por error y la base de datos principal no está disponible cuando la aplicación cliente se conecta por primera vez, se produce una excepción <xref:System.Data.SqlClient.SqlException>.  
  
 Cuando una <xref:System.Data.SqlClient.SqlConnection> se abre correctamente, el servidor devuelve el nombre del asociado de conmutación por error, que invalida cualquier valor especificado en la cadena de conexión.  
  
> [!NOTE]
>  Se debe especificar de forma explícita el catálogo o el nombre de la base de datos original en la cadena de conexión para los escenarios de creación de reflejos. Si el cliente recibe información de conmutación por error sobre una conexión para la que no se ha especificado de forma explícita un catálogo o base de datos original, dicha información no se almacena en caché y la aplicación no intenta una conmutación por error si el servidor principal da error. Si una cadena de conexión tiene un valor para el asociado de conmutación por error, pero no para el catálogo o la base de datos original, se produce una excepción `InvalidArgumentException`.  
  
## <a name="retrieving-the-current-server-name"></a>Recuperación del nombre del servidor actual  
 En caso de una conmutación por error, puede recuperar el nombre del servidor al que hay actualmente una conexión mediante la propiedad <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> de un objeto <xref:System.Data.SqlClient.SqlConnection>. El siguiente fragmento de código recupera el nombre del servidor activo, suponiendo que la variable de conexión hace referencia a una <xref:System.Data.SqlClient.SqlConnection> abierta.  
  
 Cuando se produce un evento de conmutación por error y se cambia la conexión al servidor reflejado, la **DataSource** propiedad se actualiza para reflejar el nombre del servidor.  
  
```vb  
Dim activeServer As String = connection.DataSource  
```  
  
```csharp  
string activeServer = connection.DataSource;  
```  
  
## <a name="sqlclient-mirroring-behavior"></a>Comportamiento del reflejo de SqlClient  
 El cliente siempre intenta conectarse al servidor principal actual. Si da error, prueba con el asociado de conmutación por error. Si se ha cambiado el rol de la base de datos reflejada al de principal en el servidor asociado, la conexión se realiza correctamente y la nueva asignación principal-reflejada se envía al cliente y se almacena en caché durante la vigencia de la llamada a <xref:System.AppDomain>. No se almacena en el almacenamiento persistente y no está disponible para las posteriores conexiones en otra **AppDomain** o proceso. Sin embargo, está disponible para las posteriores conexiones en el mismo **AppDomain**. Tenga en cuenta que otro **AppDomain** o proceso que se ejecuta en el mismo o en otro equipo siempre tiene su grupo de conexiones, y esas conexiones no se restablecen. En ese caso, si la base de datos principal deja de funcionar, cada proceso o **AppDomain** se produce un error una vez y el grupo se borra automáticamente.  
  
> [!NOTE]
>  En el servidor, la compatibilidad con el reflejo se configura por cada base de datos. Si se ejecutan operaciones de manipulación de datos en otras bases de datos no incluidas en el conjunto principal/reflejada, o bien con nombres de varias partes o mediante el cambio de la base de datos actual, los cambios en estas otras bases de datos no se propagarán si se produce un error. Cuando los datos se modifican en una base de datos sin reflejo, no se generan errores. El programador deberá valorar los posibles efectos de tales operaciones.  
  
## <a name="database-mirroring-resources"></a>Recursos de reflejos de base de datos  
 Para obtener documentación conceptual e información sobre cómo configurar, implementar y administrar la creación de reflejo, vea los siguientes recursos en la documentación de SQL Server.  
  
|Recurso|Descripción|  
|--------------|-----------------|  
|[Creación de reflejo de base de datos](/sql/database-engine/database-mirroring/database-mirroring-sql-server)|Describe cómo establecer y configurar la creación de reflejos en SQL Server.|  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
