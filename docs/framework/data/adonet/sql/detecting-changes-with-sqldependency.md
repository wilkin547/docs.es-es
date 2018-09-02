---
title: Detectar cambios con SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: 63d6a17e5aaf3e5d39ed0eda288e75c071be4d73
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405439"
---
# <a name="detecting-changes-with-sqldependency"></a>Detectar cambios con SqlDependency
Un objeto <xref:System.Data.SqlClient.SqlDependency> se puede asociar a <xref:System.Data.SqlClient.SqlCommand> para detectar si los resultados de consulta son diferentes de los recuperados originalmente. También puede asignar un delegado al evento `OnChange`, que se activará cuando los resultados cambien en un comando asociado. Para poder ejecutar el comando, debe asociar <xref:System.Data.SqlClient.SqlDependency> con el comando. La propiedad `HasChanges` de <xref:System.Data.SqlClient.SqlDependency> se puede utilizar también para determinar si los resultados de la consulta han cambiado desde que los datos se recuperaron por primera vez.  
  
## <a name="security-considerations"></a>Consideraciones de seguridad  
 La infraestructura de dependencia se basa en un <xref:System.Data.SqlClient.SqlConnection> que se abre cuando se llama a <xref:System.Data.SqlClient.SqlDependency.Start%2A> para recibir notificaciones de que los datos subyacentes han cambiado para un comando concreto. La capacidad de un cliente de iniciar la llamada a `SqlDependency.Start` se controla mediante el uso de <xref:System.Data.SqlClient.SqlClientPermission> y los atributos de seguridad de acceso del código. Para obtener más información, consulte [habilitar las notificaciones de consulta](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) y [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).  
  
### <a name="example"></a>Ejemplo  
 Los pasos siguientes muestran cómo declarar una dependencia, ejecutar un comando y recibir una notificación cuando cambie el conjunto de resultados:  
  
1.  Inicie una conexión `SqlDependency` al servidor.  
  
2.  Cree objetos <xref:System.Data.SqlClient.SqlConnection> y <xref:System.Data.SqlClient.SqlCommand> para conectarse al servidor y defina una instrucción Transact-SQL.  
  
3.  Cree un objeto `SqlDependency` nuevo o utilice uno ya existente, y enlácelo al objeto `SqlCommand`. Con ello se crea, a nivel interno, un objeto <xref:System.Data.Sql.SqlNotificationRequest> y se enlaza al objeto de comando si es necesario. Esta solicitud de notificación contiene un identificador interno que identifica de forma única este objeto `SqlDependency`. Con ello también se inicia la escucha de cliente si aún no se ha activado.  
  
4.  Suscriba un controlador de eventos al evento `OnChange` del objeto `SqlDependency`.  
  
5.  Ejecute el comando mediante uno de los métodos `Execute` del objeto `SqlCommand`. Como el comando está enlazado al objeto de notificación, el servidor reconoce que debe generar una notificación y la información de la cola apuntará a la cola de dependencias.  
  
6.  Detenga la conexión `SqlDependency` al servidor.  
  
 Si algún usuario cambia posteriormente los datos subyacentes, Microsoft SQL Server detecta que hay una notificación pendiente de tal cambio y publica una notificación que se procesa y reenvía al cliente a través del `SqlConnection` subyacente que se creó llamando a `SqlDependency.Start`. La escucha de cliente recibe el mensaje de invalidación. A continuación, la escucha de cliente localiza el objeto `SqlDependency` asociado y activa el evento `OnChange`.  
  
 El siguiente fragmento de código muestra el patrón de diseño que se puede utilizar para crear una aplicación de ejemplo.  
  
```vb  
Sub Initialization()  
    ' Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName)  
End Sub  
  
Sub SomeMethod()   
    ' Assume connection is an open SqlConnection.  
    ' Create a new SqlCommand object.  
    Using command As New SqlCommand( _  
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _  
      connection)  
  
        ' Create a dependency and associate it with the SqlCommand.  
        Dim dependency As New SqlDependency(command)  
        ' Maintain the refence in a class member.  
        ' Subscribe to the SqlDependency event.  
        AddHandler dependency.OnChange, AddressOf OnDependencyChange  
  
        ' Execute the command.  
        Using reader = command.ExecuteReader()  
            ' Process the DataReader.  
        End Using  
    End Using  
End Sub   
  
' Handler method  
Sub OnDependencyChange(ByVal sender As Object, _  
    ByVal e As SqlNotificationEventArgs)   
    ' Handle the event (for example, invalidate this cache entry).  
End Sub  
  
Sub Termination()  
    ' Release the dependency  
    SqlDependency.Stop(connectionString, queueName)  
End Sub  
```  
  
```csharp  
void Initialization()  
{  
    // Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName);  
}  
  
void SomeMethod()  
{  
    // Assume connection is an open SqlConnection.  
  
    // Create a new SqlCommand object.  
    using (SqlCommand command=new SqlCommand(  
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",   
        connection))  
    {  
  
        // Create a dependency and associate it with the SqlCommand.  
        SqlDependency dependency=new SqlDependency(command);  
        // Maintain the reference in a class member.  
  
        // Subscribe to the SqlDependency event.  
        dependency.OnChange+=new  
           OnChangeEventHandler(OnDependencyChange);  
  
        // Execute the command.  
        using (SqlDataReader reader = command.ExecuteReader())  
        {  
            // Process the DataReader.  
        }  
    }  
}  
  
// Handler method  
void OnDependencyChange(object sender,   
   SqlNotificationEventArgs e )  
{  
  // Handle the event (for example, invalidate this cache entry).  
}  
  
void Termination()  
{  
    // Release the dependency.  
    SqlDependency.Stop(connectionString, queueName);  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Notificaciones de consulta en SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
