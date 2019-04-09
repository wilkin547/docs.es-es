---
title: < (Menor que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 0373dc2d066252d76cd3d4408790404ca70ab701
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105175"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="a89c9-102">\< (Menor que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a89c9-102">\< (Less Than) (Entity SQL)</span></span>
<span data-ttu-id="a89c9-103">Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor menor que el de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="a89c9-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a89c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a89c9-104">Syntax</span></span>  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="a89c9-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a89c9-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="a89c9-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="a89c9-106">Any valid expression.</span></span> <span data-ttu-id="a89c9-107">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="a89c9-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="a89c9-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="a89c9-108">Result Types</span></span>  
 `true` <span data-ttu-id="a89c9-109">Si la expresión izquierda tiene un valor menor que la expresión derecha; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a89c9-109">if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a89c9-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a89c9-110">Example</span></span>  
 <span data-ttu-id="a89c9-111">La consulta de Entity SQL siguiente utiliza el operador de comparación < para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="a89c9-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="a89c9-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="a89c9-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="a89c9-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a89c9-113">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="a89c9-114">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="a89c9-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="a89c9-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="a89c9-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a><span data-ttu-id="a89c9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a89c9-116">See also</span></span>

- [<span data-ttu-id="a89c9-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a89c9-117">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
