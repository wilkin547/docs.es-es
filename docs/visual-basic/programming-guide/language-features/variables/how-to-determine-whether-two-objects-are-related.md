---
description: 'Más información acerca de cómo: determinar si dos objetos están relacionados (Visual Basic)'
title: Procedimiento para determinar si dos objetos están relacionados
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 79a6dae83cc780a3aed64fd40fb284e7479ffacc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481914"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a>Cómo: Determinar si dos objetos están relacionados (Visual Basic)

Puede comparar dos objetos para determinar la relación, si existe, entre las clases de las que se crean. El <xref:System.Type.IsInstanceOfType%2A> método de la <xref:System.Type?displayProperty=nameWithType> clase devuelve `True` si la clase especificada hereda de la clase actual, o si el tipo actual es una interfaz compatible con la clase especificada.

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a>Para determinar si un objeto hereda de la clase o la interfaz de otro objeto

1. En el objeto que cree que podría ser del tipo base, invoque el <xref:System.Object.GetType%2A> método.

2. En el <xref:System.Type?displayProperty=nameWithType> objeto devuelto por <xref:System.Object.GetType%2A> , invoque el <xref:System.Type.IsInstanceOfType%2A> método.

3. En la lista de argumentos de <xref:System.Type.IsInstanceOfType%2A> , especifique el objeto que piensa que podría ser del tipo derivado.

    <xref:System.Type.IsInstanceOfType%2A> Devuelve `True` si su tipo de argumento hereda del <xref:System.Type?displayProperty=nameWithType> tipo de objeto.

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

Tenga en cuenta la colocación inesperada de las dos variables de objeto en la llamada a <xref:System.Type.IsInstanceOfType%2A> . El tipo base supuesto se usa para generar la <xref:System.Type?displayProperty=nameWithType> clase y el tipo derivado supuesto se pasa como argumento al <xref:System.Type.IsInstanceOfType%2A> método.

## <a name="see-also"></a>Consulte también

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Variables de objeto](object-variables.md)
- [Valores de las variables de objeto](object-variable-values.md)
- [Procedimiento para determinar si dos objetos son idénticos](how-to-determine-whether-two-objects-are-identical.md)
