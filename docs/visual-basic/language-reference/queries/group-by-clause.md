---
title: Group By (Cláusula, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryGroupByInto
- vb.QueryGroupBy
- vb.QueryGroupRef
- vb.QueryGroupInto
- vb.QueryGroup
helpviewer_keywords:
- queries [Visual Basic], Group By
- Group By statement [Visual Basic]
- Group By clause [Visual Basic]
ms.assetid: b1b5dcea-6654-473b-a2db-01f7e4c265d7
ms.openlocfilehash: 7cf688dc2e0ccd10c8bfbe5f0308f0aa808fbef0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605035"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="81276-102">Group By (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81276-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="81276-103">Agrupa los elementos de los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="81276-103">Groups the elements of a query result.</span></span> <span data-ttu-id="81276-104">También se puede usar para aplicar funciones de agregado a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="81276-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="81276-105">La operación de agrupación se basa en una o varias claves.</span><span class="sxs-lookup"><span data-stu-id="81276-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81276-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81276-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="81276-107">Elementos</span><span class="sxs-lookup"><span data-stu-id="81276-107">Parts</span></span>  
  
-   <span data-ttu-id="81276-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="81276-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="81276-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="81276-109">Optional.</span></span> <span data-ttu-id="81276-110">Uno o más campos de la variable o las variables de consulta que identifican explícitamente los campos que se incluirán en el resultado agrupado.</span><span class="sxs-lookup"><span data-stu-id="81276-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="81276-111">Si no se especifica ningún campo, se incluyen todos los campos de la variable o las variables de consulta en el resultado agrupado.</span><span class="sxs-lookup"><span data-stu-id="81276-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
-   `keyExp1`  
  
     <span data-ttu-id="81276-112">Requerido.</span><span class="sxs-lookup"><span data-stu-id="81276-112">Required.</span></span> <span data-ttu-id="81276-113">Expresión que identifica la clave que se va a usar para determinar los grupos de elementos.</span><span class="sxs-lookup"><span data-stu-id="81276-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="81276-114">Puede especificar más de una clave para especificar una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="81276-114">You can specify more than one key to specify a composite key.</span></span>  
  
-   `keyExp2`  
  
     <span data-ttu-id="81276-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="81276-115">Optional.</span></span> <span data-ttu-id="81276-116">Uno o más claves adicionales que se combinan con `keyExp1` para crear una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="81276-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
-   `aggregateList`  
  
     <span data-ttu-id="81276-117">Requerido.</span><span class="sxs-lookup"><span data-stu-id="81276-117">Required.</span></span> <span data-ttu-id="81276-118">Una o más expresiones que identifican cómo se agregan los grupos.</span><span class="sxs-lookup"><span data-stu-id="81276-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="81276-119">Para identificar un nombre de miembro para los resultados agrupados, use la palabra clave `Group` , que puede estar en cualquiera de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="81276-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="81276-120">-o bien-</span><span class="sxs-lookup"><span data-stu-id="81276-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="81276-121">También puede incluir funciones de agregado para aplicar al grupo.</span><span class="sxs-lookup"><span data-stu-id="81276-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81276-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81276-122">Remarks</span></span>  
 <span data-ttu-id="81276-123">Puede usar la cláusula `Group By` para dividir los resultados de una consulta en grupos.</span><span class="sxs-lookup"><span data-stu-id="81276-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="81276-124">La agrupación se basa en una clave o una clave compuesta formada por varias claves.</span><span class="sxs-lookup"><span data-stu-id="81276-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="81276-125">Los elementos que están asociados con valores de clave coincidentes se incluyen en el mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="81276-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="81276-126">El parámetro `aggregateList` de la cláusula `Into` y la palabra clave `Group` se usan para identificar el nombre del miembro usado para hacer referencia al grupo.</span><span class="sxs-lookup"><span data-stu-id="81276-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="81276-127">También puede incluir funciones de agregado en la cláusula `Into` para calcular los valores de los elementos agrupados.</span><span class="sxs-lookup"><span data-stu-id="81276-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="81276-128">Para obtener una lista de funciones de agregado estándar, consulte [Aggregate (cláusula)](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="81276-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81276-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81276-129">Example</span></span>  
 <span data-ttu-id="81276-130">En el ejemplo de código siguiente se agrupa una lista de clientes según su ubicación (país) y se proporciona un recuento de los clientes de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="81276-130">The following code example groups a list of customers based on their location (country) and provides a count of the customers in each group.</span></span> <span data-ttu-id="81276-131">Los resultados se ordenan por nombre de país.</span><span class="sxs-lookup"><span data-stu-id="81276-131">The results are ordered by country name.</span></span> <span data-ttu-id="81276-132">Los resultados agrupados se ordenan por nombre de ciudad.</span><span class="sxs-lookup"><span data-stu-id="81276-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/group-by-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="81276-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="81276-133">See Also</span></span>  
 [<span data-ttu-id="81276-134">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81276-134">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="81276-135">Consultas</span><span class="sxs-lookup"><span data-stu-id="81276-135">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="81276-136">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="81276-136">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="81276-137">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="81276-137">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="81276-138">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="81276-138">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="81276-139">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="81276-139">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="81276-140">Group Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="81276-140">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
