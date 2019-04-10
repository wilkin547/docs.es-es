---
title: Llamar a funciones en consultas de LINQ to Entities
ms.date: 03/30/2017
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
ms.openlocfilehash: 6fa1a7204a91a62c30e8683c449cc2be44132b4f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312090"
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="e2ebc-102">Llamar a funciones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e2ebc-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="e2ebc-103">Los temas de esta sección describen cómo realizar llamadas a funciones en consultas de LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="e2ebc-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="e2ebc-104">Las clases <xref:System.Data.Objects.EntityFunctions> y <xref:System.Data.Objects.SqlClient.SqlFunctions> proporcionan acceso a funciones canónicas y de base de datos como parte de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="e2ebc-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="e2ebc-105">Para obtener más información, vea [Cómo: Llamar a funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) y [Cómo: Llamar a funciones de base de datos](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="e2ebc-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="e2ebc-106">El proceso para llamar a una función personalizada requiere tres pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="e2ebc-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1. <span data-ttu-id="e2ebc-107">Defina una función en su modelo conceptual o declare una función en su modelo de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e2ebc-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2. <span data-ttu-id="e2ebc-108">Agregue un método a su aplicación y asígnelo a la función del modelo con un <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e2ebc-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3. <span data-ttu-id="e2ebc-109">Llame a la función en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="e2ebc-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="e2ebc-110">Para obtener más información, vea los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="e2ebc-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2ebc-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e2ebc-111">In This Section</span></span>  
 [<span data-ttu-id="e2ebc-112">Filtrar para llamar a funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="e2ebc-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="e2ebc-113">Filtrar para llamar a funciones de base de datos</span><span class="sxs-lookup"><span data-stu-id="e2ebc-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="e2ebc-114">Filtrar para llamar a funciones de base de datos personalizadas</span><span class="sxs-lookup"><span data-stu-id="e2ebc-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="e2ebc-115">Filtrar para llamar a funciones definidas por el modelo en consultas</span><span class="sxs-lookup"><span data-stu-id="e2ebc-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="e2ebc-116">Filtrar para llamar a funciones definidas por el modelo como métodos de objeto</span><span class="sxs-lookup"><span data-stu-id="e2ebc-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2ebc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2ebc-117">See also</span></span>

- [<span data-ttu-id="e2ebc-118">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="e2ebc-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
- [<span data-ttu-id="e2ebc-119">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="e2ebc-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
- [<span data-ttu-id="e2ebc-120">.edmx, Información general sobre el archivo</span><span class="sxs-lookup"><span data-stu-id="e2ebc-120">.edmx File Overview</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [<span data-ttu-id="e2ebc-121">Filtrar Definir funciones personalizadas en el modelo Conceptual</span><span class="sxs-lookup"><span data-stu-id="e2ebc-121">How to: Define Custom Functions in the Conceptual Model</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))
