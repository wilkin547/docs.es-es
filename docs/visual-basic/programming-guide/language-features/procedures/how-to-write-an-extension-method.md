---
title: "Cómo: Escribir un método de extensión (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65cdabf59886e7457a327ee9cde968a6a73f2280
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Cómo: Escribir un método de extensión (Visual Basic)
Métodos de extensión permiten agregar métodos a una clase existente. El método de extensión puede llamarse como si fuera una instancia de esa clase.  
  
### <a name="to-define-an-extension-method"></a>Para definir un método de extensión  
  
1.  Abra una aplicación de Visual Basic nueva o existente en Visual Studio.  
  
2.  En la parte superior del archivo en el que desea definir un método de extensión, incluir la siguiente instrucción de importación:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  Dentro de un módulo en la aplicación nueva o existente, comience la definición de método con el atributo de extensión:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Declare el método de la manera normal, salvo que el tipo del primer parámetro debe ser el tipo de datos que desea extender.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara un método de extensión en el módulo `StringExtensions`. Un segundo módulo `Module1`, importa `StringExtensions` y llama al método. El método de extensión debe estar en ámbito cuando se llama. Método de extensión `PrintAndPunctuate` amplía la <xref:System.String> clase con un método que muestra la instancia de cadena seguida de una cadena de signos de puntuación que se envían como un parámetro.  
  
```vb  
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
  
```vb  
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
  
 Tenga en cuenta que el método se define con dos parámetros y se llama con una sola. El primer parámetro, `aString`, en el método de definición se enlaza a `example`, la instancia de `String` que llama al método. El resultado del ejemplo es el siguiente:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [Métodos de extensión](./extension-methods.md)  
 [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
