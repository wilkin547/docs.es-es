---
title: Configuración de ejemplos de copia masiva
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: ac09ed85315aee7c6b29952916088ebe6e301eb9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794422"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="a0779-102">Configuración de ejemplos de copia masiva</span><span class="sxs-lookup"><span data-stu-id="a0779-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="a0779-103">La clase <xref:System.Data.SqlClient.SqlBulkCopy> sólo se puede utilizar para escribir datos en tablas SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a0779-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="a0779-104">Los ejemplos de código que se muestran en este tema usan el SQL Server base de datos de ejemplo, **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="a0779-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="a0779-105">Con el fin de evitar modificar las tablas existentes, los ejemplos de código escriben datos en tablas que primero deberá crear.</span><span class="sxs-lookup"><span data-stu-id="a0779-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="a0779-106">Las tablas **BulkCopyDemoMatchingColumns** y **BulkCopyDemoDifferentColumns** se basan en la tabla **AdventureWorks** **Production. Products** .</span><span class="sxs-lookup"><span data-stu-id="a0779-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="a0779-107">En los ejemplos de código que usan estas tablas, los datos se agregan desde la tabla **Production. Products** a una de estas tablas de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a0779-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="a0779-108">La tabla **BulkCopyDemoDifferentColumns** se usa cuando el ejemplo muestra cómo asignar columnas de los datos de origen a la tabla de destino. **BulkCopyDemoMatchingColumns** se usa para la mayoría de los demás ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a0779-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="a0779-109">En algunos de los ejemplos de código se muestra cómo utilizar una clase <xref:System.Data.SqlClient.SqlBulkCopy> para escribir en varias tablas.</span><span class="sxs-lookup"><span data-stu-id="a0779-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="a0779-110">En estos ejemplos, se usan las tablas **BulkCopyDemoOrderHeader** y **BulkCopyDemoOrderDetail** como tablas de destino.</span><span class="sxs-lookup"><span data-stu-id="a0779-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="a0779-111">Estas tablas se basan en las tablas **sales. SalesOrderHeader** y **sales. SalesOrderDetail** de **AdventureWorks**.</span><span class="sxs-lookup"><span data-stu-id="a0779-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0779-112">Los ejemplos de código **SqlBulkCopy** se proporcionan para mostrar la sintaxis para usar únicamente **SqlBulkCopy** .</span><span class="sxs-lookup"><span data-stu-id="a0779-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="a0779-113">Si las tablas de origen y de destino están incluidas en la misma instancia de SQL Server, lo más rápido y sencillo es usar una instrucción `INSERT … SELECT` de Transact-SQL para copiar los datos.</span><span class="sxs-lookup"><span data-stu-id="a0779-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="a0779-114">Configuración de las tablas</span><span class="sxs-lookup"><span data-stu-id="a0779-114">Table Setup</span></span>  
 <span data-ttu-id="a0779-115">Para crear las tablas necesarias para que los ejemplos de código de funcionen correctamente, debe ejecutar las siguientes instrucciones Transact-SQL en una base de datos SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a0779-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
```  
USE AdventureWorks  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoMatchingColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoMatchingColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoMatchingColumns]([ProductID] [int] IDENTITY(1,1) NOT NULL,  
    [Name] [nvarchar](50) NOT NULL,  
    [ProductNumber] [nvarchar](25) NOT NULL,  
 CONSTRAINT [PK_ProductID] PRIMARY KEY CLUSTERED  
(  
    [ProductID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoDifferentColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoDifferentColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoDifferentColumns]([ProdID] [int] IDENTITY(1,1) NOT NULL,  
    [ProdNum] [nvarchar](25) NOT NULL,  
    [ProdName] [nvarchar](50) NOT NULL,  
 CONSTRAINT [PK_ProdID] PRIMARY KEY CLUSTERED  
(  
    [ProdID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderHeader]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderHeader]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderHeader]([SalesOrderID] [int] IDENTITY(1,1) NOT NULL,  
    [OrderDate] [datetime] NOT NULL,  
    [AccountNumber] [nvarchar](15) NULL,  
 CONSTRAINT [PK_SalesOrderID] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderDetail]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderDetail]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderDetail]([SalesOrderID] [int] NOT NULL,  
    [SalesOrderDetailID] [int] NOT NULL,  
    [OrderQty] [smallint] NOT NULL,  
    [ProductID] [int] NOT NULL,  
    [UnitPrice] [money] NOT NULL,  
 CONSTRAINT [PK_LineNumber] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC,  
    [SalesOrderDetailID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0779-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0779-116">See also</span></span>

- [<span data-ttu-id="a0779-117">Operaciones de copia masiva en SQL Server</span><span class="sxs-lookup"><span data-stu-id="a0779-117">Bulk Copy Operations in SQL Server</span></span>](bulk-copy-operations-in-sql-server.md)
- [<span data-ttu-id="a0779-118">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a0779-118">ADO.NET Overview</span></span>](../ado-net-overview.md)
