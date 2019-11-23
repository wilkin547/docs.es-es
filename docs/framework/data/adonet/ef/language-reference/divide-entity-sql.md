---
title: '- Dividir (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 79fdbebc648daac4f695387d52d2a915383f99ca
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833886"
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="a1d31-102">/ (Dividir) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a1d31-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="a1d31-103">Divide un número entre otro.</span><span class="sxs-lookup"><span data-stu-id="a1d31-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1d31-104">Syntax</span></span>  
  
```sql  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="a1d31-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a1d31-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="a1d31-106">Expresión numérica que se va a dividir.</span><span class="sxs-lookup"><span data-stu-id="a1d31-106">The numeric expression to divide.</span></span> <span data-ttu-id="a1d31-107">`dividend` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="a1d31-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="a1d31-108">Expresión numérica entre la que se divide el dividendo.</span><span class="sxs-lookup"><span data-stu-id="a1d31-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="a1d31-109">`divisor` es una expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="a1d31-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a1d31-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="a1d31-110">Result Types</span></span>  
 <span data-ttu-id="a1d31-111">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="a1d31-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="a1d31-112">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="a1d31-112">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1d31-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1d31-113">Example</span></span>  
 <span data-ttu-id="a1d31-114">La consulta de Entity SQL siguiente utiliza el operador aritmético/para dividir un número entre otro.</span><span class="sxs-lookup"><span data-stu-id="a1d31-114">The following Entity SQL query uses the / arithmetic operator to divide one number by another.</span></span> <span data-ttu-id="a1d31-115">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="a1d31-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a1d31-116">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a1d31-116">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="a1d31-117">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a1d31-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="a1d31-118">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a1d31-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#DIVIDE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="a1d31-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1d31-119">See also</span></span>

- [<span data-ttu-id="a1d31-120">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a1d31-120">Entity SQL Reference</span></span>](entity-sql-reference.md)
