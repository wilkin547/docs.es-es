---
title: Procedimiento Ocultar una variable con el mismo nombre que la variable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 487e0a15ba6b52f92ab39fe0bae4ab15fa92707f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629988"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Procedimiento Ocultar una variable con el mismo nombre que la variable (Visual Basic)

Puede ocultar una variable mediante la *sombra* , es decir, si la vuelve a definir con una variable del mismo nombre. Puede sombrear la variable que desea ocultar de dos maneras:

- **Sombreado a través del ámbito.** Puede prevalecer en el ámbito si lo redeclara dentro de una subregión de la región que contiene la variable que desea ocultar.

- **Sombrear a través de la herencia.** Si la variable que desea ocultar se define en el nivel de clase, puede sombrearla a través de la herencia si la redeclara con la palabra clave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) en una clase derivada.

## <a name="two-ways-to-hide-a-variable"></a>Dos maneras de ocultar una variable

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Para ocultar una variable mediante su sombreado a través del ámbito

1. Determine la región que define la variable que desea ocultar y determine la subregión en la que se va a volver a definir con la variable.

    |Región de la variable|Subregión permitida para redefinirla|
    |-----------------------|-------------------------------------------|
    |Module|Una clase dentro del módulo|
    |Clase|Una subclase dentro de la clase<br /><br /> Un procedimiento dentro de la clase|

    No se puede volver a definir una variable de procedimiento en un bloque dentro de ese procedimiento `If`, por ejemplo, en... `End If` construcción`For` o bucle.

2. Cree la subregión si aún no existe.

3. Dentro de la subregión, escriba una [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) que declare la variable de sombreado.

    Cuando el código dentro de la subregión hace referencia al nombre de variable, el compilador resuelve la referencia a la variable de sombreado.

    En el ejemplo siguiente se muestra el sombreado a través del ámbito, así como una referencia que omite el sombreado.

    ```vb
    Module shadowByScope
        ' The following statement declares num as a module-level variable.
        Public num As Integer
        Sub show()
            ' The following statement declares num as a local variable.
            Dim num As Integer
            ' The following statement sets the value of the local variable.
            num = 2
            ' The following statement displays the module-level variable.
            MsgBox(CStr(shadowByScope.num))
        End Sub
        Sub useModuleLevelNum()
            ' The following statement sets the value of the module-level variable.
            num = 1
            show()
        End Sub
    End Module
    ```

    En el ejemplo anterior se declara la `num` variable en el nivel de módulo y en el nivel de procedimiento `show`(en el procedimiento). La variable `num` local prevalece sobre la variable `num` de nivel de `show`módulo en, por lo que la variable local se establece en 2. Sin embargo, no hay ninguna variable local para `num` la sombra `useModuleLevelNum` en el procedimiento. Por lo `useModuleLevelNum` tanto, establece el valor de la variable de nivel de módulo en 1.

    La `MsgBox` llamada dentro `show` de omite el mecanismo de sombreado mediante la `num` calificación del nombre del módulo. Por lo tanto, se muestra la variable de nivel de módulo en lugar de la variable local.

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Ocultar una variable mediante su sombreado a través de la herencia

1. Asegúrese de que la variable que desea ocultar está declarada en una clase y en el nivel de clase (fuera de cualquier procedimiento). De lo contrario, no puede sombrearla a través de la herencia.

2. Defina una clase derivada de la clase de la variable si aún no existe una.

3. Dentro de la clase derivada, escriba `Dim` una instrucción que declare la variable. Incluya la palabra clave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) en la declaración.

    Cuando el código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia a la variable.

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

La sombra introduce más de una versión de una variable con el mismo nombre. Cuando una instrucción de código hace referencia al nombre de la variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación. Esto puede aumentar el riesgo de hacer referencia a una versión no intencionada de una variable de la que se ha realizado una copia sombra. Puede reducir este riesgo calificando por completo todas las referencias a una variable de la que se ha realizado una copia sombra.

## <a name="see-also"></a>Vea también

- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Diferencias entre sombrear y reemplazar](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Procedimientos: Ocultar una variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Procedimientos: Acceder a una variable oculta por una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
