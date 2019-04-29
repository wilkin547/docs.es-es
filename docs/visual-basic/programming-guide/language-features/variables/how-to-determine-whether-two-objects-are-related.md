---
title: Procedimiento Determinar si dos objetos están relacionados (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: f59e00d80d28fc4bf24874d25b5c12643649c834
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769075"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Procedimiento Determinar si dos objetos están relacionados (Visual Basic)
Puede comparar dos objetos para determinar la relación, si hay alguno, entre las clases desde el que se crean. El <xref:System.Type.IsInstanceOfType%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase devuelve `True` si hereda de la clase especificada de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Para determinar si un objeto hereda de otro objeto clase o interfaz  
  
1. En el objeto que piensa que podría ser del tipo base, invoque el <xref:System.Object.GetType%2A> método.  
  
2. En el <xref:System.Type?displayProperty=nameWithType> objeto devuelto por <xref:System.Object.GetType%2A>, invocar el <xref:System.Type.IsInstanceOfType%2A> método.  
  
3. En la lista de argumentos para <xref:System.Type.IsInstanceOfType%2A>, especifique el objeto que piensa que podría ser del tipo derivado.  
  
     <xref:System.Type.IsInstanceOfType%2A> Devuelve `True` si su tipo de argumento que se hereda de la <xref:System.Type?displayProperty=nameWithType> tipo de objeto.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente determina si un objeto representa una clase derivada de la clase de otro objeto.  
  
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
  
 Tenga en cuenta la posición inesperada de las dos variables de objeto en la llamada a <xref:System.Type.IsInstanceOfType%2A>. El tipo base supuesto se utiliza para generar el <xref:System.Type?displayProperty=nameWithType> clase y el tipo derivado supuesto se pasa como argumento a la <xref:System.Type.IsInstanceOfType%2A> método.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Cómo: Determinar si dos objetos son idénticos](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
