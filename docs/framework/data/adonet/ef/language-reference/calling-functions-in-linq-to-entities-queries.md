---
title: Llamar a funciones en consultas de LINQ to Entities
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b4989fcce44f6081dba52cd17d0349c87197d508
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="1fbc3-102">Llamar a funciones en consultas de LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="1fbc3-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="1fbc3-103">Los temas de esta sección describen cómo realizar llamadas a funciones en consultas de LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="1fbc3-104">Las clases <xref:System.Data.Objects.EntityFunctions> y <xref:System.Data.Objects.SqlClient.SqlFunctions> proporcionan acceso a funciones canónicas y de base de datos como parte de Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="1fbc3-105">Para obtener más información, consulte [Cómo: llamar a funciones canónicas](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) y [Cómo: llamar a funciones de base de datos](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1fbc3-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="1fbc3-106">El proceso para llamar a una función personalizada requiere tres pasos básicos:</span><span class="sxs-lookup"><span data-stu-id="1fbc3-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1.  <span data-ttu-id="1fbc3-107">Defina una función en su modelo conceptual o declare una función en su modelo de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2.  <span data-ttu-id="1fbc3-108">Agregue un método a su aplicación y asígnelo a la función del modelo con un <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3.  <span data-ttu-id="1fbc3-109">Llame a la función en una consulta LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="1fbc3-110">Para obtener más información, vea los temas de esta sección.</span><span class="sxs-lookup"><span data-stu-id="1fbc3-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1fbc3-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1fbc3-111">In This Section</span></span>  
 [<span data-ttu-id="1fbc3-112">Llamada a funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="1fbc3-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="1fbc3-113">Llamada a funciones de base de datos</span><span class="sxs-lookup"><span data-stu-id="1fbc3-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="1fbc3-114">Llamada a funciones de base de datos personalizadas</span><span class="sxs-lookup"><span data-stu-id="1fbc3-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="1fbc3-115">Llamada a funciones definidas por el modelo en consultas</span><span class="sxs-lookup"><span data-stu-id="1fbc3-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="1fbc3-116">Llamada a funciones definidas por el modelo como métodos de objeto</span><span class="sxs-lookup"><span data-stu-id="1fbc3-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="1fbc3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fbc3-117">See Also</span></span>  
 [<span data-ttu-id="1fbc3-118">Consultas en LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="1fbc3-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="1fbc3-119">Funciones canónicas</span><span class="sxs-lookup"><span data-stu-id="1fbc3-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [<span data-ttu-id="1fbc3-120">información general de archivo .edmx</span><span class="sxs-lookup"><span data-stu-id="1fbc3-120">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="1fbc3-121">Cómo: definir funciones personalizadas en el modelo Conceptual</span><span class="sxs-lookup"><span data-stu-id="1fbc3-121">How to: Define Custom Functions in the Conceptual Model</span></span>](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)
