---
title: Detectar cambios con SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: 839642c4fea45f4f37c5dc351d71417d46d07093
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376209"
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="de24c-102">Detectar cambios con SqlDependency</span><span class="sxs-lookup"><span data-stu-id="de24c-102">Detecting Changes with SqlDependency</span></span>

<span data-ttu-id="de24c-103">Un objeto <xref:System.Data.SqlClient.SqlDependency> se puede asociar a <xref:System.Data.SqlClient.SqlCommand> para detectar si los resultados de consulta son diferentes de los recuperados originalmente.</span><span class="sxs-lookup"><span data-stu-id="de24c-103">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="de24c-104">También puede asignar un delegado al evento `OnChange`, que se activará cuando los resultados cambien en un comando asociado.</span><span class="sxs-lookup"><span data-stu-id="de24c-104">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="de24c-105">Para poder ejecutar el comando, debe asociar <xref:System.Data.SqlClient.SqlDependency> con el comando.</span><span class="sxs-lookup"><span data-stu-id="de24c-105">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="de24c-106">La propiedad `HasChanges` de <xref:System.Data.SqlClient.SqlDependency> se puede utilizar también para determinar si los resultados de la consulta han cambiado desde que los datos se recuperaron por primera vez.</span><span class="sxs-lookup"><span data-stu-id="de24c-106">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="de24c-107">Consideraciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="de24c-107">Security Considerations</span></span>

<span data-ttu-id="de24c-108">La infraestructura de dependencia se basa en un <xref:System.Data.SqlClient.SqlConnection> que se abre cuando se llama a <xref:System.Data.SqlClient.SqlDependency.Start%2A> para recibir notificaciones de que los datos subyacentes han cambiado para un comando concreto.</span><span class="sxs-lookup"><span data-stu-id="de24c-108">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="de24c-109">La capacidad de un cliente de iniciar la llamada a `SqlDependency.Start` se controla mediante el uso de <xref:System.Data.SqlClient.SqlClientPermission> y los atributos de seguridad de acceso del código.</span><span class="sxs-lookup"><span data-stu-id="de24c-109">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="de24c-110">Para obtener más información, consulte [habilitar las notificaciones de consulta](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) y [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="de24c-110">For more information, see [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) and [Code Access Security and ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).</span></span>

### <a name="example"></a><span data-ttu-id="de24c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de24c-111">Example</span></span>

<span data-ttu-id="de24c-112">Los pasos siguientes muestran cómo declarar una dependencia, ejecutar un comando y recibir una notificación cuando cambie el conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="de24c-112">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>

1. <span data-ttu-id="de24c-113">Inicie una conexión `SqlDependency` al servidor.</span><span class="sxs-lookup"><span data-stu-id="de24c-113">Initiate a `SqlDependency` connection to the server.</span></span>

2. <span data-ttu-id="de24c-114">Cree objetos <xref:System.Data.SqlClient.SqlConnection> y <xref:System.Data.SqlClient.SqlCommand> para conectarse al servidor y defina una instrucción Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="de24c-114">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>

3. <span data-ttu-id="de24c-115">Cree un objeto `SqlDependency` nuevo o utilice uno ya existente, y enlácelo al objeto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="de24c-115">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="de24c-116">Con ello se crea, a nivel interno, un objeto <xref:System.Data.Sql.SqlNotificationRequest> y se enlaza al objeto de comando si es necesario.</span><span class="sxs-lookup"><span data-stu-id="de24c-116">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="de24c-117">Esta solicitud de notificación contiene un identificador interno que identifica de forma única este objeto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="de24c-117">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="de24c-118">Con ello también se inicia la escucha de cliente si aún no se ha activado.</span><span class="sxs-lookup"><span data-stu-id="de24c-118">It also starts the client listener if it is not already active.</span></span>

4. <span data-ttu-id="de24c-119">Suscriba un controlador de eventos al evento `OnChange` del objeto `SqlDependency`.</span><span class="sxs-lookup"><span data-stu-id="de24c-119">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>

5. <span data-ttu-id="de24c-120">Ejecute el comando mediante uno de los métodos `Execute` del objeto `SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="de24c-120">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="de24c-121">Como el comando está enlazado al objeto de notificación, el servidor reconoce que debe generar una notificación y la información de la cola apuntará a la cola de dependencias.</span><span class="sxs-lookup"><span data-stu-id="de24c-121">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>

6. <span data-ttu-id="de24c-122">Detenga la conexión `SqlDependency` al servidor.</span><span class="sxs-lookup"><span data-stu-id="de24c-122">Stop the `SqlDependency` connection to the server.</span></span>

<span data-ttu-id="de24c-123">Si algún usuario cambia posteriormente los datos subyacentes, Microsoft SQL Server detecta que hay una notificación pendiente de tal cambio y publica una notificación que se procesa y reenvía al cliente a través del `SqlConnection` subyacente que se creó llamando a `SqlDependency.Start`.</span><span class="sxs-lookup"><span data-stu-id="de24c-123">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="de24c-124">La escucha de cliente recibe el mensaje de invalidación.</span><span class="sxs-lookup"><span data-stu-id="de24c-124">The client listener receives the invalidation message.</span></span> <span data-ttu-id="de24c-125">A continuación, la escucha de cliente localiza el objeto `SqlDependency` asociado y activa el evento `OnChange`.</span><span class="sxs-lookup"><span data-stu-id="de24c-125">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>

<span data-ttu-id="de24c-126">El siguiente fragmento de código muestra el patrón de diseño que se puede utilizar para crear una aplicación de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="de24c-126">The following code fragment shows the design pattern you would use to create a sample application.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="de24c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="de24c-127">See also</span></span>

- [<span data-ttu-id="de24c-128">Notificaciones de consulta en SQL Server</span><span class="sxs-lookup"><span data-stu-id="de24c-128">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="de24c-129">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="de24c-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
