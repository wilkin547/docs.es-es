---
title: "(Módulo) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: cff0e4eaadf601b7a90f3caa0ecd9cf2f48feab0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="modulo-entity-sql"></a><span data-ttu-id="68fb9-102">(Módulo) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="68fb9-102">(Modulo) (Entity SQL)</span></span>
<span data-ttu-id="68fb9-103">Devuelve el resto de una expresión dividida entre otra.</span><span class="sxs-lookup"><span data-stu-id="68fb9-103">Returns the remainder of one expression divided by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68fb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68fb9-104">Syntax</span></span>  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="68fb9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68fb9-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="68fb9-106">Expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="68fb9-106">The numeric expression to divide.</span></span> <span data-ttu-id="68fb9-107">`dividend` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="68fb9-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="68fb9-108">Expresión numérica entre la que se divide el dividendo.</span><span class="sxs-lookup"><span data-stu-id="68fb9-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="68fb9-109">`divisor` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="68fb9-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="68fb9-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="68fb9-110">Result Types</span></span>  
 <span data-ttu-id="68fb9-111">Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="68fb9-111">Edm.Int32</span></span>  
  
## <a name="example"></a><span data-ttu-id="68fb9-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68fb9-112">Example</span></span>  
 <span data-ttu-id="68fb9-113">La siguiente consulta de Entity SQL usa el operador aritmético % para devolver el resto de una expresión dividida entre otra.</span><span class="sxs-lookup"><span data-stu-id="68fb9-113">The following Entity SQL query uses the % arithmetic operator to return the remainder of one expression divided by another.</span></span> <span data-ttu-id="68fb9-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="68fb9-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="68fb9-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="68fb9-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="68fb9-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="68fb9-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="68fb9-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="68fb9-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a><span data-ttu-id="68fb9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="68fb9-118">See Also</span></span>  
 [<span data-ttu-id="68fb9-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="68fb9-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
