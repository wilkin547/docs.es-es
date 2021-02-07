---
description: 'Más información sobre: cláusula of (Visual Basic)'
title: Cláusula Of
ms.date: 07/20/2015
f1_keywords:
- Of
- vb.Of
- vb.of
helpviewer_keywords:
- Of keyword [Visual Basic]
- arguments [Visual Basic], data types
- constraints, Visual Basic generic types
- generic parameters
- generics [Visual Basic], constraints
- parameters [Visual Basic], type
- types [Visual Basic], generic
- parameters [Visual Basic], generic
- type parameters
- data type arguments
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
ms.openlocfilehash: d6002041a2fe8db5b07e12e9e396a65fde30b716
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768849"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="c1751-103">Of (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1751-103">Of Clause (Visual Basic)</span></span>

<span data-ttu-id="c1751-104">Introduce una `Of` cláusula, que identifica un *parámetro de tipo* en una clase *genérica* , una estructura, una interfaz, un delegado o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c1751-104">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="c1751-105">Para obtener información sobre los tipos genéricos, vea [tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="c1751-105">For information on generic types, see [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="c1751-106">Usar la palabra clave of</span><span class="sxs-lookup"><span data-stu-id="c1751-106">Using the Of Keyword</span></span>  

 <span data-ttu-id="c1751-107">En el ejemplo de código siguiente `Of` se usa la palabra clave para definir el contorno de una clase que toma dos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="c1751-107">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="c1751-108">*Restringe* el `keyType` parámetro mediante la <xref:System.IComparable> interfaz, lo que significa que el código utilizado debe proporcionar un argumento de tipo que implemente <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="c1751-108">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="c1751-109">Esto es necesario para que el `add` procedimiento pueda llamar al <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="c1751-109">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c1751-110">Para más información sobre las restricciones, vea [Type List](type-list.md).</span><span class="sxs-lookup"><span data-stu-id="c1751-110">For more information on constraints, see [Type List](type-list.md).</span></span>  
  
```vb  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 <span data-ttu-id="c1751-111">Si completa la definición de clase anterior, puede crear una variedad de `dictionary` clases a partir de ella.</span><span class="sxs-lookup"><span data-stu-id="c1751-111">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="c1751-112">Los tipos que se suministran a `entryType` y `keyType` determinan qué tipo de entrada contiene la clase y qué tipo de clave asocia a cada entrada.</span><span class="sxs-lookup"><span data-stu-id="c1751-112">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="c1751-113">Debido a la restricción, debe proporcionar a `keyType` un tipo que implementa <xref:System.IComparable> .</span><span class="sxs-lookup"><span data-stu-id="c1751-113">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="c1751-114">En el ejemplo de código siguiente se crea un objeto que contiene `String` entradas y asocia una `Integer` clave a cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="c1751-114">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="c1751-115">`Integer` implementa <xref:System.IComparable> y, por tanto, satisface la restricción en `keyType` .</span><span class="sxs-lookup"><span data-stu-id="c1751-115">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```vb  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="c1751-116">La palabra clave `Of` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="c1751-116">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="c1751-117">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="c1751-117">Class Statement</span></span>](class-statement.md)  
  
 [<span data-ttu-id="c1751-118">Delegate (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="c1751-118">Delegate Statement</span></span>](delegate-statement.md)  
  
 [<span data-ttu-id="c1751-119">Instrucción Function</span><span class="sxs-lookup"><span data-stu-id="c1751-119">Function Statement</span></span>](function-statement.md)  
  
 [<span data-ttu-id="c1751-120">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="c1751-120">Interface Statement</span></span>](interface-statement.md)  
  
 [<span data-ttu-id="c1751-121">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="c1751-121">Structure Statement</span></span>](structure-statement.md)  
  
 [<span data-ttu-id="c1751-122">Instrucción Sub</span><span class="sxs-lookup"><span data-stu-id="c1751-122">Sub Statement</span></span>](sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1751-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1751-123">See also</span></span>

- <xref:System.IComparable>
- [<span data-ttu-id="c1751-124">Type List</span><span class="sxs-lookup"><span data-stu-id="c1751-124">Type List</span></span>](type-list.md)
- [<span data-ttu-id="c1751-125">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1751-125">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="c1751-126">In</span><span class="sxs-lookup"><span data-stu-id="c1751-126">In</span></span>](../modifiers/in-generic-modifier.md)
- [<span data-ttu-id="c1751-127">Fuera</span><span class="sxs-lookup"><span data-stu-id="c1751-127">Out</span></span>](../modifiers/out-generic-modifier.md)
