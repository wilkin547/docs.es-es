---
title: "Cómo: Llamar a un método de extensión (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25b5a86af15694e6f64f96a5d5d645a01f8f1f12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Cómo: Llamar a un método de extensión (Visual Basic)
Métodos de extensión permiten agregar métodos a una clase existente. Después de que se declara un método de extensión y se incluyen en el ámbito, se puede llamar como un método de instancia del tipo que extiende. Para obtener más información sobre cómo escribir un método de extensión, vea [Cómo: escribir un método de extensión](./how-to-write-an-extension-method.md).  
  
 Las instrucciones siguientes hacen referencia al método de extensión `PrintAndPunctuate`, que mostrará la instancia de cadena que lo invoca, seguida de cualquier valor se envía para el segundo parámetro, `punc`.  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 El método debe estar en ámbito cuando se llama.  
  
### <a name="to-call-an-extension-method"></a>Para llamar a un método de extensión  
  
1.  Declare una variable que tiene el tipo de datos del primer parámetro del método de extensión. Para `PrintAndPunctuate`, necesita un <xref:System.String> variable:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  Que la variable va a invocar el método de extensión y su valor se enlaza al primer parámetro, `aString`. Se mostrará la siguiente instrucción que realiza la llamada `Ready?`.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Tenga en cuenta que la llamada a este método de extensión se parece simplemente como una llamada a cualquiera de los <xref:System.String> métodos que requieren un parámetro de instancia:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  Declare otra variable de cadena y llame al método nuevo para comprobar que funciona con cualquier cadena.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     El resultado es este tiempo: `or not!!!`.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente es un ejemplo completo de la creación y uso de un método de extensión simple.  
  
```vb  
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
  
## <a name="see-also"></a>Vea también  
 [Escribir un método de extensión](./how-to-write-an-extension-method.md)  
 [Métodos de extensión](./extension-methods.md)  
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
