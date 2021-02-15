---
description: 'Más información acerca de cómo: llamar a un método de extensión (Visual Basic)'
title: Procedimiento para llamar a un método de extensión
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: ec5217526eb0cb28d172ab917df08a8bfe87fe95
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471388"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Cómo: Llamar a un método de extensión (Visual Basic)

Los métodos de extensión permiten agregar métodos a una clase existente. Una vez declarado y incorporado un método de extensión en el ámbito, puede llamarlo como un método de instancia del tipo que extiende. Para obtener más información sobre cómo escribir un método de extensión, vea [Cómo: escribir un método de extensión](./how-to-write-an-extension-method.md).

 Las instrucciones siguientes hacen referencia al método de extensión `PrintAndPunctuate` , que mostrará la instancia de la cadena que lo invoca, seguido del valor que se envía para el segundo parámetro, `punc` .

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

El método debe estar en el ámbito cuando se llama a.

### <a name="to-call-an-extension-method"></a>Para llamar a un método de extensión

1. Declare una variable que tenga el tipo de datos del primer parámetro del método de extensión. Para `PrintAndPunctuate` , necesita una <xref:System.String> variable:

    ```vb
    Dim example = "Ready"
    ```

2. Esa variable invocará el método de extensión y su valor se enlazará al primer parámetro, `aString` . Se mostrará la siguiente instrucción de llamada `Ready?` .

    ```vb
    example.PrintAndPunctuate("?")
    ```

     Observe que la llamada a este método de extensión tiene el aspecto de una llamada a cualquiera de los <xref:System.String> métodos de instancia que requieren un parámetro:

    ```vb
    example.EndsWith("dy")
    example.IndexOf("R")
    ```

3. Declare otra variable de cadena y llame de nuevo al método para ver que funciona con cualquier cadena.

    ```vb
    Dim example2 = " or not"
    example2.PrintAndPunctuate("!!!")
    ```

     El resultado es: `or not!!!` .

## <a name="example"></a>Ejemplo

 El código siguiente es un ejemplo completo de la creación y el uso de un método de extensión simple.

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

## <a name="see-also"></a>Consulte también

- [Procedimiento para escribir un método de extensión](./how-to-write-an-extension-method.md)
- [Métodos de extensión](./extension-methods.md)
- [Ámbito en Visual Basic](../declared-elements/scope.md)
