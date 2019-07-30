---
title: Procedimiento Escribir un método de extensión (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 7a7a9d16d9f69071e9d1dacb0558f7ca92e1d21e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631025"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Procedimiento Escribir un método de extensión (Visual Basic)
Los métodos de extensión permiten agregar métodos a una clase existente. Se puede llamar al método de extensión como si fuera una instancia de esa clase.

### <a name="to-define-an-extension-method"></a>Para definir un método de extensión

1. Abra una aplicación Visual Basic nueva o existente en Visual Studio.

2. En la parte superior del archivo en el que desea definir un método de extensión, incluya la siguiente instrucción de importación:

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. Dentro de un módulo en la aplicación nueva o existente, comience la definición del método con el atributo de extensión:

    ```vb
    <Extension()>
    ```

4. Declare el método de la manera habitual, salvo que el tipo del primer parámetro debe ser el tipo de datos que desea extender.

    ```vb
    <Extension()>
    Public Sub SubName (ByVal para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a>Ejemplo
 En el ejemplo siguiente se declara un método de extensión `StringExtensions`en el módulo. Un segundo módulo, `Module1`, importa `StringExtensions` y llama al método. El método de extensión debe estar en el ámbito cuando se llama a. El método `PrintAndPunctuate` de extensión <xref:System.String> extiende la clase con un método que muestra la instancia de cadena seguida de una cadena de símbolos de puntuación enviados como parámetro.
  
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
  
 Observe que el método se define con dos parámetros y se llama con solo uno. El primer parámetro, `aString`, en la definición del método, se `example`enlaza a, la `String` instancia de que llama al método. El resultado del ejemplo es el siguiente:
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Métodos de extensión](./extension-methods.md)
- [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
