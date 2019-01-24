---
title: Procedimiento Escribir un método de extensión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 019104956b21e527c0498c286d85da27abdc5695
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576076"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Procedimiento Escribir un método de extensión (Visual Basic)
Métodos de extensión permiten agregar métodos a una clase existente. El método de extensión puede llamarse como si fuera una instancia de esa clase.  
  
### <a name="to-define-an-extension-method"></a>Para definir un método de extensión  
  
1.  Abra una aplicación nueva o existente de Visual Basic en Visual Studio.  
  
2.  En la parte superior del archivo en el que desea definir un método de extensión, incluya la siguiente instrucción import:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  Dentro de un módulo en la aplicación nueva o existente, comience la definición de método con el atributo de extensión:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Declare el método de la manera normal, excepto que el tipo del primer parámetro debe ser el tipo de datos que desea extender.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara un método de extensión en el módulo `StringExtensions`. Un segundo módulo `Module1`, importa `StringExtensions` y llama al método. El método de extensión debe estar en ámbito cuando se llama. Método de extensión `PrintAndPunctuate` amplía la <xref:System.String> clase con un método que muestra la instancia de la cadena seguida de una cadena de signos de puntuación enviados como un parámetro.  
  
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
  
 Tenga en cuenta que el método se define con dos parámetros y llama a con solo uno. El primer parámetro, `aString`, en el método de definición se enlaza a `example`, la instancia de `String` que llama al método. El resultado del ejemplo es el siguiente:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>Vea también
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Métodos de extensión](./extension-methods.md)
- [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
