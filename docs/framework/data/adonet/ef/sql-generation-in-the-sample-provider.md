---
title: Generación de SQL en el proveedor de ejemplo
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 7275a67927d7692dc943e2555d65d1f7d6e4ba5a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762158"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="17d4c-102">Generación de SQL en el proveedor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="17d4c-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="17d4c-103">El [proveedor de ejemplo de Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) muestra los nuevos componentes de proveedores de datos de ADO.NET que admiten la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17d4c-103">The [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="17d4c-104">Funciona con una base de datos SQL Server 2005 y se implementa como un contenedor del proveedor de datos ADO.NET 2.0 System.Data.SqlClient.</span><span class="sxs-lookup"><span data-stu-id="17d4c-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="17d4c-105">El módulo Generación de SQL del proveedor de ejemplo (ubicado en la carpeta Generación de SQL, salvo el archivo DmlSqlGenerator.cs) toma una entrada DbQueryCommandTree y genera una instrucción SQL SELECT única.</span><span class="sxs-lookup"><span data-stu-id="17d4c-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17d4c-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="17d4c-106">In This Section</span></span>  
 <span data-ttu-id="17d4c-107">Esta sección contiene los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="17d4c-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="17d4c-108">Arquitectura y diseño</span><span class="sxs-lookup"><span data-stu-id="17d4c-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="17d4c-109">Tutorial: generación de SQL</span><span class="sxs-lookup"><span data-stu-id="17d4c-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="17d4c-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="17d4c-110">See Also</span></span>  
 [<span data-ttu-id="17d4c-111">Generación de SQL</span><span class="sxs-lookup"><span data-stu-id="17d4c-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
