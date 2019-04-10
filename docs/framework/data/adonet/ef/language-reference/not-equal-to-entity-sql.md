---
title: '!= (Distinto de) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: f5fdbbf2892781ce44dfe73e8cd80fbe0f74cf1c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310972"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="6fd3a-102">!= (Distinto de) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6fd3a-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="6fd3a-103">Compara dos expresiones para determinar si la expresión de la izquierda no es igual que la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="6fd3a-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="6fd3a-104">El operador != (No es igual a) es funcionalmente equivalente al operador <>.</span><span class="sxs-lookup"><span data-stu-id="6fd3a-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fd3a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fd3a-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6fd3a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6fd3a-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="6fd3a-107">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="6fd3a-107">Any valid expression.</span></span> <span data-ttu-id="6fd3a-108">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="6fd3a-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6fd3a-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="6fd3a-109">Result Types</span></span>  
 `true` <span data-ttu-id="6fd3a-110">Si la expresión izquierda no es igual a la expresión derecha; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="6fd3a-110">if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fd3a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6fd3a-111">Example</span></span>  
 <span data-ttu-id="6fd3a-112">La consulta de Entity SQL siguiente usa el operador != para comparar dos expresiones con el fin de determinar si la expresión de la izquierda es distinta de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="6fd3a-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="6fd3a-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6fd3a-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6fd3a-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6fd3a-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6fd3a-115">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6fd3a-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6fd3a-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6fd3a-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="6fd3a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fd3a-117">See also</span></span>

- [<span data-ttu-id="6fd3a-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6fd3a-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
