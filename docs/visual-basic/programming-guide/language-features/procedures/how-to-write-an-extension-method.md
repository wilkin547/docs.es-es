---
description: 'Más información acerca de cómo: escribir un método de extensión (Visual Basic)'
title: Procedimiento para escribir un método de extensión
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: 4c5d88976e55288ccb350ab82d459db0a23f468e
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476194"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Cómo: Escribir un método de extensión (Visual Basic)

Los métodos de extensión permiten agregar métodos a una clase existente. Se puede llamar al método de extensión como si fuera una instancia de esa clase.

### <a name="to-define-an-extension-method"></a>Para definir un método de extensión

1. Abra una aplicación Visual Basic nueva o existente en Visual Studio.

2. En la parte superior del archivo en el que desea definir un método de extensión, incluya la siguiente instrucción de importación:

    ```vb
    Imports System.Runtime.CompilerServices
    ```

3. Dentro de un módulo en la aplicación nueva o existente, comience la definición del método con el [`<Extension>`](xref:System.Runtime.CompilerServices.ExtensionAttribute) atributo:

    ```vb
    <Extension()>
    ```

    Tenga en cuenta que el `Extension` atributo solo se puede aplicar a un método (un `Sub` `Function` procedimiento o) en un [módulo](../../../language-reference/statements/module-statement.md)de Visual Basic. Si se aplica a un método en `Class` o `Structure` , el compilador Visual Basic genera el error [BC36551](../../../misc/bc36551.md), "los métodos de extensión solo se pueden definir en módulos".

4. Declare el método de la manera habitual, salvo que el tipo del primer parámetro debe ser el tipo de datos que desea extender.

    ```vb
    <Extension()>
    Public Sub SubName(para1 As ExtendedType, <other parameters>)
         ' < Body of the method >
    End Sub
    ```

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se declara un método de extensión en el módulo `StringExtensions` . Un segundo módulo, `Module1` , importa `StringExtensions` y llama al método. El método de extensión debe estar en el ámbito cuando se llama a. El método de extensión `PrintAndPunctuate` extiende la <xref:System.String> clase con un método que muestra la instancia de cadena seguida de una cadena de símbolos de puntuación enviados como parámetro.

```vb
' Declarations will typically be in a separate module.
Imports System.Runtime.CompilerServices

Module StringExtensions
    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
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

Observe que el método se define con dos parámetros y se llama con solo uno. El primer parámetro, `aString` , en la definición del método, se enlaza a `example` , la instancia de `String` que llama al método. El resultado del ejemplo es el siguiente:

```console
Hello?
Hello!!!!
```

## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Métodos de extensión](extension-methods.md)
- [Module (Instrucción)](../../../language-reference/statements/module-statement.md)
- [Argumentos y parámetros de procedimiento](procedure-parameters-and-arguments.md)
- [Ámbito en Visual Basic](../declared-elements/scope.md)
