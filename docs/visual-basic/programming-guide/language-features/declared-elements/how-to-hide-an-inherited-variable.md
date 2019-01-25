---
title: Procedimiento Ocultar una Variable heredada (Visual Basic)
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
ms.openlocfilehash: 6cf45b12bebc254a0d96516ab262d7aae3d70746
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691260"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Procedimiento Ocultar una Variable heredada (Visual Basic)
Una clase derivada hereda todas las definiciones de su clase base. Si desea definir una variable con el mismo nombre que un elemento de la clase base, puede ocultar, o *sombra*, ese elemento de la clase base al definir la variable en la clase derivada. Si lo hace, el código en la clase derivada tiene acceso a la variable a menos que explícitamente omite el mecanismo de sombreado.  
  
 Es otro motivo que desea ocultar una variable heredada para protegerse frente a la revisión de la clase base. La clase base puede sufrir un cambio que modifica el elemento que se hereda. Si esto ocurre, el `Shadows` modificador fuerza las referencias de la clase derivada que se resuelva a la variable, en lugar de en el elemento de la clase base.  
  
### <a name="to-hide-an-inherited-variable"></a>Para ocultar una variable heredada  
  
1.  Asegúrese de que se declara la variable que desea ocultar en el nivel de clase (fuera de cualquier procedimiento). En caso contrario, no es necesario ocultarlo.  
  
2.  Dentro de la clase derivada, escribe un [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) declarar la variable. Use el mismo nombre que el de la variable heredada.  
  
3.  Incluir el [sombras](../../../../visual-basic/language-reference/modifiers/shadows.md) palabra clave en la declaración.  
  
     Cuando el código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia a la variable.  
  
     El ejemplo siguiente ilustra el sombreado de una variable heredada.  
  
    ```  
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
  
     El ejemplo anterior declara la variable `shadowString` en la clase base y lo reemplaza en la clase derivada. El procedimiento `showStrings` en la clase derivada, muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado. A continuación, muestra la versión sombreada cuando `shadowString` se califica con el `MyBase` palabra clave.  
  
## <a name="robust-programming"></a>Programación sólida  
 El sombreado presenta más de una versión de una variable con el mismo nombre. Cuando una instrucción de código hace referencia al nombre de variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación. Esto puede aumentar el riesgo de que hace referencia a una versión no deseada de una variable sombreada. Puede reducir este riesgo si califica completamente todas las referencias a una variable sombreada.  
  
## <a name="see-also"></a>Vea también
- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Diferencias entre sombrear y reemplazar](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Cómo: Ocultar una Variable con el mismo nombre que su Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Cómo: Obtener acceso a una Variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
