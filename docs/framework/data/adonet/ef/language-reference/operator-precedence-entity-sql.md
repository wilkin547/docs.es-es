---
description: 'Más información acerca de: precedencia de operadores (Entity SQL)'
title: Precedencia de operadores (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: 72cfdecf7dfe4ce590d99e866429e771f9ede231
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739331"
---
# <a name="operator-precedence-entity-sql"></a><span data-ttu-id="68ae2-103">Precedencia de operadores (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="68ae2-103">Operator Precedence (Entity SQL)</span></span>

<span data-ttu-id="68ae2-104">Cuando una [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta tiene varios operadores, la prioridad de operador determina la secuencia en la que se realizan las operaciones.</span><span class="sxs-lookup"><span data-stu-id="68ae2-104">When an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query has multiple operators, operator precedence determines the sequence in which the operations are performed.</span></span> <span data-ttu-id="68ae2-105">El orden de ejecución puede afectar de manera significativa al resultado de la consulta.</span><span class="sxs-lookup"><span data-stu-id="68ae2-105">The order of execution can significantly affect the query result.</span></span>  
  
 <span data-ttu-id="68ae2-106">Los operadores tienen los niveles de prioridad que se muestran en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="68ae2-106">Operators have the precedence levels shown in the following table.</span></span> <span data-ttu-id="68ae2-107">Un operador con un nivel más altos se evalúa antes que un operador con un nivel más bajo.</span><span class="sxs-lookup"><span data-stu-id="68ae2-107">An operator with a higher level is evaluated before an operator with a lower level.</span></span>  
  
|<span data-ttu-id="68ae2-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="68ae2-108">Level</span></span>|<span data-ttu-id="68ae2-109">Tipo de operación</span><span class="sxs-lookup"><span data-stu-id="68ae2-109">Operation type</span></span>|<span data-ttu-id="68ae2-110">Operator</span><span class="sxs-lookup"><span data-stu-id="68ae2-110">Operator</span></span>|  
|-----------|--------------------|--------------|  
|<span data-ttu-id="68ae2-111">1</span><span class="sxs-lookup"><span data-stu-id="68ae2-111">1</span></span>|<span data-ttu-id="68ae2-112">Principal</span><span class="sxs-lookup"><span data-stu-id="68ae2-112">Primary</span></span>|`. , [] ()`|  
|<span data-ttu-id="68ae2-113">2</span><span class="sxs-lookup"><span data-stu-id="68ae2-113">2</span></span>|<span data-ttu-id="68ae2-114">Unario</span><span class="sxs-lookup"><span data-stu-id="68ae2-114">Unary</span></span>|`! not`|  
|<span data-ttu-id="68ae2-115">3</span><span class="sxs-lookup"><span data-stu-id="68ae2-115">3</span></span>|<span data-ttu-id="68ae2-116">Multiplicativo</span><span class="sxs-lookup"><span data-stu-id="68ae2-116">Multiplicative</span></span>|`* / %`|  
|<span data-ttu-id="68ae2-117">4</span><span class="sxs-lookup"><span data-stu-id="68ae2-117">4</span></span>|<span data-ttu-id="68ae2-118">Aditivo</span><span class="sxs-lookup"><span data-stu-id="68ae2-118">Additive</span></span>|`+ -`|  
|<span data-ttu-id="68ae2-119">5</span><span class="sxs-lookup"><span data-stu-id="68ae2-119">5</span></span>|<span data-ttu-id="68ae2-120">Ordenación</span><span class="sxs-lookup"><span data-stu-id="68ae2-120">Ordering</span></span>|`< > <= >=`|  
|<span data-ttu-id="68ae2-121">6</span><span class="sxs-lookup"><span data-stu-id="68ae2-121">6</span></span>|<span data-ttu-id="68ae2-122">Igualdad</span><span class="sxs-lookup"><span data-stu-id="68ae2-122">Equality</span></span>|`= != <>`|  
|<span data-ttu-id="68ae2-123">7</span><span class="sxs-lookup"><span data-stu-id="68ae2-123">7</span></span>|<span data-ttu-id="68ae2-124">AND condicional</span><span class="sxs-lookup"><span data-stu-id="68ae2-124">Conditional AND</span></span>|`and &&`|  
|<span data-ttu-id="68ae2-125">8</span><span class="sxs-lookup"><span data-stu-id="68ae2-125">8</span></span>|<span data-ttu-id="68ae2-126">OR condicional</span><span class="sxs-lookup"><span data-stu-id="68ae2-126">Conditional OR</span></span>|`or &#124;&#124;`|  
  
 <span data-ttu-id="68ae2-127">Cuando en una expresión dos operadores tengan el mismo nivel de prioridad de operador, se evalúan de izquierda a derecha en función de su posición dentro de la consulta.</span><span class="sxs-lookup"><span data-stu-id="68ae2-127">When two operators in an expression have the same operator precedence level, they are evaluated left to right, based on their position in the query.</span></span> <span data-ttu-id="68ae2-128">Por ejemplo, `x+y-z` se evalúa como `(x+y)-z`.</span><span class="sxs-lookup"><span data-stu-id="68ae2-128">For example, `x+y-z` is evaluated as `(x+y)-z`.</span></span>  
  
 <span data-ttu-id="68ae2-129">Puede utilizar paréntesis para invalidar la prioridad definida de los operadores en una consulta.</span><span class="sxs-lookup"><span data-stu-id="68ae2-129">You can use parentheses to override the defined precedence of the operators in a query.</span></span> <span data-ttu-id="68ae2-130">Todo lo que está dentro del paréntesis se evalúa en primer lugar para producir un resultado antes de que dicho resultado lo pueda utilizar cualquier otro operador que se encuentre fuera del paréntesis.</span><span class="sxs-lookup"><span data-stu-id="68ae2-130">Everything within parentheses is evaluated first to yield a single result before that result can be used by any operator outside the parentheses.</span></span> <span data-ttu-id="68ae2-131">Por ejemplo, `x+y*z` multiplica `y` por `z` y, a continuación, agrega `x` , pero `(x+y)*z` suma `x` a `y` y, a continuación, multiplica el resultado por `z` .</span><span class="sxs-lookup"><span data-stu-id="68ae2-131">For example, `x+y*z` multiplies `y` by `z` and then adds `x`, but `(x+y)*z` adds `x` to `y` and then multiplies the result by `z`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ae2-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="68ae2-132">See also</span></span>

- [<span data-ttu-id="68ae2-133">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="68ae2-133">Entity SQL Overview</span></span>](entity-sql-overview.md)
