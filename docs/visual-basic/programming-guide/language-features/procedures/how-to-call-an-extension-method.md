---
title: "C&#243;mo: Llamar a un m&#233;todo de extensi&#243;n (Visual Basic) | Microsoft Docs"
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
  - "llamar a métodos de extensión"
  - "métodos de extensión [Visual Basic]"
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Llamar a un m&#233;todo de extensi&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los métodos de extensión permiten agregar métodos a una clase existente.  Después de declarar un método de extensión e incluirlo en el ámbito, se le puede llamar como un método de instancia del tipo que extiende.  Para obtener más información sobre cómo escribir un método de extensión, vea [Cómo: Escribir un método de extensión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-write-an-extension-method.md).  
  
 Las instrucciones siguientes hacen referencia al método de extensión `PrintAndPunctuate`, que mostrará la instancia de la cadena que lo invoca, seguida de cualquier valor que se envía para el segundo parámetro, `punc`.  
  
```vb#  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
  
```  
  
 El método debe estar en ámbito cuando se le llame.  
  
### Para llamar a un método de extensión  
  
1.  Declare una variable que tenga el tipo de datos del primer parámetro del método de extensión.  Para `PrintAndPunctuate`, necesita una variable <xref:System.String>:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  Esa variable invocará al método de extensión y su valor se enlazará al primer parámetro, `aString`.  Aparecerá la siguiente instrucción de llamada `Ready?`.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Observe que la llamada a este método de extensión se parece simplemente a una llamada a cualquiera de los métodos de instancia <xref:System.String> que requieren un parámetro:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  Declare otra variable de cadena y llame de nuevo al método para comprobar que funciona con cualquier cadena.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     Esta vez el resultado es: `or not!!!`.  
  
## Ejemplo  
 El código siguiente es un ejemplo completo de la creación y uso de un método de extensión simple.  
  
```vb#  
Imports System.Runtime.CompilerServices  
Imports ConsoleApplication1.StringExtensions  
  
Module Module1  
  
    Sub Main()  
  
        Dim example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
        Dim example2 = "Goodbye"  
        example2.PrintAndPunctuate("?")  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
End Module  
  
' Output:  
' Hello.  
' Hello!!!!  
' Goodbye?  
```  
  
## Vea también  
 [Cómo: Escribir un método de extensión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-write-an-extension-method.md)   
 [métodos de extensión.](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)