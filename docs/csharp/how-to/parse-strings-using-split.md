---
title: "Cómo: Analizar cadenas mediante String.Split (Guía de C#)"
description: String.Split devuelve una matriz de cadenas dividida entre un conjunto de delimitadores. Es una manera sencilla de analizar cadenas.
ms.date: 01/03/2018
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
author: BillWagner
ms.author: wiwagn
ms.custom: mvc
ms.openlocfilehash: fc1032f2cdf6706ec933323643dbf6ecff3e9f6f
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-parse-strings-using-stringsplit-c-guide"></a>Cómo: Analizar cadenas mediante String.Split (Guía de C#)

El método <xref:System.String.Split%2A?displayProperty=nameWithType> crea una matriz de subcadenas mediante la división de la cadena de entrada en función de uno o varios delimitadores. Suele ser la manera más fácil de separar una cadena en límites de palabras. También sirve para dividir las cadenas en otras cadenas o caracteres específicos.

Este código divide una frase común en una matriz de cadenas para cada palabra.
Para probarlo, solo tiene que presionar el botón *Ejecutar*.

[!code-csharp-interactive[split strings on word boundaries](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#1)]

Todas las instancias de un carácter separador generan un valor en la matriz devuelta. Los caracteres separadores consecutivos generan la cadena vacía como un valor en la matriz devuelta.  Puede ver esto en el ejemplo siguiente, que usa espacios como separador:

[!code-csharp-interactive[split strings with repeated separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#2)]

Este comportamiento resulta más fácil para formatos como los de los archivos de valores separados por comas (CSV) que representan datos tabulares. Las comas consecutivas representan una columna en blanco.

Puede pasar un parámetro <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=fullName> opcional para excluir cualquier cadena vacía en la matriz devuelta. Para un procesamiento más complicado de la colección devuelta, puede usar [LINQ](../programming-guide/concepts/linq/index.md) para manipular la secuencia de resultados.    

<xref:System.String.Split%2A?displayProperty=nameWithType> puede usar varios caracteres separadores. En este ejemplo se usan espacios, comas, puntos, dos puntos y tabulaciones; están incluidos todos en una matriz que contiene estos caracteres de separación y que se pasa a <xref:System.String.Split%2A>.  En el bucle al final del código se muestra cada una de las palabras de la matriz devuelta.  

[!code-csharp-interactive[split strings using multiple separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#3)]

Las instancias consecutivas de cualquier separador generan la cadena vacía en la matriz de salida:

[!code-csharp-interactive[split strings using multiple consecutive separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#4)]

<xref:System.String.Split%2A?displayProperty=nameWithType> puede tomar una matriz de cadenas (secuencias de caracteres que actúan como separadores para analizar la cadena de destino, en lugar de caracteres individuales).  
  
[!code-csharp-interactive[split strings using strings as separators](../../../samples/snippets/csharp/how-to/strings/ParseStringsUsingSplit.cs#5)]

Eche un vistazo al código de nuestro [repositorio de GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings) y pruebe estos ejemplos.

## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../programming-guide/index.md)  
 [Cadenas](../programming-guide/strings/index.md)  
 [Expresiones regulares de .NET Framework](https://msdn.microsoft.com/library/hs600312)
