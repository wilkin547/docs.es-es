---
title: 'Cómo: Determinar si dos objetos están relacionados'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b3f5fc017166ba9cf28359db5de850c81b73bd69
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348629"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Cómo: Determinar si dos objetos están relacionados (Visual Basic)

Puede comparar dos objetos para determinar la relación, si existe, entre las clases de las que se crean. El método <xref:System.Type.IsInstanceOfType%2A> de la clase <xref:System.Type?displayProperty=nameWithType> devuelve `True` si la clase especificada hereda de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Para determinar si un objeto hereda de la clase o la interfaz de otro objeto

1. En el objeto que cree que podría ser del tipo base, invoque el método <xref:System.Object.GetType%2A>.

2. En el objeto <xref:System.Type?displayProperty=nameWithType> devuelto por <xref:System.Object.GetType%2A>, invoque el método <xref:System.Type.IsInstanceOfType%2A>.

3. En la lista de argumentos de <xref:System.Type.IsInstanceOfType%2A>, especifique el objeto que cree que podría ser del tipo derivado.

    <xref:System.Type.IsInstanceOfType%2A> devuelve `True` si su tipo de argumento hereda del tipo de objeto <xref:System.Type?displayProperty=nameWithType>.

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente se determina si un objeto representa una clase derivada de la clase de otro objeto.

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

Tenga en cuenta la colocación inesperada de las dos variables de objeto en la llamada a <xref:System.Type.IsInstanceOfType%2A>. El tipo base supuesto se utiliza para generar la clase <xref:System.Type?displayProperty=nameWithType> y el tipo derivado supuesto se pasa como argumento al método <xref:System.Type.IsInstanceOfType%2A>.

## <a name="see-also"></a>Vea también

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Determinar si dos objetos son idénticos](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
