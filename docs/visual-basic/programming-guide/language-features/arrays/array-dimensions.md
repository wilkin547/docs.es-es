---
title: Dimensiones de matrices en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: 5ba92e113faf9d68bad97968937cc736132b2065
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708537"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="6acbb-102">Dimensiones de matrices en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6acbb-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="6acbb-103">Un *dimensión* es una dirección en la que puede variar la especificación de elementos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="6acbb-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="6acbb-104">Una matriz que contiene las ventas totales para cada día del mes tiene una dimensión (el día del mes).</span><span class="sxs-lookup"><span data-stu-id="6acbb-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="6acbb-105">Una matriz que contiene las ventas totales por departamento para cada día del mes tiene dos dimensiones (el número de departamento y el día del mes).</span><span class="sxs-lookup"><span data-stu-id="6acbb-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="6acbb-106">El número de dimensiones tiene una matriz se llama a su *rango*.</span><span class="sxs-lookup"><span data-stu-id="6acbb-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6acbb-107">Puede usar el <xref:System.Array.Rank%2A> propiedad para determinar cuántas dimensiones tiene de una matriz.</span><span class="sxs-lookup"><span data-stu-id="6acbb-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="6acbb-108">Trabajar con dimensiones</span><span class="sxs-lookup"><span data-stu-id="6acbb-108">Working with Dimensions</span></span>  
 <span data-ttu-id="6acbb-109">Especifica un elemento de una matriz al proporcionar un *índice* o *subíndice* para cada uno de sus dimensiones.</span><span class="sxs-lookup"><span data-stu-id="6acbb-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="6acbb-110">Los elementos son contiguos en cada dimensión desde el índice 0 hasta el índice más alto para esa dimensión.</span><span class="sxs-lookup"><span data-stu-id="6acbb-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="6acbb-111">Las ilustraciones siguientes muestran la estructura conceptual de matrices con rangos diferentes.</span><span class="sxs-lookup"><span data-stu-id="6acbb-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="6acbb-112">Cada elemento en las ilustraciones muestra los valores de índice que acceden a ellos.</span><span class="sxs-lookup"><span data-stu-id="6acbb-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="6acbb-113">Por ejemplo, puede obtener acceso el primer elemento de la segunda fila de la matriz bidimensional especificando los índices `(1, 0)`.</span><span class="sxs-lookup"><span data-stu-id="6acbb-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 <span data-ttu-id="6acbb-114">![Diagrama gráfico de uno&#45;una matriz unidimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span><span class="sxs-lookup"><span data-stu-id="6acbb-114">![Graphic diagram of one&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span></span>  
