---
title: "Of (Cláusula, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ef3ac4ac88727b1dcae50fa14abde03f29a16fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="e6605-102">Of (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e6605-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="e6605-103">Presenta un `Of` cláusula, que identifica un *parámetro de tipo* en un *genérico* clase, estructura, interfaz, delegado o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e6605-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="e6605-104">Para obtener información sobre los tipos genéricos, vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="e6605-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="e6605-105">Mediante la palabra clave</span><span class="sxs-lookup"><span data-stu-id="e6605-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="e6605-106">El siguiente ejemplo de código utiliza la `Of` (palabra clave) para definir el contorno de una clase que toma dos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="e6605-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="e6605-107">Se *restringe* el `keyType` parámetro por la <xref:System.IComparable> interfaz, lo que significa que el código utilizado debe proporcionar un argumento de tipo que implementa <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="e6605-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="e6605-108">Esto es necesario para que la `add` procedimiento puede llamar a la <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="e6605-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e6605-109">Para obtener más información sobre las restricciones, vea [lista de tipo](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="e6605-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
```  
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
  
 <span data-ttu-id="e6605-110">Si completa la definición de clase anterior, puede construir una variedad de `dictionary` clases de él.</span><span class="sxs-lookup"><span data-stu-id="e6605-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="e6605-111">Los tipos que se pasan al `entryType` y `keyType` determinar qué tipo de entrada de la clase contiene y qué tipo de clave se asocia a cada entrada.</span><span class="sxs-lookup"><span data-stu-id="e6605-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="e6605-112">Debido a la restricción, debe proporcionar al `keyType` un tipo que implementa <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="e6605-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="e6605-113">En el ejemplo de código siguiente se crea un objeto que contiene `String` entradas y asocia un `Integer` clave con cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="e6605-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="e6605-114">`Integer`implementa <xref:System.IComparable> y por consiguiente satisface la restricción en `keyType`.</span><span class="sxs-lookup"><span data-stu-id="e6605-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="e6605-115">La palabra clave `Of` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="e6605-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e6605-116">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e6605-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="e6605-117">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e6605-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="e6605-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e6605-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e6605-119">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e6605-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="e6605-120">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e6605-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="e6605-121">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e6605-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e6605-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6605-122">See Also</span></span>  
 <xref:System.IComparable>  
 [<span data-ttu-id="e6605-123">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="e6605-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="e6605-124">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e6605-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="e6605-125">In</span><span class="sxs-lookup"><span data-stu-id="e6605-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [<span data-ttu-id="e6605-126">Out</span><span class="sxs-lookup"><span data-stu-id="e6605-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
