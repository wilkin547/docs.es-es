---
title: Instrucción ReDim
ms.date: 07/20/2015
f1_keywords:
- vb.ReDim
- vb.Preserve
helpviewer_keywords:
- fixed-length strings [Visual Basic], declaring
- ReDim statement [Visual Basic], syntax
- dynamic arrays [Visual Basic], ReDim statement
- arrays [Visual Basic], reallocating
- arrays [Visual Basic], reinitializing
- arrays [Visual Basic], dimensions
- scalars, and arrays
- scalars
- declarations [Visual Basic], dynamic arrays
- variables [Visual Basic], scalar
- ReDim statement [Visual Basic]
- data types [Visual Basic], assigning
- As keyword [Visual Basic], in ReDim statement
- To keyword [Visual Basic], ReDim statement
- arrays [Visual Basic], declaring
- Preserve keyword [Visual Basic], ReDim statement
- storage [Visual Basic], allocating
- arrays [Visual Basic], and scalars
- declaration statements [Visual Basic]
- scalar variables [Visual Basic]
ms.assetid: ad1c5e07-dcd7-4ae1-a79e-ad3f2dcc2083
ms.openlocfilehash: 17bc806f2e92c61f1dd7425de40b1a68f926a583
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872031"
---
# <a name="redim-statement-visual-basic"></a><span data-ttu-id="57bac-102">Instrucción ReDim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57bac-102">ReDim Statement (Visual Basic)</span></span>

<span data-ttu-id="57bac-103">Reasigna espacio de almacenamiento a una variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-103">Reallocates storage space for an array variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57bac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57bac-104">Syntax</span></span>  
  
