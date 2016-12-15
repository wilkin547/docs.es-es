---
title: "C&#243;mo: Ocultar una variable con el mismo nombre que su variable (Visual Basic) | Microsoft Docs"
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
  - "instrucciones de declaración, elementos declarados"
  - "declaraciones, elementos"
  - "elementos declarados, acerca de los elementos declarados"
  - "elementos declarados, hacer referencia"
  - "declarar elementos"
  - "nombres de elementos, calificación"
  - "calificación, de nombres de elementos"
  - "referencias, elementos declarados"
  - "hacer referencia a elementos declarados"
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
caps.latest.revision: 25
caps.handback.revision: 25
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Ocultar una variable con el mismo nombre que su variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puede ocultar una variable *sombreándola*, es decir, volviéndola a definir con una variable del mismo nombre.  Puede sombrear la variable que desea ocultar de dos maneras:  
  
-   **Sombreado por ámbito.** Puede sombrearla por ámbito volviéndola a declarar dentro de una subregión de la región que contiene la variable que desea ocultar.  
  
-   **Sombreado por herencia.** Si la variable que desea ocultar está definida en el nivel de clase, puede sombrearla por herencia volviéndola a declarar con la palabra clave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) en una clase derivada.  
  
## Dos maneras a ocultar una variable  
  
#### Para ocultar una variable sombreándola por ámbito  
  
1.  Determine la región que define la variable que desea ocultar y determine una subregión en la que va a definirla de nuevo en su variable.  
  
    |Región de la variable|Subregión permitida para volverla a definir|  
    |---------------------------|-------------------------------------------------|  
    |Módulo|Una clase dentro del módulo|  
    |Clase|Una subclase dentro de la clase<br /><br /> Un procedimiento dentro de la clase|  
  
     No puede volver a definir una variable de procedimiento en un bloque dentro de ese procedimiento, por ejemplo en una construcción `If`...`End If` o en un bucle `For`.  
  
2.  Cree la subregión si es que no existe ya.  
  
3.  Dentro de la subregión, escriba una instrucción [Dim \(Instrucción\)](../../../../visual-basic/language-reference/statements/dim-statement.md) que declara la variable de sombreado.  
  
     Cuando un código de la subregión hace referencia al nombre de variable, el compilador resuelve la referencia con la variable sombreada.  
  
     El ejemplo siguiente ilustra el sombreado por ámbito, así como una referencia que omite el sombreado.  
  
    ```  
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
  
     El ejemplo anterior declara la variable `num` tanto en el nivel de módulo como en el nivel de procedimiento \(en el procedimiento `show`\).  La variable local `num` prevalece sobre la variable de nivel de módulo `num` en `show`, por lo que la variable local se establece en 2.  Sin embargo, no hay ninguna variable local que prevalezca sobre `num` en el procedimiento `useModuleLevelNum`.  Por consiguiente, `useModuleLevelNum` establece el valor de la variable de nivel de módulo en 1.  
  
     La llamada a `MsgBox` dentro de `show` omite el mecanismo de sombreado calificando `num` con el nombre del módulo.  Por consiguiente, muestra la variable de nivel de módulo en lugar de la variable local.  
  
#### Para ocultar una variable sombreándola por herencia  
  
1.  Asegúrese de que la variable que desea ocultar está declarada en una clase y en el nivel de clase \(fuera de cualquier procedimiento\).  De lo contrario no puede sombrearla por herencia.  
  
2.  Defina una clase derivada de la clase de la variable si es que no existe ya una.  
  
3.  Dentro de la clase derivada, escriba una instrucción `Dim` que declare su variable.  Incluya la palabra clave [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) en la declaración.  
  
     Cuando un código de la clase derivada hace referencia al nombre de variable, el compilador resuelve la referencia en su variable.  
  
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
  
     En el ejemplo anterior, se declara la variable `shadowString` en la clase base y se sombrea dicha variable en la clase derivada.  El procedimiento `showStrings` de la clase derivada muestra la versión de sombreado de la cadena cuando el nombre `shadowString` no está calificado.  Luego, muestra la versión oculta cuando `shadowString` está calificado con la palabra clave `MyBase`.  
  
## Programación eficaz  
 El ocultamiento presenta más de una versión de una variable con el mismo nombre.  Cuando una instrucción de código hace referencia al nombre de variable, la versión en la que el compilador resuelve la referencia depende de factores como la ubicación de la instrucción de código y la presencia de una cadena de calificación.  Esto puede aumentar el riesgo de hacer referencia a una versión no deseada de una variable sombreada.  Puede reducir ese riesgo calificando por completo todas las referencias en una variable sombreada.  
  
## Vea también  
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Sombrear en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Diferencias entre sombrear y reemplazar](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [Cómo: Ocultar una variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [Cómo: Obtener acceso a una variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Fundamentos de la herencia](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)