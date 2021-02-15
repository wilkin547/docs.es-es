---
description: 'Más información acerca de: conversiones de matriz (Visual Basic)'
title: Conversiones de matriz
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 1600042e1d41cbc2bd52468544db0e806e776d9c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466411"
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="7a9b9-103">Conversión de matrices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a9b9-103">Array Conversions (Visual Basic)</span></span>

<span data-ttu-id="7a9b9-104">Puede convertir un tipo de matriz en un tipo de matriz diferente siempre que se cumplan las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="7a9b9-104">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
- <span data-ttu-id="7a9b9-105">**Rango igual.**</span><span class="sxs-lookup"><span data-stu-id="7a9b9-105">**Equal Rank.**</span></span> <span data-ttu-id="7a9b9-106">Los rangos de las dos matrices deben ser iguales, es decir, deben tener el mismo número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-106">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="7a9b9-107">Sin embargo, no es necesario que las longitudes de las dimensiones respectivas sean las mismas.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-107">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
- <span data-ttu-id="7a9b9-108">**Tipo de datos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="7a9b9-108">**Element Data Type.**</span></span> <span data-ttu-id="7a9b9-109">Los tipos de datos de los elementos de ambas matrices deben ser tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-109">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="7a9b9-110">No se puede convertir una `Integer` matriz en una `Long` matriz, ni siquiera en una `Object` matriz, porque se implica al menos un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-110">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="7a9b9-111">Para obtener más información, vea [tipos de valor y tipos de referencia](value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="7a9b9-111">For more information, see [Value Types and Reference Types](value-types-and-reference-types.md).</span></span>  
  
- <span data-ttu-id="7a9b9-112">**Convertibility.**</span><span class="sxs-lookup"><span data-stu-id="7a9b9-112">**Convertibility.**</span></span> <span data-ttu-id="7a9b9-113">Una conversión, ya sea de ampliación o de restricción, debe ser posible entre los tipos de elemento de las dos matrices.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-113">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="7a9b9-114">Un ejemplo en el que se produce un error en este requisito es un intento de conversión entre una `String` matriz y una matriz de una clase derivada de <xref:System.Attribute?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7a9b9-114">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7a9b9-115">Estos dos tipos no tienen nada en común y no existe ninguna conversión de ningún tipo entre ellos.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-115">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="7a9b9-116">Una conversión de un tipo de matriz a otro es la ampliación o la restricción, dependiendo de si la conversión de los elementos respectivos es de ampliación o reducción.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-116">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="7a9b9-117">Para obtener más información, consulta [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="7a9b9-117">For more information, see [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="7a9b9-118">Conversión a una matriz de objetos</span><span class="sxs-lookup"><span data-stu-id="7a9b9-118">Conversion to an Object Array</span></span>  

 <span data-ttu-id="7a9b9-119">Cuando se declara una `Object` matriz sin inicializarla, su tipo de elemento es `Object` siempre que permanezca sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-119">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="7a9b9-120">Cuando se establece en una matriz de una clase específica, toma el tipo de esa clase.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-120">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="7a9b9-121">Sin embargo, su tipo subyacente sigue siendo `Object` y puede establecerlo posteriormente en otra matriz de una clase no relacionada.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-121">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="7a9b9-122">Dado que todas las clases derivan de `Object` , puede cambiar el tipo de elemento de la matriz de cualquier clase a cualquier otra clase.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-122">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="7a9b9-123">En el ejemplo siguiente, no existe ninguna conversión entre tipos `student` y `String` , pero ambos derivan de `Object` , por lo que todas las asignaciones son válidas.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-123">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="7a9b9-124">Tipo subyacente de una matriz</span><span class="sxs-lookup"><span data-stu-id="7a9b9-124">Underlying Type of an Array</span></span>  

 <span data-ttu-id="7a9b9-125">Si declara originalmente una matriz con una clase concreta, su tipo de elemento subyacente es esa clase.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-125">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="7a9b9-126">Si posteriormente lo establece en una matriz de otra clase, debe haber una conversión entre las dos clases.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-126">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="7a9b9-127">En el ejemplo siguiente, `students` es una `student` matriz.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-127">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="7a9b9-128">Dado que no existe ninguna conversión entre `String` y `student` , se produce un error en la última instrucción.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-128">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="7a9b9-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a9b9-129">See also</span></span>

- [<span data-ttu-id="7a9b9-130">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7a9b9-130">Data Types</span></span>](index.md)
- [<span data-ttu-id="7a9b9-131">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a9b9-131">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="7a9b9-132">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="7a9b9-132">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="7a9b9-133">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="7a9b9-133">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="7a9b9-134">Cómo: Convertir un objeto en otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a9b9-134">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="7a9b9-135">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="7a9b9-135">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="7a9b9-136">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="7a9b9-136">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="7a9b9-137">Matrices</span><span class="sxs-lookup"><span data-stu-id="7a9b9-137">Arrays</span></span>](../arrays/index.md)
