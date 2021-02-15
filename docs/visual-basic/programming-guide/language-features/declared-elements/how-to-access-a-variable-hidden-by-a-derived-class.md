---
description: 'Más información sobre: Cómo: obtener acceso a una variable oculta por una clase derivada (Visual Basic)'
title: Procedimiento para obtener acceso a una variable que se encuentra oculta por una clase derivada
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 5ac1dd8afc8c32c91b748c8316d035d69468d887
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430058"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Cómo: Obtener acceso a una variable que oculta una clase derivada (Visual Basic)

Cuando el código de una clase derivada tiene acceso a una variable, el compilador resuelve normalmente la referencia a la versión accesible más cercana, es decir, a la versión accesible el menor paso de derivación hacia atrás desde la clase de acceso. Si la variable se define en la clase derivada, el código normalmente accede a esa definición.

Si la variable de clase derivada sombrea una variable de la clase base, oculta la versión de la clase base. Sin embargo, puede tener acceso a la variable de clase base mediante la calificación de la `MyBase` palabra clave.

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Para tener acceso a una variable de clase base oculta por una clase derivada

- En una expresión o instrucción de asignación, anteponga a la `MyBase` palabra clave y un punto () el nombre de la variable `.` .

    El compilador resuelve la referencia a la versión de la clase base de la variable.

    En el ejemplo siguiente se ilustra el sombreado a través de la herencia. Hace dos referencias, una que tiene acceso a la variable de sombreado y otra que omite el sombreado.

    ```vb
    Public Class shadowBaseClass
        Public shadowString As String = "This is the base class string."
    End Class
    Public Class shadowDerivedClass
        Inherits shadowBaseClass
        Public Shadows shadowString As String = "This is the derived class string."
        Public Sub showStrings()
            Dim s As String = "Unqualified shadowString: " & shadowString &
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString
            MsgBox(s)
        End Sub
    End Class
    ```

    En el ejemplo anterior se declara la variable `shadowString` en la clase base y se sombrea en la clase derivada. El procedimiento `showStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado. A continuación, muestra la versión sombreada cuando `shadowString` se califica con la `MyBase`  palabra clave.

## <a name="robust-programming"></a>Programación sólida

Para reducir el riesgo de hacer referencia a una versión no intencionada de una variable de la que se ha realizado una copia sombra, puede calificar totalmente todas las referencias a una variable de la que se ha realizado una copia sombra. La sombra introduce más de una versión de una variable con el mismo nombre. Cuando una instrucción de código hace referencia al nombre de la variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación. Esto puede aumentar el riesgo de hacer referencia a la versión incorrecta de la variable.

## <a name="see-also"></a>Consulte también

- [References to Declared Elements](references-to-declared-elements.md)
- [Sombrear en Visual Basic](shadowing.md)
- [Diferencias entre sombrear y reemplazar](differences-between-shadowing-and-overriding.md)
- [Procedimiento para ocultar una variable con el mismo nombre que su variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedimiento para ocultar una variable heredada](how-to-hide-an-inherited-variable.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [Invalidaciones](../../../language-reference/modifiers/overrides.md)
- [Me, My, MyBase y MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../objects-and-classes/inheritance-basics.md)
