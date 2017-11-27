---
title: "- (División) (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0f215e12f9f86ee08679bdb2e2638c0c8df35ea4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="d6104-102">/ (Dividir) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d6104-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="d6104-103">Divide un número entre otro.</span><span class="sxs-lookup"><span data-stu-id="d6104-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6104-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6104-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="d6104-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d6104-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="d6104-106">Expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="d6104-106">The numeric expression to divide.</span></span> <span data-ttu-id="d6104-107">`dividend` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="d6104-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="d6104-108">Expresión numérica entre la que se divide el dividendo.</span><span class="sxs-lookup"><span data-stu-id="d6104-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="d6104-109">`divisor` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="d6104-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="d6104-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="d6104-110">Result Types</span></span>  
 <span data-ttu-id="d6104-111">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="d6104-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="d6104-112">Para obtener más información acerca de la promoción de tipos implícita, vea [sistema de tipos](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d6104-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6104-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d6104-113">Example</span></span>  
 <span data-ttu-id="d6104-114">La siguiente consulta de Entity SQL usa el operador aritmético /  para dividir un número entre otro.</span><span class="sxs-lookup"><span data-stu-id="d6104-114">The following Entity SQL query uses the / arithmetic operator to divide one numer by another.</span></span> <span data-ttu-id="d6104-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="d6104-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d6104-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="d6104-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d6104-117">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d6104-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="d6104-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="d6104-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="d6104-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6104-119">See Also</span></span>  
 [<span data-ttu-id="d6104-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="d6104-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
