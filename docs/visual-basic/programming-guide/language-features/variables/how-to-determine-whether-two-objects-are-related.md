---
title: 'Cómo: Determinar si dos objetos están relacionados (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2041f89ffd954e479046eb85c6dd82de1f8793ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649830"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="6c916-102">Cómo: Determinar si dos objetos están relacionados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c916-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="6c916-103">Puede comparar dos objetos para determinar la relación entre las clases desde el que se creó.</span><span class="sxs-lookup"><span data-stu-id="6c916-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="6c916-104">El <xref:System.Type.IsInstanceOfType%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase devuelve `True` si la clase especificada se hereda de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="6c916-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="6c916-105">Para determinar si un objeto se hereda de la clase o interfaz de otro objeto</span><span class="sxs-lookup"><span data-stu-id="6c916-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1.  <span data-ttu-id="6c916-106">En el objeto que piensa que podría ser del tipo base, invoque el <xref:System.Object.GetType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6c916-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2.  <span data-ttu-id="6c916-107">En el <xref:System.Type?displayProperty=nameWithType> objeto devuelto por <xref:System.Object.GetType%2A>, invocar el <xref:System.Type.IsInstanceOfType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6c916-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3.  <span data-ttu-id="6c916-108">En la lista de argumentos para <xref:System.Type.IsInstanceOfType%2A>, especifique el objeto que piensa que podría ser del tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="6c916-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="6c916-109"><xref:System.Type.IsInstanceOfType%2A> Devuelve `True` si su tipo de argumento hereda de la <xref:System.Type?displayProperty=nameWithType> tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="6c916-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c916-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6c916-110">Example</span></span>  
 <span data-ttu-id="6c916-111">En el ejemplo siguiente se determina si un objeto representa una clase derivada de la clase de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="6c916-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
```  
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
  
 <span data-ttu-id="6c916-112">Tenga en cuenta la posición inesperada de las dos variables de objeto en la llamada a <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="6c916-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="6c916-113">El tipo base supuesto se utiliza para generar el <xref:System.Type?displayProperty=nameWithType> clase y el tipo derivado supuesto se pasa como argumento a la <xref:System.Type.IsInstanceOfType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6c916-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c916-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c916-114">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [<span data-ttu-id="6c916-115">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="6c916-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="6c916-116">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="6c916-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="6c916-117">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="6c916-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="6c916-118">Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="6c916-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
