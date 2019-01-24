---
title: Of (Cláusula, Visual Basic)
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
ms.openlocfilehash: e4c6c5cb8c041f1f0dfb3a9a3f858850d67d1c38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698246"
---
# <a name="of-clause-visual-basic"></a><span data-ttu-id="e8169-102">Of (Cláusula, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8169-102">Of Clause (Visual Basic)</span></span>
<span data-ttu-id="e8169-103">Presenta un `Of` cláusula que identifica un *parámetro de tipo* en un *genérico* clase, estructura, interfaz, delegado o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e8169-103">Introduces an `Of` clause, which identifies a *type parameter* on a *generic* class, structure, interface, delegate, or procedure.</span></span> <span data-ttu-id="e8169-104">Para obtener información sobre los tipos genéricos, vea [tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span><span class="sxs-lookup"><span data-stu-id="e8169-104">For information on generic types, see [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).</span></span>  
  
## <a name="using-the-of-keyword"></a><span data-ttu-id="e8169-105">Mediante la palabra clave</span><span class="sxs-lookup"><span data-stu-id="e8169-105">Using the Of Keyword</span></span>  
 <span data-ttu-id="e8169-106">El siguiente ejemplo de código utiliza el `Of` palabra clave para definir el contorno de una clase que toma dos parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="e8169-106">The following code example uses the `Of` keyword to define the outline of a class that takes two type parameters.</span></span> <span data-ttu-id="e8169-107">Lo *restringe* el `keyType` parámetro por el <xref:System.IComparable> interfaz, lo que significa que el código usado debe proporcionar un argumento de tipo que implementa <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="e8169-107">It *constrains* the `keyType` parameter by the <xref:System.IComparable> interface, which means the consuming code must supply a type argument that implements <xref:System.IComparable>.</span></span> <span data-ttu-id="e8169-108">Esto es necesario para que la `add` procedimiento puede llamar a la <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="e8169-108">This is necessary so that the `add` procedure can call the <xref:System.IComparable.CompareTo%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e8169-109">Para más información sobre las restricciones, vea [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="e8169-109">For more information on constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
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
  
 <span data-ttu-id="e8169-110">Si completa la definición de clase anterior, puede construir una variedad de `dictionary` clases a partir de él.</span><span class="sxs-lookup"><span data-stu-id="e8169-110">If you complete the preceding class definition, you can construct a variety of `dictionary` classes from it.</span></span> <span data-ttu-id="e8169-111">Los tipos que proporciona a `entryType` y `keyType` determinar qué tipo de entrada de la clase contiene y qué tipo de clave se asocia a cada entrada.</span><span class="sxs-lookup"><span data-stu-id="e8169-111">The types you supply to `entryType` and `keyType` determine what type of entry the class holds and what type of key it associates with each entry.</span></span> <span data-ttu-id="e8169-112">Debido a la restricción, debe proporcionar al `keyType` un tipo que implementa <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="e8169-112">Because of the constraint, you must supply to `keyType` a type that implements <xref:System.IComparable>.</span></span>  
  
 <span data-ttu-id="e8169-113">En el ejemplo de código siguiente se crea un objeto que contiene `String` entradas y asocia un `Integer` clave con cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="e8169-113">The following code example creates an object that holds `String` entries and associates an `Integer` key with each one.</span></span> <span data-ttu-id="e8169-114">`Integer` implementa <xref:System.IComparable> y, por tanto, cumple la restricción en `keyType`.</span><span class="sxs-lookup"><span data-stu-id="e8169-114">`Integer` implements <xref:System.IComparable> and therefore satisfies the constraint on `keyType`.</span></span>  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 <span data-ttu-id="e8169-115">La palabra clave `Of` se puede usar en los siguientes contextos:</span><span class="sxs-lookup"><span data-stu-id="e8169-115">The `Of` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e8169-116">Class (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8169-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="e8169-117">Delegate (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8169-117">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="e8169-118">Function (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8169-118">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="e8169-119">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8169-119">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="e8169-120">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8169-120">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="e8169-121">Sub (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e8169-121">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e8169-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8169-122">See also</span></span>
- <xref:System.IComparable>
- [<span data-ttu-id="e8169-123">Lista de tipos</span><span class="sxs-lookup"><span data-stu-id="e8169-123">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="e8169-124">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e8169-124">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="e8169-125">In</span><span class="sxs-lookup"><span data-stu-id="e8169-125">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [<span data-ttu-id="e8169-126">Out</span><span class="sxs-lookup"><span data-stu-id="e8169-126">Out</span></span>](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
