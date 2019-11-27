---
title: Tipos de datos compuestos
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
ms.openlocfilehash: 1c099c5082f1c4173a50c70998c99135c94821e6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346375"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="dfd9d-102">Tipos de datos compuestos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfd9d-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="dfd9d-103">Además de los tipos de datos elementales Visual Basic proporciona, también puede ensamblar elementos de tipos diferentes para crear *tipos de datos compuestos* como estructuras, matrices y clases.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="dfd9d-104">Puede crear tipos de datos compuestos a partir de tipos elementales y de otros tipos compuestos.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="dfd9d-105">Por ejemplo, puede definir una matriz de elementos de estructura o una estructura con miembros de matriz.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="dfd9d-106">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="dfd9d-106">Data Types</span></span>  
 <span data-ttu-id="dfd9d-107">Un tipo compuesto es diferente del tipo de datos de cualquiera de sus componentes.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="dfd9d-108">Por ejemplo, una matriz de elementos `Integer` no es del tipo de datos `Integer`.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="dfd9d-109">Normalmente, un tipo de datos de matriz se representa mediante el tipo de elemento, paréntesis y comas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="dfd9d-110">Por ejemplo, una matriz unidimensional de elementos `String` se representa como `String()`y una matriz bidimensional de elementos `Boolean` se representa como `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="dfd9d-111">Tipos de estructura</span><span class="sxs-lookup"><span data-stu-id="dfd9d-111">Structure Types</span></span>  
 <span data-ttu-id="dfd9d-112">No hay ningún tipo de datos único que incluya todas las estructuras.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="dfd9d-113">En su lugar, cada definición de una estructura representa un tipo de datos único, incluso si dos estructuras definen elementos idénticos en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="dfd9d-114">Sin embargo, si crea dos o más instancias de la misma estructura, Visual Basic considera que son del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="dfd9d-115">Tuplas</span><span class="sxs-lookup"><span data-stu-id="dfd9d-115">Tuples</span></span>

<span data-ttu-id="dfd9d-116">Una tupla es una estructura ligera que contiene dos o más campos cuyos tipos están predefinidos.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="dfd9d-117">Las tuplas se admiten a partir de Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="dfd9d-118">Las tuplas se suelen usar para devolver varios valores de una sola llamada al método sin tener que pasar argumentos por referencia o empaquetar los campos devueltos en una estructura o clase más pesada.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="dfd9d-119">Vea el tema sobre [tuplas](tuples.md) para obtener más información sobre las tuplas.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="dfd9d-120">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="dfd9d-120">Array Types</span></span>  
 <span data-ttu-id="dfd9d-121">No hay ningún tipo de datos único que comprenda todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="dfd9d-122">El tipo de datos de una instancia determinada de una matriz viene determinado por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dfd9d-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="dfd9d-123">El hecho de ser una matriz</span><span class="sxs-lookup"><span data-stu-id="dfd9d-123">The fact of being an array</span></span>  
  
- <span data-ttu-id="dfd9d-124">Rango (número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-124">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="dfd9d-125">El tipo de elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-125">The element type of the array</span></span>  
  
 <span data-ttu-id="dfd9d-126">En concreto, la longitud de una dimensión determinada no forma parte del tipo de datos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="dfd9d-127">En el ejemplo siguiente se ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-127">The following example illustrates this.</span></span>  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="dfd9d-128">En el ejemplo anterior, las variables de matriz `arrayA` y `arrayB` se consideran del mismo tipo de datos, `Byte()`, aunque se hayan inicializado a longitudes diferentes.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="dfd9d-129">Las variables `arrayB` y `arrayC` no son del mismo tipo porque sus tipos de elemento son diferentes.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="dfd9d-130">Las variables `arrayC` y `arrayD` no son del mismo tipo porque sus rangos son diferentes.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="dfd9d-131">Las variables `arrayD` y `arrayE` tienen el mismo tipo, `Short(,)`, porque sus rangos y tipos de elemento son los mismos, aunque aún no se ha inicializado `arrayD`.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="dfd9d-132">Para obtener más información sobre las matrices, vea [matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="dfd9d-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="dfd9d-133">Tipos de clase</span><span class="sxs-lookup"><span data-stu-id="dfd9d-133">Class Types</span></span>  
 <span data-ttu-id="dfd9d-134">No hay ningún tipo de datos único que incluya todas las clases.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="dfd9d-135">Aunque una clase puede heredar de otra clase, cada una es un tipo de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="dfd9d-136">Varias instancias de la misma clase tienen el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="dfd9d-137">Si asigna una variable de instancia de clase a otra, y no solo tienen el mismo tipo de datos, apuntan a la misma instancia de clase en la memoria.</span><span class="sxs-lookup"><span data-stu-id="dfd9d-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="dfd9d-138">Para obtener más información sobre las clases, vea [objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="dfd9d-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd9d-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfd9d-139">See also</span></span>

- [<span data-ttu-id="dfd9d-140">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="dfd9d-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="dfd9d-141">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="dfd9d-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="dfd9d-142">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfd9d-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="dfd9d-143">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="dfd9d-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="dfd9d-144">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfd9d-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="dfd9d-145">Estructuras</span><span class="sxs-lookup"><span data-stu-id="dfd9d-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="dfd9d-146">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="dfd9d-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="dfd9d-147">Contener más de un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="dfd9d-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
