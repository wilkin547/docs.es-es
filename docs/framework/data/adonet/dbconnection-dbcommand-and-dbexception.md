---
description: 'Más información acerca de: DbConnection, DbCommand y DbException'
title: DbConnection, DbCommand y DbException
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 58aab611-7e6f-4749-b983-28ab7ae87dbe
ms.openlocfilehash: b5cb748a8dd5fb06f2f5dc5ab0479a679b2cc07d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651280"
---
# <a name="dbconnection-dbcommand-and-dbexception"></a><span data-ttu-id="dff16-103">DbConnection, DbCommand y DbException</span><span class="sxs-lookup"><span data-stu-id="dff16-103">DbConnection, DbCommand and DbException</span></span>

<span data-ttu-id="dff16-104">Después de crear un objeto <xref:System.Data.Common.DbProviderFactory> y un objeto <xref:System.Data.Common.DbConnection>, puede trabajar con comandos y lectores de datos para recuperar datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="dff16-104">Once you have created a <xref:System.Data.Common.DbProviderFactory> and a <xref:System.Data.Common.DbConnection>, you can then work with commands and data readers to retrieve data from the data source.</span></span>  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="dff16-105">Ejemplo de recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="dff16-105">Retrieving Data Example</span></span>  

 <span data-ttu-id="dff16-106">En este ejemplo se utiliza un objeto `DbConnection` como argumento.</span><span class="sxs-lookup"><span data-stu-id="dff16-106">This example takes a `DbConnection` object as an argument.</span></span> <span data-ttu-id="dff16-107">Se crea un objeto <xref:System.Data.Common.DbCommand> para seleccionar datos de la tabla Categories mediante el establecimiento de <xref:System.Data.Common.DbCommand.CommandText%2A> en una instrucción SELECT de SQL.</span><span class="sxs-lookup"><span data-stu-id="dff16-107">A <xref:System.Data.Common.DbCommand> is created to select data from the Categories table by setting the <xref:System.Data.Common.DbCommand.CommandText%2A> to a SQL SELECT statement.</span></span> <span data-ttu-id="dff16-108">El código asume que la tabla Categories existe en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="dff16-108">The code assumes that the Categories table exists at the data source.</span></span> <span data-ttu-id="dff16-109">Se abre la conexión y los datos se recuperan mediante <xref:System.Data.Common.DbDataReader>.</span><span class="sxs-lookup"><span data-stu-id="dff16-109">The connection is opened and the data is retrieved using a <xref:System.Data.Common.DbDataReader>.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommandData#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommandData/VB/source.vb#1)]  
  
## <a name="executing-a-command-example"></a><span data-ttu-id="dff16-110">Ejemplo de ejecución de un comando</span><span class="sxs-lookup"><span data-stu-id="dff16-110">Executing a Command Example</span></span>  

 <span data-ttu-id="dff16-111">En este ejemplo se utiliza un objeto `DbConnection` como argumento.</span><span class="sxs-lookup"><span data-stu-id="dff16-111">This example takes a `DbConnection` object as an argument.</span></span> <span data-ttu-id="dff16-112">Si el objeto `DbConnection` es válido, se abre la conexión y, a continuación, se crea y se ejecuta un objeto <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="dff16-112">If the `DbConnection` is valid, the connection is opened and a <xref:System.Data.Common.DbCommand> is created and executed.</span></span> <span data-ttu-id="dff16-113"><xref:System.Data.Common.DbCommand.CommandText%2A> se establece en una instrucción INSERT de SQL que realiza una inserción en la tabla Categories de la base de datos Northwind.</span><span class="sxs-lookup"><span data-stu-id="dff16-113">The <xref:System.Data.Common.DbCommand.CommandText%2A> is set to a SQL INSERT statement that performs an insert to the Categories table in the Northwind database.</span></span> <span data-ttu-id="dff16-114">El código a sume que la base de datos Northwind existe en el origen de datos y que la sintaxis de SQL usada en la instrucción INSERT es válida en el proveedor especificado.</span><span class="sxs-lookup"><span data-stu-id="dff16-114">The code assumes that the Northwind database exists at the data source, and that the SQL syntax used in the INSERT statement is valid for the specified provider.</span></span> <span data-ttu-id="dff16-115">El bloque de código <xref:System.Data.Common.DbException> controla los errores que se producen en el origen de datos y el bloque <xref:System.Exception> controla todas las demás excepciones.</span><span class="sxs-lookup"><span data-stu-id="dff16-115">Errors occurring at the data source are handled by the <xref:System.Data.Common.DbException> code block, and all other exceptions are handled in the <xref:System.Exception> block.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbCommand#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbCommand/VB/source.vb#1)]  
  
