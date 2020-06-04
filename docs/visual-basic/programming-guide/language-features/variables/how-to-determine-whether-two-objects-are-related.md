---
title: Procedimiento para determinar si dos objetos están relacionados
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 30e88a21e737aa57513745899577381ed34151a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410469"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="b62a8-102">Cómo: Determinar si dos objetos están relacionados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b62a8-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="b62a8-103">Puede comparar dos objetos para determinar la relación, si existe, entre las clases de las que se crean.</span><span class="sxs-lookup"><span data-stu-id="b62a8-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="b62a8-104">El <xref:System.Type.IsInstanceOfType%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase devuelve `True` si la clase especificada hereda de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="b62a8-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="b62a8-105">Para determinar si un objeto hereda de la clase o la interfaz de otro objeto</span><span class="sxs-lookup"><span data-stu-id="b62a8-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="b62a8-106">En el objeto que cree que podría ser del tipo base, invoque el <xref:System.Object.GetType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b62a8-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="b62a8-107">En el <xref:System.Type?displayProperty=nameWithType> objeto devuelto por <xref:System.Object.GetType%2A> , invoque el <xref:System.Type.IsInstanceOfType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b62a8-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="b62a8-108">En la lista de argumentos de <xref:System.Type.IsInstanceOfType%2A> , especifique el objeto que piensa que podría ser del tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="b62a8-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="b62a8-109"><xref:System.Type.IsInstanceOfType%2A>Devuelve `True` si su tipo de argumento hereda del <xref:System.Type?displayProperty=nameWithType> tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="b62a8-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="b62a8-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b62a8-110">Example</span></span>
 <span data-ttu-id="b62a8-111">En el ejemplo siguiente se determina si un objeto representa una clase derivada de la clase de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="b62a8-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

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

<span data-ttu-id="b62a8-112">Tenga en cuenta la colocación inesperada de las dos variables de objeto en la llamada a <xref:System.Type.IsInstanceOfType%2A> .</span><span class="sxs-lookup"><span data-stu-id="b62a8-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="b62a8-113">El tipo base supuesto se usa para generar la <xref:System.Type?displayProperty=nameWithType> clase y el tipo derivado supuesto se pasa como argumento al <xref:System.Type.IsInstanceOfType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b62a8-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="b62a8-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b62a8-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="b62a8-115">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="b62a8-115">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="b62a8-116">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="b62a8-116">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="b62a8-117">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="b62a8-117">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="b62a8-118">Procedimiento para determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="b62a8-118">How to: Determine Whether Two Objects Are Identical</span></span>](how-to-determine-whether-two-objects-are-identical.md)