<span data-ttu-id="6acbb-115">Matriz unidimensional</span><span class="sxs-lookup"><span data-stu-id="6acbb-115">One-dimensional array</span></span>  
  
 <span data-ttu-id="6acbb-116">![Diagrama gráfico de dos&#45;una matriz unidimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span><span class="sxs-lookup"><span data-stu-id="6acbb-116">![Graphic diagram of two&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span></span>  
<span data-ttu-id="6acbb-117">matriz bidimensional</span><span class="sxs-lookup"><span data-stu-id="6acbb-117">Two-dimensional array</span></span>  
  
 <span data-ttu-id="6acbb-118">![Diagrama gráfico de tres&#45;una matriz unidimensional](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span><span class="sxs-lookup"><span data-stu-id="6acbb-118">![Graphic diagram of three&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span></span>  
<span data-ttu-id="6acbb-119">matriz tridimensional</span><span class="sxs-lookup"><span data-stu-id="6acbb-119">Three-dimensional array</span></span>  
  
### <a name="one-dimension"></a><span data-ttu-id="6acbb-120">Una dimensión</span><span class="sxs-lookup"><span data-stu-id="6acbb-120">One Dimension</span></span>  
 <span data-ttu-id="6acbb-121">Muchas matrices tienen solo una dimensión, como el número de personas de cada edad.</span><span class="sxs-lookup"><span data-stu-id="6acbb-121">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="6acbb-122">El único requisito para especificar un elemento es la edad para los que ese elemento contiene el recuento.</span><span class="sxs-lookup"><span data-stu-id="6acbb-122">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="6acbb-123">Por lo tanto, este tipo de matriz utiliza sólo un índice.</span><span class="sxs-lookup"><span data-stu-id="6acbb-123">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="6acbb-124">En el ejemplo siguiente se declara una variable que contenga un *matriz unidimensional* de edad recuentos de edades de 0 a 120.</span><span class="sxs-lookup"><span data-stu-id="6acbb-124">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="6acbb-125">Dos dimensiones</span><span class="sxs-lookup"><span data-stu-id="6acbb-125">Two Dimensions</span></span>  
 <span data-ttu-id="6acbb-126">Algunas matrices tienen dos dimensiones, como el número de oficinas de cada planta de cada edificio en un campus.</span><span class="sxs-lookup"><span data-stu-id="6acbb-126">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="6acbb-127">La especificación de un elemento requiere el número de edificio y piso y cada elemento contiene el recuento para esa combinación de edificio y piso.</span><span class="sxs-lookup"><span data-stu-id="6acbb-127">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="6acbb-128">Por lo tanto, este tipo de matriz utiliza dos índices.</span><span class="sxs-lookup"><span data-stu-id="6acbb-128">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="6acbb-129">En el ejemplo siguiente se declara una variable que contenga un *matriz bidimensional* de recuentos de office, de 0 a 40 edificios y 0 a 5 plantas.</span><span class="sxs-lookup"><span data-stu-id="6acbb-129">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="6acbb-130">Una matriz bidimensional también se denomina un *matriz rectangular*.</span><span class="sxs-lookup"><span data-stu-id="6acbb-130">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="6acbb-131">Tres dimensiones</span><span class="sxs-lookup"><span data-stu-id="6acbb-131">Three Dimensions</span></span>  
 <span data-ttu-id="6acbb-132">Algunas matrices tienen tres dimensiones, como los valores de un espacio tridimensional.</span><span class="sxs-lookup"><span data-stu-id="6acbb-132">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="6acbb-133">Este tipo de matriz utiliza tres índices, que se representan en este caso la x, y y las coordenadas z del espacio físico.</span><span class="sxs-lookup"><span data-stu-id="6acbb-133">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="6acbb-134">En el ejemplo siguiente se declara una variable que contenga un *matriz tridimensional* de temperatura del aire en diversos puntos en un volumen tridimensional.</span><span class="sxs-lookup"><span data-stu-id="6acbb-134">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="6acbb-135">Más de tres dimensiones</span><span class="sxs-lookup"><span data-stu-id="6acbb-135">More than Three Dimensions</span></span>  
 <span data-ttu-id="6acbb-136">Aunque una matriz puede tener como máximo 32 dimensiones, es poco habitual tener más de tres.</span><span class="sxs-lookup"><span data-stu-id="6acbb-136">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6acbb-137">Cuando se agregan dimensiones a una matriz, el almacenamiento total necesario para la matriz aumenta considerablemente, por lo que use las matrices multidimensionales con cuidado.</span><span class="sxs-lookup"><span data-stu-id="6acbb-137">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="6acbb-138">Uso de distintas dimensiones</span><span class="sxs-lookup"><span data-stu-id="6acbb-138">Using Different Dimensions</span></span>  
 <span data-ttu-id="6acbb-139">Suponga que desea realizar un seguimiento de los importes de ventas para todos los días del mes actual.</span><span class="sxs-lookup"><span data-stu-id="6acbb-139">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="6acbb-140">Puede declarar una matriz unidimensional con 31 elementos, uno para cada día del mes, como en el ejemplo siguiente se muestra.</span><span class="sxs-lookup"><span data-stu-id="6acbb-140">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="6acbb-141">Ahora suponga que desea realizar un seguimiento de la misma información no solo para todos los días del mes, sino también para todos los meses del año.</span><span class="sxs-lookup"><span data-stu-id="6acbb-141">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="6acbb-142">Puede declarar una matriz bidimensional con 12 filas (para los meses) y 31 columnas (para los días), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6acbb-142">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="6acbb-143">Ahora suponga que decide tiene la matriz contienen información durante más de un año.</span><span class="sxs-lookup"><span data-stu-id="6acbb-143">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="6acbb-144">Si desea realizar un seguimiento de los importes de ventas durante 5 años, podría declarar una matriz tridimensional con 5 capas, 12 filas y 31 columnas, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6acbb-144">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="6acbb-145">Tenga en cuenta que, dado que cada índice varía entre 0 y su valor máximo, cada dimensión de `salesAmounts` se declara como uno menos que la longitud necesaria para esa dimensión.</span><span class="sxs-lookup"><span data-stu-id="6acbb-145">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="6acbb-146">Tenga en cuenta también que el tamaño de la matriz aumenta con cada nueva dimensión.</span><span class="sxs-lookup"><span data-stu-id="6acbb-146">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="6acbb-147">Los tres tamaños en los ejemplos anteriores son 31, 372 y 1.860 elementos respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6acbb-147">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6acbb-148">Puede crear una matriz sin utilizar el `Dim` instrucción o el `New` cláusula.</span><span class="sxs-lookup"><span data-stu-id="6acbb-148">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="6acbb-149">Por ejemplo, puede llamar a la <xref:System.Array.CreateInstance%2A> método u otro componente puede pasar el código de una matriz creada de esta manera.</span><span class="sxs-lookup"><span data-stu-id="6acbb-149">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="6acbb-150">Dicha matriz puede tener un límite inferior distinto de 0.</span><span class="sxs-lookup"><span data-stu-id="6acbb-150">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="6acbb-151">Siempre puede probar el límite inferior de una dimensión mediante el <xref:System.Array.GetLowerBound%2A> método o la `LBound` función.</span><span class="sxs-lookup"><span data-stu-id="6acbb-151">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acbb-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="6acbb-152">See also</span></span>
- [<span data-ttu-id="6acbb-153">Matrices</span><span class="sxs-lookup"><span data-stu-id="6acbb-153">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="6acbb-154">Solución de problemas de matrices</span><span class="sxs-lookup"><span data-stu-id="6acbb-154">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
