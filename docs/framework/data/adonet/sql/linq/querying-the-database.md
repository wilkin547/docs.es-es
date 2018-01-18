---
title: Consultar la base de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eefb8b0c-ff07-4e86-a3d3-567479523fe9
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4e7f2c2a3936fc27e963867a4a4bf4bc210c6b7e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="querying-the-database"></a><span data-ttu-id="dec19-102">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="dec19-102">Querying the Database</span></span>
<span data-ttu-id="dec19-103">Este grupo de temas describe cómo desarrollar y ejecutar consultas en proyectos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dec19-103">This group of topics describes how to develop and execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dec19-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dec19-104">In This Section</span></span>  
 [<span data-ttu-id="dec19-105">Consulta de información</span><span class="sxs-lookup"><span data-stu-id="dec19-105">How to: Query for Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-query-for-information.md)  
 <span data-ttu-id="dec19-106">Demuestra brevemente cómo las consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] son básicamente iguales que las consultas [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dec19-106">Briefly shows how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are basically the same as [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries generally.</span></span>  
  
 [<span data-ttu-id="dec19-107">Recuperación de información con formato de solo lectura</span><span class="sxs-lookup"><span data-stu-id="dec19-107">How to: Retrieve Information As Read-Only</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)  
 <span data-ttu-id="dec19-108">Describe cómo mejorar el rendimiento de las consultas cuando no está previsto ningún cambio en los datos.</span><span class="sxs-lookup"><span data-stu-id="dec19-108">Describes how to increase query performance when no change to the data is planned.</span></span>  
  
 [<span data-ttu-id="dec19-109">Control de la cantidad de datos relacionados que se recuperan</span><span class="sxs-lookup"><span data-stu-id="dec19-109">How to: Control How Much Related Data Is Retrieved</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-control-how-much-related-data-is-retrieved.md)  
 <span data-ttu-id="dec19-110">Describe cómo controlar qué datos relacionados se recuperan junto con el destino principal.</span><span class="sxs-lookup"><span data-stu-id="dec19-110">Describes how to control which related data is retrieved together with the main target.</span></span>  
  
 [<span data-ttu-id="dec19-111">Filtrado de datos relacionados</span><span class="sxs-lookup"><span data-stu-id="dec19-111">How to: Filter Related Data</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-filter-related-data.md)  
 <span data-ttu-id="dec19-112">Describe cómo recuperar datos relacionados mediante una subconsulta.</span><span class="sxs-lookup"><span data-stu-id="dec19-112">Describes how to retrieve related data by using a sub-query.</span></span>  
  
 [<span data-ttu-id="dec19-113">Desactivación de la carga diferida</span><span class="sxs-lookup"><span data-stu-id="dec19-113">How to: Turn Off Deferred Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-turn-off-deferred-loading.md)  
 <span data-ttu-id="dec19-114">Describe cómo desactivar la carga aplazada.</span><span class="sxs-lookup"><span data-stu-id="dec19-114">Describes how to turn off deferred loading.</span></span>  
  
 [<span data-ttu-id="dec19-115">Ejecución directa de consultas SQL</span><span class="sxs-lookup"><span data-stu-id="dec19-115">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 <span data-ttu-id="dec19-116">Describe cómo enviar consultas con lenguaje SQL.</span><span class="sxs-lookup"><span data-stu-id="dec19-116">Describes how to submit queries by using SQL language.</span></span>  
  
 [<span data-ttu-id="dec19-117">Almacenamiento y reutilización de consultas</span><span class="sxs-lookup"><span data-stu-id="dec19-117">How to: Store and Reuse Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md)  
 <span data-ttu-id="dec19-118">Describe cómo compilar una consulta una sola vez pero utilizarla varias veces con parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="dec19-118">Describes how to compile a query one time but use it multiple times with different parameters.</span></span>  
  
 [<span data-ttu-id="dec19-119">Control de claves compuestas en consultas</span><span class="sxs-lookup"><span data-stu-id="dec19-119">How to: Handle Composite Keys in Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-handle-composite-keys-in-queries.md)  
 <span data-ttu-id="dec19-120">Describe cómo incluir más de una columna en una consulta donde el operador utiliza un solo argumento.</span><span class="sxs-lookup"><span data-stu-id="dec19-120">Describes how to include more than one column in a query where the operator takes only a single argument.</span></span>  
  
 [<span data-ttu-id="dec19-121">Recuperación de muchos objetos a la vez</span><span class="sxs-lookup"><span data-stu-id="dec19-121">How to: Retrieve Many Objects At Once</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-many-objects-at-once.md)  
 <span data-ttu-id="dec19-122">Describe cómo usar <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="dec19-122">Describes how to use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="dec19-123">Filtrado en el nivel de DataContext</span><span class="sxs-lookup"><span data-stu-id="dec19-123">How to: Filter at the DataContext Level</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-filter-at-the-datacontext-level.md)  
 <span data-ttu-id="dec19-124">Describe otro uso de <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="dec19-124">Describes another use of <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="dec19-125">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="dec19-125">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="dec19-126">Proporciona numerosos ejemplos de consultas.</span><span class="sxs-lookup"><span data-stu-id="dec19-126">Provides many examples of queries.</span></span>
