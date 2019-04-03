---
title: Filtrar Obtener acceso a una Variable que oculta una clase derivada (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: a97a51d4570d87eaa873fb3152ad810f528dff46
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832182"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Filtrar Obtener acceso a una Variable que oculta una clase derivada (Visual Basic)
Cuando el código en una clase derivada tiene acceso a una variable, el compilador resuelve normalmente la referencia a la versión accesible más cercana, es decir, la versión accesible los mínimos pasos de derivación en sentido con versiones anteriores de la clase que tiene acceso. Si la variable se define en la clase derivada, el código tiene acceso normalmente a esa definición.  
  
 Si la variable de clase derivada oculta una variable en la clase base, oculta la versión de la clase base. Sin embargo, puede acceder a la variable de clase base mediante su calificación con la `MyBase` palabra clave.  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Para obtener acceso a una variable de clase base oculta por una clase derivada  
  
-   En una expresión o instrucción de asignación, delante del nombre de variable con el `MyBase` palabra clave y un período (`.`).  
  
     El compilador resuelve la referencia a la versión de la variable de clase base.  
  
     El ejemplo siguiente ilustra el sombreado por herencia. Hace que dos referencias, uno que tiene acceso a la variable de sombreado y otro que omite el sombreado.  
  
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
 Para reducir el riesgo de que hace referencia a una versión no deseada de una variable sombreada, puede calificar todas las referencias a una variable sombreada. El sombreado presenta más de una versión de una variable con el mismo nombre. Cuando una instrucción de código hace referencia al nombre de variable, la versión a la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación. Esto puede aumentar el riesgo de que hace referencia a una versión incorrecta de la variable.  
  
## <a name="see-also"></a>Vea también

- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Diferencias entre sombrear y reemplazar](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Cómo: Ocultar una Variable con el mismo nombre que su Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Cómo: Ocultar una Variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
