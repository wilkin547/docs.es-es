---
title: Precedencia de operadores (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 722ebe5f0ec530f8c7f86e9f9901451b060903f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760355"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="463eb-102">Precedencia de operadores (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="463eb-102">Operator Precedence (Entity SQL)</span></span>
<span data-ttu-id="463eb-103">Cuando un [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta tiene múltiples operadores, prioridad de operador determina la secuencia en que se realizan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="463eb-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="463eb-104">El orden de ejecución puede afectar de manera significativa al resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="463eb-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="463eb-105">Los operadores tienen los niveles de prioridad que se muestran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="463eb-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="463eb-106">Un operador con un nivel más altos se evalúa antes que un operador con un nivel más bajo.</span><span class="sxs-lookup"><span data-stu-id="463eb-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="463eb-107">Nivel</span><span class="sxs-lookup"><span data-stu-id="463eb-107">Level</span></span>|<span data-ttu-id="463eb-108">Tipo de operación</span><span class="sxs-lookup"><span data-stu-id="463eb-108">Operation type</span></span>|<span data-ttu-id="463eb-109">Operador</span><span class="sxs-lookup"><span data-stu-id="463eb-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="463eb-110">1</span><span class="sxs-lookup"><span data-stu-id="463eb-110">1</span></span>|<span data-ttu-id="463eb-111">Principal</span><span class="sxs-lookup"><span data-stu-id="463eb-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="463eb-112">2</span><span class="sxs-lookup"><span data-stu-id="463eb-112">2</span></span>|<span data-ttu-id="463eb-113">Unario</span><span class="sxs-lookup"><span data-stu-id="463eb-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="463eb-114">3</span><span class="sxs-lookup"><span data-stu-id="463eb-114">3</span></span>|<span data-ttu-id="463eb-115">Multiplicativo</span><span class="sxs-lookup"><span data-stu-id="463eb-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="463eb-116">4</span><span class="sxs-lookup"><span data-stu-id="463eb-116">4</span></span>|<span data-ttu-id="463eb-117">Aditivo</span><span class="sxs-lookup"><span data-stu-id="463eb-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="463eb-118">5</span><span class="sxs-lookup"><span data-stu-id="463eb-118">5</span></span>|<span data-ttu-id="463eb-119">Ordenación</span><span class="sxs-lookup"><span data-stu-id="463eb-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="463eb-120">6</span><span class="sxs-lookup"><span data-stu-id="463eb-120">6</span></span>|<span data-ttu-id="463eb-121">Igualdad</span><span class="sxs-lookup"><span data-stu-id="463eb-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="463eb-122">7</span><span class="sxs-lookup"><span data-stu-id="463eb-122">7</span></span>|<span data-ttu-id="463eb-123">AND condicional</span><span class="sxs-lookup"><span data-stu-id="463eb-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="463eb-124">8</span><span class="sxs-lookup"><span data-stu-id="463eb-124">8</span></span>|<span data-ttu-id="463eb-125">OR condicional</span><span class="sxs-lookup"><span data-stu-id="463eb-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="463eb-126">Cuando en una expresión dos operadores tengan el mismo nivel de prioridad de operador, se evalúan de izquierda a derecha en función de su posición dentro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="463eb-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="463eb-127">Por ejemplo, `x+y-z` se evalúa como `(x+y)-z`.</span><span class="sxs-lookup"><span data-stu-id="463eb-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="463eb-128">Puede utilizar paréntesis para invalidar la prioridad definida de los operadores en una consulta.</span><span class="sxs-lookup"><span data-stu-id="463eb-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="463eb-129">Todo lo que está dentro del paréntesis se evalúa en primer lugar para producir un resultado antes de que dicho resultado lo pueda utilizar cualquier otro operador que se encuentre fuera del paréntesis.</span><span class="sxs-lookup"><span data-stu-id="463eb-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="463eb-130">Por ejemplo, `x+y*z` multiplica `y` por `z` y, a continuación, agrega `x`, pero `(x+y)*z` agrega `x` a `y` y, a continuación, multiplica el resultado por `z`.</span><span class="sxs-lookup"><span data-stu-id="463eb-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="463eb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="463eb-131">See also</span></span>

- [<span data-ttu-id="463eb-132">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="463eb-132">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