```vb  
ReDim [ Preserve ] name(boundlist) [ ,  name(boundlist) [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="57bac-105">Partes</span><span class="sxs-lookup"><span data-stu-id="57bac-105">Parts</span></span>  
  
|<span data-ttu-id="57bac-106">Término</span><span class="sxs-lookup"><span data-stu-id="57bac-106">Term</span></span>|<span data-ttu-id="57bac-107">Definición</span><span class="sxs-lookup"><span data-stu-id="57bac-107">Definition</span></span>|  
|----------|----------------|  
|`Preserve`|<span data-ttu-id="57bac-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="57bac-108">Optional.</span></span> <span data-ttu-id="57bac-109">Modificador usado para mantener los datos en la matriz existente cuando cambia el tamaño solamente de la última dimensión.</span><span class="sxs-lookup"><span data-stu-id="57bac-109">Modifier used to preserve the data in the existing array when you change the size of only the last dimension.</span></span>|  
|`name`|<span data-ttu-id="57bac-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="57bac-110">Required.</span></span> <span data-ttu-id="57bac-111">Nombre de la variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-111">Name of the array variable.</span></span> <span data-ttu-id="57bac-112">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="57bac-112">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
|`boundlist`|<span data-ttu-id="57bac-113">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="57bac-113">Required.</span></span> <span data-ttu-id="57bac-114">Lista de límites de cada dimensión de la matriz redefinida.</span><span class="sxs-lookup"><span data-stu-id="57bac-114">List of bounds of each dimension of the redefined array.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57bac-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57bac-115">Remarks</span></span>  

 <span data-ttu-id="57bac-116">Puede utilizar la instrucción `ReDim` para cambiar el tamaño de una o más dimensiones de una matriz que ya se ha declarado.</span><span class="sxs-lookup"><span data-stu-id="57bac-116">You can use the `ReDim` statement to change the size of one or more dimensions of an array that has already been declared.</span></span> <span data-ttu-id="57bac-117">Si tiene una matriz grande y ya no necesita algunos de sus elementos, `ReDim` puede liberar memoria al reducir el tamaño de la matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-117">If you have a large array and you no longer need some of its elements, `ReDim` can free up memory by reducing the array size.</span></span> <span data-ttu-id="57bac-118">Por otro lado, si la matriz necesita más elementos, `ReDim` puede agregarlos.</span><span class="sxs-lookup"><span data-stu-id="57bac-118">On the other hand, if your array needs more elements, `ReDim` can add them.</span></span>  
  
 <span data-ttu-id="57bac-119">La instrucción `ReDim` está destinada solo a las matrices.</span><span class="sxs-lookup"><span data-stu-id="57bac-119">The `ReDim` statement is intended only for arrays.</span></span> <span data-ttu-id="57bac-120">No es válida en escalares (variables que contienen un único valor), colecciones ni estructuras.</span><span class="sxs-lookup"><span data-stu-id="57bac-120">It's not valid on scalars (variables that contain only a single value), collections, or structures.</span></span> <span data-ttu-id="57bac-121">Tenga en cuenta que, si declara una variable de tipo `Array`, la instrucción `ReDim` no tiene suficiente información de tipo para crear la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-121">Note that if you declare a variable to be of type `Array`, the `ReDim` statement doesn't have sufficient type information to create the new array.</span></span>  
  
 <span data-ttu-id="57bac-122">Solo puede usar `ReDim` en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="57bac-122">You can use `ReDim` only at procedure level.</span></span> <span data-ttu-id="57bac-123">Por lo tanto, el contexto de declaración de la variable debe ser un procedimiento; no puede ser un archivo de código fuente, un espacio de nombres, una interfaz, una clase, una estructura, un módulo o un bloque.</span><span class="sxs-lookup"><span data-stu-id="57bac-123">Therefore, the declaration context for the variable must be a procedure; it can't be a source file, a namespace, an interface, a class, a structure, a module, or a block.</span></span> <span data-ttu-id="57bac-124">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="57bac-124">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="57bac-125">Reglas</span><span class="sxs-lookup"><span data-stu-id="57bac-125">Rules</span></span>  
  
- <span data-ttu-id="57bac-126">**Varias variables.**</span><span class="sxs-lookup"><span data-stu-id="57bac-126">**Multiple Variables.**</span></span> <span data-ttu-id="57bac-127">Puede cambiar el tamaño de varias variables de matriz en la misma instrucción de declaración y especificar las `name` `boundlist` partes y para cada variable.</span><span class="sxs-lookup"><span data-stu-id="57bac-127">You can resize several array variables in the same declaration statement and specify the `name` and `boundlist` parts for each variable.</span></span> <span data-ttu-id="57bac-128">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="57bac-128">Multiple variables are separated by commas.</span></span>  
  
- <span data-ttu-id="57bac-129">**Límites de matriz.**</span><span class="sxs-lookup"><span data-stu-id="57bac-129">**Array Bounds.**</span></span> <span data-ttu-id="57bac-130">Cada entrada en `boundlist` puede especificar los límites inferior y superior de esa dimensión.</span><span class="sxs-lookup"><span data-stu-id="57bac-130">Each entry in `boundlist` can specify the lower and upper bounds of that dimension.</span></span> <span data-ttu-id="57bac-131">El límite inferior es siempre 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="57bac-131">The lower bound is always 0 (zero).</span></span> <span data-ttu-id="57bac-132">El límite superior es el valor de índice posible más alto para esa dimensión, no la longitud de la dimensión (que es el límite superior más uno).</span><span class="sxs-lookup"><span data-stu-id="57bac-132">The upper bound is the highest possible index value for that dimension, not the length of the dimension (which is the upper bound plus one).</span></span> <span data-ttu-id="57bac-133">El índice de cada dimensión puede variar entre 0 y el valor del límite superior.</span><span class="sxs-lookup"><span data-stu-id="57bac-133">The index for each dimension can vary from 0 through its upper bound value.</span></span>  
  
     <span data-ttu-id="57bac-134">El número de dimensiones de `boundlist` debe coincidir con el número de dimensiones (rango) de la matriz original.</span><span class="sxs-lookup"><span data-stu-id="57bac-134">The number of dimensions in `boundlist` must match the original number of dimensions (rank) of the array.</span></span>  
  
- <span data-ttu-id="57bac-135">**Tipos de datos.**</span><span class="sxs-lookup"><span data-stu-id="57bac-135">**Data Types.**</span></span> <span data-ttu-id="57bac-136">La `ReDim` instrucción no puede cambiar el tipo de datos de una variable de matriz o sus elementos.</span><span class="sxs-lookup"><span data-stu-id="57bac-136">The `ReDim` statement cannot change the data type of an array variable or its elements.</span></span>  
  
- <span data-ttu-id="57bac-137">**Inicial.**</span><span class="sxs-lookup"><span data-stu-id="57bac-137">**Initialization.**</span></span> <span data-ttu-id="57bac-138">La `ReDim` instrucción no puede proporcionar nuevos valores de inicialización para los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-138">The `ReDim` statement cannot provide new initialization values for the array elements.</span></span>  
  
- <span data-ttu-id="57bac-139">**Criterios.**</span><span class="sxs-lookup"><span data-stu-id="57bac-139">**Rank.**</span></span> <span data-ttu-id="57bac-140">La `ReDim` instrucción no puede cambiar el rango (número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-140">The `ReDim` statement cannot change the rank (the number of dimensions) of the array.</span></span>  
  
- <span data-ttu-id="57bac-141">**Cambiar el tamaño con Preserve.**</span><span class="sxs-lookup"><span data-stu-id="57bac-141">**Resizing with Preserve.**</span></span> <span data-ttu-id="57bac-142">Si usa `Preserve` , solo puede cambiar el tamaño de la última dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-142">If you use `Preserve`, you can resize only the last dimension of the array.</span></span> <span data-ttu-id="57bac-143">Para cualquier otra dimensión, debe especificar el límite de la matriz existente.</span><span class="sxs-lookup"><span data-stu-id="57bac-143">For every other dimension, you must specify the bound of the existing array.</span></span>  
  
     <span data-ttu-id="57bac-144">Por ejemplo, si su matriz tiene solo una dimensión, puede cambiar el tamaño de esa dimensión y conservar todo el contenido de la matriz, ya que es la última y única dimensión.</span><span class="sxs-lookup"><span data-stu-id="57bac-144">For example, if your array has only one dimension, you can resize that dimension and still preserve all the contents of the array, because you are changing the last and only dimension.</span></span> <span data-ttu-id="57bac-145">Sin embargo, si su matriz tiene dos o más dimensiones, puede cambiar solamente el tamaño de la última dimensión si utiliza `Preserve`.</span><span class="sxs-lookup"><span data-stu-id="57bac-145">However, if your array has two or more dimensions, you can change the size of only the last dimension if you use `Preserve`.</span></span>  
  
- <span data-ttu-id="57bac-146">**Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="57bac-146">**Properties.**</span></span> <span data-ttu-id="57bac-147">Puede usar `ReDim` en una propiedad que contiene una matriz de valores.</span><span class="sxs-lookup"><span data-stu-id="57bac-147">You can use `ReDim` on a property that holds an array of values.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="57bac-148">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="57bac-148">Behavior</span></span>  
  
- <span data-ttu-id="57bac-149">**Reemplazo de matriz.**</span><span class="sxs-lookup"><span data-stu-id="57bac-149">**Array Replacement.**</span></span> <span data-ttu-id="57bac-150">`ReDim` libera la matriz existente y crea una nueva matriz con el mismo rango.</span><span class="sxs-lookup"><span data-stu-id="57bac-150">`ReDim` releases the existing array and creates a new array with the same rank.</span></span> <span data-ttu-id="57bac-151">La nueva matriz reemplaza la matriz liberada en la variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-151">The new array replaces the released array in the array variable.</span></span>  
  
- <span data-ttu-id="57bac-152">**Inicialización sin Preserve.**</span><span class="sxs-lookup"><span data-stu-id="57bac-152">**Initialization without Preserve.**</span></span> <span data-ttu-id="57bac-153">Si no especifica `Preserve` , `ReDim` inicializa los elementos de la nueva matriz utilizando el valor predeterminado para su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="57bac-153">If you do not specify `Preserve`, `ReDim` initializes the elements of the new array by using the default value for their data type.</span></span>  
  
- <span data-ttu-id="57bac-154">**Inicialización con Preserve.**</span><span class="sxs-lookup"><span data-stu-id="57bac-154">**Initialization with Preserve.**</span></span> <span data-ttu-id="57bac-155">Si especifica `Preserve` , Visual Basic copia los elementos de la matriz existente en la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-155">If you specify `Preserve`, Visual Basic copies the elements from the existing array to the new array.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57bac-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57bac-156">Example</span></span>  

 <span data-ttu-id="57bac-157">El ejemplo siguiente aumenta el tamaño de la última dimensión de una matriz dinámica sin perder los datos existentes en la matriz y, a continuación, reduce el tamaño con pérdida de datos parcial.</span><span class="sxs-lookup"><span data-stu-id="57bac-157">The following example increases the size of the last dimension of a dynamic array without losing any existing data in the array, and then decreases the size with partial data loss.</span></span> <span data-ttu-id="57bac-158">Por último, reduce el tamaño a su valor original y reinicializa todos los elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-158">Finally, it decreases the size back to its original value and reinitializes all the array elements.</span></span>  
  
 [!code-vb[VbVbalrStatements#52](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#52)]  
  
 <span data-ttu-id="57bac-159">La instrucción `Dim` crea una nueva matriz con tres dimensiones.</span><span class="sxs-lookup"><span data-stu-id="57bac-159">The `Dim` statement creates a new array with three dimensions.</span></span> <span data-ttu-id="57bac-160">Cada dimensión se declara con un límite de 10, por lo que el índice de matriz para cada dimensión puede oscilar entre 0 y 10.</span><span class="sxs-lookup"><span data-stu-id="57bac-160">Each dimension is declared with a bound of 10, so the array index for each dimension can range from 0 through 10.</span></span> <span data-ttu-id="57bac-161">En el siguiente análisis, las tres dimensiones se conocen como capa, fila y columna.</span><span class="sxs-lookup"><span data-stu-id="57bac-161">In the following discussion, the three dimensions are referred to as layer, row, and column.</span></span>  
  
 <span data-ttu-id="57bac-162">El primer `ReDim` crea una nueva matriz que reemplaza la matriz existente en la variable `intArray`.</span><span class="sxs-lookup"><span data-stu-id="57bac-162">The first `ReDim` creates a new array which replaces the existing array in variable `intArray`.</span></span> <span data-ttu-id="57bac-163">`ReDim` copia todos los elementos de la matriz existente en la nueva matriz.</span><span class="sxs-lookup"><span data-stu-id="57bac-163">`ReDim` copies all the elements from the existing array into the new array.</span></span> <span data-ttu-id="57bac-164">También agrega 10 columnas más al final de cada fila en cada capa e inicializa los elementos de estas nuevas columnas a 0 (el valor predeterminado de `Integer`, que es el tipo de elemento de la matriz).</span><span class="sxs-lookup"><span data-stu-id="57bac-164">It also adds 10 more columns to the end of every row in every layer and initializes the elements in these new columns to 0 (the default value of `Integer`, which is the element type of the array).</span></span>  
  
 <span data-ttu-id="57bac-165">El segundo `ReDim` crea otra nueva matriz y copia todos los elementos que quepan.</span><span class="sxs-lookup"><span data-stu-id="57bac-165">The second `ReDim` creates another new array and copies all the elements that fit.</span></span> <span data-ttu-id="57bac-166">Sin embargo, se pierden cinco columnas del final de cada fila en cada capa.</span><span class="sxs-lookup"><span data-stu-id="57bac-166">However, five columns are lost from the end of every row in every layer.</span></span> <span data-ttu-id="57bac-167">No es un problema si ya ha terminado de utilizar estas columnas.</span><span class="sxs-lookup"><span data-stu-id="57bac-167">This is not a problem if you have finished using these columns.</span></span> <span data-ttu-id="57bac-168">Reducir el tamaño de una matriz grande puede liberar memoria que ya no necesite.</span><span class="sxs-lookup"><span data-stu-id="57bac-168">Reducing the size of a large array can free up memory that you no longer need.</span></span>  
  
 <span data-ttu-id="57bac-169">El tercer `ReDim` crea otra nueva matriz y quita otras cinco columnas del final de cada fila en cada capa.</span><span class="sxs-lookup"><span data-stu-id="57bac-169">The third `ReDim` creates another new array and removes another five columns from the end of every row in every layer.</span></span> <span data-ttu-id="57bac-170">Esta vez no copia los elementos existentes.</span><span class="sxs-lookup"><span data-stu-id="57bac-170">This time it does not copy any existing elements.</span></span> <span data-ttu-id="57bac-171">Esta instrucción revierte la matriz a su tamaño original.</span><span class="sxs-lookup"><span data-stu-id="57bac-171">This statement reverts the array to its original size.</span></span> <span data-ttu-id="57bac-172">Dado que la instrucción no incluye el modificador `Preserve`, establece todos los elementos de matriz con sus valores predeterminados originales.</span><span class="sxs-lookup"><span data-stu-id="57bac-172">Because the statement doesn't include the `Preserve` modifier, it sets all array elements to their original default values.</span></span>  
  
 <span data-ttu-id="57bac-173">Para obtener más ejemplos, consulte [matrices](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="57bac-173">For additional examples, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57bac-174">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57bac-174">See also</span></span>

- <xref:System.IndexOutOfRangeException>
- [<span data-ttu-id="57bac-175">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="57bac-175">Const Statement</span></span>](const-statement.md)
- [<span data-ttu-id="57bac-176">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="57bac-176">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="57bac-177">Instrucción Erase</span><span class="sxs-lookup"><span data-stu-id="57bac-177">Erase Statement</span></span>](erase-statement.md)
- [<span data-ttu-id="57bac-178">Nothing</span><span class="sxs-lookup"><span data-stu-id="57bac-178">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="57bac-179">Matrices</span><span class="sxs-lookup"><span data-stu-id="57bac-179">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
