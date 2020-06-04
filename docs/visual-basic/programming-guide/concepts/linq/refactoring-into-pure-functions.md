---
title: Refactorización en funciones puras
ms.date: 07/20/2015
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
ms.openlocfilehash: 415b088661eca347330f4776901d68ee514d8dad
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413484"
---
# <a name="refactoring-into-pure-functions-visual-basic"></a>Refactorizar en funciones puras (Visual Basic)

Un aspecto importante de las transformaciones funcionales puras es aprender cómo refactorizar código usando funciones puras.

Tal como se indicó previamente en esta sección, una función pura tiene dos características útiles:

- No tiene efectos secundarios. La función no cambia variables o datos de ningún tipo fuera de la función.

- Es coherente. Con el mismo conjunto de datos de entrada, siempre devolverá el mismo valor de salida.

 Una forma de realizar una transición a la programación funcional es refactorizar código existente para eliminar efectos secundarios innecesarios y dependencias externas. De esta forma puede crear versiones de función pura del código existente.

En este tema se trata qué es una función pura y qué no es. En el tutorial [: manipular contenido en un documento WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) se muestra cómo manipular un documento WordprocessingML e incluye dos ejemplos de cómo refactorizar usando una función pura.

## <a name="eliminating-side-effects-and-external-dependencies"></a>Eliminar efectos secundarios y dependencias externas

Los siguientes ejemplos contraponen dos funciones no puras y una función pura.

### <a name="non-pure-function-that-changes-a-class-member"></a>Función no pura que cambia un miembro de clase

En el siguiente código, la función `HyphenatedConcat` no es una función pura porque modifica el miembro de datos `aMember` en la clase:

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

Este código genera el siguiente resultado:

```console
StringOne-StringTwo
```

Tenga en cuenta que es irrelevante si los datos que se están modificando tienen `public` `private` acceso o son `shared` miembros o un miembro de instancia. Una función pura no cambia datos fuera de la función.

### <a name="non-pure-function-that-changes-an-argument"></a>Función no pura que cambia un argumento

Asimismo, la siguiente versión de esta misma función no es pura porque modifica el contenido de su parámetro, `sb`.

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

Esta versión del programa crea el mismo resultado que la primera versión porque la función `HyphenatedConcat` ha cambiado el valor (estado) de su primer parámetro invocando la función de miembro <xref:System.Text.StringBuilder.Append%2A>. Tenga en cuenta que esta modificación se produce a pesar del hecho que `HyphenatedConcat` usar el paso de parámetros llamada por valor.

> [!IMPORTANT]
> Para los tipos de referencia, si pasa un parámetro por valor, tiene como resultado una copia de la referencia a un objeto que se está pasando. Esta copia sigue asociada con los mismos datos de la instancia que la referencia original (hasta que la variable de referencia se asigna a un objeto nuevo). La llamada por referencia no es necesariamente requerida para que una función modifique un parámetro.

### <a name="pure-function"></a>Función pura

La versión siguiente del programa muestra cómo implementar la función `HyphenatedConcat` como una función pura.

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

De nuevo, esta versión crea la misma línea de salida: `StringOne-StringTwo`. Tenga en cuenta que para conservar un valor concatenado, se almacena en la variable intermedia `s2`.

Un enfoque que puede ser muy útil para escribir funciones que son localmente impuras (es decir, declaran y modifican variables locales) pero que son globalmente puras. Tales funciones tienen muchas características deseables de facilidad de creación, pero evitan algunas de las expresiones de programación funcional más complicadas, como tener que usar una recursión cuando un simple bucle lograría lo mismo.

## <a name="standard-query-operators"></a>Operadores de consulta estándar

Una característica importante de los operadores de consulta estándar es que se implementan como funciones puras.

Para obtener más información, vea [información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md).

## <a name="see-also"></a>Consulte también

- [Introducción a las transformaciones funcionales puras (Visual Basic)](introduction-to-pure-functional-transformations.md)
- [Programación funcional frente a programación imperativa (Visual Basic)](functional-programming-vs-imperative-programming.md)
