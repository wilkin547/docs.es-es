---
title: "C&#243;mo: Obtener acceso a una variable que oculta una clase derivada (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases base, tener acceso a elementos"
  - "elementos declarados, hacer referencia"
  - "nombres de elementos, calificación"
  - "calificación, de nombres de elementos"
  - "referencias, elementos declarados"
  - "variables [Visual Basic], tener acceso a los ocultos"
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Obtener acceso a una variable que oculta una clase derivada (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Cuando un código de una clase derivada tiene acceso a una variable, el compilador resuelve normalmente la referencia en la versión accesible más cercana, es decir, la versión accesible con el menor número de pasos de derivación en sentido inverso desde la clase que obtiene acceso.  Si la variable está definida en la clase derivada, el código tiene acceso normalmente a esta definición.  
  
 Si la variable de la clase derivada enmascara una variable de la clase base, oculta la versión de la clase base.  Sin embargo, puede tener acceso a la variable de la clase base calificándola con la palabra clave `MyBase`.  
  
### Para tener acceso a una variable de la clase base ocultada por una clase derivada  
  
-   En una expresión o instrucción de asignación, preceda el nombre de variable con la palabra clave `MyBase` y un punto \(`.`\).  
  
     El compilador resuelve la referencia en la versión de la clase base de la variable.  
  
     El ejemplo siguiente ilustra el sombreado por herencia.  Realiza dos referencias, una que tiene acceso a la variable de sombreado y otra que omite el sombreado.  
  
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
  
     En el ejemplo anterior, se declara la variable `shadowString` en la clase base y se sombrea dicha variable en la clase derivada.  El procedimiento `showStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado.  Luego, muestra la versión oculta cuando `shadowString` está calificado con la palabra clave `MyBase` .  
  
## Programación eficaz  
 Para reducir el riesgo de hacer referencia a una versión no deseada de una variable oculta, puede calificar por completo todas las referencias a una variable oculta.  El ocultamiento presenta más de una versión de una variable con el mismo nombre.  Cuando una instrucción de código hace referencia al nombre de variable, la versión en la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.  Esto puede aumentar el riesgo de hacer referencia a una versión errónea de la variable.  
  
## Vea también  
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Diferencias entre sombrear y reemplazar](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [Cómo: Ocultar una variable con el mismo nombre que su variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [Cómo: Ocultar una variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)