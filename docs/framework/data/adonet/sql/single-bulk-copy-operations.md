---
description: 'Más información acerca de: operaciones de copia masiva únicas'
title: Operaciones de copia masiva únicas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
ms.openlocfilehash: f6b046fbd73ad798f3f9f117eea0b72f46e43b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767484"
---
# <a name="single-bulk-copy-operations"></a><span data-ttu-id="8bf92-103">Operaciones de copia masiva únicas</span><span class="sxs-lookup"><span data-stu-id="8bf92-103">Single Bulk Copy Operations</span></span>

<span data-ttu-id="8bf92-104">El método más sencillo para realizar una operación de copia masiva de SQL Server es realizar una operación única con una base de datos.</span><span class="sxs-lookup"><span data-stu-id="8bf92-104">The simplest approach to performing a SQL Server bulk copy operation is to perform a single operation against a database.</span></span> <span data-ttu-id="8bf92-105">De forma predeterminada, una operación de copia masiva se realiza como una operación aislada: la operación de copia tiene lugar sin transacciones y no es posible revertirla.</span><span class="sxs-lookup"><span data-stu-id="8bf92-105">By default, a bulk copy operation is performed as an isolated operation: the copy operation occurs in a non-transacted way, with no opportunity for rolling it back.</span></span>

