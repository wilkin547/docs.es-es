---
title: Construcciones de referencia inversa en expresiones regulares
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2ec92933bdf123412a3d489fc493d76c4a0dc0d0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a>Construcciones de referencia inversa en expresiones regulares
Las referencias inversas proporcionan una forma cómoda de identificar un carácter o subcadena repetidos dentro de una cadena. Por ejemplo, si la cadena de entrada contiene varias apariciones de una subcadena arbitraria, puede buscar una coincidencia con la primera aparición con un grupo de captura y después usar una referencia inversa para buscar una coincidencia con las siguientes apariciones de la subcadena.  
  
> [!NOTE]
>  Se usa una sintaxis independiente para hacer referencia a los grupos de captura con numeración y con nombre de las cadenas de reemplazo. Para obtener más información, consulta [Substitutions](substitutions-in-regular-expressions.md).  
  
 .NET define elementos del lenguaje independientes para hacer referencia a los grupos de captura con numeración y con nombre. Para más información sobre los grupos de captura con nombre, vea [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
## <a name="numbered-backreferences"></a>Referencias inversas con numeración  
 Una referencia inversa con numeración usa la siguiente sintaxis:  
  
 `\` *número*  
  
 donde *número* es la posición ordinal del grupo de captura en la expresión regular. Por ejemplo, `\4` coincide con el contenido del cuarto grupo de captura. Si *número* no está definido en el patrón de expresión regular, se produce un error de análisis y el motor de expresiones regulares produce una clase <xref:System.ArgumentException>. Por ejemplo, la expresión regular `\b(\w+)\s\1` es válida, porque `(\w+)` es el primer y único grupo de captura de la expresión. Por otro lado, `\b(\w+)\s\2` no es válida y produce una excepción de argumento porque no hay ningún grupo de captura con numeración `\2`.  
  
 Tenga en cuenta la ambigüedad entre los códigos de escape octales (como `\16`) y las referencias inversas `\`*número* que usan la misma notación. Esta ambigüedad se resuelve de la siguiente forma:  
  
-   Las expresiones `\1` a `\9` siempre se interpretan como referencias inversas y no como códigos octales.  
  
-   Si el primer dígito de una expresión con varios dígitos es 8 o 9 (como `\80` o `\91`), la expresión se interpreta como un literal.  
  
-   Las expresiones a partir de `\10` y superiores se consideran referencias inversas si hay una referencia inversa que se corresponda con ese número; en caso contrario, se interpretan como códigos octales.  
  
-   Si una expresión regular contiene una referencia inversa a un número de grupo sin definir, se produce un error de análisis y el motor de expresiones regulares produce una clase <xref:System.ArgumentException>.  
  
 Si la ambigüedad constituye un problema, puede usar la notación `\k<`*nombre*`>`, que es inequívoca y no se puede confundir con códigos de caracteres octales. De forma similar, los códigos hexadecimales como `\xdd` son inequívocos y no se pueden confundir con las referencias inversas.  
  
 En el ejemplo siguiente, se buscan caracteres de palabra duplicados en una cadena. Define una expresión regular, `(\w)\1`, que consta de los siguientes elementos.  
  
|Elemento|Description|  
|-------------|-----------------|  
|`(\w)`|Coincide con un carácter que se usa para formar palabras y se lo asigna al primer grupo de captura.|  
|`\1`|Coincide con el siguiente carácter que sea igual que el valor del primer grupo de captura.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a>Referencias inversas con nombre  
 Una referencia inversa con nombre se define mediante la sintaxis siguiente:  
  
 `\k<` *name* `>`  
  
 O bien  
  
 `\k'` *nombre* `'`  
  
 donde *nombre* es el nombre de un grupo de captura definido en el patrón de expresión regular. Si *nombre* no está definido en el patrón de expresión regular, se produce un error de análisis y el motor de expresiones regulares produce una clase <xref:System.ArgumentException>.  
  
 En el ejemplo siguiente, se buscan caracteres de palabra duplicados en una cadena. Define una expresión regular, `(?<char>\w)\k<char>`, que consta de los siguientes elementos.  
  
|Elemento|Description|  
|-------------|-----------------|  
|`(?<char>\w)`|Coincide con un carácter que se usa para formar palabras y se lo asigna a un grupo de captura denominado `char`.|  
|`\k<char>`|Coincide con el siguiente carácter que sea igual que el valor del grupo de captura `char`.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 Tenga en cuenta que *nombre* también puede ser la representación de cadena de un número. Por ejemplo, en el ejemplo siguiente, se usa la expresión regular `(?<2>\w)\k<2>` para buscar caracteres de palabra duplicados en una cadena.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a>Con qué coinciden las referencias inversas  
 Una referencia inversa constituye la definición más reciente de un grupo (la definición más inmediatamente a la izquierda, al coincidir de izquierda a derecha). Cuando un grupo realiza varias capturas, una referencia inversa se refiere a la captura más reciente.  
  
 En el ejemplo siguiente, se incluye un patrón de expresión regular, `(?<1>a)(?<1>\1b)*`, que redefine el grupo con nombre \1. En la tabla siguiente, se describe cada patrón de la expresión regular.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`(?<1>a)`|Coincide con el carácter "a" y asigna el resultado al grupo de captura denominado `1`.|  
|`(?<1>\1b)*`|Coincide con 0 o 1 apariciones del grupo denominado `1` junto con una "b" y asigna el resultado al grupo de captura denominado `1`.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 Al comparar la expresión regular con la cadena de entrada ("aababb"), el motor de expresiones regulares realiza las siguientes operaciones:  
  
1.  Comienza al principio de la cadena y hace que "a" coincida correctamente con la expresión `(?<1>a)`. Ahora, el valor del grupo `1` es "a".  
  
2.  Se desplaza hasta el segundo carácter y hace que la cadena "ab" coincida correctamente con la expresión `\1b`, o "ab". Después, asigna el resultado "ab" a `\1`.  
  
3.  Se desplaza hasta el cuarto carácter. La expresión `(?<1>\1b)` puede coincidir cero o más veces, así que la cadena "abb" coincide correctamente con la expresión `\1b`. Vuelve a asignar el resultado, "abb", a `\1`.  
  
 En este ejemplo, `*` es un cuantificador de bucle: se evalúa repetidas veces hasta que el motor de expresiones regulares no puede coincidir con el patrón que define. Los cuantificadores de bucle no borran las definiciones de grupo.  
  
 Si un grupo no ha capturado ninguna subcadena, no se define una referencia inversa a ese grupo y no coincide nunca. Así lo ilustra el patrón de expresión regular `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b` que se define de la siguiente forma:  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Comienza la búsqueda de coincidencias en un límite de palabras.|  
|`(\p{Lu}{2})`|Coincide con dos letras mayúsculas. Este es el primer grupo de captura.|  
|`(\d{2})?`|Coincide con una o ninguna aparición de dos dígitos decimales. Este es el segundo grupo de captura.|  
|`(\p{Lu}{2})`|Coincide con dos letras mayúsculas. Éste es el tercer grupo de captura.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
 Una cadena de entrada puede coincidir con esta expresión regular aunque no estén presentes los dos dígitos decimales que define el segundo grupo de captura. En el ejemplo siguiente, se muestra que, aunque la coincidencia es correcta, hay un grupo de captura vacío entre dos grupos de captura correctos.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a>Vea también  
 [Lenguaje de expresiones regulares: referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
