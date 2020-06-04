---
title: Dimensiones de matriz
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: f971f0c3693177adbcb8869d487e3ad41d49ddc2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413109"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="e5967-102">Dimensiones de matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5967-102">Array Dimensions in Visual Basic</span></span>

<span data-ttu-id="e5967-103">Una *dimensión* es una dirección en la que puede variar la especificación de los elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="e5967-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="e5967-104">Una matriz que contiene el total de ventas de cada día del mes tiene una dimensión (el día del mes).</span><span class="sxs-lookup"><span data-stu-id="e5967-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="e5967-105">Una matriz que contiene el total de ventas por departamento para cada día del mes tiene dos dimensiones (el número de departamento y el día del mes).</span><span class="sxs-lookup"><span data-stu-id="e5967-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="e5967-106">El número de dimensiones que tiene una matriz se denomina su *rango*.</span><span class="sxs-lookup"><span data-stu-id="e5967-106">The number of dimensions an array has is called its *rank*.</span></span>

> [!NOTE]
> <span data-ttu-id="e5967-107">Puede utilizar la <xref:System.Array.Rank%2A> propiedad para determinar el número de dimensiones de una matriz.</span><span class="sxs-lookup"><span data-stu-id="e5967-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>

## <a name="working-with-dimensions"></a><span data-ttu-id="e5967-108">Trabajar con dimensiones</span><span class="sxs-lookup"><span data-stu-id="e5967-108">Working with Dimensions</span></span>

<span data-ttu-id="e5967-109">Para especificar un elemento de una matriz, debe proporcionar un *Índice* o *subíndice* para cada una de sus dimensiones.</span><span class="sxs-lookup"><span data-stu-id="e5967-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="e5967-110">Los elementos son contiguos a lo largo de cada dimensión desde el índice 0 hasta el índice más alto de esa dimensión.</span><span class="sxs-lookup"><span data-stu-id="e5967-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>

<span data-ttu-id="e5967-111">En las ilustraciones siguientes se muestra la estructura conceptual de matrices con distintos rangos.</span><span class="sxs-lookup"><span data-stu-id="e5967-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="e5967-112">Cada elemento de las ilustraciones muestra los valores de índice que tienen acceso a él.</span><span class="sxs-lookup"><span data-stu-id="e5967-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="e5967-113">Por ejemplo, puede tener acceso al primer elemento de la segunda fila de la matriz bidimensional especificando los índices `(1, 0)` .</span><span class="sxs-lookup"><span data-stu-id="e5967-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>

![Diagrama que muestra una matriz unidimensional.](./media/array-dimensions/one-dimensional-array.gif)

![Diagrama que muestra una matriz bidimensional.](./media/array-dimensions/two-dimensional-array.gif)

![Diagrama que muestra una matriz tridimensional.](./media/array-dimensions/three-dimensional-array.gif)

### <a name="one-dimension"></a><span data-ttu-id="e5967-117">Una dimensión</span><span class="sxs-lookup"><span data-stu-id="e5967-117">One Dimension</span></span>

<span data-ttu-id="e5967-118">Muchas matrices tienen solo una dimensión, como el número de personas de cada edad.</span><span class="sxs-lookup"><span data-stu-id="e5967-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="e5967-119">El único requisito para especificar un elemento es la edad para la que ese elemento contiene el recuento.</span><span class="sxs-lookup"><span data-stu-id="e5967-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="e5967-120">Por lo tanto, una matriz de este tipo solo utiliza un índice.</span><span class="sxs-lookup"><span data-stu-id="e5967-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="e5967-121">En el ejemplo siguiente se declara una variable para que contenga una *matriz unidimensional* de recuentos de edad de entre 0 y 120.</span><span class="sxs-lookup"><span data-stu-id="e5967-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>

```vb
Dim ageCounts(120) As UInteger
```

### <a name="two-dimensions"></a><span data-ttu-id="e5967-122">Dos dimensiones</span><span class="sxs-lookup"><span data-stu-id="e5967-122">Two Dimensions</span></span>

<span data-ttu-id="e5967-123">Algunas matrices tienen dos dimensiones, como el número de oficinas en cada piso de cada edificio en un campus.</span><span class="sxs-lookup"><span data-stu-id="e5967-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="e5967-124">La especificación de un elemento requiere tanto el número de compilación como el piso y cada elemento contiene el recuento de la combinación de edificio y piso.</span><span class="sxs-lookup"><span data-stu-id="e5967-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="e5967-125">Por lo tanto, una matriz de este tipo utiliza dos índices.</span><span class="sxs-lookup"><span data-stu-id="e5967-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="e5967-126">En el ejemplo siguiente se declara una variable que contiene una *matriz bidimensional* de recuentos de oficinas, para los edificios 0 a 40 y las plantas 0 a 5.</span><span class="sxs-lookup"><span data-stu-id="e5967-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>

```vb
Dim officeCounts(40, 5) As Byte
```