## <a name="handling-data-errors-with-dbexception"></a><span data-ttu-id="dff16-116">Controlar errores de datos con DbException</span><span class="sxs-lookup"><span data-stu-id="dff16-116">Handling Data Errors with DbException</span></span>  

 <span data-ttu-id="dff16-117">La clase <xref:System.Data.Common.DbException> es la clase base para todas las excepciones que se producen por cuenta del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="dff16-117">The <xref:System.Data.Common.DbException> class is the base class for all exceptions thrown on behalf of a data source.</span></span> <span data-ttu-id="dff16-118">Puede usarla en el código de control de excepciones para controlar las excepciones que inician diferentes proveedores sin necesidad de hacer referencia a una clase de excepción específica.</span><span class="sxs-lookup"><span data-stu-id="dff16-118">You can use it in your exception handling code to handle exceptions thrown by different providers without having to reference a specific exception class.</span></span> <span data-ttu-id="dff16-119">En el fragmento de código siguiente se muestra cómo utilizar <xref:System.Data.Common.DbException>para mostrar la información de error que devuelve el origen de datos mediante las propiedades <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A> y <xref:System.Exception.Message%2A>.</span><span class="sxs-lookup"><span data-stu-id="dff16-119">The following code fragment demonstrates how to use <xref:System.Data.Common.DbException> to display error information returned by the data source using <xref:System.Exception.GetType%2A>, <xref:System.Exception.Source%2A>, <xref:System.Runtime.InteropServices.ExternalException.ErrorCode%2A>, and <xref:System.Exception.Message%2A> properties.</span></span> <span data-ttu-id="dff16-120">El resultado mostrará el tipo de error, el origen que indica el nombre de proveedor, un código de error y el mensaje asociado al error.</span><span class="sxs-lookup"><span data-stu-id="dff16-120">The output will display the type of error, the source indicating the provider name, an error code, and the message associated with the error.</span></span>  
  
```vb  
Try  
    ' Do work here.  
Catch ex As DbException  
    ' Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType())  
    Console.WriteLine("Source: {0}", ex.Source)  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode)  
    Console.WriteLine("Message: {0}", ex.Message)  
Finally  
    ' Perform cleanup here.  
End Try  
```  
  
```csharp  
try  
{  
    // Do work here.  
}  
catch (DbException ex)  
{  
    // Display information about the exception.  
    Console.WriteLine("GetType: {0}", ex.GetType());  
    Console.WriteLine("Source: {0}", ex.Source);  
    Console.WriteLine("ErrorCode: {0}", ex.ErrorCode);  
    Console.WriteLine("Message: {0}", ex.Message);  
}  
finally  
{  
    // Perform cleanup here.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="dff16-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dff16-121">See also</span></span>

- [<span data-ttu-id="dff16-122">Objetos DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="dff16-122">DbProviderFactories</span></span>](dbproviderfactories.md)
- [<span data-ttu-id="dff16-123">Obtener un objeto DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="dff16-123">Obtaining a DbProviderFactory</span></span>](obtaining-a-dbproviderfactory.md)
- [<span data-ttu-id="dff16-124">Modificar datos con un objeto DbDataAdapter</span><span class="sxs-lookup"><span data-stu-id="dff16-124">Modifying Data with a DbDataAdapter</span></span>](modifying-data-with-a-dbdataadapter.md)
- [<span data-ttu-id="dff16-125">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="dff16-125">ADO.NET Overview</span></span>](ado-net-overview.md)
