---
description: Más información acerca de:! = (no es igual a) (Entity SQL)
title: '!= (Distinto de) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 3b4a02ad-ddfc-4c42-8dfa-676234461312
ms.openlocfilehash: a7a96606fb1834b757253948c3a0d2cde11893dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696404"
---
# <a name="-not-equal-to-entity-sql"></a><span data-ttu-id="6d22c-103">!= (Distinto de) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6d22c-103">!= (Not Equal To) (Entity SQL)</span></span>

<span data-ttu-id="6d22c-104">Compara dos expresiones para determinar si la expresión de la izquierda no es igual que la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="6d22c-104">Compares two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="6d22c-105">El operador != (No es igual a) es funcionalmente equivalente al operador <>.</span><span class="sxs-lookup"><span data-stu-id="6d22c-105">The != (Not Equal To) operator is functionally equivalent to the <> operator.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d22c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d22c-106">Syntax</span></span>  
  
```sql  
expression != expression  
-- or  
expression <> expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6d22c-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6d22c-107">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="6d22c-108">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="6d22c-108">Any valid expression.</span></span> <span data-ttu-id="6d22c-109">Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="6d22c-109">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="6d22c-110">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="6d22c-110">Result Types</span></span>  

 <span data-ttu-id="6d22c-111">`true` si la expresión de la izquierda no es igual a la expresión de la derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="6d22c-111">`true` if the left expression is not equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d22c-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d22c-112">Example</span></span>  

 <span data-ttu-id="6d22c-113">La consulta de Entity SQL siguiente usa el operador != para comparar dos expresiones con el fin de determinar si la expresión de la izquierda es distinta de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="6d22c-113">The following Entity SQL query uses the != operator to compare two expressions to determine whether the left expression is not equal to the right expression.</span></span> <span data-ttu-id="6d22c-114">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="6d22c-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6d22c-115">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6d22c-115">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="6d22c-116">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6d22c-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="6d22c-117">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="6d22c-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NOT_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="6d22c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d22c-118">See also</span></span>

- [<span data-ttu-id="6d22c-119">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6d22c-119">Entity SQL Reference</span></span>](entity-sql-reference.md)
