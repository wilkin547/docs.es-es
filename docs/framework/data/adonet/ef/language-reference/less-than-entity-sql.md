---
title: < (menor que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 389c50a697c90dadb075369fe696f7382caf3cff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161924"
---
# <a name="-less-than-entity-sql"></a><span data-ttu-id="58c01-102">\< (Menor que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="58c01-102">\< (Less Than) (Entity SQL)</span></span>

<span data-ttu-id="58c01-103">Compara dos expresiones para determinar si la expresión de la izquierda tiene un valor menor que el de la expresión de la derecha.</span><span class="sxs-lookup"><span data-stu-id="58c01-103">Compares two expressions to determine whether the left expression has a value less than the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58c01-104">Syntax</span></span>  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="58c01-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="58c01-105">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="58c01-106">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="58c01-106">Any valid expression.</span></span> <span data-ttu-id="58c01-107">Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="58c01-107">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="58c01-108">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="58c01-108">Result Types</span></span>  

 <span data-ttu-id="58c01-109">`true` si la expresión izquierda tiene un valor menor que el de la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="58c01-109">`true` if the left expression has a value less than the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58c01-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58c01-110">Example</span></span>  

 <span data-ttu-id="58c01-111">La consulta de Entity SQL siguiente utiliza el operador de comparación < para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="58c01-111">The following Entity SQL query uses < comparison operator to compare two expressions to determine whether the left expression has a value less than the right expression.</span></span> <span data-ttu-id="58c01-112">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="58c01-112">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="58c01-113">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="58c01-113">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="58c01-114">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="58c01-114">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="58c01-115">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="58c01-115">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a><span data-ttu-id="58c01-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58c01-116">See also</span></span>

- [<span data-ttu-id="58c01-117">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="58c01-117">Entity SQL Reference</span></span>](entity-sql-reference.md)
