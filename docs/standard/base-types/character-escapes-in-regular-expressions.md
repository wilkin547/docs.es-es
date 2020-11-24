---
title: Escapes de carácter en expresiones regulares de .NET
description: Obtenga información sobre los caracteres especiales y caracteres de escape de expresiones regulares de .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unescaped characters
- replacement patterns
- characters, escapes
- regular expressions, character escapes
- escape characters
- .NET regular expressions, character escapes
- constructs, character escapes
ms.assetid: f49cc9cc-db7d-4058-8b8a-422bc08b29b0
ms.openlocfilehash: 5a9890f9ada6a4e749c8cf5ee96d9e8668525040
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823269"
---
# <a name="character-escapes-in-regular-expressions"></a>Escapes de carácter en expresiones regulares
La barra diagonal inversa (\\) en una expresión regular indica una de las siguientes situaciones:  
  
- El carácter que va detrás de ella es un carácter especial, como se muestra en la tabla de la sección siguiente. Por ejemplo, `\b` es un delimitador que indica que una coincidencia de expresión regular debería comenzar en un límite de palabras, `\t` representa un carácter de tabulación y `\x020` representa un espacio.  
  
- Un carácter que de otro modo se interpretaría como una construcción de lenguaje sin escape, se debe interpretar literalmente. Por ejemplo, una llave (`{`) inicia la definición de un cuantificador, pero una barra diagonal inversa seguida de una llave (`\{`) indica que el motor de expresiones regulares debería coincidir con la llave. De igual forma, una sola barra diagonal inversa marca el principio de una construcción de lenguaje con escape, pero dos barras diagonales inversas (`\\`) indican que el motor de expresiones regulares debería coincidir con la barra diagonal inversa.  
  
> [!NOTE]
> Los escapes de caracteres se reconocen en los patrones de expresiones regulares, pero no en los patrones de reemplazo.  
  
## <a name="character-escapes-in-net"></a>Escapes de carácter en .NET  
 En la tabla siguiente se enumeran los escapes de caracteres admitidos en las expresiones regulares de .NET.  
  
|Carácter o secuencia|Descripción|  
|---------------------------|-----------------|  
|Todos los caracteres excepto los siguientes:<br /><br /> . $ ^ { [ ( &#124; ) * + ? \ |Los caracteres que no aparecen en la columna **Carácter o secuencia** no tienen ningún significado especial en las expresiones regulares, sino que equivalen a sí mismos.<br /><br /> Los caracteres incluidos en la columna **Carácter o secuencia** son elementos del lenguaje especial de expresiones regulares. Para que coincidan en una expresión regular, deben escribirse entre secuencias de escape o incluirse en un [grupo de caracteres positivos](character-classes-in-regular-expressions.md). Por ejemplo, las expresiones regulares `\$\d+` o `[$]\d+` coinciden con "$1200".|  
|`\a`|Coincide con un carácter de campana (alarma), `\u0007`.|  
|`\b`|En una clase de caracteres `[`*grupo_caracteres*`]`, coincide con un retroceso, `\u0008`.  (Consulte [Clases de caracteres](character-classes-in-regular-expressions.md)). Fuera de una clase de caracteres, `\b` es un delimitador que coincide con un límite de palabras. (Consulte [Delimitadores](anchors-in-regular-expressions.md)).|  
|`\t`|Coincide con un carácter de tabulación, `\u0009`.|  
|`\r`|Coincide con un retorno de carro, `\u000D`. Observe que `\r` no es equivalente al carácter de nueva línea, `\n`.|  
|`\v`|Coincide con una tabulación vertical, `\u000B`.|  
|`\f`|Coincide con un avance de página, `\u000C`.|  
|`\n`|Coincide con una nueva línea, `\u000A`.|  
|`\e`|Coincide con un escape, `\u001B`.|  
|`\` *nnn*|Coincide con un carácter ASCII, donde *nnn* está compuesto de dos o tres dígitos que representan el código de carácter octal. Por ejemplo, `\040` representa un carácter de espacio. Esta construcción se interpreta como una referencia inversa si tiene un solo dígito (por ejemplo, `\2`) o si se corresponde con el número de un grupo de captura. (Consulte [Construcciones de referencia inversa](backreference-constructs-in-regular-expressions.md)).|  
|`\x` *nn*|Coincide con un carácter ASCII, donde *nn* es un código de carácter hexadecimal de dos dígitos.|  
|`\c` *X*|Coincide con un carácter de control ASCII, donde X es la letra del carácter de control. Por ejemplo, `\cC` es CTRL-C.|  
|`\u` *nnnn*|Coincide con una unidad de código UTF-16 cuyo valor hexadecimal es *nnnn*. **Nota:**  .NET no admite el escape de caracteres de Perl 5 usado para especificar Unicode. El escape de caracteres de Perl 5 tiene el formato `\x{` *####* `…}`, donde *####* `…` es una serie de dígitos hexadecimales. En su lugar, use `\u`*nnnn*.|  
|`\`|Si va seguido de un carácter que no se reconoce como carácter de escape, coincide con ese carácter. Por ejemplo, `\*` coincide con un asterisco (*) y es igual que `\x2A`.|  
  
## <a name="an-example"></a>Un ejemplo  
 En el ejemplo siguiente se muestra el uso de escapes de carácter en una expresión regular. Analiza una cadena que contiene los nombres de las ciudades más grandes del mundo y sus poblaciones en 2009. Cada nombre de ciudad se separa de su población por un carácter de tabulación (`\t`) o una barra vertical (&#124; o `\u007c`). Cada ciudad y su población está separada de la siguiente por un retorno de carro y un avance de línea.  
  
 [!code-csharp[RegularExpressions.Language.Escapes#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.escapes/cs/escape1.cs#1)]
 [!code-vb[RegularExpressions.Language.Escapes#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.escapes/vb/escape1.vb#1)]  
  
 La expresión regular `\G(.+)[\t\u007c](.+)\r?\n` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\G`|Comienza la búsqueda de coincidencias donde finalizó la última coincidencia.|  
|`(.+)`|Buscar cualquier carácter coincidente una o más veces. Este es el primer grupo de captura.|  
|`[\t\u007c]`|Coincide con un carácter de tabulación (`\t`) o una barra vertical (&#124;).|  
|`(.+)`|Buscar cualquier carácter coincidente una o más veces. Este es el segundo grupo de captura.|  
|`\r?\n`|Coincide con cero o un retorno de carro seguido de una nueva línea.|  
  
## <a name="see-also"></a>Vea también

- [Lenguaje de expresiones regulares: referencia rápida](regular-expression-language-quick-reference.md)
