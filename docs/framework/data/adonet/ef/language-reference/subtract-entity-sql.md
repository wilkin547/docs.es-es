---
title: '- Restar (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: 8b5cfee4c82757e55babdf1ad14f6cf3c743a5a2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249013"
---
# <a name="--subtract-entity-sql"></a><span data-ttu-id="8d3d8-102">- (Restar) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="8d3d8-102">- (Subtract) (Entity SQL)</span></span>
<span data-ttu-id="8d3d8-103">Resta dos números.</span><span class="sxs-lookup"><span data-stu-id="8d3d8-103">Subtracts two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d3d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d3d8-104">Syntax</span></span>  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="8d3d8-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8d3d8-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="8d3d8-106">Expresión válida de cualquier tipo de datos numérico.</span><span class="sxs-lookup"><span data-stu-id="8d3d8-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="8d3d8-107">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="8d3d8-107">Result Types</span></span>  
 <span data-ttu-id="8d3d8-108">El tipo de datos que resulta de la promoción de tipos implícita de dos argumentos.</span><span class="sxs-lookup"><span data-stu-id="8d3d8-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="8d3d8-109">Para obtener más información sobre la promoción de tipos implícita, vea [sistema de tipos](type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="8d3d8-109">For more information about implicit type promotion, see [Type System](type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d3d8-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d3d8-110">Example</span></span>  
 <span data-ttu-id="8d3d8-111">La siguiente consulta de Entity SQL usa el operador aritmético - para restar dos números.</span><span class="sxs-lookup"><span data-stu-id="8d3d8-111">The following Entity SQL query uses the - arithmetic operator to subtract two numbers.</span></span> <span data-ttu-id="8d3d8-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="8d3d8-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="8d3d8-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8d3d8-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="8d3d8-114">Siga el procedimiento descrito [en cómo: Ejecute una consulta que devuelva resultados](../how-to-execute-a-query-that-returns-structuraltype-results.md)de StructuralType.</span><span class="sxs-lookup"><span data-stu-id="8d3d8-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="8d3d8-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="8d3d8-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a><span data-ttu-id="8d3d8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d3d8-116">See also</span></span>

- [<span data-ttu-id="8d3d8-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="8d3d8-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
