---
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
ms.openlocfilehash: 5fce4f818e22373de7f1b37b941fd88155f3a33f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359895"
---
# <a name="group-by-clause-visual-basic"></a><span data-ttu-id="46367-102">Group By (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46367-102">Group By Clause (Visual Basic)</span></span>
<span data-ttu-id="46367-103">Agrupa los elementos de los resultados de una consulta.</span><span class="sxs-lookup"><span data-stu-id="46367-103">Groups the elements of a query result.</span></span> <span data-ttu-id="46367-104">También se puede usar para aplicar funciones de agregado a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="46367-104">Can also be used to apply aggregate functions to each group.</span></span> <span data-ttu-id="46367-105">La operación de agrupación se basa en una o varias claves.</span><span class="sxs-lookup"><span data-stu-id="46367-105">The grouping operation is based on one or more keys.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46367-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46367-106">Syntax</span></span>  
  
```vb  
Group [ listField1 [, listField2 [...] ] By keyExp1 [, keyExp2 [...] ]  
  Into aggregateList  
```  
  
## <a name="parts"></a><span data-ttu-id="46367-107">Partes</span><span class="sxs-lookup"><span data-stu-id="46367-107">Parts</span></span>  
  
- <span data-ttu-id="46367-108">`listField1`, `listField2`</span><span class="sxs-lookup"><span data-stu-id="46367-108">`listField1`, `listField2`</span></span>  
  
     <span data-ttu-id="46367-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="46367-109">Optional.</span></span> <span data-ttu-id="46367-110">Uno o más campos de la variable o las variables de consulta que identifican explícitamente los campos que se incluirán en el resultado agrupado.</span><span class="sxs-lookup"><span data-stu-id="46367-110">One or more fields of the query variable or variables that explicitly identify the fields to be included in the grouped result.</span></span> <span data-ttu-id="46367-111">Si no se especifica ningún campo, se incluyen todos los campos de la variable o las variables de consulta en el resultado agrupado.</span><span class="sxs-lookup"><span data-stu-id="46367-111">If no fields are specified, all fields of the query variable or variables are included in the grouped result.</span></span>  
  
- `keyExp1`  
  
     <span data-ttu-id="46367-112">Necesario.</span><span class="sxs-lookup"><span data-stu-id="46367-112">Required.</span></span> <span data-ttu-id="46367-113">Expresión que identifica la clave que se va a usar para determinar los grupos de elementos.</span><span class="sxs-lookup"><span data-stu-id="46367-113">An expression that identifies the key to use to determine the groups of elements.</span></span> <span data-ttu-id="46367-114">Puede especificar más de una clave para especificar una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="46367-114">You can specify more than one key to specify a composite key.</span></span>  
  
- `keyExp2`  
  
     <span data-ttu-id="46367-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="46367-115">Optional.</span></span> <span data-ttu-id="46367-116">Uno o más claves adicionales que se combinan con `keyExp1` para crear una clave compuesta.</span><span class="sxs-lookup"><span data-stu-id="46367-116">One or more additional keys that are combined with `keyExp1` to create a composite key.</span></span>  
  
- `aggregateList`  
  
     <span data-ttu-id="46367-117">Necesario.</span><span class="sxs-lookup"><span data-stu-id="46367-117">Required.</span></span> <span data-ttu-id="46367-118">Una o más expresiones que identifican cómo se agregan los grupos.</span><span class="sxs-lookup"><span data-stu-id="46367-118">One or more expressions that identify how the groups are aggregated.</span></span> <span data-ttu-id="46367-119">Para identificar un nombre de miembro para los resultados agrupados, use la palabra clave `Group` , que puede estar en cualquiera de los formatos siguientes:</span><span class="sxs-lookup"><span data-stu-id="46367-119">To identify a member name for the grouped results, use the `Group` keyword, which can be in either of the following forms:</span></span>  
  
    ```vb  
    Into Group  
    ```  
  
     <span data-ttu-id="46367-120">O bien</span><span class="sxs-lookup"><span data-stu-id="46367-120">-or-</span></span>  
  
    ```vb  
    Into <alias> = Group  
    ```  
  
     <span data-ttu-id="46367-121">También puede incluir funciones de agregado para aplicar al grupo.</span><span class="sxs-lookup"><span data-stu-id="46367-121">You can also include aggregate functions to apply to the group.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46367-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="46367-122">Remarks</span></span>  
 <span data-ttu-id="46367-123">Puede usar la cláusula `Group By` para dividir los resultados de una consulta en grupos.</span><span class="sxs-lookup"><span data-stu-id="46367-123">You can use the `Group By` clause to break the results of a query into groups.</span></span> <span data-ttu-id="46367-124">La agrupación se basa en una clave o una clave compuesta formada por varias claves.</span><span class="sxs-lookup"><span data-stu-id="46367-124">The grouping is based on a key or a composite key consisting of multiple keys.</span></span> <span data-ttu-id="46367-125">Los elementos que están asociados con valores de clave coincidentes se incluyen en el mismo grupo.</span><span class="sxs-lookup"><span data-stu-id="46367-125">Elements that are associated with matching key values are included in the same group.</span></span>  
  
 <span data-ttu-id="46367-126">El parámetro `aggregateList` de la cláusula `Into` y la palabra clave `Group` se usan para identificar el nombre del miembro usado para hacer referencia al grupo.</span><span class="sxs-lookup"><span data-stu-id="46367-126">You use the `aggregateList` parameter of the `Into` clause and the `Group` keyword to identify the member name that is used to reference the group.</span></span> <span data-ttu-id="46367-127">También puede incluir funciones de agregado en la cláusula `Into` para calcular los valores de los elementos agrupados.</span><span class="sxs-lookup"><span data-stu-id="46367-127">You can also include aggregate functions in the `Into` clause to compute values for the grouped elements.</span></span> <span data-ttu-id="46367-128">Para obtener una lista de las funciones de agregado estándar, consulte [Aggregate Clause](aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="46367-128">For a list of standard aggregate functions, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="46367-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46367-129">Example</span></span>  
 <span data-ttu-id="46367-130">En el ejemplo de código siguiente se agrupa una lista de clientes según su ubicación (país o región) y se proporciona un recuento de los clientes de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="46367-130">The following code example groups a list of customers based on their location (country/region) and provides a count of the customers in each group.</span></span> <span data-ttu-id="46367-131">Los resultados se ordenan por nombre de país o región.</span><span class="sxs-lookup"><span data-stu-id="46367-131">The results are ordered by country/region name.</span></span> <span data-ttu-id="46367-132">Los resultados agrupados se ordenan por nombre de ciudad.</span><span class="sxs-lookup"><span data-stu-id="46367-132">The grouped results are ordered by city name.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="46367-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46367-133">See also</span></span>

- [<span data-ttu-id="46367-134">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="46367-134">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="46367-135">Consultas</span><span class="sxs-lookup"><span data-stu-id="46367-135">Queries</span></span>](index.md)
- [<span data-ttu-id="46367-136">Select (cláusula)</span><span class="sxs-lookup"><span data-stu-id="46367-136">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="46367-137">Cláusula FROM</span><span class="sxs-lookup"><span data-stu-id="46367-137">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="46367-138">Cláusula Order By</span><span class="sxs-lookup"><span data-stu-id="46367-138">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="46367-139">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="46367-139">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="46367-140">Cláusula Group Join</span><span class="sxs-lookup"><span data-stu-id="46367-140">Group Join Clause</span></span>](group-join-clause.md)
