---
title: Tipos de datos compuestos (Visual Basic)
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: c7243108d0b7c06f48a21f343321322bb2cc2946
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560287"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="acde3-102">Tipos de datos compuestos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acde3-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="acde3-103">Además de los tipos de datos básicos que proporciona Visual Basic, también puede ensamblar los elementos de distintos tipos para crear *tipos de datos compuestos* como clases, matrices y estructuras.</span><span class="sxs-lookup"><span data-stu-id="acde3-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="acde3-104">Puede crear tipos de datos compuestos de tipos elementales y de otros tipos compuestos.</span><span class="sxs-lookup"><span data-stu-id="acde3-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="acde3-105">Por ejemplo, puede definir una matriz de elementos de estructura o una estructura con miembros de la matriz.</span><span class="sxs-lookup"><span data-stu-id="acde3-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="acde3-106">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="acde3-106">Data Types</span></span>  
 <span data-ttu-id="acde3-107">Un tipo compuesto es diferente del tipo de datos de cualquiera de sus componentes.</span><span class="sxs-lookup"><span data-stu-id="acde3-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="acde3-108">Por ejemplo, una matriz de `Integer` elementos no es de la `Integer` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="acde3-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="acde3-109">Un tipo de datos de matriz normalmente se representa mediante el tipo de elemento, paréntesis y comas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="acde3-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="acde3-110">Por ejemplo, una matriz unidimensional de `String` elementos se representa como `String()`y una matriz bidimensional de `Boolean` elementos se representa como `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="acde3-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="acde3-111">Tipos de estructura</span><span class="sxs-lookup"><span data-stu-id="acde3-111">Structure Types</span></span>  
 <span data-ttu-id="acde3-112">No hay ningún tipo de datos que incluye todas las estructuras.</span><span class="sxs-lookup"><span data-stu-id="acde3-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="acde3-113">En su lugar, cada definición de una estructura representa un tipo de datos único, incluso si dos estructuras de definan elementos idénticos en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="acde3-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="acde3-114">Sin embargo, si crea dos o más instancias de la misma estructura, Visual Basic considera que son del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="acde3-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="acde3-115">Tuplas</span><span class="sxs-lookup"><span data-stu-id="acde3-115">Tuples</span></span>

<span data-ttu-id="acde3-116">Una tupla es una estructura ligera que contiene dos o más campos cuyos tipos predefinidos.</span><span class="sxs-lookup"><span data-stu-id="acde3-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="acde3-117">Las tuplas se admiten a partir de Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="acde3-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="acde3-118">Las tuplas se usan normalmente para devolver varios valores de una única llamada al método sin tener que pasar argumentos por referencia o empaquetar los campos devueltos en una clase o estructura con más ligeras y pesadas.</span><span class="sxs-lookup"><span data-stu-id="acde3-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="acde3-119">Consulte la [tuplas](tuples.md) tema para obtener más información sobre las tuplas.</span><span class="sxs-lookup"><span data-stu-id="acde3-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="acde3-120">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="acde3-120">Array Types</span></span>  
 <span data-ttu-id="acde3-121">No hay ningún tipo de datos que incluya todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="acde3-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="acde3-122">El tipo de datos de una instancia determinada de una matriz se determina por el texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="acde3-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
-   <span data-ttu-id="acde3-123">El hecho de ser una matriz</span><span class="sxs-lookup"><span data-stu-id="acde3-123">The fact of being an array</span></span>  
  
-   <span data-ttu-id="acde3-124">El rango (número de dimensiones) de la matriz</span><span class="sxs-lookup"><span data-stu-id="acde3-124">The rank (number of dimensions) of the array</span></span>  
  
-   <span data-ttu-id="acde3-125">El tipo de elemento de la matriz</span><span class="sxs-lookup"><span data-stu-id="acde3-125">The element type of the array</span></span>  
  
 <span data-ttu-id="acde3-126">En concreto, la longitud de una dimensión determinada no es parte de la instancia tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="acde3-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="acde3-127">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="acde3-127">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="acde3-128">En el ejemplo anterior, las variables de matriz `arrayA` y `arrayB` se consideran del mismo tipo de datos: `Byte()` , aunque se hayan inicializado con distintas longitudes.</span><span class="sxs-lookup"><span data-stu-id="acde3-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="acde3-129">Las variables `arrayB` y `arrayC` no son del mismo tipo, porque sus tipos de elemento son diferentes.</span><span class="sxs-lookup"><span data-stu-id="acde3-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="acde3-130">Las variables `arrayC` y `arrayD` no son del mismo tipo porque sus rangos son diferentes.</span><span class="sxs-lookup"><span data-stu-id="acde3-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="acde3-131">Las variables `arrayD` y `arrayE` tienen el mismo tipo — `Short(,)` , porque sus rangos y tipos de elemento son los mismos, aunque `arrayD` aún no está inicializado.</span><span class="sxs-lookup"><span data-stu-id="acde3-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="acde3-132">Para obtener más información sobre matrices, vea [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="acde3-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="acde3-133">Tipos de clase</span><span class="sxs-lookup"><span data-stu-id="acde3-133">Class Types</span></span>  
 <span data-ttu-id="acde3-134">No hay ningún tipo de datos que incluye todas las clases.</span><span class="sxs-lookup"><span data-stu-id="acde3-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="acde3-135">Aunque una clase puede heredar de otra clase, cada uno de ellos es un tipo de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="acde3-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="acde3-136">Varias instancias de la misma clase son del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="acde3-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="acde3-137">Si asigna una variable de instancia de clase a otra, no sólo tienen los mismos datos de tipo, que señalan a la misma instancia de clase en la memoria.</span><span class="sxs-lookup"><span data-stu-id="acde3-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="acde3-138">Para obtener más información sobre las clases, vea [objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="acde3-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acde3-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="acde3-139">See also</span></span>
- [<span data-ttu-id="acde3-140">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="acde3-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="acde3-141">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="acde3-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="acde3-142">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="acde3-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="acde3-143">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="acde3-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="acde3-144">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="acde3-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="acde3-145">Estructuras</span><span class="sxs-lookup"><span data-stu-id="acde3-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="acde3-146">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="acde3-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="acde3-147">Cómo: Contener más de un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="acde3-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
