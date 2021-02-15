---
description: 'Más información sobre: tipos de datos compuestos (Visual Basic)'
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
ms.openlocfilehash: 981ee36c416f2524be155b1238f5b306c98aa92b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456437"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="d91ca-103">Tipos de datos compuestos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d91ca-103">Composite Data Types (Visual Basic)</span></span>

<span data-ttu-id="d91ca-104">Además de los tipos de datos elementales Visual Basic proporciona, también puede ensamblar elementos de tipos diferentes para crear *tipos de datos compuestos* como estructuras, matrices y clases.</span><span class="sxs-lookup"><span data-stu-id="d91ca-104">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="d91ca-105">Puede crear tipos de datos compuestos a partir de tipos elementales y de otros tipos compuestos.</span><span class="sxs-lookup"><span data-stu-id="d91ca-105">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="d91ca-106">Por ejemplo, puede definir una matriz de elementos de estructura o una estructura con miembros de matriz.</span><span class="sxs-lookup"><span data-stu-id="d91ca-106">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="d91ca-107">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d91ca-107">Data Types</span></span>  

 <span data-ttu-id="d91ca-108">Un tipo compuesto es diferente del tipo de datos de cualquiera de sus componentes.</span><span class="sxs-lookup"><span data-stu-id="d91ca-108">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="d91ca-109">Por ejemplo, una matriz de `Integer` elementos no es del `Integer` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d91ca-109">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="d91ca-110">Normalmente, un tipo de datos de matriz se representa mediante el tipo de elemento, paréntesis y comas según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d91ca-110">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="d91ca-111">Por ejemplo, una matriz unidimensional de `String` elementos se representa como `String()` y una matriz bidimensional de `Boolean` elementos se representa como `Boolean(,)` .</span><span class="sxs-lookup"><span data-stu-id="d91ca-111">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="d91ca-112">Tipos de estructura</span><span class="sxs-lookup"><span data-stu-id="d91ca-112">Structure Types</span></span>  

 <span data-ttu-id="d91ca-113">No hay ningún tipo de datos único que incluya todas las estructuras.</span><span class="sxs-lookup"><span data-stu-id="d91ca-113">There is no single data type comprising all structures.</span></span> <span data-ttu-id="d91ca-114">En su lugar, cada definición de una estructura representa un tipo de datos único, incluso si dos estructuras definen elementos idénticos en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="d91ca-114">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="d91ca-115">Sin embargo, si crea dos o más instancias de la misma estructura, Visual Basic considera que son del mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d91ca-115">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="d91ca-116">Tuplas</span><span class="sxs-lookup"><span data-stu-id="d91ca-116">Tuples</span></span>

<span data-ttu-id="d91ca-117">Una tupla es una estructura ligera que contiene dos o más campos cuyos tipos están predefinidos.</span><span class="sxs-lookup"><span data-stu-id="d91ca-117">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="d91ca-118">Las tuplas se admiten a partir de Visual Basic 2017.</span><span class="sxs-lookup"><span data-stu-id="d91ca-118">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="d91ca-119">Las tuplas se suelen usar para devolver varios valores de una sola llamada al método sin tener que pasar argumentos por referencia o empaquetar los campos devueltos en una estructura o clase más pesada.</span><span class="sxs-lookup"><span data-stu-id="d91ca-119">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="d91ca-120">Vea el tema sobre [tuplas](tuples.md) para obtener más información sobre las tuplas.</span><span class="sxs-lookup"><span data-stu-id="d91ca-120">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="d91ca-121">Tipos de matriz</span><span class="sxs-lookup"><span data-stu-id="d91ca-121">Array Types</span></span>  

 <span data-ttu-id="d91ca-122">No hay ningún tipo de datos único que comprenda todas las matrices.</span><span class="sxs-lookup"><span data-stu-id="d91ca-122">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="d91ca-123">El tipo de datos de una instancia determinada de una matriz viene determinado por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d91ca-123">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="d91ca-124">El hecho de ser una matriz</span><span class="sxs-lookup"><span data-stu-id="d91ca-124">The fact of being an array</span></span>  
  
- <span data-ttu-id="d91ca-125">Rango (número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d91ca-125">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="d91ca-126">El tipo de elemento de la matriz.</span><span class="sxs-lookup"><span data-stu-id="d91ca-126">The element type of the array</span></span>  
  
 <span data-ttu-id="d91ca-127">En concreto, la longitud de una dimensión determinada no forma parte del tipo de datos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="d91ca-127">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="d91ca-128">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d91ca-128">The following example illustrates this.</span></span>  
  
```vb  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="d91ca-129">En el ejemplo anterior, las variables `arrayA` de matriz y `arrayB` se consideran del mismo tipo de datos, `Byte()` aunque se inicializan en longitudes diferentes.</span><span class="sxs-lookup"><span data-stu-id="d91ca-129">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="d91ca-130">Las variables `arrayB` y `arrayC` no son del mismo tipo porque sus tipos de elemento son diferentes.</span><span class="sxs-lookup"><span data-stu-id="d91ca-130">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="d91ca-131">Las variables `arrayC` y `arrayD` no son del mismo tipo porque sus rangos son diferentes.</span><span class="sxs-lookup"><span data-stu-id="d91ca-131">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="d91ca-132">Variables `arrayD` y `arrayE` tienen el mismo tipo ( `Short(,)` ) porque sus rangos y tipos de elemento son los mismos, aunque `arrayD` aún no se ha inicializado.</span><span class="sxs-lookup"><span data-stu-id="d91ca-132">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="d91ca-133">Para obtener más información sobre las matrices, vea [matrices](../arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="d91ca-133">For more information on arrays, see [Arrays](../arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="d91ca-134">Tipos de clase</span><span class="sxs-lookup"><span data-stu-id="d91ca-134">Class Types</span></span>  

 <span data-ttu-id="d91ca-135">No hay ningún tipo de datos único que incluya todas las clases.</span><span class="sxs-lookup"><span data-stu-id="d91ca-135">There is no single data type comprising all classes.</span></span> <span data-ttu-id="d91ca-136">Aunque una clase puede heredar de otra clase, cada una es un tipo de datos independiente.</span><span class="sxs-lookup"><span data-stu-id="d91ca-136">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="d91ca-137">Varias instancias de la misma clase tienen el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d91ca-137">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="d91ca-138">Si asigna una variable de instancia de clase a otra, y no solo tienen el mismo tipo de datos, apuntan a la misma instancia de clase en la memoria.</span><span class="sxs-lookup"><span data-stu-id="d91ca-138">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="d91ca-139">Para obtener más información sobre las clases, vea [objetos y clases](../objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="d91ca-139">For more information on classes, see [Objects and Classes](../objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d91ca-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d91ca-140">See also</span></span>

- [<span data-ttu-id="d91ca-141">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="d91ca-141">Data Types</span></span>](index.md)
- [<span data-ttu-id="d91ca-142">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="d91ca-142">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="d91ca-143">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d91ca-143">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="d91ca-144">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="d91ca-144">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="d91ca-145">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d91ca-145">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="d91ca-146">Estructuras</span><span class="sxs-lookup"><span data-stu-id="d91ca-146">Structures</span></span>](structures.md)
- [<span data-ttu-id="d91ca-147">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d91ca-147">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="d91ca-148">Procedimiento Inclusión de más de un valor en una variable</span><span class="sxs-lookup"><span data-stu-id="d91ca-148">How to: Hold More Than One Value in a Variable</span></span>](how-to-hold-more-than-one-value-in-a-variable.md)
