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
ms.openlocfilehash: 04378d2c9a7e565343ff663997e2a3e61f04f9d2
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423578"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="38150-102">Group By (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38150-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="38150-103">Agrupa los elementos de los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="38150-103">Groups the elements of a query result.</span></span> <span data-ttu-id="38150-104">También se puede usar para aplicar funciones de agregado a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="38150-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="38150-105">La operación de agrupación se basa en una o varias claves.</span><span class="sxs-lookup"><span data-stu-id="38150-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38150-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38150-106">Syntax</span></span>  
  
```  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="38150-107">Elementos</span><span class="sxs-lookup"><span data-stu-id="38150-107">Parts</span></span>  
  
- <span data-ttu-id="38150-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="38150-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="38150-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="38150-109">Optional.</span></span> <span data-ttu-id="38150-110">Uno o más campos de la variable o las variables de consulta que identifican explícitamente los campos que se incluirán en el resultado agrupado.</span><span class="sxs-lookup"><span data-stu-id="38150-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="38150-111">Si no se especifica ningún campo, se incluyen todos los campos de la variable o las variables de consulta en el resultado agrupado.</span><span class="sxs-lookup"><span data-stu-id="38150-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
- `keyExp1`  
  
     <span data-ttu-id="38150-112">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="38150-112">Required.</span></span> <span data-ttu-id="38150-113">Expresión que identifica la clave que se va a usar para determinar los grupos de elementos.</span><span class="sxs-lookup"><span data-stu-id="38150-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="38150-114">Puede especificar más de una clave para especificar una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="38150-114">You can specify more than one key to specify a composite key.</span></span>  
  
- `keyExp2`  
  
     <span data-ttu-id="38150-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="38150-115">Optional.</span></span> <span data-ttu-id="38150-116">Uno o más claves adicionales que se combinan con `keyExp1` para crear una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="38150-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
- `aggregateList`  
  
     <span data-ttu-id="38150-117">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="38150-117">Required.</span></span> <span data-ttu-id="38150-118">Una o más expresiones que identifican cómo se agregan los grupos.</span><span class="sxs-lookup"><span data-stu-id="38150-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="38150-119">Para identificar un nombre de miembro para los resultados agrupados, use la palabra clave `Group` , que puede estar en cualquiera de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="38150-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```  
    Into Group  
    ```  
  
     <span data-ttu-id="38150-120">-o bien-</span><span class="sxs-lookup"><span data-stu-id="38150-120">-or-</span></span>  
  
    ```  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="38150-121">También puede incluir funciones de agregado para aplicar al grupo.</span><span class="sxs-lookup"><span data-stu-id="38150-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38150-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38150-122">Remarks</span></span>  
 <span data-ttu-id="38150-123">Puede usar la cláusula `Group By` para dividir los resultados de una consulta en grupos.</span><span class="sxs-lookup"><span data-stu-id="38150-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="38150-124">La agrupación se basa en una clave o una clave compuesta formada por varias claves.</span><span class="sxs-lookup"><span data-stu-id="38150-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="38150-125">Los elementos que están asociados con valores de clave coincidentes se incluyen en el mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="38150-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="38150-126">El parámetro `aggregateList` de la cláusula `Into` y la palabra clave `Group` se usan para identificar el nombre del miembro usado para hacer referencia al grupo.</span><span class="sxs-lookup"><span data-stu-id="38150-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="38150-127">También puede incluir funciones de agregado en la cláusula `Into` para calcular los valores de los elementos agrupados.</span><span class="sxs-lookup"><span data-stu-id="38150-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="38150-128">Para obtener una lista de las funciones de agregado estándar, consulte [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="38150-128">For a list of standard aggregate functions, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="38150-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38150-129">Example</span></span>  
 <span data-ttu-id="38150-130">En el ejemplo de código siguiente se agrupa una lista de clientes según su ubicación (país o región) y proporciona un recuento de los clientes en cada grupo.</span><span class="sxs-lookup"><span data-stu-id="38150-130">The following code example groups a list of customers based on their location (country/region) and provides a count of the customers in each group.</span></span> <span data-ttu-id="38150-131">Los resultados se ordenan por nombre de país o región.</span><span class="sxs-lookup"><span data-stu-id="38150-131">The results are ordered by country/region name.</span></span> <span data-ttu-id="38150-132">Los resultados agrupados se ordenan por nombre de ciudad.</span><span class="sxs-lookup"><span data-stu-id="38150-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="38150-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="38150-133">See also</span></span>

- [<span data-ttu-id="38150-134">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="38150-134">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="38150-135">Consultas</span><span class="sxs-lookup"><span data-stu-id="38150-135">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="38150-136">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="38150-136">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="38150-137">From (cláusula)</span><span class="sxs-lookup"><span data-stu-id="38150-137">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="38150-138">Order By (cláusula)</span><span class="sxs-lookup"><span data-stu-id="38150-138">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="38150-139">Aggregate (cláusula)</span><span class="sxs-lookup"><span data-stu-id="38150-139">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="38150-140">Group Join (cláusula)</span><span class="sxs-lookup"><span data-stu-id="38150-140">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
