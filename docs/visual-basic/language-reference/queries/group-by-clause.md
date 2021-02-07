---
description: 'Más información acerca de: cláusula Group by (Visual Basic)'
title: Cláusula Group By
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
ms.openlocfilehash: f5cfb76b0f4b1d191f959ae1812140c6872e93bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700512"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="66128-103">Group By (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66128-103">Group By Clause (Visual Basic)</span></span>

<span data-ttu-id="66128-104">Agrupa los elementos de los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="66128-104">Groups the elements of a query result.</span></span> <span data-ttu-id="66128-105">También se puede usar para aplicar funciones de agregado a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="66128-105">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="66128-106">La operación de agrupación se basa en una o varias claves.</span><span class="sxs-lookup"><span data-stu-id="66128-106">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66128-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66128-107">Syntax</span></span>  
  
```vb  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="66128-108">Partes</span><span class="sxs-lookup"><span data-stu-id="66128-108">Parts</span></span>  
  
- <span data-ttu-id="66128-109">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="66128-109">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="66128-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="66128-110">Optional.</span></span> <span data-ttu-id="66128-111">Uno o más campos de la variable o las variables de consulta que identifican explícitamente los campos que se incluirán en el resultado agrupado.</span><span class="sxs-lookup"><span data-stu-id="66128-111">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="66128-112">Si no se especifica ningún campo, se incluyen todos los campos de la variable o las variables de consulta en el resultado agrupado.</span><span class="sxs-lookup"><span data-stu-id="66128-112">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
- `keyExp1`  
  
     <span data-ttu-id="66128-113">Necesario.</span><span class="sxs-lookup"><span data-stu-id="66128-113">Required.</span></span> <span data-ttu-id="66128-114">Expresión que identifica la clave que se va a usar para determinar los grupos de elementos.</span><span class="sxs-lookup"><span data-stu-id="66128-114">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="66128-115">Puede especificar más de una clave para especificar una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="66128-115">You can specify more than one key to specify a composite key.</span></span>  
  
- `keyExp2`  
  
     <span data-ttu-id="66128-116">Opcional.</span><span class="sxs-lookup"><span data-stu-id="66128-116">Optional.</span></span> <span data-ttu-id="66128-117">Uno o más claves adicionales que se combinan con `keyExp1` para crear una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="66128-117">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
- `aggregateList`  
  
     <span data-ttu-id="66128-118">Necesario.</span><span class="sxs-lookup"><span data-stu-id="66128-118">Required.</span></span> <span data-ttu-id="66128-119">Una o más expresiones que identifican cómo se agregan los grupos.</span><span class="sxs-lookup"><span data-stu-id="66128-119">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="66128-120">Para identificar un nombre de miembro para los resultados agrupados, use la palabra clave `Group` , que puede estar en cualquiera de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="66128-120">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```vb  
    Into Group  
    ```  
  
     <span data-ttu-id="66128-121">o bien</span><span class="sxs-lookup"><span data-stu-id="66128-121">-or-</span></span>  
  
    ```vb  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="66128-122">También puede incluir funciones de agregado para aplicar al grupo.</span><span class="sxs-lookup"><span data-stu-id="66128-122">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66128-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="66128-123">Remarks</span></span>  

 <span data-ttu-id="66128-124">Puede usar la cláusula `Group By` para dividir los resultados de una consulta en grupos.</span><span class="sxs-lookup"><span data-stu-id="66128-124">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="66128-125">La agrupación se basa en una clave o una clave compuesta formada por varias claves.</span><span class="sxs-lookup"><span data-stu-id="66128-125">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="66128-126">Los elementos que están asociados con valores de clave coincidentes se incluyen en el mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="66128-126">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="66128-127">El parámetro `aggregateList` de la cláusula `Into` y la palabra clave `Group` se usan para identificar el nombre del miembro usado para hacer referencia al grupo.</span><span class="sxs-lookup"><span data-stu-id="66128-127">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="66128-128">También puede incluir funciones de agregado en la cláusula `Into` para calcular los valores de los elementos agrupados.</span><span class="sxs-lookup"><span data-stu-id="66128-128">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="66128-129">Para obtener una lista de las funciones de agregado estándar, consulte [Aggregate Clause](aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="66128-129">For a list of standard aggregate functions, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66128-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66128-130">Example</span></span>  

 <span data-ttu-id="66128-131">En el ejemplo de código siguiente se agrupa una lista de clientes según su ubicación (país o región) y se proporciona un recuento de los clientes de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="66128-131">The following code example groups a list of customers based on their location (country/region) and provides a count of the customers in each group.</span></span> <span data-ttu-id="66128-132">Los resultados se ordenan por nombre de país o región.</span><span class="sxs-lookup"><span data-stu-id="66128-132">The results are ordered by country/region name.</span></span> <span data-ttu-id="66128-133">Los resultados agrupados se ordenan por nombre de ciudad.</span><span class="sxs-lookup"><span data-stu-id="66128-133">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="66128-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="66128-134">See also</span></span>

- [<span data-ttu-id="66128-135">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="66128-135">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="66128-136">Consultas</span><span class="sxs-lookup"><span data-stu-id="66128-136">Queries</span></span>](index.md)
- [<span data-ttu-id="66128-137">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="66128-137">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="66128-138">Cláusula From</span><span class="sxs-lookup"><span data-stu-id="66128-138">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="66128-139">Cláusula order by</span><span class="sxs-lookup"><span data-stu-id="66128-139">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="66128-140">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="66128-140">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="66128-141">Cláusula Group Join</span><span class="sxs-lookup"><span data-stu-id="66128-141">Group Join Clause</span></span>](group-join-clause.md)
