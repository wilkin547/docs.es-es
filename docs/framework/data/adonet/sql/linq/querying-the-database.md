---
description: Más información acerca de cómo consultar la base de datos
title: Consultar la base de datos
ms.date: 03/30/2017
ms.assetid: eefb8b0c-ff07-4e86-a3d3-567479523fe9
ms.openlocfilehash: 19eac5d42af644e3ba0eb5a7bfd82fc7f0e3f1fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695240"
---
# <a name="querying-the-database"></a><span data-ttu-id="d30a4-103">Consultar la base de datos</span><span class="sxs-lookup"><span data-stu-id="d30a4-103">Querying the Database</span></span>

<span data-ttu-id="d30a4-104">Este grupo de temas describe cómo desarrollar y ejecutar consultas en proyectos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d30a4-104">This group of topics describes how to develop and execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d30a4-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d30a4-105">In This Section</span></span>  

 [<span data-ttu-id="d30a4-106">Procedimiento para consultar información</span><span class="sxs-lookup"><span data-stu-id="d30a4-106">How to: Query for Information</span></span>](how-to-query-for-information.md)  
 <span data-ttu-id="d30a4-107">Muestra brevemente cómo las [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] consultas son básicamente las mismas que las consultas LINQ en general.</span><span class="sxs-lookup"><span data-stu-id="d30a4-107">Briefly shows how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are basically the same as LINQ queries generally.</span></span>  
  
 [<span data-ttu-id="d30a4-108">Procedimiento para recuperar información con formato de solo lectura</span><span class="sxs-lookup"><span data-stu-id="d30a4-108">How to: Retrieve Information As Read-Only</span></span>](how-to-retrieve-information-as-read-only.md)  
 <span data-ttu-id="d30a4-109">Describe cómo mejorar el rendimiento de las consultas cuando no está previsto ningún cambio en los datos.</span><span class="sxs-lookup"><span data-stu-id="d30a4-109">Describes how to increase query performance when no change to the data is planned.</span></span>  
  
 [<span data-ttu-id="d30a4-110">Procedimiento para controlar la cantidad de datos relacionados que se recupera</span><span class="sxs-lookup"><span data-stu-id="d30a4-110">How to: Control How Much Related Data Is Retrieved</span></span>](how-to-control-how-much-related-data-is-retrieved.md)  
 <span data-ttu-id="d30a4-111">Describe cómo controlar qué datos relacionados se recuperan junto con el destino principal.</span><span class="sxs-lookup"><span data-stu-id="d30a4-111">Describes how to control which related data is retrieved together with the main target.</span></span>  
  
 [<span data-ttu-id="d30a4-112">Procedimiento para filtrar datos relacionados</span><span class="sxs-lookup"><span data-stu-id="d30a4-112">How to: Filter Related Data</span></span>](how-to-filter-related-data.md)  
 <span data-ttu-id="d30a4-113">Describe cómo recuperar datos relacionados mediante una subconsulta.</span><span class="sxs-lookup"><span data-stu-id="d30a4-113">Describes how to retrieve related data by using a sub-query.</span></span>  
  
 [<span data-ttu-id="d30a4-114">Procedimiento para desactivar la carga diferida</span><span class="sxs-lookup"><span data-stu-id="d30a4-114">How to: Turn Off Deferred Loading</span></span>](how-to-turn-off-deferred-loading.md)  
 <span data-ttu-id="d30a4-115">Describe cómo desactivar la carga aplazada.</span><span class="sxs-lookup"><span data-stu-id="d30a4-115">Describes how to turn off deferred loading.</span></span>  
  
 [<span data-ttu-id="d30a4-116">Procedimiento para ejecutar directamente consultas SQL</span><span class="sxs-lookup"><span data-stu-id="d30a4-116">How to: Directly Execute SQL Queries</span></span>](how-to-directly-execute-sql-queries.md)  
 <span data-ttu-id="d30a4-117">Describe cómo enviar consultas con lenguaje SQL.</span><span class="sxs-lookup"><span data-stu-id="d30a4-117">Describes how to submit queries by using SQL language.</span></span>  
  
 [<span data-ttu-id="d30a4-118">Procedimiento para almacenar y reutilizar consultas</span><span class="sxs-lookup"><span data-stu-id="d30a4-118">How to: Store and Reuse Queries</span></span>](how-to-store-and-reuse-queries.md)  
 <span data-ttu-id="d30a4-119">Describe cómo compilar una consulta una sola vez pero utilizarla varias veces con parámetros diferentes.</span><span class="sxs-lookup"><span data-stu-id="d30a4-119">Describes how to compile a query one time but use it multiple times with different parameters.</span></span>  
  
 [<span data-ttu-id="d30a4-120">Procedimiento para administrar claves compuestas en consultas</span><span class="sxs-lookup"><span data-stu-id="d30a4-120">How to: Handle Composite Keys in Queries</span></span>](how-to-handle-composite-keys-in-queries.md)  
 <span data-ttu-id="d30a4-121">Describe cómo incluir más de una columna en una consulta donde el operador utiliza un solo argumento.</span><span class="sxs-lookup"><span data-stu-id="d30a4-121">Describes how to include more than one column in a query where the operator takes only a single argument.</span></span>  
  
 [<span data-ttu-id="d30a4-122">Procedimiento para recuperar muchos objetos a la vez</span><span class="sxs-lookup"><span data-stu-id="d30a4-122">How to: Retrieve Many Objects At Once</span></span>](how-to-retrieve-many-objects-at-once.md)  
 <span data-ttu-id="d30a4-123">Describe cómo usar <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="d30a4-123">Describes how to use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="d30a4-124">Procedimiento para filtrar en el nivel de DataContext</span><span class="sxs-lookup"><span data-stu-id="d30a4-124">How to: Filter at the DataContext Level</span></span>](how-to-filter-at-the-datacontext-level.md)  
 <span data-ttu-id="d30a4-125">Describe otro uso de <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span><span class="sxs-lookup"><span data-stu-id="d30a4-125">Describes another use of <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.</span></span>  
  
 [<span data-ttu-id="d30a4-126">Ejemplos de consultas</span><span class="sxs-lookup"><span data-stu-id="d30a4-126">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="d30a4-127">Proporciona numerosos ejemplos de consultas.</span><span class="sxs-lookup"><span data-stu-id="d30a4-127">Provides many examples of queries.</span></span>
