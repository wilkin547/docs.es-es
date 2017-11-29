---
title: "Conversión de matrices (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40dc9805157dd0bc991ca2375c3436aa6b6e09a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="array-conversions-visual-basic"></a><span data-ttu-id="a76e4-102">Conversión de matrices (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a76e4-102">Array Conversions (Visual Basic)</span></span>
<span data-ttu-id="a76e4-103">Puede convertir un tipo de matriz en otro tipo de matriz siempre que se cumplan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a76e4-103">You can convert an array type to a different array type provided you meet the following conditions:</span></span>  
  
-   <span data-ttu-id="a76e4-104">**Rango igual.**</span><span class="sxs-lookup"><span data-stu-id="a76e4-104">**Equal Rank.**</span></span> <span data-ttu-id="a76e4-105">Los rangos de las dos matrices deben ser los mismos, es decir, deben tener el mismo número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="a76e4-105">The ranks of the two arrays must be the same, that is, they must have the same number of dimensions.</span></span> <span data-ttu-id="a76e4-106">Sin embargo, las longitudes de las dimensiones respectivas no es necesario ser el mismo.</span><span class="sxs-lookup"><span data-stu-id="a76e4-106">However, the lengths of the respective dimensions do not need to be the same.</span></span>  
  
-   <span data-ttu-id="a76e4-107">**Tipo de datos del elemento.**</span><span class="sxs-lookup"><span data-stu-id="a76e4-107">**Element Data Type.**</span></span> <span data-ttu-id="a76e4-108">Los tipos de datos de los elementos de ambas matrices deben ser tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="a76e4-108">The data types of the elements of both arrays must be reference types.</span></span> <span data-ttu-id="a76e4-109">No se puede convertir un `Integer` de matriz a un `Long` de matriz, o incluso en un `Object` de matriz, porque al menos un tipo de valor está implicado.</span><span class="sxs-lookup"><span data-stu-id="a76e4-109">You cannot convert an `Integer` array to a `Long` array, or even to an `Object` array, because at least one value type is involved.</span></span> <span data-ttu-id="a76e4-110">Para obtener más información, consulte [tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="a76e4-110">For more information, see [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
-   <span data-ttu-id="a76e4-111">**Convertibility.**</span><span class="sxs-lookup"><span data-stu-id="a76e4-111">**Convertibility.**</span></span> <span data-ttu-id="a76e4-112">Una conversión de ampliación o restricción, debe ser posible entre los tipos de elemento de las dos matrices.</span><span class="sxs-lookup"><span data-stu-id="a76e4-112">A conversion, either widening or narrowing, must be possible between the element types of the two arrays.</span></span> <span data-ttu-id="a76e4-113">Un ejemplo que no cumple este requisito es un intento de conversión entre una `String` matriz y una matriz de una clase derivan de <xref:System.Attribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a76e4-113">An example that fails this requirement is an attempted conversion between a `String` array and an array of a class derived from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a76e4-114">Estos dos tipos no tienen nada en común y no existe ninguna conversión de ningún tipo entre ellos.</span><span class="sxs-lookup"><span data-stu-id="a76e4-114">These two types have nothing in common, and no conversion of any kind exists between them.</span></span>  
  
 <span data-ttu-id="a76e4-115">Una conversión de tipo de matriz de uno a otro es de ampliación o restricción dependiendo de si la conversión de los respectivos elementos es de ampliación o restricción.</span><span class="sxs-lookup"><span data-stu-id="a76e4-115">A conversion of one array type to another is widening or narrowing depending on whether the conversion of the respective elements is widening or narrowing.</span></span> <span data-ttu-id="a76e4-116">Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="a76e4-116">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span>  
  
## <a name="conversion-to-an-object-array"></a><span data-ttu-id="a76e4-117">Conversión a una matriz de objetos</span><span class="sxs-lookup"><span data-stu-id="a76e4-117">Conversion to an Object Array</span></span>  
 <span data-ttu-id="a76e4-118">Cuando se declara un `Object` matriz sin inicializarla, su tipo de elemento es `Object` mientras permanezca sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="a76e4-118">When you declare an `Object` array without initializing it, its element type is `Object` as long as it remains uninitialized.</span></span> <span data-ttu-id="a76e4-119">Cuando se establece en una matriz de una clase específica, toma el tipo de esa clase.</span><span class="sxs-lookup"><span data-stu-id="a76e4-119">When you set it to an array of a specific class, it takes on the type of that class.</span></span> <span data-ttu-id="a76e4-120">Sin embargo, su tipo subyacente sigue siendo `Object`, y posteriormente se puede establecer en otra matriz de una clase no relacionada.</span><span class="sxs-lookup"><span data-stu-id="a76e4-120">However, its underlying type is still `Object`, and you can subsequently set it to another array of an unrelated class.</span></span> <span data-ttu-id="a76e4-121">Dado que todas las clases que derivan de `Object`, puede cambiar el tipo de elemento de la matriz de cualquier clase a cualquier otra clase.</span><span class="sxs-lookup"><span data-stu-id="a76e4-121">Since all classes derive from `Object`, you can change the array's element type from any class to any other class.</span></span>  
  
 <span data-ttu-id="a76e4-122">En el ejemplo siguiente, no existe ninguna conversión entre tipos `student` y `String`, pero ambos derivan de `Object`, por lo que todas las asignaciones son válidas.</span><span class="sxs-lookup"><span data-stu-id="a76e4-122">In the following example, no conversion exists between types `student` and `String`, but both derive from `Object`, so all assignments are valid.</span></span>  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a><span data-ttu-id="a76e4-123">El tipo subyacente de una matriz</span><span class="sxs-lookup"><span data-stu-id="a76e4-123">Underlying Type of an Array</span></span>  
 <span data-ttu-id="a76e4-124">Si originalmente se declara una matriz con una clase específica, su tipo de elemento subyacente es esa clase.</span><span class="sxs-lookup"><span data-stu-id="a76e4-124">If you originally declare an array with a specific class, its underlying element type is that class.</span></span> <span data-ttu-id="a76e4-125">Si posteriormente se establece en una matriz de otra clase, debe haber una conversión entre las dos clases.</span><span class="sxs-lookup"><span data-stu-id="a76e4-125">If you subsequently set it to an array of another class, there must be a conversion between the two classes.</span></span>  
  
 <span data-ttu-id="a76e4-126">En el ejemplo siguiente, `students` es un `student` matriz.</span><span class="sxs-lookup"><span data-stu-id="a76e4-126">In the following example, `students` is a `student` array.</span></span> <span data-ttu-id="a76e4-127">Puesto que no existe ninguna conversión entre `String` y `student`, se produce un error en la última instrucción.</span><span class="sxs-lookup"><span data-stu-id="a76e4-127">Since no conversion exists between `String` and `student`, the last statement fails.</span></span>  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a><span data-ttu-id="a76e4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a76e4-128">See Also</span></span>  
 [<span data-ttu-id="a76e4-129">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a76e4-129">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="a76e4-130">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a76e4-130">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="a76e4-131">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="a76e4-131">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="a76e4-132">Conversiones entre cadenas y otros tipos</span><span class="sxs-lookup"><span data-stu-id="a76e4-132">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="a76e4-133">Cómo: convertir un objeto a otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a76e4-133">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="a76e4-134">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="a76e4-134">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="a76e4-135">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="a76e4-135">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a76e4-136">Matrices</span><span class="sxs-lookup"><span data-stu-id="a76e4-136">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
