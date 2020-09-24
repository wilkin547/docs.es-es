---
title: Modificar datos con procedimientos almacenados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 65116a48533fd6ce86894c6a4522929285f8e1f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150757"
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="97fc9-102">Modificar datos con procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="97fc9-102">Modifying Data with Stored Procedures</span></span>

<span data-ttu-id="97fc9-103">Los procedimientos almacenados pueden aceptar datos como parámetros de entrada y pueden devolver datos como parámetros de salida, conjuntos de resultados o valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="97fc9-103">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="97fc9-104">En el ejemplo siguiente se muestra cómo ADO.NET envía y recibe parámetros de entrada, parámetros de salida y valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="97fc9-104">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="97fc9-105">El ejemplo inserta un nuevo registro en una tabla cuya columna de clave principal es una columna de identidad en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97fc9-105">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97fc9-106">Si está utilizando procedimientos almacenados de SQL Server para editar o eliminar datos con <xref:System.Data.SqlClient.SqlDataAdapter>, asegúrese de que no utiliza SET NOCOUNT ON en la definición del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="97fc9-106">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="97fc9-107">Esto hace que el recuento de filas afectadas vuelva a cero, lo que `DataAdapter` interpreta como un conflicto de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="97fc9-107">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="97fc9-108">En este caso, se iniciará una <xref:System.Data.DBConcurrencyException>.</span><span class="sxs-lookup"><span data-stu-id="97fc9-108">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97fc9-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97fc9-109">Example</span></span>  

 <span data-ttu-id="97fc9-110">En el ejemplo se usa el siguiente procedimiento almacenado para insertar una nueva categoría en la tabla **Categories** de **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="97fc9-110">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="97fc9-111">El procedimiento almacenado toma el valor de la columna **CategoryName** como parámetro de entrada y usa la función SCOPE_IDENTITY () para recuperar el nuevo valor del campo de identidad, **CategoryID**, y devolverlo en un parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="97fc9-111">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="97fc9-112">La instrucción return utiliza la @ROWCOUNT función @ para devolver el número de filas insertadas.</span><span class="sxs-lookup"><span data-stu-id="97fc9-112">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="97fc9-113">En el siguiente ejemplo de código se utiliza el anterior procedimiento almacenado `InsertCategory` como origen de la propiedad <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> de <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="97fc9-113">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="97fc9-114">El parámetro de salida `@Identity` se reflejará en <xref:System.Data.DataSet> una vez que se haya insertado el registro en la base de dados al llamar al método `Update` del <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="97fc9-114">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="97fc9-115">El código también recupera el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="97fc9-115">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="97fc9-116">Al utilizar <xref:System.Data.OleDb.OleDbDataAdapter> , debe especificar los parámetros con un <xref:System.Data.ParameterDirection> de **ReturnValue** antes que los demás parámetros.</span><span class="sxs-lookup"><span data-stu-id="97fc9-116">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="97fc9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="97fc9-117">See also</span></span>

- [<span data-ttu-id="97fc9-118">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97fc9-118">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="97fc9-119">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="97fc9-119">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="97fc9-120">Ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="97fc9-120">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="97fc9-121">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97fc9-121">ADO.NET Overview</span></span>](ado-net-overview.md)
