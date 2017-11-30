---
title: "Cómo: Determinar si dos objetos están relacionados (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7824742459fca355c0043ad8ed20a26330402c05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="6f1e7-102">Cómo: Determinar si dos objetos están relacionados (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f1e7-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="6f1e7-103">Puede comparar dos objetos para determinar la relación entre las clases desde el que se creó.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="6f1e7-104">El <xref:System.Type.IsInstanceOfType%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase devuelve `True` si la clase especificada se hereda de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="6f1e7-105">Para determinar si un objeto se hereda de la clase o interfaz de otro objeto</span><span class="sxs-lookup"><span data-stu-id="6f1e7-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1.  <span data-ttu-id="6f1e7-106">En el objeto que piensa que podría ser del tipo base, invoque el <xref:System.Object.GetType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2.  <span data-ttu-id="6f1e7-107">En el <xref:System.Type?displayProperty=nameWithType> objeto devuelto por <xref:System.Object.GetType%2A>, invocar el <xref:System.Type.IsInstanceOfType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3.  <span data-ttu-id="6f1e7-108">En la lista de argumentos para <xref:System.Type.IsInstanceOfType%2A>, especifique el objeto que piensa que podría ser del tipo derivado.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="6f1e7-109"><xref:System.Type.IsInstanceOfType%2A>Devuelve `True` si su tipo de argumento hereda de la <xref:System.Type?displayProperty=nameWithType> tipo de objeto.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f1e7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f1e7-110">Example</span></span>  
 <span data-ttu-id="6f1e7-111">En el ejemplo siguiente se determina si un objeto representa una clase derivada de la clase de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
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
  
 <span data-ttu-id="6f1e7-112">Tenga en cuenta la posición inesperada de las dos variables de objeto en la llamada a <xref:System.Type.IsInstanceOfType%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="6f1e7-113">El tipo base supuesto se utiliza para generar el <xref:System.Type?displayProperty=nameWithType> clase y el tipo derivado supuesto se pasa como argumento a la <xref:System.Type.IsInstanceOfType%2A> método.</span><span class="sxs-lookup"><span data-stu-id="6f1e7-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1e7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f1e7-114">See Also</span></span>  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [<span data-ttu-id="6f1e7-115">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="6f1e7-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="6f1e7-116">Variables de objeto</span><span class="sxs-lookup"><span data-stu-id="6f1e7-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="6f1e7-117">Valores de las variables de objeto</span><span class="sxs-lookup"><span data-stu-id="6f1e7-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="6f1e7-118">Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="6f1e7-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
