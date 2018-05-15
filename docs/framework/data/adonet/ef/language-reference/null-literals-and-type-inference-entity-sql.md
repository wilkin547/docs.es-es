---
title: Literales NULL e inferencia de tipos (Entity SQL)
ms.date: 03/30/2017
ms.assetid: edd56afb-af1b-4e7d-b210-cb8998143426
ms.openlocfilehash: 74ff2b459488f896c5ea6af4f7d1e045da5a7983
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="null-literals-and-type-inference-entity-sql"></a><span data-ttu-id="30461-102">Literales NULL e inferencia de tipos (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="30461-102">Null Literals and Type Inference (Entity SQL)</span></span>
<span data-ttu-id="30461-103">Los literales null son compatibles con cualquier tipo del sistema de tipos [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30461-103">Null literals are compatible with any type in the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] type system.</span></span> <span data-ttu-id="30461-104">Sin embargo, para el tipo de un literal null se infiera correctamente, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] impone determinadas restricciones sobre dónde puede utilizarse un literal null.</span><span class="sxs-lookup"><span data-stu-id="30461-104">However, for the type of a null literal to be inferred correctly, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] imposes certain constraints on where a null literal can be used.</span></span>  
  
## <a name="typed-nulls"></a><span data-ttu-id="30461-105">Valores null con tipo</span><span class="sxs-lookup"><span data-stu-id="30461-105">Typed Nulls</span></span>  
 <span data-ttu-id="30461-106">Los valores null con tipo se pueden utilizar en cualquier lugar.</span><span class="sxs-lookup"><span data-stu-id="30461-106">Typed nulls can be used anywhere.</span></span> <span data-ttu-id="30461-107">La inferencia de tipos no es necesaria para los valores null con tipo porque el tipo es conocido.</span><span class="sxs-lookup"><span data-stu-id="30461-107">Type inference is not required for typed nulls because the type is known.</span></span> <span data-ttu-id="30461-108">Por ejemplo, puede crear un valor null de tipo Int16 con la siguiente construcción [!INCLUDE[esql](../../../../../../includes/esql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="30461-108">For example, you can construct a null of type Int16 with the following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] construct:</span></span>  
  
 `(cast(null as Int16))`  
  
## <a name="free-floating-null-literals"></a><span data-ttu-id="30461-109">Literales null flotantes</span><span class="sxs-lookup"><span data-stu-id="30461-109">Free-Floating Null Literals</span></span>  
 <span data-ttu-id="30461-110">Los literales null flotantes se pueden utilizar en los siguientes contextos.</span><span class="sxs-lookup"><span data-stu-id="30461-110">Free-floating null literals can be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="30461-111">Como un argumento para una expresión CAST o TREAT.</span><span class="sxs-lookup"><span data-stu-id="30461-111">As an argument to a CAST or TREAT expression.</span></span> <span data-ttu-id="30461-112">Esta es la forma que se recomienda para generar una expresión null con tipo.</span><span class="sxs-lookup"><span data-stu-id="30461-112">This is the recommended way to produce a typed null expression.</span></span>  
  
-   <span data-ttu-id="30461-113">Como un argumento para un método o una función.</span><span class="sxs-lookup"><span data-stu-id="30461-113">As an argument to a method or a function.</span></span> <span data-ttu-id="30461-114">Se aplican las reglas estándar de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="30461-114">Standard overload rules apply.</span></span>  
  
-   <span data-ttu-id="30461-115">Como uno de los argumentos de una expresión aritmética, como +, - o /.</span><span class="sxs-lookup"><span data-stu-id="30461-115">As one of the arguments to an arithmetic expression such as +, -, or /.</span></span> <span data-ttu-id="30461-116">El resto de argumentos no pueden ser literales null; si fuera el caso, no es posible la inferencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="30461-116">The other arguments cannot be null literals, otherwise type inference is not possible.</span></span>  
  
-   <span data-ttu-id="30461-117">Como cualquiera de los argumentos de una expresión lógica (AND, OR o NOT).</span><span class="sxs-lookup"><span data-stu-id="30461-117">As any of the arguments to a logical expression (AND, OR, or NOT).</span></span> <span data-ttu-id="30461-118">Todos los argumentos se conocen como que son del tipo Boolean.</span><span class="sxs-lookup"><span data-stu-id="30461-118">All the arguments are known to be of type Boolean.</span></span>  
  
-   <span data-ttu-id="30461-119">Como el argumento a una expresión IS NULL o IS NOT NULL.</span><span class="sxs-lookup"><span data-stu-id="30461-119">As the argument to an IS NULL or IS NOT NULL expression.</span></span>  
  
-   <span data-ttu-id="30461-120">Como uno o más de los argumentos de una expresión LIKE.</span><span class="sxs-lookup"><span data-stu-id="30461-120">As one or more of the arguments to a LIKE expression.</span></span> <span data-ttu-id="30461-121">Se espera que todos los argumentos sean cadenas.</span><span class="sxs-lookup"><span data-stu-id="30461-121">All arguments are expected to be strings.</span></span>  
  
-   <span data-ttu-id="30461-122">Como uno o más de los argumentos de un constructor de tipo con nombre.</span><span class="sxs-lookup"><span data-stu-id="30461-122">As one or more of the arguments to a named-type constructor.</span></span>  
  
-   <span data-ttu-id="30461-123">Como uno o más de los argumentos de un constructor multiset.</span><span class="sxs-lookup"><span data-stu-id="30461-123">As one or more of the arguments to a multiset constructor.</span></span> <span data-ttu-id="30461-124">Al menos uno de los argumentos de un constructor multiset debe ser una expresión que no sea un literal null.</span><span class="sxs-lookup"><span data-stu-id="30461-124">At least one argument to the multiset constructor must be an expression that is not a null literal.</span></span>  
  
-   <span data-ttu-id="30461-125">Como uno o más de los argumentos de una expresión THEN o ELSE en una expresión CASE.</span><span class="sxs-lookup"><span data-stu-id="30461-125">As one or more of the THEN or ELSE expressions in a CASE expression.</span></span> <span data-ttu-id="30461-126">Al menos una de las expresiones THEN o ELSE en la expresión CASE debe ser una expresión distinta a una literal null.</span><span class="sxs-lookup"><span data-stu-id="30461-126">At least one of the THEN or ELSE expressions in the CASE expression must be an expression other than a null literal.</span></span>  
  
 <span data-ttu-id="30461-127">Los literales null flotantes no se pueden utilizar en otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="30461-127">Free-floating null literals cannot be used in other scenarios.</span></span> <span data-ttu-id="30461-128">Por ejemplo, no se puede utilizar como argumentos para un constructor row.</span><span class="sxs-lookup"><span data-stu-id="30461-128">For example,  they cannot be used as arguments to a row constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30461-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="30461-129">See Also</span></span>  
 [<span data-ttu-id="30461-130">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="30461-130">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
