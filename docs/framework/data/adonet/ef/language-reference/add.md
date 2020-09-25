---
title: + (agregar)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: b86d273658362c3bb204d5220ff5e9db1f8de9fe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198059"
---
# <a name="-add"></a><span data-ttu-id="93cc8-102">+ (Sumar)</span><span class="sxs-lookup"><span data-stu-id="93cc8-102">+ (Add)</span></span>

<span data-ttu-id="93cc8-103">Suma dos números.</span><span class="sxs-lookup"><span data-stu-id="93cc8-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93cc8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93cc8-104">Syntax</span></span>  
  
```csharp  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="93cc8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="93cc8-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="93cc8-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="93cc8-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="93cc8-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="93cc8-107">Result Types</span></span>  

 <span data-ttu-id="93cc8-108">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="93cc8-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="93cc8-109">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="93cc8-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93cc8-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="93cc8-110">Remarks</span></span>  

 <span data-ttu-id="93cc8-111">Para los tipos EDM.String, la suma es una concatenación.</span><span class="sxs-lookup"><span data-stu-id="93cc8-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93cc8-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93cc8-112">Example</span></span>  

 <span data-ttu-id="93cc8-113">La siguiente consulta de Entity SQL usa el operador aritmético +  para sumar dos números.</span><span class="sxs-lookup"><span data-stu-id="93cc8-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="93cc8-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="93cc8-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="93cc8-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="93cc8-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="93cc8-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="93cc8-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="93cc8-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="93cc8-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="93cc8-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93cc8-118">See also</span></span>

- [<span data-ttu-id="93cc8-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="93cc8-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="93cc8-120">Tipos de modelos conceptuales (CSDL)</span><span class="sxs-lookup"><span data-stu-id="93cc8-120">Conceptual Model Types (CSDL)</span></span>](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
