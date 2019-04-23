---
title: Generación de SQL en el proveedor de ejemplo
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 88223930b65ccec9d030104c62d8b4b2e77ddbe2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079427"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="0ca7d-102">Generación de SQL en el proveedor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ca7d-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="0ca7d-103">El [proveedor de ejemplo de Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) muestra los nuevos componentes de proveedores de datos de ADO.NET que admiten la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ca7d-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="0ca7d-104">Funciona con una base de datos SQL Server 2005 y se implementa como un contenedor del proveedor de datos ADO.NET 2.0 System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="0ca7d-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="0ca7d-105">El módulo Generación de SQL del proveedor de ejemplo (ubicado en la carpeta Generación de SQL, salvo el archivo DmlSqlGenerator.cs) toma una entrada DbQueryCommandTree y genera una instrucción SQL SELECT única.</span><span class="sxs-lookup"><span data-stu-id="0ca7d-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ca7d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="0ca7d-106">In This Section</span></span>  
 <span data-ttu-id="0ca7d-107">Esta sección contiene los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="0ca7d-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="0ca7d-108">Arquitectura y diseño</span><span class="sxs-lookup"><span data-stu-id="0ca7d-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="0ca7d-109">Tutorial: Generación de SQL</span><span class="sxs-lookup"><span data-stu-id="0ca7d-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="0ca7d-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ca7d-110">See also</span></span>

- [<span data-ttu-id="0ca7d-111">Generación de SQL</span><span class="sxs-lookup"><span data-stu-id="0ca7d-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
