---
title: Refactorizar en funciones puras (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99e7d27b-a3ff-4577-bdb2-5a8278d6d7af
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d0a1b8d314cf1403ef5065e5432f7acd15ebb440
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="refactoring-into-pure-functions-visual-basic"></a>Refactorizar en funciones puras (Visual Basic)
Un aspecto importante de las transformaciones funcionales puras es aprender cómo refactorizar código usando funciones puras.  
  
 Tal como se indicó previamente en esta sección, una función pura tiene dos características útiles:  
  
-   No tiene efectos secundarios. La función no cambia variables o datos de ningún tipo fuera de la función.  
  
-   Es coherente. Con el mismo conjunto de datos de entrada, siempre devolverá el mismo valor de salida.  
  
 Una forma de realizar una transición a la programación funcional es refactorizar código existente para eliminar efectos secundarios innecesarios y dependencias externas. De esta forma puede crear versiones de función pura del código existente.  
  
 En este tema se trata qué es una función pura y qué no es. El [Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial muestra cómo manipular un documento WordprocessingML e incluye dos ejemplos de cómo refactorizar usando una función pura.  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a>Eliminar efectos secundarios y dependencias externas  
 Los siguientes ejemplos contraponen dos funciones no puras y una función pura.  
  
### <a name="non-pure-function-that-changes-a-class-member"></a>Función no pura que cambia un miembro de clase  
 En el siguiente código, la función `HypenatedConcat` no es una función pura porque modifica el miembro de datos `aMember` en la clase:  
  
```vb  
Module Module1  
    Dim aMember As String = "StringOne"  
  
    Public Sub HypenatedConcat(ByVal appendStr As String)  
        aMember = aMember & "-" & appendStr  
    End Sub  
  
    Sub Main()  
        HypenatedConcat("StringTwo")  
        Console.WriteLine(aMember)  
    End Sub  
End Module  
```  
  
 Este código genera el siguiente resultado:  
  
```  
StringOne-StringTwo  
```  
  
 Tenga en cuenta que es irrelevante si tienen los datos que se está modificaciones `public` o `private` acceder, o es una `shared` miembro o un miembro de instancia. Una función pura no cambia datos fuera de la función.  
  
### <a name="non-pure-function-that-changes-an-argument"></a>Función no pura que cambia un argumento  
 Asimismo, la siguiente versión de esta misma función no es pura porque modifica el contenido de su parámetro, `sb`.  
  
```vb  
Module Module1  
    Public Sub HypenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)  
        sb.Append("-" & appendStr)  
    End Sub  
  
    Sub Main()  
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")  
        HypenatedConcat(sb1, "StringTwo")  
        Console.WriteLine(sb1)  
    End Sub  
End Module  
```  
  
 Esta versión del programa crea el mismo resultado que la primera versión porque la función `HypenatedConcat` ha cambiado el valor (estado) de su primer parámetro invocando la función de miembro <xref:System.Text.StringBuilder.Append%2A>. Tenga en cuenta que esta modificación se produce a pesar del hecho que `HypenatedConcat` usar el paso de parámetros llamada por valor.  
  
> [!IMPORTANT]
>  Para los tipos de referencia, si pasa un parámetro por valor, tiene como resultado una copia de la referencia a un objeto que se está pasando. Esta copia sigue asociada con los mismos datos de la instancia que la referencia original (hasta que la variable de referencia se asigna a un objeto nuevo). La llamada por referencia no es necesariamente requerida para que una función modifique un parámetro.  
  
### <a name="pure-function"></a>Función pura  
 La versión siguiente del programa muestra cómo implementar la función `HypenatedConcat` como una función pura.  
  
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
  
 Para obtener más información, consulte [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las transformaciones funcionales puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [Diferencias entre la programación funcional y Programación imperativa (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