<span data-ttu-id="e5967-127">Una matriz bidimensional también se denomina *matriz rectangular*.</span><span class="sxs-lookup"><span data-stu-id="e5967-127">A two-dimensional array is also called a *rectangular array*.</span></span>

### <a name="three-dimensions"></a><span data-ttu-id="e5967-128">Tres dimensiones</span><span class="sxs-lookup"><span data-stu-id="e5967-128">Three Dimensions</span></span>

<span data-ttu-id="e5967-129">Algunas matrices tienen tres dimensiones, como los valores en el espacio de tres dimensiones.</span><span class="sxs-lookup"><span data-stu-id="e5967-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="e5967-130">Este tipo de matriz utiliza tres índices, que en este caso representan las coordenadas x, y y z del espacio físico.</span><span class="sxs-lookup"><span data-stu-id="e5967-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="e5967-131">En el ejemplo siguiente se declara una variable para que contenga una *matriz tridimensional* de temperaturas aéreas en varios puntos de un volumen tridimensional.</span><span class="sxs-lookup"><span data-stu-id="e5967-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>

```vb
Dim airTemperatures(99, 99, 24) As Single
```

### <a name="more-than-three-dimensions"></a><span data-ttu-id="e5967-132">Más de tres dimensiones</span><span class="sxs-lookup"><span data-stu-id="e5967-132">More than Three Dimensions</span></span>

<span data-ttu-id="e5967-133">Aunque una matriz puede tener hasta 32 dimensiones, es poco habitual tener más de tres.</span><span class="sxs-lookup"><span data-stu-id="e5967-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>

> [!NOTE]
> <span data-ttu-id="e5967-134">Al agregar dimensiones a una matriz, el almacenamiento total que necesita la matriz aumenta considerablemente, por lo que debe usar matrices multidimensionales con cuidado.</span><span class="sxs-lookup"><span data-stu-id="e5967-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>

## <a name="using-different-dimensions"></a><span data-ttu-id="e5967-135">Usar dimensiones diferentes</span><span class="sxs-lookup"><span data-stu-id="e5967-135">Using Different Dimensions</span></span>

<span data-ttu-id="e5967-136">Supongamos que desea realizar un seguimiento de los importes de ventas de cada día del mes presente.</span><span class="sxs-lookup"><span data-stu-id="e5967-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="e5967-137">Podría declarar una matriz unidimensional con 31 elementos, uno para cada día del mes, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5967-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>

```vb
Dim salesAmounts(30) As Double
```

<span data-ttu-id="e5967-138">Ahora Supongamos que desea realizar un seguimiento de la misma información no solo para cada día de un mes, sino también para cada mes del año.</span><span class="sxs-lookup"><span data-stu-id="e5967-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="e5967-139">Podría declarar una matriz bidimensional con 12 filas (para los meses) y 31 columnas (para los días), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5967-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>

```vb
Dim salesAmounts(11, 30) As Double
```

<span data-ttu-id="e5967-140">Ahora Supongamos que decide que la matriz contiene información durante más de un año.</span><span class="sxs-lookup"><span data-stu-id="e5967-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="e5967-141">Si desea realizar un seguimiento de los importes de ventas durante 5 años, puede declarar una matriz tridimensional con 5 capas, 12 filas y 31 columnas, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e5967-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>

```vb
Dim salesAmounts(4, 11, 30) As Double
```

<span data-ttu-id="e5967-142">Tenga en cuenta que, dado que cada índice varía de 0 a su máximo, cada dimensión de `salesAmounts` se declara como una menor que la longitud necesaria para esa dimensión.</span><span class="sxs-lookup"><span data-stu-id="e5967-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="e5967-143">Tenga en cuenta también que el tamaño de la matriz aumenta con cada nueva dimensión.</span><span class="sxs-lookup"><span data-stu-id="e5967-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="e5967-144">Los tres tamaños de los ejemplos anteriores son los elementos 31, 372 y 1.860, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e5967-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="e5967-145">Puede crear una matriz sin usar la `Dim` instrucción o la `New` cláusula.</span><span class="sxs-lookup"><span data-stu-id="e5967-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="e5967-146">Por ejemplo, puede llamar al <xref:System.Array.CreateInstance%2A> método u otro componente puede pasar el código a una matriz creada de esta manera.</span><span class="sxs-lookup"><span data-stu-id="e5967-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="e5967-147">Este tipo de matriz puede tener un límite inferior distinto de 0.</span><span class="sxs-lookup"><span data-stu-id="e5967-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="e5967-148">Siempre puede probar el límite inferior de una dimensión mediante el <xref:System.Array.GetLowerBound%2A> método o la `LBound` función.</span><span class="sxs-lookup"><span data-stu-id="e5967-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5967-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e5967-149">See also</span></span>

- [<span data-ttu-id="e5967-150">Matrices</span><span class="sxs-lookup"><span data-stu-id="e5967-150">Arrays</span></span>](index.md)
- [<span data-ttu-id="e5967-151">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="e5967-151">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
