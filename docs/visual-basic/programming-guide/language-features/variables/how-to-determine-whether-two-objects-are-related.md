---
title: Procedimiento Determinar si dos objetos están relacionados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2b17be4ef5a7dabfc4779ab6f5675cc2baec9c3c
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626553"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="88d6a-102">Procedimiento Determinar si dos objetos están relacionados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88d6a-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="88d6a-103">Puede comparar dos objetos para determinar la relación, si existe, entre las clases de las que se crean.</span><span class="sxs-lookup"><span data-stu-id="88d6a-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="88d6a-104">El <xref:System.Type.IsInstanceOfType%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase devuelve `True` si la clase especificada hereda de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="88d6a-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="88d6a-105">Para determinar si un objeto hereda de la clase o la interfaz de otro objeto</span><span class="sxs-lookup"><span data-stu-id="88d6a-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="88d6a-106">En el objeto que cree que podría ser del tipo base, invoque <xref:System.Object.GetType%2A> el método.</span><span class="sxs-lookup"><span data-stu-id="88d6a-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="88d6a-107">En el <xref:System.Type?displayProperty=nameWithType> objeto devuelto <xref:System.Object.GetType%2A>por, invoque el <xref:System.Type.IsInstanceOfType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="88d6a-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="88d6a-108">En la lista de argumentos <xref:System.Type.IsInstanceOfType%2A>de, especifique el objeto que piensa que podría ser del tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="88d6a-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="88d6a-109"><xref:System.Type.IsInstanceOfType%2A>Devuelve `True` si su tipo <xref:System.Type?displayProperty=nameWithType> de argumento hereda del tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="88d6a-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="88d6a-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="88d6a-110">Example</span></span>
 <span data-ttu-id="88d6a-111">En el ejemplo siguiente se determina si un objeto representa una clase derivada de la clase de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="88d6a-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

<span data-ttu-id="88d6a-112">Tenga en cuenta la colocación inesperada de las dos variables de <xref:System.Type.IsInstanceOfType%2A>objeto en la llamada a.</span><span class="sxs-lookup"><span data-stu-id="88d6a-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="88d6a-113">El tipo base supuesto se usa para generar la <xref:System.Type?displayProperty=nameWithType> clase y el tipo derivado supuesto se pasa como argumento <xref:System.Type.IsInstanceOfType%2A> al método.</span><span class="sxs-lookup"><span data-stu-id="88d6a-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="88d6a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="88d6a-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="88d6a-115">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="88d6a-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="88d6a-116">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="88d6a-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="88d6a-117">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="88d6a-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="88d6a-118">Procedimientos: Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="88d6a-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
