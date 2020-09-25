---
title: Precedencia de operadores (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: f8aa0f213a24d6431d8910af849571a67fbd9f57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175647"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="82e5d-102">Precedencia de operadores (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="82e5d-102">Operator Precedence (Entity SQL)</span></span>

<span data-ttu-id="82e5d-103">Cuando una [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta tiene varios operadores, la prioridad de operador determina la secuencia en la que se realizan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="82e5d-103">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="82e5d-104">El orden de ejecución puede afectar de manera significativa al resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="82e5d-104">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="82e5d-105">Los operadores tienen los niveles de prioridad que se muestran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="82e5d-105">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="82e5d-106">Un operador con un nivel más altos se evalúa antes que un operador con un nivel más bajo.</span><span class="sxs-lookup"><span data-stu-id="82e5d-106">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="82e5d-107">Nivel</span><span class="sxs-lookup"><span data-stu-id="82e5d-107">Level</span></span>|<span data-ttu-id="82e5d-108">Tipo de operación</span><span class="sxs-lookup"><span data-stu-id="82e5d-108">Operation type</span></span>|<span data-ttu-id="82e5d-109">Operador</span><span class="sxs-lookup"><span data-stu-id="82e5d-109">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="82e5d-110">1</span><span class="sxs-lookup"><span data-stu-id="82e5d-110">1</span></span>|<span data-ttu-id="82e5d-111">Principal</span><span class="sxs-lookup"><span data-stu-id="82e5d-111">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="82e5d-112">2</span><span class="sxs-lookup"><span data-stu-id="82e5d-112">2</span></span>|<span data-ttu-id="82e5d-113">Unario</span><span class="sxs-lookup"><span data-stu-id="82e5d-113">Unary</span></span>|`! not`|  
|<span data-ttu-id="82e5d-114">3</span><span class="sxs-lookup"><span data-stu-id="82e5d-114">3</span></span>|<span data-ttu-id="82e5d-115">Multiplicativo</span><span class="sxs-lookup"><span data-stu-id="82e5d-115">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="82e5d-116">4</span><span class="sxs-lookup"><span data-stu-id="82e5d-116">4</span></span>|<span data-ttu-id="82e5d-117">Aditivo</span><span class="sxs-lookup"><span data-stu-id="82e5d-117">Additive</span></span>|`+ -`|  
|<span data-ttu-id="82e5d-118">5</span><span class="sxs-lookup"><span data-stu-id="82e5d-118">5</span></span>|<span data-ttu-id="82e5d-119">Ordenación</span><span class="sxs-lookup"><span data-stu-id="82e5d-119">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="82e5d-120">6</span><span class="sxs-lookup"><span data-stu-id="82e5d-120">6</span></span>|<span data-ttu-id="82e5d-121">Igualdad</span><span class="sxs-lookup"><span data-stu-id="82e5d-121">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="82e5d-122">7</span><span class="sxs-lookup"><span data-stu-id="82e5d-122">7</span></span>|<span data-ttu-id="82e5d-123">AND condicional</span><span class="sxs-lookup"><span data-stu-id="82e5d-123">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="82e5d-124">8</span><span class="sxs-lookup"><span data-stu-id="82e5d-124">8</span></span>|<span data-ttu-id="82e5d-125">OR condicional</span><span class="sxs-lookup"><span data-stu-id="82e5d-125">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="82e5d-126">Cuando en una expresión dos operadores tengan el mismo nivel de prioridad de operador, se evalúan de izquierda a derecha en función de su posición dentro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="82e5d-126">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="82e5d-127">Por ejemplo, `x+y-z` se evalúa como `(x+y)-z`.</span><span class="sxs-lookup"><span data-stu-id="82e5d-127">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="82e5d-128">Puede utilizar paréntesis para invalidar la prioridad definida de los operadores en una consulta.</span><span class="sxs-lookup"><span data-stu-id="82e5d-128">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="82e5d-129">Todo lo que está dentro del paréntesis se evalúa en primer lugar para producir un resultado antes de que dicho resultado lo pueda utilizar cualquier otro operador que se encuentre fuera del paréntesis.</span><span class="sxs-lookup"><span data-stu-id="82e5d-129">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="82e5d-130">Por ejemplo, `x+y*z` multiplica `y` por `z` y, a continuación, agrega `x` , pero `(x+y)*z` suma `x` a `y` y, a continuación, multiplica el resultado por `z` .</span><span class="sxs-lookup"><span data-stu-id="82e5d-130">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e5d-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82e5d-131">See also</span></span>

- [<span data-ttu-id="82e5d-132">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="82e5d-132">Entity SQL Overview</span></span>](entity-sql-overview.md)
