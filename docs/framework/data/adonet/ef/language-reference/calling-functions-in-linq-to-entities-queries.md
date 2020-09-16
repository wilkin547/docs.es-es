---
title: Llamar a funciones en consultas de LINQ to Entities
description: Use estos artículos para ver cómo las clases EntityFunctions y SqlFunctions proporcionan acceso a las funciones canónicas y de base de datos como parte de la Entity Framework.
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: eb206e9b331da1ae442c1f310e78fec5c6b57e82
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546053"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="76585-103">Llamar a funciones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="76585-103">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="76585-104">Los temas de esta sección describen cómo realizar llamadas a funciones en consultas de LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="76585-104">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="76585-105">Las clases <xref:System.Data.Objects.EntityFunctions> y <xref:System.Data.Objects.SqlClient.SqlFunctions> proporcionan acceso a funciones canónicas y de base de datos como parte de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="76585-105">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="76585-106">Para obtener más información, vea [Cómo: llamar a funciones canónicas](how-to-call-canonical-functions.md) y [Cómo: llamar a funciones de base de datos](how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="76585-106">For more information, see [How to: Call Canonical Functions](how-to-call-canonical-functions.md) and [How to: Call Database Functions](how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="76585-107">El proceso para llamar a una función personalizada requiere tres pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="76585-107">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="76585-108">Defina una función en su modelo conceptual o declare una función en su modelo de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="76585-108">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="76585-109">Agregue un método a su aplicación y asígnelo a la función del modelo con un <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="76585-109">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="76585-110">Llame a la función en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="76585-110">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="76585-111">Para obtener más información, vea los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="76585-111">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76585-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="76585-112">In This Section</span></span>  
 [<span data-ttu-id="76585-113">Procedimiento para llamar a funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="76585-113">How to: Call Canonical Functions</span></span>](how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="76585-114">Procedimiento para llamar a funciones de base de datos</span><span class="sxs-lookup"><span data-stu-id="76585-114">How to: Call Database Functions</span></span>](how-to-call-database-functions.md)  
  
 [<span data-ttu-id="76585-115">Procedimiento para llamar a funciones de base de datos personalizadas</span><span class="sxs-lookup"><span data-stu-id="76585-115">How to: Call Custom Database Functions</span></span>](how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="76585-116">Procedimiento para llamar a funciones definidas por el modelo en consultas</span><span class="sxs-lookup"><span data-stu-id="76585-116">How to: Call Model-Defined Functions in Queries</span></span>](how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="76585-117">Procedimiento para llamar a funciones definidas por el modelo como métodos de objeto</span><span class="sxs-lookup"><span data-stu-id="76585-117">How to: Call Model-Defined Functions as Object Methods</span></span>](how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="76585-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="76585-118">See also</span></span>

- [<span data-ttu-id="76585-119">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="76585-119">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
- [<span data-ttu-id="76585-120">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="76585-120">Canonical Functions</span></span>](canonical-functions.md)
- <span data-ttu-id="76585-121">[.edmx, Información general sobre el archivo](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="76585-121">[.edmx File Overview](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- <span data-ttu-id="76585-122">[Cómo: Definir funciones personalizadas en el modelo conceptual](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="76585-122">[How to: Define Custom Functions in the Conceptual Model](/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))</span></span>
