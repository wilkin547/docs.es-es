---
title: Refactorizar en funciones puras (C#)
description: Aprenda a refactorizar el código con funciones puras. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: cc5dd26923e2edaed34c8f1b742b3dfa1e935e68
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87300233"
---
# <a name="refactoring-into-pure-functions-c"></a>Refactorizar en funciones puras (C#)

Un aspecto importante de las transformaciones funcionales puras es aprender cómo refactorizar código usando funciones puras.  
  
> [!NOTE]
> La nomenclatura común en la programación funcional consiste en refactorizar programas usando funciones puras. En Visual Basic y C++, esto se alinea con el uso de funciones en los lenguajes respectivos. No obstante, en C#, las funciones son métodos llamados. Con fines de análisis, una función pura se implementa como un método en C#.  
  
 Tal como se indicó previamente en esta sección, una función pura tiene dos características útiles:  
  
- No tiene efectos secundarios. La función no cambia variables o datos de ningún tipo fuera de la función.  
  
- Es coherente. Con el mismo conjunto de datos de entrada, siempre devolverá el mismo valor de salida.  
  
 Una forma de realizar una transición a la programación funcional es refactorizar código existente para eliminar efectos secundarios innecesarios y dependencias externas. De esta forma puede crear versiones de función pura del código existente.  
  
 En este tema se trata qué es una función pura y qué no es. El tutorial [Tutorial: Manipular contenido en un documento de WordprocessingML (C#)](./shape-of-wordprocessingml-documents.md) muestra cómo manipular un documento de WordprocessingML e incluye dos ejemplos de cómo refactorizar usando una función pura.  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a>Eliminar efectos secundarios y dependencias externas  
 Los siguientes ejemplos contraponen dos funciones no puras y una función pura.  
  
### <a name="non-pure-function-that-changes-a-class-member"></a>Función no pura que cambia un miembro de clase  
 En el siguiente código, la función `HyphenatedConcat` no es una función pura porque modifica el miembro de datos `aMember` en la clase:  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HyphenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HyphenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 Este código genera el siguiente resultado:  
  
```output  
StringOne-StringTwo  
```  
  
 Tenga en cuenta que es irrelevante si los datos que se están modificando tienen acceso a `public` o `private`, o si son un miembro de `static` o un miembro de instancia. Una función pura no cambia datos fuera de la función.  
  
### <a name="non-pure-function-that-changes-an-argument"></a>Función no pura que cambia un argumento  
 Asimismo, la siguiente versión de esta misma función no es pura porque modifica el contenido de su parámetro, `sb`.  
  
```csharp  
public class Program  
{  
    public static void HyphenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HyphenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 Esta versión del programa crea el mismo resultado que la primera versión porque la función `HyphenatedConcat` ha cambiado el valor (estado) de su primer parámetro invocando la función de miembro <xref:System.Text.StringBuilder.Append%2A>. Tenga en cuenta que esta modificación se produce a pesar del hecho que `HyphenatedConcat` usar el paso de parámetros llamada por valor.  
  
> [!IMPORTANT]
> Para los tipos de referencia, si pasa un parámetro por valor, tiene como resultado una copia de la referencia a un objeto que se está pasando. Esta copia sigue asociada con los mismos datos de la instancia que la referencia original (hasta que la variable de referencia se asigna a un objeto nuevo). La llamada por referencia no es necesariamente requerida para que una función modifique un parámetro.  
  
### <a name="pure-function"></a>Función pura  
La versión siguiente del programa muestra cómo implementar la función `HyphenatedConcat` como una función pura.  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 De nuevo, esta versión crea la misma línea de salida: `StringOne-StringTwo`. Tenga en cuenta que para conservar un valor concatenado, se almacena en la variable intermedia `s2`.  
  
 Un enfoque que puede ser muy útil para escribir funciones que son localmente impuras (es decir, declaran y modifican variables locales) pero que son globalmente puras. Tales funciones tienen muchas características deseables de facilidad de creación, pero evitan algunas de las expresiones de programación funcional más complicadas, como tener que usar una recursión cuando un simple bucle lograría lo mismo.  
  
## <a name="standard-query-operators"></a>Operadores de consulta estándar  
 Una característica importante de los operadores de consulta estándar es que se implementan como funciones puras.  
  
 Para obtener más información, vea [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#)).  
  
## <a name="see-also"></a>Consulte también

- [Introducción a las transformaciones funcionales puras (C#)](./introduction-to-pure-functional-transformations.md)
- [Diferencias entre la programación funcional y la programación imperativa (C#)](./functional-programming-vs-imperative-programming.md)
