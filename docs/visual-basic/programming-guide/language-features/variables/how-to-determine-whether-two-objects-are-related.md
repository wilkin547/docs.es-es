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
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Cómo: Determinar si dos objetos están relacionados (Visual Basic)
Puede comparar dos objetos para determinar la relación entre las clases desde el que se creó. El <xref:System.Type.IsInstanceOfType%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase devuelve `True` si la clase especificada se hereda de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Para determinar si un objeto se hereda de la clase o interfaz de otro objeto  
  
1.  En el objeto que piensa que podría ser del tipo base, invoque el <xref:System.Object.GetType%2A> método.  
  
2.  En el <xref:System.Type?displayProperty=nameWithType> objeto devuelto por <xref:System.Object.GetType%2A>, invocar el <xref:System.Type.IsInstanceOfType%2A> método.  
  
3.  En la lista de argumentos para <xref:System.Type.IsInstanceOfType%2A>, especifique el objeto que piensa que podría ser del tipo derivado.  
  
     <xref:System.Type.IsInstanceOfType%2A> Devuelve `True` si su tipo de argumento hereda de la <xref:System.Type?displayProperty=nameWithType> tipo de objeto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se determina si un objeto representa una clase derivada de la clase de otro objeto.  
  
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
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.IsInstanceOfType%2A>  
 [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Determinar si dos objetos son idénticos](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
