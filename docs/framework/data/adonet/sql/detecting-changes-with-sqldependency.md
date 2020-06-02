---
title: Detectar cambios con SqlDependency
description: Asociar un objeto SqlDependency a un SqlCommand para detectar cuándo se diferencian los resultados de la consulta de los recuperados originalmente en ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: b196d42477e1778c45df64b1390502645fdd649d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286473"
---
# <a name="detecting-changes-with-sqldependency"></a>Detectar cambios con SqlDependency

Un objeto <xref:System.Data.SqlClient.SqlDependency> se puede asociar a <xref:System.Data.SqlClient.SqlCommand> para detectar cuándo se diferencian los resultados de la consulta de los recuperados originalmente. También puede asignar un delegado al evento `OnChange`, que se activará cuando cambien los resultados de un comando asociado. Debe asociar <xref:System.Data.SqlClient.SqlDependency> con el comando antes de ejecutar el comando. La propiedad `HasChanges` de <xref:System.Data.SqlClient.SqlDependency> también se puede utilizar para determinar si los resultados de la consulta han cambiado desde que se recuperaron los datos por primera vez.

## <a name="security-considerations"></a>Consideraciones sobre la seguridad

La infraestructura de dependencias se basa en un objeto <xref:System.Data.SqlClient.SqlConnection> que se abre cuando se llama a <xref:System.Data.SqlClient.SqlDependency.Start%2A> para recibir notificaciones de que los datos subyacentes han cambiado para un comando determinado. La capacidad de un cliente de iniciar la llamada a `SqlDependency.Start` se controla mediante el uso de los atributos de seguridad de acceso del código y <xref:System.Data.SqlClient.SqlClientPermission>. Para obtener más información, vea [habilitar notificaciones de consulta](enabling-query-notifications.md) y [seguridad de acceso del código y ADO.net](../code-access-security.md).

### <a name="example"></a>Ejemplo

En los pasos siguientes se muestra cómo declarar una dependencia, ejecutar un comando y recibir una notificación cuando cambia el conjunto de resultados:

1. Inicie una conexión `SqlDependency` al servidor.

2. Cree objetos <xref:System.Data.SqlClient.SqlConnection> y <xref:System.Data.SqlClient.SqlCommand> para conectarse al servidor y definir una instrucción Transact-SQL.

3. Cree un objeto `SqlDependency`, o bien use uno que ya exista y enlácelo al objeto `SqlCommand`. Internamente, esta acción crea un objeto <xref:System.Data.Sql.SqlNotificationRequest> y lo enlaza al objeto de comando según sea necesario. Esta solicitud de notificación contiene un identificador interno que identifica de forma única este objeto `SqlDependency`. También inicia el agente de escucha del cliente si aún no está activo.

4. Suscriba un controlador de eventos al evento `OnChange` del objeto `SqlDependency`.

5. Ejecute el comando con cualquiera de los métodos `Execute` del objeto `SqlCommand`. Dado que el comando está enlazado al objeto de notificación, el servidor reconoce que debe generar una notificación y la información de la cola apunta a la cola de dependencias.

6. Se ha perdido la conexión de `SqlDependency` al servidor.

Si cualquier usuario cambia posteriormente los datos subyacentes, Microsoft SQL Server detecta que hay una notificación pendiente para ese cambio y envía una notificación que se procesa y reenvía al cliente a través del objeto `SqlConnection` subyacente que se creó mediante una llamada a `SqlDependency.Start`. El agente de escucha del cliente recibe el mensaje de invalidación. A continuación, el agente de escucha del cliente busca el objeto `SqlDependency` asociado y activa el evento `OnChange`.

En el fragmento de código siguiente se muestra el patrón de diseño que se usaría para crear una aplicación de ejemplo.

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
        ' Maintain the refernce in a class member.
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

## <a name="see-also"></a>Consulte también

- [Notificaciones de consulta en SQL Server](query-notifications-in-sql-server.md)
- [Información general de ADO.NET](../ado-net-overview.md)
