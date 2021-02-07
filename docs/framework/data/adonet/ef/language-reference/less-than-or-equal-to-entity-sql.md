---
description: 'Más información acerca de: <= (menor o igual que) (Entity SQL)'
title: <= (menor o igual que) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: f720c4ef87cdd0cceea175b1ea70caf5ac6e1deb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748263"
---
# <a name="-less-than-or-equal-to-entity-sql"></a><span data-ttu-id="c8cc5-103">\<= (Menor o igual que) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="c8cc5-103">\<= (Less Than or Equal To) (Entity SQL)</span></span>

<span data-ttu-id="c8cc5-104">Compara dos expresiones para determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="c8cc5-104">Compares two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cc5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8cc5-105">Syntax</span></span>  
  
```sql  
expression <= expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8cc5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c8cc5-106">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="c8cc5-107">Cualquier expresión válida.</span><span class="sxs-lookup"><span data-stu-id="c8cc5-107">Any valid expression.</span></span> <span data-ttu-id="c8cc5-108">Ambas expresiones deben tener tipos de datos que se puedan convertir implícitamente.</span><span class="sxs-lookup"><span data-stu-id="c8cc5-108">Both expressions must have implicitly convertible data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="c8cc5-109">Tipos de resultado</span><span class="sxs-lookup"><span data-stu-id="c8cc5-109">Result Types</span></span>  

 <span data-ttu-id="c8cc5-110">`true` si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c8cc5-110">`true` if the left expression has a value less than or equal to the right expression; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8cc5-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c8cc5-111">Example</span></span>  

 <span data-ttu-id="c8cc5-112">La consulta de Entity SQL siguiente utiliza el operador de comparación <= para comparar dos expresiones con el fin de determinar si la expresión izquierda tiene un valor igual o menor que el de la expresión derecha.</span><span class="sxs-lookup"><span data-stu-id="c8cc5-112">The following Entity SQL query uses <= comparison operator to compare two expressions to determine whether the left expression has a value less than or equal to the right expression.</span></span> <span data-ttu-id="c8cc5-113">La consulta se basa en el modelo AdventureWorks Sales.</span><span class="sxs-lookup"><span data-stu-id="c8cc5-113">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="c8cc5-114">Para compilar y ejecutar esta consulta, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c8cc5-114">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="c8cc5-115">Siga el procedimiento de [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="c8cc5-115">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="c8cc5-116">Pase la consulta siguiente como argumento al método `ExecuteStructuralTypeQuery` :</span><span class="sxs-lookup"><span data-stu-id="c8cc5-116">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#LESS_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less_or_equals)]  
  
## <a name="see-also"></a><span data-ttu-id="c8cc5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8cc5-117">See also</span></span>

- [<span data-ttu-id="c8cc5-118">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="c8cc5-118">Entity SQL Reference</span></span>](entity-sql-reference.md)
