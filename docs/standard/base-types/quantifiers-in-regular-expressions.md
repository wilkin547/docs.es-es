---
title: cuantificadores en expresiones regulares
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
- regular expressions, quantifiers
- metacharacters, quantifiers
- minimal matching quantifiers
- quantifiers in regular expressions
- .NET Framework regular expressions, quantifiers
- quantifiers
- lazy quantifiers
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab06aa0c331c8cbd4c8986cced29334046f30264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="quantifiers-in-regular-expressions"></a>cuantificadores en expresiones regulares
Los cuantificadores especifican cuántas instancias de un carácter, grupo o clase de caracteres deben estar presentes en la entrada para que se encuentre una coincidencia.  En la tabla siguiente se indican los cuantificadores compatibles con .NET.  
  
|Cuantificador expansivo|Cuantificador diferido|Descripción|  
|-----------------------|---------------------|-----------------|  
|`*`|`*?`|Coincide cero o más veces.|  
|`+`|`+?`|Coincide una o más veces.|  
|`?`|`??`|Coincide cero o una vez.|  
|`{` *n* `}`|`{` *n* `}?`|Coincidir exactamente con  *n*  veces.|  
|`{` *n* `,}`|`{` *n* `,}?`|Coincide con al menos  *n*  veces.|  
|`{` *n* `,` *m* `}`|`{` *n* `,` *m* `}?`|Coincide con la de  *n*  a *m* veces.|  
  
 Las cantidades `n` y `m` son constantes de tipo entero. Normalmente, los cuantificadores son expansivos, ya que hacen que el motor de expresiones regulares busque el mayor número posible de repeticiones de patrones concretos. Si se anexa el carácter `?` a un cuantificador se convierte en diferido, ya que hace que el motor de expresiones regulares busque el menor número posible de repeticiones. Para obtener una descripción completa de la diferencia entre los cuantificadores expansivos y diferidos, consulte la sección [Cuantificadores expansivos y diferidos](#Greedy) más adelante en este tema.  
  
> [!IMPORTANT]
>  El anidamiento de cuantificadores (por ejemplo, como hace el patrón de expresión regular `(a*)*`) puede aumentar el número de comparaciones que debe realizar el motor de expresiones regulares, como una función exponencial del número de caracteres de la cadena de entrada. Para obtener más información acerca de este comportamiento y sus soluciones alternativas, consulte [retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).  
  
## <a name="regular-expression-quantifiers"></a>Cuantificadores de expresiones regulares  
 En las secciones siguientes se enumeran los cuantificadores admitidos en expresiones regulares de .NET.  
  
> [!NOTE]
>  Si el *, +,?, {, y} caracteres se encuentran en un patrón de expresión regular, el motor de expresiones regulares los interpreta como cuantificadores o como parte de construcciones de cuantificador, a menos que se incluyen en un [clase de caracteres](../../../docs/standard/base-types/character-classes-in-regular-expressions.md). Para interpretarlos como caracteres literales fuera de una clase de caracteres, debe anteponerles una barra diagonal inversa para indicar su secuencia de escape. Por ejemplo, la cadena `\*` en una expresión regular patrón se interpreta como un asterisco literal ("\*") caracteres.  
  
### <a name="match-zero-or-more-times-"></a>Coincidir cero o más veces: *  
 El cuantificador `*` coincide con el elemento anterior cero o más veces. Es equivalente a la `{0,}` cuantificador. `*`es un cuantificador no expansivo cuyo equivalente diferida es `*?`.  
  
 En el ejemplo siguiente se muestra esta expresión regular. De los nueve dígitos de la cadena de entrada, cinco coinciden con el patrón y cuatro (`95`, `929`, `9129` y `9919`) no coinciden.  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`91*`|Coincide con un "9" seguido de cero o más caracteres "1".|  
|`9*`|Coincide con cero o más caracteres "9".|  
|`\b`|Finaliza en un límite de palabras.|  
  
### <a name="match-one-or-more-times-"></a>Coincidir una o más veces: +  
 El `+` cuantificador coincide con el elemento anterior una o más veces. Es equivalente a `{1,}`. `+`es un cuantificador no expansivo cuyo equivalente diferida es `+?`.  
  
 Por ejemplo, la expresión regular `\ban+\w*?\b` intenta coincidir con palabras completas que empiezan por la letra `a` seguida de una o más instancias de la letra `n`. En el ejemplo siguiente se muestra esta expresión regular. La expresión regular coincide con las palabras `an`, `annual`, `announcement` y `antique`, y no coincide con `autumn` y `all`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`an+`|Coincide con una "a" seguida de uno o más caracteres "n".|  
|`\w*?`|Coincide con un carácter de palabra cero o más veces, pero el menor número de veces que sea posible.|  
|`\b`|Finaliza en un límite de palabras.|  
  
### <a name="match-zero-or-one-time-"></a>Coincidir cero o una vez: ?  
 El `?` cuantificador coincide con la hora de elemento cero o uno anterior. Es equivalente a `{0,1}`. `?`es un cuantificador no expansivo cuyo equivalente diferida es `??`.  
  
 Por ejemplo, la expresión regular `\ban?\b` intenta coincidir con palabras completas que empiezan por la letra `a` seguida de cero o una instancia de la letra `n`. En otras palabras, intenta coincidir con las palabras `a` y `an`. En el ejemplo siguiente se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`an?`|Coincide con una "a" seguida de cero o un carácter "n".|  
|`\b`|Finaliza en un límite de palabras.|  
  
### <a name="match-exactly-n-times-n"></a>Coincidir exactamente n veces: {n}  
 El `{`  *n*  `}` cuantificador coincide con el elemento anterior exactamente  *n*  veces, donde  *n* es un número entero. `{`*n*`}`es un cuantificador no expansivo cuyo equivalente diferida es `{`  *n*  `}?`.  
  
 Por ejemplo, la expresión regular `\b\d+\,\d{3}\b` intenta coincidir con un límite de palabra seguido de uno o más dígitos decimales, seguidos de tres dígitos decimales, seguidos de un límite de palabra. En el ejemplo siguiente se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`\,`|Coincide con un carácter de coma.|  
|`\d{3}`|Coincide con tres dígitos decimales.|  
|`\b`|Finaliza en un límite de palabras.|  
  
### <a name="match-at-least-n-times-n"></a>Coincidir al menos n veces: {n,}  
 El `{`  *n*  `,}` cuantificador coincide con el elemento anterior al menos  *n*  veces, donde  *n* es un número entero. `{`*n*`,}`es un cuantificador no expansivo cuyo equivalente diferida es `{`  *n*  `}?`.  
  
 Por ejemplo, la expresión regular `\b\d{2,}\b\D+` intenta coincidir con un límite de palabra seguido de por lo menos dos dígitos, seguidos de un límite de palabra y de un carácter que no sea un dígito. En el ejemplo siguiente se muestra esta expresión regular. Se produce un error en la expresión regular para que coincida con la frase `"7 days"` porque contiene un solo dígito decimal, pero coincide correctamente con las frases `"10 weeks and 300 years"`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`\d{2,}`|Coincide con al menos dos dígitos decimales.|  
|`\b`|Coincide con un límite de palabras.|  
|`\D+`|Coincide con al menos un carácter de dígito no decimal.|  
  
### <a name="match-between-n-and-m-times-nm"></a>Coincidir de n a m veces: {n,m}  
 El `{`  *n*  `,` *m* `}` cuantificador coincide con el elemento anterior al menos  *n*  veces, pero no más de *m* veces, donde  *n*  y *m* son enteros. `{`*n*`,`*m* `}` es un cuantificador no expansivo cuyo equivalente diferida es `{`  *n*  `,` *m*`}?`.  
  
 En el ejemplo siguiente, la expresión regular `(00\s){2,4}` intenta coincidir con dos ceros seguidos de un espacio que se repitan de dos a cuatro veces. Observe que la parte final de la cadena de entrada incluye este patrón cinco veces en lugar del máximo de cuatro. Pero solo la parte inicial de esta subcadena (hasta el espacio y el quinto par de ceros) coincide con el patrón de la expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### <a name="match-zero-or-more-times-lazy-match-"></a>Coincidir cero o más veces (coincidencia diferida): *?  
 El `*?` cuantificador coincide con el elemento anterior cero o más veces, pero el menor número de veces que sea posible. Es el equivalente no expansivo del cuantificador expansivo `*`.  
  
 En el ejemplo siguiente, la expresión regular `\b\w*?oo\w*?\b` coincide con todas las palabras que contienen la cadena `oo`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`\w*?`|Coincide con cero o más caracteres de palabra, pero con el menor número de caracteres posible.|  
|`oo`|Coincide con la cadena "oo".|  
|`\w*?`|Coincide con cero o más caracteres de palabra, pero con el menor número de caracteres posible.|  
|`\b`|Finaliza en un límite de palabras.|  
  
### <a name="match-one-or-more-times-lazy-match-"></a>Coincidir una o más veces (coincidencia diferida): +?  
 El `+?` cuantificador coincide con el elemento anterior una o más veces, pero el menor número de veces que sea posible. Es el equivalente no expansivo del cuantificador expansivo `+`.  
  
 Por ejemplo, la expresión regular `\b\w+?\b` coincide con uno o más caracteres separados por límites de palabra. En el ejemplo siguiente se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### <a name="match-zero-or-one-time-lazy-match-"></a>Coincidir cero o una vez (coincidencia diferida): ??  
 El `??` cuantificador coincide con la hora de elemento cero o uno anterior, pero el menor número de veces posible. Es el equivalente no expansivo del cuantificador expansivo `?`.  
  
 Por ejemplo, la expresión regular `^\s*(System.)??Console.Write(Line)??\(??` intenta coincidir con las cadenas "Console.Write" o "Console.WriteLine". La cadena también puede incluir "System." antes de "Console", y puede ir seguida de un paréntesis de apertura. La cadena debe estar al principio de una línea, aunque puede ir precedida de un espacio en blanco. En el ejemplo siguiente se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`^`|Coincide con el inicio del flujo de entrada.|  
|`\s*`|Busca coincidencias con cero o más caracteres de espacio en blanco.|  
|`(System.)??`|Coincide con cero o una repetición de la cadena "System.".|  
|`Console.Write`|Coincide con la cadena "Console.Write".|  
|`(Line)??`|Coincide con cero o una repetición de la cadena "Line".|  
|`\(??`|Coincide con cero o con una repetición del paréntesis de apertura.|  
  
### <a name="match-exactly-n-times-lazy-match-n"></a>Coincidir exactamente n veces (coincidencia diferida): {n}?  
 El `{`  *n*  `}?` cuantificador coincide con el elemento anterior exactamente `n` veces, donde  *n*  es un número entero. Es el equivalente no expansivo del cuantificador expansivo `{`  *n*  `}+`.  
  
 En el ejemplo siguiente, la expresión regular `\b(\w{3,}?\.){2}?\w{3,}?\b` se usa para identificar la dirección de un sitio web. Observe que coincide con "www.microsoft.com" y con "msdn.microsoft.com", pero no coincide con "mywebsite" ni con "mycompany.com".  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(\w{3,}?\.)`|Coincide con al menos 3 caracteres de palabra, pero con el menor número de caracteres posible, seguidos de un carácter de punto. Este es el primer grupo de captura.|  
|`(\w{3,}?\.){2}?`|Coincide con el patrón del primer grupo dos veces, pero el menor número de veces posible.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
### <a name="match-at-least-n-times-lazy-match-n"></a>Coincidir al menos n veces (coincidencia diferida): {n,}?  
 El `{`  *n*  `,}?` cuantificador coincide con el elemento anterior al menos `n` veces, donde  *n*  es un número entero, pero el menor número de veces es posible. Es el equivalente no expansivo del cuantificador expansivo `{`  *n*  `,}`.  
  
 Vea el ejemplo de la `{`  *n*  `}?` cuantificador en la sección anterior para ver una ilustración. La expresión regular en el ejemplo utiliza la `{`  *n*  `,}` cuantificador para que coincida con una cadena que tiene al menos tres caracteres seguido de un punto.  
  
### <a name="match-between-n-and-m-times-lazy-match-nm"></a>Coincidir de n a m veces (coincidencia diferida): {n,m}?  
 El `{`  *n*  `,` *m* `}?` cuantificador coincide con el elemento anterior entre `n` y `m` veces, donde  *n*  y *m* son números enteros, pero el menor número de veces que sea posible. Es el equivalente no expansivo del cuantificador expansivo `{`  *n*  `,` *m*`}`.  
  
 En el ejemplo siguiente, la expresión regular `\b[A-Z](\w*\s+){1,10}?[.!?]` coincide con las frases que contengan de una a diez palabras. Coincidencia con todas las frases de la cadena de entrada, excepto con una frase que contiene 18 palabras.  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`[A-Z]`|Coincide con cualquier letra mayúscula de la A a la Z.|  
|`(\w*\s+)`|Coincide con cero o más caracteres de palabra, seguidos de uno o más caracteres de espacio en blanco. Este es el primer grupo de capturas.|  
|`{1,10}?`|Coincide con el patrón anterior entre una y diez veces, pero el menor número de veces que sea posible.|  
|`[.!?]`|Coincide con cualquiera de los caracteres de puntuación ".", "!" o "?".|  
  
<a name="Greedy"></a>   
## <a name="greedy-and-lazy-quantifiers"></a>Cuantificadores expansivos y diferidos  
 Varios cuantificadores tienen dos versiones:  
  
-   Una versión expansiva.  
  
     Un cuantificador expansivo intenta coincidir con un elemento tantas veces como sea posible.  
  
-   Una versión no expansivos (o no).  
  
     Un cuantificador no expansivo intenta coincidir con un elemento el menor número de veces que sea posible. Puede convertir un cuantificador expansivo en un cuantificador no expansivo agregando simplemente un `?`.  
  
 Considere una expresión regular simple diseñada para extraer los cuatro últimos dígitos de una cadena de números, como un número de tarjeta de crédito. La versión de la expresión regular que usa el `*` cuantificador expansivo es `\b.*([0-9]{4})\b`. Pero si una cadena contiene dos números, esta expresión regular coincide con los cuatro últimos dígitos del segundo número, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 Se produce un error en la expresión regular para que coincida con el primer número porque el `*` cuantificador intenta buscar coincidencias con el elemento anterior tantas veces como sea posible en toda la cadena y, por lo que encuentra su coincidencia al final de la cadena.  
  
 Este no es el comportamiento deseado. En su lugar, puede usar el `*?`cuantificador no expansivo para extraer los dígitos de ambos números, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 En la mayoría de los casos, las expresiones regulares con cuantificadores expansivos y diferidos devuelven las mismas coincidencias. Suelen devolver resultados diferentes cuando se utilizan con el carácter comodín (`.`) metacarácter, que coincide con cualquier carácter.  
  
## <a name="quantifiers-and-empty-matches"></a>Cuantificadores y coincidencias vacías  
 Los cuantificadores `*`, `+`, y `{`  *n*  `,` *m* `}` y sus homólogos perezosos nunca se repiten tras vacío coincidencia cuando se ha encontrado el número mínimo de capturas. Esta regla impide que los cuantificadores entren en bucles infinitos en coincidencias de subexpresiones vacías cuando el número máximo de posibles capturas de grupo es infinito o cerca de infinito.  
  
 Por ejemplo, el código siguiente muestra el resultado de una llamada a la <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> método con el patrón de expresión regular `(a?)*`, que coincide con cero o un carácter "a" cero o más veces. Tenga en cuenta que el grupo de captura solo captura entre "a" como así como <xref:System.String.Empty?displayProperty=nameWithType>, pero que no hay ninguna coincidencia vacía segundo, porque hace que la primera coincidencia vacía el cuantificador dejar de repetirse.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 Para ver la diferencia práctica entre un grupo de captura que define un número mínimo y máximo de capturas y otro que define un número fijo de capturas, tenga en cuenta los patrones de expresiones regulares `(a\1|(?(1)\1)){0,2}` y `(a\1|(?(1)\1)){2}`. Ambas expresiones regulares constan de un único grupo de captura, que se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`(a\1`|Coincide con "a", junto con el valor del primer grupo capturado...|  
|`&#124;(?(1)`|… o bien, prueba si se ha definido el primer grupo capturado. (Tenga en cuenta que el `(?(1)` construcción no define un grupo de captura.)|  
|`\1))`|Si el primer grupo capturado existe, coincide con su valor. Si el grupo no existe, se corresponderá con el grupo <xref:System.String.Empty?displayProperty=nameWithType>.|  
  
 La primera expresión regular intenta coincidir con este patrón de cero a dos veces; el segundo, exactamente dos veces. Dado que el primer patrón alcanza el número mínimo de capturas con su primera captura de <xref:System.String.Empty?displayProperty=nameWithType>, nunca se repite para intentar hacer coincidir `a\1`; el `{0,2}` cuantificador sólo permite coincidencias vacías en la última iteración. En cambio, la segunda expresión regular coincide con "a" porque evalúa `a\1` una segunda vez. El número mínimo de iteraciones (dos) obliga al motor a repetirse tras una coincidencia vacía.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 [Lenguaje de expresiones regulares: referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)  
 [Retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)
