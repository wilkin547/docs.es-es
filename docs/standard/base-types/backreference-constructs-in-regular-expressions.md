---
title: "Construcciones de referencia inversa en expresiones regulares | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "expresiones regulares de .NET Framework, construcciones de referencia inversa"
  - "referencias inversas"
  - "construcciones, referencia inversa"
  - "expresiones regulares, construcciones de referencia inversa"
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Construcciones de referencia inversa en expresiones regulares
Las referencias inversas proporcionan una manera conveniente de identificar un carácter o subcadena repetido dentro de una cadena.  Por ejemplo, si la cadena de entrada contiene varias veces la misma subcadena arbitraria, puede asociar la primera aparición con un grupo de captura y, a continuación, utilizar una referencia inversa para hacerla coincidir con las siguientes apariciones de la subcadena.  
  
> [!NOTE]
>  Una sintaxis independiente se utiliza para hacer referencia a grupos de captura con nombre y número en cadenas de reemplazo.  Para obtener más información, vea [Sustituciones](../../../docs/standard/base-types/substitutions-in-regular-expressions.md).  
  
 .NET Framework define distintos elementos del lenguaje para hacer referencia a grupos de captura numerados y con nombre.  Para obtener más información sobre los grupos de capturas, vea [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
## Referencias inversas numeradas  
 Una referencia inversa numerada usa la siguiente sintaxis:  
  
 `\` *number*  
  
 donde es la posición ordinal *number* del grupo de captura en la expresión regular.  Por ejemplo, `\4` coincide con el contenido del cuarto grupo de capturas.  Si *number* no se define en la expresión regular, un error de análisis aparece, y el motor de expresiones regulares produce <xref:System.ArgumentException>.  Por ejemplo, la expresión regular `\b(\w+)\s\1` es válida porque `(\w+)` es el primer y único grupo de capturas de la expresión.  Por otro lado, `\b(\w+)\s\2` no es válido e inicia una excepción de argumento porque no hay ningún grupo de capturas con el número `\2`.  
  
 Observe la ambigüedad entre los códigos de escape octales \(como `\16`\) y referencias inversas de `\`*number* que utilizan la misma notación.  Esta ambigüedad se resuelve como sigue:  
  
-   Las expresiones `\1` a `\9` siempre se interpretan como referencias inversas, no como códigos octales.  
  
-   Si el primer dígito de una expresión con varios dígitos es 8 ó 9 \(como `\80` o `\91`\), se interpretará la expresión como un literal.  
  
-   Las expresiones de `\10` y mayores están consideradas referencias inversas si hay una referencia inversa que corresponde a ese número; de lo contrario, se interpretan como códigos octales.  
  
-   Si una expresión regular contiene una referencia inversa a un número de grupo indefinido, se produce un error de análisis y el motor de expresiones regulares inicia una excepción <xref:System.ArgumentException>.  
  
 Si la ambigüedad es un problema, puede utilizar la notación de `\k<`*name*`>` , que no es ambigua y no se puede confundir con códigos de carácter octales.  De forma similar, los códigos hexadecimales como `\xdd` son inequívocos y no se pueden confundir con referencias inversas.  
  
 El ejemplo siguiente busca caracteres de palabra duplicados en una cadena.  Define una expresión regular, `(\w)\1`, que se compone de los siguientes elementos.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`(\w)`|Busca una coincidencia con un carácter de palabra y la asigna al primero grupo de capturas.|  
|`\1`|Busca una coincidencia con el siguiente carácter que sea igual que el valor del primer grupo de capturas.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## Referencias inversas con nombre  
 Una referencia inversa con nombre se define con la sintaxis siguiente:  
  
 `\k<` *name* `>`  
  
 O bien  
  
 `\k'` *name* `'`  
  
 donde es el nombre *name* de un grupo de captura definido en la expresión regular.  Si *name* no se define en la expresión regular, un error de análisis aparece, y el motor de expresiones regulares produce <xref:System.ArgumentException>.  
  
 El ejemplo siguiente busca caracteres de palabra duplicados en una cadena.  Define una expresión regular, `(?<char>\w)\k<char>`, que se compone de los siguientes elementos.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`(?<char>\w)`|Busca una coincidencia con un carácter de palabra y la asigna a un grupo de capturas denominado `char`.|  
|`\k<char>`|Busca una coincidencia con el siguiente carácter que sea igual que el valor del grupo de capturas `char`.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 Observe que *name* también puede ser la representación de cadena de un número.  En el siguiente ejemplo, se utiliza la expresión regular `(?<2>\w)\k<2>` para buscar caracteres de palabra duplicados en una cadena.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## Qué coincidencias buscan las referencias inversas  
 Una referencia inversa constituye la definición más reciente de un grupo \(la definición que se encuentra más a la izquierda, cuando la búsqueda de coincidencias es de izquierda a derecha\).  Cuando un grupo realiza varias capturas, una referencia inversa se corresponde con la captura más reciente.  
  
 En el siguiente ejemplo se incluye un modelo de expresión regular, `(?<1>a)(?<1>\1b)*`, que vuelve a definir el grupo con nombre \\1.  La tabla siguiente describe cada modelo de la expresión regular.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`(?<1>a)`|Busca una coincidencia con el carácter "a" y asigna el resultado al grupo de capturas denominado `1`.|  
|`(?<1>\1b)*`|Busca 0 ó 1 coincidencia con el grupo denominado `1` junto con una "b" y asigna el resultado al grupo de capturas denominado `1`.|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 Al comparar la expresión regular con la cadena de entrada \("aababb"\), el motor de expresiones regulares realiza las siguientes operaciones:  
  
1.  Comienza al principio de la cadena y hace coincidir "a" con la expresión `(?<1>a)`.  El valor del grupo `1` es ahora "a".  
  
2.  Avanza hasta el segundo carácter y hace coincidir correctamente la cadena "ab" con la expresión `\1b` o "ab".  A continuación, asigna el resultado, "ab", a `\1`.  
  
3.  Avanza hasta el cuarto carácter.  La expresión `(?<1>\1b)` va a coincidir cero o más veces, de modo que coincida correctamente la cadena "abb" con la expresión `\1b`.  Vuelve a asignar el resultado, "abb", a `\1`.  
  
 En este ejemplo, `*` es un cuantificador de bucle: se evalúa repetidas veces hasta que el motor de expresiones regulares no encuentre coincidencias con el modelo definido.  Los cuantificadores de bucle no borran las definiciones de grupo.  
  
 Si un grupo no captura ninguna subcadena, la referencia inversa a ese grupo no está definida y nunca coincide con ninguna cadena.  Esto se ilustra mediante el modelo de expresión regular `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, que se define como sigue:  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Comienza la búsqueda de coincidencias en un límite de palabras.|  
|`(\p{Lu}{2})`|Busca una coincidencia con dos letras mayúsculas.  Éste es el primer grupo de captura.|  
|`(\d{2})?`|Busca cero o una coincidencia con dos dígitos decimales.  Éste es el segundo grupo de captura.|  
|`(\p{Lu}{2})`|Busca una coincidencia con dos letras mayúsculas.  Éste es el tercer grupo de captura.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
 Una cadena de entrada puede coincidir con esta expresión regular aun cuando los dos dígitos decimales que son definidos por el segundo grupo capturador no están presentes.  El ejemplo siguiente muestra que aunque la coincidencia es correcta, hay un grupo capturador vacío entre dos grupos capturadores correctos.  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## Vea también  
 [Lenguaje de expresiones regulares \- Referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)