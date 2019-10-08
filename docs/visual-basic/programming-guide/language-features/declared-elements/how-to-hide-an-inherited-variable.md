---
title: Procedimiento Ocultar una variable heredada (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: f575830df44076f694c1dfb2f68379594240fb80
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004845"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Procedimiento Ocultar una variable heredada (Visual Basic)

Una clase derivada hereda todas las definiciones de su clase base. Si desea definir una variable con el mismo nombre que un elemento de la clase base, puede ocultar, o *sombra*, ese elemento de clase base cuando defina la variable en la clase derivada. Si lo hace, el código de la clase derivada accede a su variable a menos que omita explícitamente el mecanismo de sombreado.

Otro motivo por el que podría querer ocultar una variable heredada es proteger contra la revisión de la clase base. La clase base puede someterse a un cambio que modifica el elemento que se va a heredar. Si esto ocurre, el modificador `Shadows` fuerza las referencias de la clase derivada para que se resuelvan en la variable, en lugar de en el elemento de clase base.

## <a name="to-hide-an-inherited-variable"></a>Para ocultar una variable heredada

1. Asegúrese de que la variable que desea ocultar se declara en el nivel de clase (fuera de cualquier procedimiento). De lo contrario, no es necesario ocultarlo.
  
2. Dentro de la clase derivada, escriba una [instrucción Dim](../../../language-reference/statements/dim-statement.md) que declare la variable. Use el mismo nombre que el de la variable heredada.

3. Incluya la palabra clave [Shadows](../../../language-reference/modifiers/shadows.md) en la declaración.

     Cuando el código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia a la variable.

     En el ejemplo siguiente se muestra la sombra de una variable heredada:
  
    ```vb  
    Public Class ShadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class ShadowDerivedClass  
        Inherits ShadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub ShowStrings()  
            Dim s As String = $"Unqualified shadowString: {shadowString}{vbCrLf}MyBase.shadowString: {MyBase.shadowString}"
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     En el ejemplo anterior se declara la variable `shadowString` en la clase base y se sombrea en la clase derivada. El procedimiento `ShowStrings` en la clase derivada muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado. A continuación, muestra la versión sombreada cuando `shadowString` está calificado con la palabra clave `MyBase`.  
  
## <a name="robust-programming"></a>Programación sólida

La sombra introduce más de una versión de una variable con el mismo nombre. Cuando una instrucción de código hace referencia al nombre de la variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación. Esto puede aumentar el riesgo de hacer referencia a una versión no intencionada de una variable de la que se ha realizado una copia sombra. Puede reducir este riesgo calificando por completo todas las referencias a una variable de la que se ha realizado una copia sombra.

## <a name="see-also"></a>Vea también

- [Referencias a elementos declarados](references-to-declared-elements.md)
- [Sombrear en Visual Basic](shadowing.md)
- [Diferencias entre sombrear y reemplazar](differences-between-shadowing-and-overriding.md)
- [Cómo: Ocultar una variable con el mismo nombre que la variable @ no__t-0
- [Cómo: Acceder a una variable oculta por una clase derivada @ no__t-0
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase y MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../objects-and-classes/inheritance-basics.md)
