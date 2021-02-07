---
description: 'Más información acerca de: + (agregar)'
title: + (agregar)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: b8ec9f50b349fe971513f399b7e9984e9044cf58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697314"
---
# <a name="-add"></a><span data-ttu-id="e8d04-103">+ (Sumar)</span><span class="sxs-lookup"><span data-stu-id="e8d04-103">+ (Add)</span></span>

<span data-ttu-id="e8d04-104">Suma dos números.</span><span class="sxs-lookup"><span data-stu-id="e8d04-104">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d04-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8d04-105">Syntax</span></span>  
  
```csharp  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="e8d04-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e8d04-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="e8d04-107">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="e8d04-107">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="e8d04-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="e8d04-108">Result Types</span></span>  

 <span data-ttu-id="e8d04-109">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="e8d04-109">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="e8d04-110">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="e8d04-110">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8d04-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e8d04-111">Remarks</span></span>  

 <span data-ttu-id="e8d04-112">Para los tipos EDM.String, la suma es una concatenación.</span><span class="sxs-lookup"><span data-stu-id="e8d04-112">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8d04-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8d04-113">Example</span></span>  

 <span data-ttu-id="e8d04-114">La siguiente consulta de Entity SQL usa el operador aritmético +  para sumar dos números.</span><span class="sxs-lookup"><span data-stu-id="e8d04-114">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="e8d04-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="e8d04-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="e8d04-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e8d04-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="e8d04-117">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="e8d04-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="e8d04-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="e8d04-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="e8d04-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8d04-119">See also</span></span>

- [<span data-ttu-id="e8d04-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="e8d04-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="e8d04-121">Tipos de modelos conceptuales (CSDL)</span><span class="sxs-lookup"><span data-stu-id="e8d04-121">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
