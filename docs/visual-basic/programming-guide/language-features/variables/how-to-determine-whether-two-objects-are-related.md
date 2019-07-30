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
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Procedimiento Determinar si dos objetos están relacionados (Visual Basic)

Puede comparar dos objetos para determinar la relación, si existe, entre las clases de las que se crean. El <xref:System.Type.IsInstanceOfType%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase devuelve `True` si la clase especificada hereda de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Para determinar si un objeto hereda de la clase o la interfaz de otro objeto

1. En el objeto que cree que podría ser del tipo base, invoque <xref:System.Object.GetType%2A> el método.

2. En el <xref:System.Type?displayProperty=nameWithType> objeto devuelto <xref:System.Object.GetType%2A>por, invoque el <xref:System.Type.IsInstanceOfType%2A> método.

3. En la lista de argumentos <xref:System.Type.IsInstanceOfType%2A>de, especifique el objeto que piensa que podría ser del tipo derivado.

    <xref:System.Type.IsInstanceOfType%2A>Devuelve `True` si su tipo <xref:System.Type?displayProperty=nameWithType> de argumento hereda del tipo de objeto.

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

Tenga en cuenta la colocación inesperada de las dos variables de <xref:System.Type.IsInstanceOfType%2A>objeto en la llamada a. El tipo base supuesto se usa para generar la <xref:System.Type?displayProperty=nameWithType> clase y el tipo derivado supuesto se pasa como argumento <xref:System.Type.IsInstanceOfType%2A> al método.

## <a name="see-also"></a>Vea también

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Procedimientos: Determinar si dos objetos son idénticos](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
