---
title: "C&#243;mo: Ocultar una variable heredada (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "instrucciones de declaración, elementos declarados"
  - "elementos declarados, acerca de los elementos declarados"
  - "elementos declarados, hacer referencia"
  - "nombres de elementos, calificación"
  - "calificación, de nombres de elementos"
  - "referencias, elementos declarados"
  - "hacer referencia a elementos declarados"
  - "variables [Visual Basic], ocultar heredadas"
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# C&#243;mo: Ocultar una variable heredada (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Una clase derivada hereda todas las definiciones de su clase base.  Si desea definir una variable con el mismo nombre que un elemento de la clase base, puede ocultar o *sombrear* ese elemento de la clase base al definir su variable en la clase derivada.  De este modo, un código de la clase derivada tiene acceso a su variable a menos que omita de forma explícita el mecanismo de sombreado.  
  
 Otra razón para desear ocultar una variable heredada es protegerla de la revisión de la clase base.  La clase base puede experimentar un cambio que modifica el elemento que ha heredado.  En este caso, el modificador `Shadows` fuerza las referencias de la clase derivada que se deben resolver en la variable, no en el elemento de la clase base.  
  
### Para ocultar una variable heredada  
  
1.  Asegúrese de que la variable que desea ocultar está declarada en el nivel de clase \(fuera de cualquier procedimiento\).  De lo contrario, no necesita ocultarla.  
  
2.  Dentro de la clase derivada, escriba [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) para declarar la variable.  Utilice el mismo nombre que el de la variable heredada.  
  
3.  Incluya la palabra clave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) en la declaración.  
  
     Cuando un código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia en su variable.  
  
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
  
     En el ejemplo anterior, se declara la variable `shadowString` en la clase base y se sombrea dicha variable en la clase derivada.  El procedimiento `showStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado.  Luego, muestra la versión sombreada cuando `shadowString` está calificado con la palabra clave `MyBase`.  
  
## Programación eficaz  
 El ocultamiento presenta más de una versión de una variable con el mismo nombre.  Cuando una instrucción de código hace referencia al nombre de variable, la versión en la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.  Esto puede aumentar el riesgo de hacer referencia a una versión no deseada de una variable sombreada.  Puede reducir ese riesgo calificando por completo todas las referencias en una variable sombreada.  
  
## Vea también  
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Diferencias entre sombrear y reemplazar](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [Cómo: Ocultar una variable con el mismo nombre que su variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [Cómo: Obtener acceso a una variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)