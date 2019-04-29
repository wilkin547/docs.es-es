---
title: '!= (Distinto de) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: f5fdbbf2892781ce44dfe73e8cd80fbe0f74cf1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760342"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="b6b39-102">!= (Distinto de) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b6b39-102">!= (Not Equal To) (Entity SQL)</span></span>
<span data-ttu-id="b6b39-103">Compara dos expresiones para determinar si la expresión de la izquierda no es igual que la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="b6b39-103">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="b6b39-104">El operador != (No es igual a) es funcionalmente equivalente al operador <>.</span><span class="sxs-lookup"><span data-stu-id="b6b39-104">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b39-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6b39-105">Syntax</span></span>  
  
```  
expression != expression  
or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="b6b39-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b6b39-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="b6b39-107">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="b6b39-107">Any valid expression.</span></span> <span data-ttu-id="b6b39-108">Ambas expresiones deben tener tipos de datos convertibles implícitamente.</span><span class="sxs-lookup"><span data-stu-id="b6b39-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="b6b39-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="b6b39-109">Result Types</span></span>  
 <span data-ttu-id="b6b39-110">`true` si la expresión de la izquierda no es igual a la expresión de la derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b6b39-110">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6b39-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6b39-111">Example</span></span>  
 <span data-ttu-id="b6b39-112">La consulta de Entity SQL siguiente usa el operador != para comparar dos expresiones con el fin de determinar si la expresión de la izquierda es distinta de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="b6b39-112">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="b6b39-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="b6b39-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b6b39-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b6b39-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="b6b39-115">Siga el procedimiento de [Cómo: Ejecutar una consulta que devuelve resultados StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b6b39-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="b6b39-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="b6b39-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NOT_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="b6b39-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6b39-117">See also</span></span>

- [<span data-ttu-id="b6b39-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b6b39-118">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
