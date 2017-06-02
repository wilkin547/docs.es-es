---
title: "Construcciones miscel&#225;neas en expresiones regulares | Microsoft Docs"
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
  - "expresiones regulares de .NET Framework, construcciones varias"
  - "construcciones, varios"
  - "expresiones regulares, construcciones varias"
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Construcciones miscel&#225;neas en expresiones regulares
Las expresiones regulares de .NET Framework incluyen tres construcciones de lenguaje misceláneas.  Uno permite habilitar o deshabilitar determinadas opciones de coincidencia en un modelo de expresión regular.  Los dos restantes le permiten incluir comentarios en una expresión regular.  
  
## Opciones insertadas  
 Puede establecer o deshabilitar determinadas opciones de coincidencia de modelos para parte de una expresión regular utilizando la sintaxis  
  
```  
(?imnsx-imnsx)  
```  
  
 Indique las opciones que desee habilitar después del signo de interrogación y las opciones que desee deshabilitar después del signo menos.  En la siguiente tabla se describe cada una de las opciones.  Para obtener más información sobre cada opción, vea [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
|Opción|Descripción|  
|------------|-----------------|  
|`i`|Coincidencia sin distinción entre mayúsculas y minúsculas.|  
|`m`|Modo multilínea.|  
|`n`|Solo capturas explícitas. \(Los paréntesis no actúan como grupos de captura.\)|  
|`s`|Modo de una sola línea.|  
|`x`|Omite el espacio en blanco sin escape y permite comentarios en modo x.|  
  
 Cualquier cambio en las opciones de expresión regular definidas por la construcción `(?imnsx-imnsx)` permanece en vigor hasta el fin del grupo envolvente.  
  
> [!NOTE]
>  `(?imnsx-imnsx:` *subexpression* `)` que agrupa la construcción proporciona funcionalidad idéntica para una subexpresión.  Para obtener más información, vea [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 En el siguiente ejemplo se utilizan las opciones `i`, `n` y `x` para habilitar la no distinción entre mayúsculas y minúsculas y las capturas explícitas, y para omitir el espacio en blanco en el modelo de expresión regular en medio de una expresión regular.  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 En el ejemplo se definen dos expresiones regulares.  El primero, `\b(D\w+)\s(d\w+)\b`, coincide con dos palabras consecutivas que comienzan con una "D" mayúscula y una "d" minúscula.  La segunda expresión regular, `\b(D\w+)(?ixn) \s (d\w+) \b`, utiliza opciones alineadas para modificar este modelo, tal y como se describe en la siguiente tabla.  Una comparación de los resultados confirma el efecto del constructo `(?ixn)`.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(D\w+)`|Busca una coincidencia con una letra mayúscula "D" seguida de uno o varios caracteres de palabra.  Este es el primer grupo de capturas.|  
|`(?ixn)`|A partir de ese punto, las comparaciones se realizan sin distinción de mayúsculas y minúsculas, solo se realizan capturas explícitas y se omite el espacio en blanco en el modelo de expresión regular.|  
|`\s`|Buscar coincidencias con un carácter que sea un espacio en blanco.|  
|`(d\w+)`|Busca una coincidencia de una letra "d" en minúscula o mayúscula seguida de uno o varios caracteres de palabra.  No se captura este grupo porque la opción `n` \(captura explícita\) estaba habilitada.|  
|`\b`|Hacer coincidir con un límite de palabras.|  
  
## Comentario insertado  
 La construcción de `(?#` *comment*`)` permite incluir un comentario escrito en una expresión regular.  El motor de expresiones regulares no utiliza ninguna parte del comentario en la coincidencia de modelos, aunque el comentario está incluido en la cadena devuelta por el método <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=fullName>.  El comentario termina en el primer paréntesis de cierre.  
  
 En el siguiente ejemplo se repite el primer modelo de expresión regular del ejemplo de la sección anterior.  Agrega dos comentarios insertados a la expresión regular para indicar si la comparación distingue entre mayúsculas y minúsculas.  El modelo de expresión regular, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, se define como sigue.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(?# case-sensitive comparison)`|Comentario  No afecta al comportamiento de coincidencia de modelos.|  
|`(D\w+)`|Busca una coincidencia con una letra mayúscula "D" seguida de uno o varios caracteres de palabra.  Éste es el primer grupo de captura.|  
|`\s`|Buscar coincidencias con un carácter que sea un espacio en blanco.|  
|`(?ixn)`|A partir de ese punto, las comparaciones se realizan sin distinción de mayúsculas y minúsculas, solo se realizan capturas explícitas y se omite el espacio en blanco en el modelo de expresión regular.|  
|`(?#case-insensitive comparison)`|Comentario  No afecta al comportamiento de coincidencia de modelos.|  
|`(d\w+)`|Busca una coincidencia de una letra "d" en minúscula o mayúscula seguida de uno o varios caracteres de palabra.  Éste es el segundo grupo de capturas.|  
|`\b`|Hacer coincidir con un límite de palabras.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## Comentario de fin de línea  
 Una almohadilla \(`#`\) marca un comentario del modo x, que se inicia en el carácter de no escape \# al final del modelo de expresión regular y continúa hasta el fin de la línea.  Para utilizar esta construcción, debe habilitar la opción `x` \(mediante opciones alineadas\) o proporcionar el valor <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> al parámetro `option` al crear instancias del objeto <xref:System.Text.RegularExpressions.Regex> o llamar a un método estático <xref:System.Text.RegularExpressions.Regex>.  
  
 En el ejemplo siguiente se muestra la construcción de comentario de fin de línea.  Determina si una cadena es una cadena de formato compuesto que incluye al menos un elemento de formato.  La tabla siguiente describe las construcciones del modelo de expresión regular:  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\{`|Busca una coincidencia de una llave de apertura.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`(,-*\d+)*`|Busca cero o una coincidencia con un carácter de coma seguido de un signo menos opcional seguido de uno o varios dígitos decimales.|  
|`(\:\w{1,4}?)*`|Busca una o varias coincidencias con un carácter de dos puntos seguido de uno a cuatro caracteres de espacio en blanco, pero limitando estos caracteres al menor número posible.|  
|`(?#case insensitive comparison)`|Un comentario alineado.  No afecta al comportamiento de coincidencia de modelos.|  
|`\}`|Busca una coincidencia con una llave de cierre.|  
|`(?x)`|Habilite la opción de omitir espacio en blanco para que se reconozca el comentario del fin de línea.|  
|`# Looks for a composite format item.`|Un comentario de fin de línea.|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 Observe que, en lugar de proporcionar la construcción `(?x)` en la expresión regular, el comentario también pudo haberse reconocido llamando al método <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=fullName> y pasándole el valor de enumeración <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
## Vea también  
 [Lenguaje de expresiones regulares \- Referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)