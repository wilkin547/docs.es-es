---
title: "Escapes de carácter en expresiones regulares"
description: "Escapes de carácter en expresiones regulares"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 41d35531-2af9-47d4-9780-fbc1e682fbc2
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 08a781be74120d26b8408ee8e9b12051b005ad54

---

# <a name="character-escapes-in-regular-expressions"></a>Escapes de carácter en expresiones regulares

La barra diagonal inversa (\) en una expresión regular indica una de las siguientes situaciones: 

* El carácter que va detrás de ella es un carácter especial, como se muestra en la tabla de la sección siguiente. Por ejemplo, **\b** es un delimitador que indica que una coincidencia de expresión regular debería comenzar en un límite de palabras, **\t** representa un carácter de tabulación y **\x020** representa un espacio.

* Un carácter que de otro modo se interpretaría como una construcción de lenguaje sin escape, se debe interpretar literalmente. Por ejemplo, una llave (**{**) inicia la definición de un cuantificador, pero una barra diagonal inversa seguida de una llave (**\{**) indica que el motor de expresiones regulares debería coincidir con la llave. De igual forma, una sola barra diagonal inversa marca el principio de una construcción de lenguaje con escape, pero dos barras diagonales inversas (**\\**) indican que el motor de expresiones regulares debería coincidir con la barra diagonal inversa.

> [!NOTE]
> Los escapes de caracteres se reconocen en los patrones de expresiones regulares, pero no en los patrones de reemplazo. 
 
## <a name="character-escapes-in-net"></a>Escapes de carácter en .NET

En la tabla siguiente se enumeran los escapes de caracteres admitidos en las expresiones regulares de .NET.

Carácter o secuencia | Descripción
--------------------- | ----------- 
Todos los caracteres excepto los siguientes: **. $ ^ { [ ( &#124; ) * + ? \** | Los caracteres que no aparecen en la columna **Carácter o secuencia** no tienen ningún significado especial en las expresiones regulares, sino que equivalen a sí mismos. Los caracteres incluidos en la columna **Carácter o secuencia** son elementos del lenguaje especial de expresiones regulares. Para que coincidan en una expresión regular, deben escribirse entre secuencias de escape o incluirse en un grupo de caracteres positivos. Por ejemplo, la expresión regular `\$\d+ or [$]\d+` coincide con "$1200". 
**\a** | Coincide con un carácter de campana (alarma), **\u0007**.
**\b** | En una clase de caracteres __[__*character*_*group*__]__, coincide con un retroceso, **\u0008**. (Consulte [Clases de carácter en expresiones regulares](classes.md)). Fuera de una clase de caracteres, **\b** es un delimitador que coincide con un límite de palabras. (Consulte [Delimitadores en expresiones regulares](anchors.md)).
**\t** | Coincide con una tabulación, **\u0009**.
**\r** | Coincide con un retorno de carro, **\u000D**. Observe que **\r** no es equivalente al carácter de nueva línea, **\n**.
**\v** | Coincide con una tabulación vertical, **\u000B**.
**\f** | Coincide con un avance de página, **\u000C**.
**\n** | Coincide con una nueva línea, **\u000A**.
**\e** | Coincide con un escape, **\u001B**.
**\**_nnn_ | Coincide con un carácter ASCII, donde nnn está compuesto de dos o tres dígitos que representan el código de carácter octal. Por ejemplo, `\040` representa un carácter de espacio. Esta construcción se interpreta como una referencia inversa si tiene un solo dígito (por ejemplo, `\2`) o si se corresponde con el número de un grupo de captura. (Consulte [Construcciones de referencia inversa en expresiones regulares](backreference.md)). 
**\x**_nn_ | Coincide con un carácter ASCII, donde *nn* es un código de carácter hexadecimal de dos dígitos.
**\c**_X_ | Coincide con un carácter de control ASCII, donde *X* es la letra del carácter de control. Por ejemplo, `\cC` es CTRL-C.
**\u**_nnnn_ | Coincide con una unidad de código UTF-16 cuyo valor hexadecimal es *nnnn*. **Nota** .NET no admite el escape de caracteres de Perl 5 usado para especificar Unicode. El escape de caracteres de Perl 5 tiene el formato **\x{###...}**, donde **###...** es una serie de dígitos hexadecimales. En su lugar, use **\u**_nnnn_. 
**\** | Si va seguido de un carácter que no se reconoce como carácter de escape, coincide con ese carácter. Por ejemplo, `\*` coincide con un asterisco (*) y es igual que `\x2A`.
 
## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra el uso de escapes de carácter en una expresión regular. Analiza una cadena que contiene los nombres de las ciudades más grandes del mundo y sus poblaciones en 2009. Cada nombre de ciudad se separa de su población con un carácter de tabulación (**\t**) o una barra vertical (| o `\u007c`). Cada ciudad y su población está separada de la siguiente por un retorno de carro y un avance de línea. 

```csharp
using System;
using System.Text.RegularExpressions;

public class Example
{
   public static void Main()
   {
      string delimited = @"\G(.+)[\t\u007c](.+)\r?\n";
      string input = "Mumbai, India|13,922,125\t\n" + 
                            "Shanghai, China\t13,831,900\n" + 
                            "Karachi, Pakistan|12,991,000\n" + 
                            "Delhi, India\t12,259,230\n" + 
                            "Istanbul, Turkey|11,372,613\n";
      Console.WriteLine("Population of the World's Largest Cities, 2009");
      Console.WriteLine();
      Console.WriteLine("{0,-20} {1,10}", "City", "Population");
      Console.WriteLine();
      foreach (Match match in Regex.Matches(input, delimited))
         Console.WriteLine("{0,-20} {1,10}", match.Groups[1].Value, 
                                            match.Groups[2].Value);
   }
}
// The example displyas the following output:
//       Population of the World's Largest Cities, 2009
//       
//       City                 Population
//       
//       Mumbai, India        13,922,125
//       Shanghai, China      13,831,900
//       Karachi, Pakistan    12,991,000
//       Delhi, India         12,259,230
//       Istanbul, Turkey     11,372,613
```

```vb
Imports System.Text.RegularExpressions

Module Example
   Public Sub Main()
      Dim delimited As String = "\G(.+)[\t\u007c](.+)\r?\n"
      Dim input As String = "Mumbai, India|13,922,125" + vbCrLf + _
                            "Shanghai, China" + vbTab + "13,831,900" + vbCrLf + _
                            "Karachi, Pakistan|12,991,000" + vbCrLf + _
                            "Delhi, India" + vbTab + "12,259,230" + vbCrLf + _
                            "Istanbul, Turkey|11,372,613" + vbCrLf
      Console.WriteLine("Population of the World's Largest Cities, 2009")
      Console.WriteLine()
      Console.WriteLine("{0,-20} {1,10}", "City", "Population")
      Console.WriteLine()
      For Each match As Match In Regex.Matches(input, delimited)
         Console.WriteLine("{0,-20} {1,10}", match.Groups(1).Value, _
                                            match.Groups(2).Value)
      Next                         
   End Sub
End Module
' The example displays the following output:
'       Population of the World's Largest Cities, 2009
'       
'       City                 Population
'       
'       Mumbai, India        13,922,125
'       Shanghai, China      13,831,900
'       Karachi, Pakistan    12,991,000
'       Delhi, India         12,259,230
'       Istanbul, Turkey     11,372,613
```

La expresión regular `\G(.+)[\t|\u007c](.+)\r?\n` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`\G` | Comienza la búsqueda de coincidencias donde finalizó la última coincidencia.
`(.+)` | Buscar cualquier carácter coincidente una o más veces. Este es el primer grupo de captura.
`[\t\u007c]` | Coincide con un carácter de tabulación (**\t**) o una barra vertical (&#124;).
`(.+)` | Buscar cualquier carácter coincidente una o más veces. Este es el segundo grupo de captura.
`\r?\n` | Coincide con cero o un retorno de carro seguido de una nueva línea.
 
## <a name="see-also"></a>Vea también

[Lenguaje de expresiones regulares: referencia rápida](quick-ref.md)




<!--HONumber=Nov16_HO1-->


