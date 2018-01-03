---
title: Operaciones de copia masiva en SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83a7a0d2-8018-4354-97b9-0b1d99f8342b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: fadb149e92b65988b8f9f322752bc63e1ee65f19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="bulk-copy-operations-in-sql-server"></a><span data-ttu-id="0df14-102">Operaciones de copia masiva en SQL Server</span><span class="sxs-lookup"><span data-stu-id="0df14-102">Bulk Copy Operations in SQL Server</span></span>
<span data-ttu-id="0df14-103">Microsoft SQL Server incluye una conocida utilidad de línea de comandos denominada **bcp** para rápidamente copie de forma masiva archivos grandes en tablas o vistas de bases de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0df14-103">Microsoft SQL Server includes a popular command-line utility named **bcp** for quickly bulk copying large files into tables or views in SQL Server databases.</span></span> <span data-ttu-id="0df14-104">La clase <xref:System.Data.SqlClient.SqlBulkCopy> permite escribir soluciones de código administrado que ofrecen una funcionalidad similar.</span><span class="sxs-lookup"><span data-stu-id="0df14-104">The <xref:System.Data.SqlClient.SqlBulkCopy> class allows you to write managed code solutions that provide similar functionality.</span></span> <span data-ttu-id="0df14-105">Aunque existen otras formas de cargar datos en una tabla SQL Server (por ejemplo, mediante instrucciones INSERT), <xref:System.Data.SqlClient.SqlBulkCopy> tiene la ventaja sobre las demás de un rendimiento significativo.</span><span class="sxs-lookup"><span data-stu-id="0df14-105">There are other ways to load data into a SQL Server table (INSERT statements, for example) but <xref:System.Data.SqlClient.SqlBulkCopy> offers a significant performance advantage over them.</span></span>  
  
 <span data-ttu-id="0df14-106">La clase <xref:System.Data.SqlClient.SqlBulkCopy> sólo se puede utilizar para escribir datos en tablas SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0df14-106">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="0df14-107">Sin embargo, el origen de datos no está limitado a SQL Server; se puede utilizar cualquier origen de datos siempre y cuando pueda cargarse en una instancia <xref:System.Data.DataTable> o leerse con una instancia <xref:System.Data.IDataReader>.</span><span class="sxs-lookup"><span data-stu-id="0df14-107">But the data source is not limited to SQL Server; any data source can be used, as long as the data can be loaded to a <xref:System.Data.DataTable> instance or read with a <xref:System.Data.IDataReader> instance.</span></span>  
  
 <span data-ttu-id="0df14-108">El uso de la clase <xref:System.Data.SqlClient.SqlBulkCopy> le permite realizar:</span><span class="sxs-lookup"><span data-stu-id="0df14-108">Using the <xref:System.Data.SqlClient.SqlBulkCopy> class, you can perform:</span></span>  
  
-   <span data-ttu-id="0df14-109">una única operación de copia masiva</span><span class="sxs-lookup"><span data-stu-id="0df14-109">A single bulk copy operation</span></span>  
  
-   <span data-ttu-id="0df14-110">varias operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="0df14-110">Multiple bulk copy operations</span></span>  
  
-   <span data-ttu-id="0df14-111">una operación de copia masiva en una transacción</span><span class="sxs-lookup"><span data-stu-id="0df14-111">A bulk copy operation within a transaction</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0df14-112">Cuando se usa .NET Framework versión 1.1 o anterior (que no admite la <xref:System.Data.SqlClient.SqlBulkCopy> clase), puede ejecutar SQL Server Transact-SQL **BULK INSERT** instrucción que usa el <xref:System.Data.SqlClient.SqlCommand> objeto.</span><span class="sxs-lookup"><span data-stu-id="0df14-112">When using .NET Framework version 1.1 or earlier (which does not support the <xref:System.Data.SqlClient.SqlBulkCopy> class), you can execute the SQL Server Transact-SQL **BULK INSERT** statement using the <xref:System.Data.SqlClient.SqlCommand> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0df14-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0df14-113">In This Section</span></span>  
 [<span data-ttu-id="0df14-114">Configuración de ejemplos de copia masiva</span><span class="sxs-lookup"><span data-stu-id="0df14-114">Bulk Copy Example Setup</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)  
 <span data-ttu-id="0df14-115">Describe las tablas usadas en los ejemplos de copia masiva y proporciona scripts SQL para crear las tablas de la base de datos AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="0df14-115">Describes the tables used in the bulk copy examples and provides SQL scripts for creating the tables in the AdventureWorks database.</span></span>  
  
 [<span data-ttu-id="0df14-116">Operaciones de copia masiva únicas</span><span class="sxs-lookup"><span data-stu-id="0df14-116">Single Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/single-bulk-copy-operations.md)  
 <span data-ttu-id="0df14-117">Describe cómo realizar una sola copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>, y cómo realizar la operación de copia masiva con las instrucciones Transact-SQL y la clase <xref:System.Data.SqlClient.SqlCommand>.</span><span class="sxs-lookup"><span data-stu-id="0df14-117">Describes how to do a single bulk copy of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class, and how to perform the bulk copy operation using Transact-SQL statements and the <xref:System.Data.SqlClient.SqlCommand> class.</span></span>  
  
 [<span data-ttu-id="0df14-118">Varias operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="0df14-118">Multiple Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-bulk-copy-operations.md)  
 <span data-ttu-id="0df14-119">Describe cómo realizar varias operaciones de copia masiva de datos en una instancia de SQL Server mediante la clase <xref:System.Data.SqlClient.SqlBulkCopy>.</span><span class="sxs-lookup"><span data-stu-id="0df14-119">Describes how to do multiple bulk copy operations of data into an instance of SQL Server using the <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span>  
  
 [<span data-ttu-id="0df14-120">Transacción y operaciones de copia masiva</span><span class="sxs-lookup"><span data-stu-id="0df14-120">Transaction and Bulk Copy Operations</span></span>](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md)  
 <span data-ttu-id="0df14-121">Describe cómo realizar una operación de copia masiva en una transacción, lo que incluye cómo confirmar o revertir la transacción.</span><span class="sxs-lookup"><span data-stu-id="0df14-121">Describes how to perform a bulk copy operation within a transaction, including how to commit or rollback the transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0df14-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="0df14-122">See Also</span></span>  
 [<span data-ttu-id="0df14-123">SQL Server y ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0df14-123">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="0df14-124">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="0df14-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
