---
title: "C&#243;mo: Escribir un m&#233;todo de extensi&#243;n (Visual Basic) | Microsoft Docs"
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
  - "extender tipos de datos"
  - "métodos de extensión [Visual Basic]"
  - "escribir métodos de extensión"
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Escribir un m&#233;todo de extensi&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los métodos de extensión permiten agregar métodos a una clase existente.  Se puede llamar al método de extensión como si fuera una instancia de esa clase.  
  
### Para definir un método de extensión  
  
1.  Abra en Visual Studio una aplicación de Visual Basic nueva o existente.  
  
2.  En la parte superior del archivo en el que desea definir un método de extensión, incluya la instrucción de importación siguiente:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  Dentro de un módulo de una aplicación nueva o existente, comience la definición de método con el atributo de extensión:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Declare el método como lo haría normalmente, salvo que el tipo del primer parámetro debe ser el tipo de datos que desea extender.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## Ejemplo  
 En el ejemplo siguiente se declara un método de extensión en un módulo `StringExtensions`.  Un segundo módulo, `Module1`, importa `StringExtensions` y llama al método.  Cuando se llama al método de extensión, debe estar en ámbito.  El método de extensión `PrintAndPunctuate` extiende la clase <xref:System.String> con un método que muestra la instancia de la cadena seguida de una cadena de signos de puntuación enviada como un parámetro.  
  
```vb#  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
```vb#  
' Import the module that holds the extension method you want to use,   
' and call it.  
  
Imports ConsoleApplication2.StringExtensions  
  
Module Module1  
  
    Sub Main()  
        Dim example = "Hello"  
        example.PrintAndPunctuate("?")  
        example.PrintAndPunctuate("!!!!")  
    End Sub  
  
End Module  
  
```  
  
 Observe que el método se define con dos parámetros y se llama solamente con uno.  El primer parámetro, `aString`, en la definición de método se enlaza a `example`, la instancia de `String` que llama al método.  El resultado del ejemplo es el siguiente:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## Vea también  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [métodos de extensión.](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Module \(Instrucción\)](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)