> [!NOTE]
> <span data-ttu-id="8bf92-106">Si necesita revertir toda o parte de la copia masiva cuando se produce un error, puede usar una transacción administrada por <xref:System.Data.SqlClient.SqlBulkCopy> o realizar la operación de copia masiva en una transacción existente.</span><span class="sxs-lookup"><span data-stu-id="8bf92-106">If you need to roll back all or part of the bulk copy when an error occurs, you can either use a <xref:System.Data.SqlClient.SqlBulkCopy>-managed transaction, or perform the bulk copy operation within an existing transaction.</span></span> <span data-ttu-id="8bf92-107">**SqlBulkCopy** también funciona con <xref:System.Transactions> si la conexión está inscrita (implícita o explícitamente) en una transacción **System.Transactions**.</span><span class="sxs-lookup"><span data-stu-id="8bf92-107">**SqlBulkCopy** will also work with <xref:System.Transactions> if the connection is enlisted (implicitly or explicitly) into a **System.Transactions** transaction.</span></span>
>
> <span data-ttu-id="8bf92-108">Para obtener más información, vea [transacciones y operaciones de copia masiva](transaction-and-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="8bf92-108">For more information, see [Transaction and Bulk Copy Operations](transaction-and-bulk-copy-operations.md).</span></span>

<span data-ttu-id="8bf92-109">Los pasos generales para realizar una operación de copia masiva son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8bf92-109">The general steps for performing a bulk copy operation are as follows:</span></span>

1. <span data-ttu-id="8bf92-110">Conéctese al servidor de origen y obtenga los datos que se van a copiar.</span><span class="sxs-lookup"><span data-stu-id="8bf92-110">Connect to the source server and obtain the data to be copied.</span></span> <span data-ttu-id="8bf92-111">Los datos también pueden provenir de otros orígenes, si se pueden recuperar de un objeto <xref:System.Data.IDataReader> o <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="8bf92-111">Data can also come from other sources, if it can be retrieved from an <xref:System.Data.IDataReader> or <xref:System.Data.DataTable> object.</span></span>

2. <span data-ttu-id="8bf92-112">Conéctese al servidor de destino (a menos que quiera que **SqlBulkCopy** establezca una conexión automáticamente).</span><span class="sxs-lookup"><span data-stu-id="8bf92-112">Connect to the destination server (unless you want **SqlBulkCopy** to establish a connection for you).</span></span>

3. <span data-ttu-id="8bf92-113">Cree un objeto de <xref:System.Data.SqlClient.SqlBulkCopy>, estableciendo las propiedades necesarias.</span><span class="sxs-lookup"><span data-stu-id="8bf92-113">Create a <xref:System.Data.SqlClient.SqlBulkCopy> object, setting any necessary properties.</span></span>

4. <span data-ttu-id="8bf92-114">Establezca la propiedad **DestinationTableName** para indicar la tabla de destino de la operación de inserción masiva.</span><span class="sxs-lookup"><span data-stu-id="8bf92-114">Set the **DestinationTableName** property to indicate the target table for the bulk insert operation.</span></span>

5. <span data-ttu-id="8bf92-115">Llame a uno de los métodos **WriteToServer**.</span><span class="sxs-lookup"><span data-stu-id="8bf92-115">Call one of the **WriteToServer** methods.</span></span>

6. <span data-ttu-id="8bf92-116">Como opción, actualice las propiedades y llame de nuevo a **WriteToServer** si fuese necesario.</span><span class="sxs-lookup"><span data-stu-id="8bf92-116">Optionally, update properties and call **WriteToServer** again as necessary.</span></span>

7. <span data-ttu-id="8bf92-117">Llame a <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>o ajuste las operaciones de copia masiva dentro de una instrucción `Using`.</span><span class="sxs-lookup"><span data-stu-id="8bf92-117">Call <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A>, or wrap the bulk copy operations within a `Using` statement.</span></span>

> [!CAUTION]
> <span data-ttu-id="8bf92-118">Se recomienda que los tipos de datos de la columna de origen y de destino coincidan.</span><span class="sxs-lookup"><span data-stu-id="8bf92-118">We recommend that the source and target column data types match.</span></span> <span data-ttu-id="8bf92-119">Si los tipos de datos no coinciden, **SqlBulkCopy** intenta convertir los valores de origen en el tipo de datos de destino mediante las reglas empleadas por <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="8bf92-119">If the data types do not match, **SqlBulkCopy** attempts to convert each source value to the target data type, using the rules employed by <xref:System.Data.SqlClient.SqlParameter.Value%2A>.</span></span> <span data-ttu-id="8bf92-120">Las conversiones pueden afectar al rendimiento y también pueden producir errores inesperados.</span><span class="sxs-lookup"><span data-stu-id="8bf92-120">Conversions can affect performance, and also can result in unexpected errors.</span></span> <span data-ttu-id="8bf92-121">Por ejemplo, un tipo de datos `Double` puede convertirse en un tipo de datos `Decimal` la mayoría de las veces, pero no siempre.</span><span class="sxs-lookup"><span data-stu-id="8bf92-121">For example, a `Double` data type can be converted to a `Decimal` data type most of the time, but not always.</span></span>

## <a name="example"></a><span data-ttu-id="8bf92-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bf92-122">Example</span></span>

<span data-ttu-id="8bf92-123">La aplicación de consola siguiente muestra cómo cargar datos mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="8bf92-123">The following console application demonstrates how to load data using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="8bf92-124">En este ejemplo se usa <xref:System.Data.SqlClient.SqlDataReader> para copiar datos de la tabla **Production.Product** de la base de datos **AdventureWorks** de SQL Server en una tabla similar de la misma base de datos.</span><span class="sxs-lookup"><span data-stu-id="8bf92-124">In this example, a <xref:System.Data.SqlClient.SqlDataReader> is used to copy data from the **Production.Product** table in the SQL Server **AdventureWorks** database to a similar table in the same database.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bf92-125">Este ejemplo no se ejecutará a menos que haya creado las tablas de trabajo como se describe en el ejemplo de configuración de la [copia masiva](bulk-copy-example-setup.md).</span><span class="sxs-lookup"><span data-stu-id="8bf92-125">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](bulk-copy-example-setup.md).</span></span> <span data-ttu-id="8bf92-126">Este código se proporciona para mostrar la sintaxis para usar **SqlBulkCopy**.</span><span class="sxs-lookup"><span data-stu-id="8bf92-126">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="8bf92-127">Si las tablas de origen y destino se encuentran en la misma instancia de SQL Server, es más fácil y rápido usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.</span><span class="sxs-lookup"><span data-stu-id="8bf92-127">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>

[!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
[!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]

## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a><span data-ttu-id="8bf92-128">Realización de una operación de copia masiva mediante Transact-SQL y la clase Command</span><span class="sxs-lookup"><span data-stu-id="8bf92-128">Performing a Bulk Copy Operation Using Transact-SQL and the Command Class</span></span>

<span data-ttu-id="8bf92-129">En el ejemplo siguiente se muestra cómo usar el método <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> para ejecutar la instrucción BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="8bf92-129">The following example illustrates how to use the <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> method to execute the BULK INSERT statement.</span></span>

> [!NOTE]
> <span data-ttu-id="8bf92-130">La ruta de acceso al origen de datos depende del servidor.</span><span class="sxs-lookup"><span data-stu-id="8bf92-130">The file path for the data source is relative to the server.</span></span> <span data-ttu-id="8bf92-131">El proceso del servidor debe tener acceso a esa ruta para que la operación de copia masiva se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="8bf92-131">The server process must have access to that path in order for the bulk copy operation to succeed.</span></span>

```vb
Using connection As SqlConnection = New SqlConnection(connectionString)
Dim queryString As String = _
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"
connection.Open()
SqlCommand command = New SqlCommand(queryString, connection);

command.ExecuteNonQuery()
End Using
```

```csharp
using (SqlConnection connection = New SqlConnection(connectionString))
{
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +
    "FROM 'f:\mydata\data.tbl' " +
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";
connection.Open();
SqlCommand command = new SqlCommand(queryString, connection);

command.ExecuteNonQuery();
}
```

## <a name="see-also"></a><span data-ttu-id="8bf92-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bf92-132">See also</span></span>

- [<span data-ttu-id="8bf92-133">Operaciones de copia masiva en SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bf92-133">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="8bf92-134">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8bf92-134">ADO.NET Overview</span></span>](../ado-net-overview.md)
