---
title: Procedimiento Llamar a un método de extensión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 5cb0684637a716dfec947740ba345c62eaabddd7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863680"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Procedimiento Llamar a un método de extensión (Visual Basic)
Métodos de extensión permiten agregar métodos a una clase existente. Después de un método de extensión se declaran y se incluyen en el ámbito, puede llamarlo como un método de instancia del tipo que extiende. Para obtener más información sobre cómo escribir un método de extensión, vea [Cómo: Escribir un método de extensión](./how-to-write-an-extension-method.md).  
  
 Las instrucciones siguientes hacen referencia al método de extensión `PrintAndPunctuate`, que mostrará la instancia de cadena que lo invoca, seguida de cualquier valor que se envía para el segundo parámetro, `punc`.  
  
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
  
1. Declare una variable que tiene el tipo de datos del primer parámetro del método de extensión. Para `PrintAndPunctuate`, necesita un <xref:System.String> variable:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2. Que variable invocará el método de extensión y su valor está enlazado al primer parámetro, `aString`. Se mostrará la siguiente instrucción de llamada `Ready?`.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Tenga en cuenta que la llamada a este método de extensión es simplemente como una llamada a cualquiera de los <xref:System.String> métodos que requieren un parámetro de instancia:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3. Declare otra variable de cadena y llame al método nuevo para comprobar que funciona con cualquier cadena.  
  
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

- [Cómo: Escribir un método de extensión](./how-to-write-an-extension-method.md)
- [Métodos de extensión](./extension-methods.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
