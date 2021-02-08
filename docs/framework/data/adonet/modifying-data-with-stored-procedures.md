---
description: Más información acerca de cómo modificar datos con procedimientos almacenados
title: Modificar datos con procedimientos almacenados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
ms.openlocfilehash: 66a4aa9577c71605bde0152a142a65dfa81a31d7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786230"
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="28be0-103">Modificar datos con procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="28be0-103">Modifying Data with Stored Procedures</span></span>

<span data-ttu-id="28be0-104">Los procedimientos almacenados pueden aceptar datos como parámetros de entrada y pueden devolver datos como parámetros de salida, conjuntos de resultados o valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="28be0-104">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="28be0-105">En el ejemplo siguiente se muestra cómo ADO.NET envía y recibe parámetros de entrada, parámetros de salida y valores de retorno.</span><span class="sxs-lookup"><span data-stu-id="28be0-105">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="28be0-106">El ejemplo inserta un nuevo registro en una tabla cuya columna de clave principal es una columna de identidad en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="28be0-106">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28be0-107">Si está utilizando procedimientos almacenados de SQL Server para editar o eliminar datos con <xref:System.Data.SqlClient.SqlDataAdapter>, asegúrese de que no utiliza SET NOCOUNT ON en la definición del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="28be0-107">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="28be0-108">Esto hace que el recuento de filas afectadas vuelva a cero, lo que `DataAdapter` interpreta como un conflicto de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="28be0-108">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="28be0-109">En este caso, se iniciará una <xref:System.Data.DBConcurrencyException>.</span><span class="sxs-lookup"><span data-stu-id="28be0-109">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28be0-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28be0-110">Example</span></span>  

 <span data-ttu-id="28be0-111">En el ejemplo se utiliza el siguiente procedimiento almacenado para insertar una nueva categoría en la tabla **Categories** de **Northwind**.</span><span class="sxs-lookup"><span data-stu-id="28be0-111">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="28be0-112">El procedimiento almacenado recibe el valor de la columna **CategoryName** como parámetro de entrada y usa la función SCOPE_IDENTITY() para recuperar el nuevo valor del campo de identidad, **CategoryID**, y devolverlo en un parámetro de salida.</span><span class="sxs-lookup"><span data-stu-id="28be0-112">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="28be0-113">La instrucción return utiliza la @ROWCOUNT función @ para devolver el número de filas insertadas.</span><span class="sxs-lookup"><span data-stu-id="28be0-113">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```sql
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="28be0-114">En el siguiente ejemplo de código se utiliza el anterior procedimiento almacenado `InsertCategory` como origen de la propiedad <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> de <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="28be0-114">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="28be0-115">El parámetro de salida `@Identity` se reflejará en <xref:System.Data.DataSet> una vez que se haya insertado el registro en la base de dados al llamar al método `Update` del <xref:System.Data.SqlClient.SqlDataAdapter>.</span><span class="sxs-lookup"><span data-stu-id="28be0-115">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="28be0-116">El código también recupera el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="28be0-116">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28be0-117">Al utilizar <xref:System.Data.OleDb.OleDbDataAdapter> , debe especificar los parámetros con un <xref:System.Data.ParameterDirection> de **ReturnValue** antes que los demás parámetros.</span><span class="sxs-lookup"><span data-stu-id="28be0-117">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="28be0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="28be0-118">See also</span></span>

- [<span data-ttu-id="28be0-119">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="28be0-119">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="28be0-120">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="28be0-120">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="28be0-121">Ejecutar un comando</span><span class="sxs-lookup"><span data-stu-id="28be0-121">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="28be0-122">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="28be0-122">ADO.NET Overview</span></span>](ado-net-overview.md)
