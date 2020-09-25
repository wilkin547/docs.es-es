---
title: Operaciones de copia masiva en SQL Server
description: Aprenda a usar la clase SqlBulkCopy para escribir soluciones de código administrado que copien de forma masiva archivos grandes en tablas o vistas en bases de datos de SQL Server.
ms.date: 03/30/2017
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
ms.openlocfilehash: 43d63f3671ea8ff05da3e10580c2784fa3aae581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197436"
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="a9932-103">Operaciones de copia masiva en SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9932-103">Bulk Copy Operations in SQL Server</span></span>

<span data-ttu-id="a9932-104">Microsoft SQL Server incluye una conocida utilidad de línea de comandos denominada **bcp** para copiar rápidamente y de forma masiva archivos grandes en tablas o vistas en bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a9932-104">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="a9932-105">La clase <xref:System.Data.SqlClient.SqlBulkCopy> permite escribir soluciones de código administrado que proporcionan una funcionalidad similar.</span><span class="sxs-lookup"><span data-stu-id="a9932-105">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="a9932-106">Hay otras maneras de cargar datos en una tabla de SQL Server (las instrucciones INSERT, por ejemplo) pero <xref:System.Data.SqlClient.SqlBulkCopy> ofrece una importante ventaja de rendimiento sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="a9932-106">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="a9932-107">La clase <xref:System.Data.SqlClient.SqlBulkCopy> puede usarse para escribir datos solo en tablas de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a9932-107">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="a9932-108">Sin embargo, el origen de datos no está limitado a SQL Server; se puede utilizar cualquier origen de datos siempre y cuando pueda cargarse en una instancia <xref:System.Data.DataTable> o leerse con una instancia <xref:System.Data.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="a9932-108">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="a9932-109">Con la clase <xref:System.Data.SqlClient.SqlBulkCopy>, puede ejecutar:</span><span class="sxs-lookup"><span data-stu-id="a9932-109">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
- <span data-ttu-id="a9932-110">Una única operación de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="a9932-110">A single bulk copy operation</span></span>  
  
- <span data-ttu-id="a9932-111">Varias operaciones de copia masiva.</span><span class="sxs-lookup"><span data-stu-id="a9932-111">Multiple bulk copy operations</span></span>  
  
- <span data-ttu-id="a9932-112">Una operación de copia masiva en una transacción</span><span class="sxs-lookup"><span data-stu-id="a9932-112">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9932-113">Si usa .NET Framework versión 1.1 o anterior (que no admite la clase <xref:System.Data.SqlClient.SqlBulkCopy>), puede ejecutar la instrucción **BULK INSERT** de Transact-SQL de SQL Server mediante el objeto <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="a9932-113">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9932-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a9932-114">In This Section</span></span>  

 [<span data-ttu-id="a9932-115">Configuración de ejemplo de copia masiva</span><span class="sxs-lookup"><span data-stu-id="a9932-115">Bulk Copy Example Setup</span></span>](bulk-copy-example-setup.md)  
 <span data-ttu-id="a9932-116">Describe las tablas usadas en los ejemplos de copia masiva y proporciona scripts SQL para crear las tablas en la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a9932-116">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="a9932-117">Operaciones de copia masiva únicas</span><span class="sxs-lookup"><span data-stu-id="a9932-117">Single Bulk Copy Operations</span></span>](single-bulk-copy-operations.md)  
 <span data-ttu-id="a9932-118">Describe cómo realizar una única copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy> y cómo realizar la operación de copia masiva mediante instrucciones Transact-SQL y la clase <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="a9932-118">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="a9932-119">Varias operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="a9932-119">Multiple Bulk Copy Operations</span></span>](multiple-bulk-copy-operations.md)  
 <span data-ttu-id="a9932-120">Describe cómo realizar varias operaciones de copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="a9932-120">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="a9932-121">Transacciones y operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="a9932-121">Transaction and Bulk Copy Operations</span></span>](transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="a9932-122">Describe cómo realizar una operación de copia masiva en una transacción, incluida la forma de confirmar o revertir la transacción.</span><span class="sxs-lookup"><span data-stu-id="a9932-122">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9932-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9932-123">See also</span></span>

- [<span data-ttu-id="a9932-124">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a9932-124">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="a9932-125">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a9932-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
