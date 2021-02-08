---
description: 'Más información sobre: literales null e inferencia de tipos (Entity SQL)'
title: Literales NULL e inferencia de tipos (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 3b3474ea9841a34970d2269173d263fda2eb1789
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802143"
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="31251-103">Literales NULL e inferencia de tipos (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="31251-103">Null Literals and Type Inference (Entity SQL)</span></span>

<span data-ttu-id="31251-104">Los literales null son compatibles con cualquier tipo del sistema de tipos [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31251-104">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="31251-105">Sin embargo, para que el tipo de un literal NULL se infiera correctamente, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] impone ciertas restricciones sobre dónde se puede utilizar un literal null.</span><span class="sxs-lookup"><span data-stu-id="31251-105">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="31251-106">Valores null con tipo</span><span class="sxs-lookup"><span data-stu-id="31251-106">Typed Nulls</span></span>  

 <span data-ttu-id="31251-107">Los valores null con tipo se pueden utilizar en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="31251-107">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="31251-108">La inferencia de tipos no es necesaria para los valores null con tipo porque el tipo es conocido.</span><span class="sxs-lookup"><span data-stu-id="31251-108">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="31251-109">Por ejemplo, puede crear un valor null de tipo Int16 con la siguiente construcción [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="31251-109">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="31251-110">Literales null flotantes</span><span class="sxs-lookup"><span data-stu-id="31251-110">Free-Floating Null Literals</span></span>  

 <span data-ttu-id="31251-111">Los literales null flotantes se pueden utilizar en los siguientes contextos.</span><span class="sxs-lookup"><span data-stu-id="31251-111">Free-floating null literals can be used in the following contexts:</span></span>  
  
- <span data-ttu-id="31251-112">Como un argumento para una expresión CAST o TREAT.</span><span class="sxs-lookup"><span data-stu-id="31251-112">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="31251-113">Esta es la forma que se recomienda para generar una expresión null con tipo.</span><span class="sxs-lookup"><span data-stu-id="31251-113">This is the recommended way to produce a typed null expression.</span></span>  
  
- <span data-ttu-id="31251-114">Como un argumento para un método o una función.</span><span class="sxs-lookup"><span data-stu-id="31251-114">As an argument to a method or a function.</span></span> <span data-ttu-id="31251-115">Se aplican las reglas estándar de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="31251-115">Standard overload rules apply.</span></span>  
  
- <span data-ttu-id="31251-116">Como uno de los argumentos de una expresión aritmética, como +, - o /.</span><span class="sxs-lookup"><span data-stu-id="31251-116">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="31251-117">El resto de argumentos no pueden ser literales null; si fuera el caso, no es posible la inferencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="31251-117">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
- <span data-ttu-id="31251-118">Como cualquiera de los argumentos de una expresión lógica (AND, OR o NOT).</span><span class="sxs-lookup"><span data-stu-id="31251-118">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="31251-119">Todos los argumentos se conocen como que son del tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="31251-119">All the arguments are known to be of type Boolean.</span></span>  
  
- <span data-ttu-id="31251-120">Como el argumento a una expresión IS NULL o IS NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="31251-120">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
- <span data-ttu-id="31251-121">Como uno o más de los argumentos de una expresión LIKE.</span><span class="sxs-lookup"><span data-stu-id="31251-121">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="31251-122">Se espera que todos los argumentos sean cadenas.</span><span class="sxs-lookup"><span data-stu-id="31251-122">All arguments are expected to be strings.</span></span>  
  
- <span data-ttu-id="31251-123">Como uno o más de los argumentos de un constructor de tipo con nombre.</span><span class="sxs-lookup"><span data-stu-id="31251-123">As one or more of the arguments to a named-type constructor.</span></span>  
  
- <span data-ttu-id="31251-124">Como uno o más de los argumentos de un constructor multiset.</span><span class="sxs-lookup"><span data-stu-id="31251-124">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="31251-125">Al menos uno de los argumentos de un constructor multiset debe ser una expresión que no sea un literal null.</span><span class="sxs-lookup"><span data-stu-id="31251-125">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
- <span data-ttu-id="31251-126">Como uno o más de los argumentos de una expresión THEN o ELSE en una expresión CASE.</span><span class="sxs-lookup"><span data-stu-id="31251-126">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="31251-127">Al menos una de las expresiones THEN o ELSE en la expresión CASE debe ser una expresión distinta a una literal null.</span><span class="sxs-lookup"><span data-stu-id="31251-127">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="31251-128">Los literales null flotantes no se pueden utilizar en otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="31251-128">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="31251-129">Por ejemplo, no se puede utilizar como argumentos para un constructor row.</span><span class="sxs-lookup"><span data-stu-id="31251-129">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31251-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="31251-130">See also</span></span>

- [<span data-ttu-id="31251-131">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="31251-131">Entity SQL Overview</span></span>](entity-sql-overview.md)
