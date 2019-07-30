---
title: Procedimiento Acceder a una variable oculta por una clase derivada (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 68f92142cdc435ebd82101eea83035e1d09dcf25
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630012"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Procedimiento Acceder a una variable oculta por una clase derivada (Visual Basic)

Cuando el código de una clase derivada tiene acceso a una variable, el compilador resuelve normalmente la referencia a la versión accesible más cercana, es decir, a la versión accesible el menor paso de derivación hacia atrás desde la clase de acceso. Si la variable se define en la clase derivada, el código normalmente accede a esa definición.

Si la variable de clase derivada sombrea una variable de la clase base, oculta la versión de la clase base. Sin embargo, puede tener acceso a la variable de clase base mediante la calificación `MyBase` de la palabra clave.

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Para tener acceso a una variable de clase base oculta por una clase derivada

- En una expresión o instrucción de asignación, anteponga a la `MyBase` palabra clave y un punto (`.`) el nombre de la variable.

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

    En el ejemplo anterior se declara la `shadowString` variable en la clase base y se sombrea en la clase derivada. El procedimiento `showStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el `shadowString` nombre no está calificado. A continuación, muestra la versión sombreada `shadowString` cuando se califica con `MyBase` la palabra clave.

## <a name="robust-programming"></a>Programación sólida

Para reducir el riesgo de hacer referencia a una versión no intencionada de una variable de la que se ha realizado una copia sombra, puede calificar totalmente todas las referencias a una variable de la que se ha realizado una copia sombra. La sombra introduce más de una versión de una variable con el mismo nombre. Cuando una instrucción de código hace referencia al nombre de la variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación. Esto puede aumentar el riesgo de hacer referencia a la versión incorrecta de la variable.

## <a name="see-also"></a>Vea también

- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Diferencias entre sombrear y reemplazar](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Cómo: Ocultar una variable con el mismo nombre que la variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Procedimientos: Ocultar una variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
