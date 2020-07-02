---
title: cuantificadores en expresiones regulares
description: Descubra los cuantificadores de expresiones regulares, que especifican cuántas instancias de un carácter, grupo o clase de caracteres deben estar presentes en la entrada para que coincidan.
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 2fc47a834f8f5b18021aa4f321345b8d7e4e8459
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662893"
---
# <a name="quantifiers-in-regular-expressions"></a>cuantificadores en expresiones regulares
Los cuantificadores especifican cuántas instancias de un carácter, grupo o clase de caracteres deben estar presentes en la entrada para que se encuentre una coincidencia.  En la tabla siguiente se indican los cuantificadores compatibles con .NET.  
  
|Cuantificador expansivo|Cuantificador diferido|Descripción|  
|-----------------------|---------------------|-----------------|  
|`*`|`*?`|Coincide cero o más veces.|  
|`+`|`+?`|Coincide una o más veces.|  
|`?`|`??`|Coincide cero o una vez.|  
|`{` *n* `}`|`{` *n* `}?`|Coincide exactamente *n* veces.|  
|`{` *n* `,}`|`{` *n* `,}?`|Coincide al menos *n* veces.|  
|`{` *n* `,` *m* `}`|`{` *n* `,` *m* `}?`|Coincide de *n* a *m* veces.|  
  
 Las cantidades `n` y `m` son constantes de tipo entero. Normalmente, los cuantificadores son expansivos, ya que hacen que el motor de expresiones regulares busque el mayor número posible de repeticiones de patrones concretos. Si se anexa el carácter `?` a un cuantificador se convierte en diferido, ya que hace que el motor de expresiones regulares busque el menor número posible de repeticiones. Para obtener una descripción completa de la diferencia entre los cuantificadores expansivos y diferidos, consulte la sección [Cuantificadores expansivos y diferidos](#Greedy) más adelante en este tema.  
  
> [!IMPORTANT]
> El anidamiento de cuantificadores (por ejemplo, como hace el patrón de expresión regular `(a*)*`) puede aumentar el número de comparaciones que debe realizar el motor de expresiones regulares, como una función exponencial del número de caracteres de la cadena de entrada. Para obtener más información sobre este comportamiento y sus soluciones alternativas, consulte [Retroceso](backtracking-in-regular-expressions.md).  
  
## <a name="regular-expression-quantifiers"></a>Cuantificadores de expresiones regulares  
 En las secciones siguientes se enumeran los cuantificadores admitidos en expresiones regulares de .NET.  
  
> [!NOTE]
> Si los caracteres *, +, ?, { y } se encuentran en un patrón de expresión regular, el motor de expresiones regulares los interpreta como cuantificadores o como parte de construcciones de cuantificador, a menos que se incluyan en una [clase de caracteres](character-classes-in-regular-expressions.md). Para interpretarlos como caracteres literales fuera de una clase de caracteres, debe anteponerles una barra diagonal inversa para indicar su secuencia de escape. Por ejemplo, la cadena `\*` en un patrón de expresión regular se interpreta como un carácter de asterisco literal ("\*").  
  
### <a name="match-zero-or-more-times-"></a>Coincidir cero o más veces: *  
 El cuantificador `*` coincide con el elemento anterior cero o más veces. Equivale al cuantificador `{0,}`. `*` es un cuantificador expansivo cuyo equivalente diferido es `*?`.  
  
 En el ejemplo siguiente se muestra esta expresión regular. De los nueve dígitos de la cadena de entrada, cinco coinciden con el patrón y cuatro (`95`, `929`, `9219` y `9919`) no coinciden.  
  
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
 El cuantificador `+` coincide con el elemento anterior una o más veces. Equivale a `{1,}`. `+` es un cuantificador expansivo cuyo equivalente diferido es `+?`.  
  
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
 El cuantificador `?` coincide con el elemento anterior cero o una vez. Equivale a `{0,1}`. `?` es un cuantificador expansivo cuyo equivalente diferido es `??`.  
  
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
 El cuantificador `{`*n*`}` coincide con el elemento anterior exactamente *n* veces, donde *n* es un entero. `{`*n*`}` es un cuantificador expansivo cuyo equivalente diferido es `{`*n*`}?`.  
  
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
 El cuantificador `{`*n*`,}` coincide con el elemento anterior al menos *n*, donde *n* es un entero. `{`*n*`,}` es un cuantificador expansivo cuyo equivalente diferido es `{`*n*`,}?`.  
  
 Por ejemplo, la expresión regular `\b\d{2,}\b\D+` intenta coincidir con un límite de palabra seguido de por lo menos dos dígitos, seguidos de un límite de palabra y de un carácter que no sea un dígito. En el ejemplo siguiente se muestra esta expresión regular. La expresión regular no coincide con la frase `"7 days"` porque solo contiene un dígito decimal, pero coincide correctamente con las frases `"10 weeks and 300 years"`.  
  
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
 El cuantificador `{`*n*`,`*m*`}` coincide con el elemento anterior al menos *n* veces, pero no más de *m* veces, donde *n* y *m* son enteros. `{`*n*`,`*m*`}` es un cuantificador expansivo cuyo equivalente diferido es `{`*n*`,`*m*`}?`.  
  
 En el ejemplo siguiente, la expresión regular `(00\s){2,4}` intenta coincidir con dos ceros seguidos de un espacio que se repitan de dos a cuatro veces. Observe que la parte final de la cadena de entrada incluye este patrón cinco veces en lugar del máximo de cuatro. Pero solo la parte inicial de esta subcadena (hasta el espacio y el quinto par de ceros) coincide con el patrón de la expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### <a name="match-zero-or-more-times-lazy-match-"></a>Coincidir cero o más veces (coincidencia diferida): *?  
 El cuantificador `*?` coincide con el elemento anterior cero o más veces, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo `*`.  
  
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
 El cuantificador `+?` coincide con el elemento anterior una o más veces, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo `+`.  
  
 Por ejemplo, la expresión regular `\b\w+?\b` coincide con uno o más caracteres separados por límites de palabra. En el ejemplo siguiente se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### <a name="match-zero-or-one-time-lazy-match-"></a>Coincidir cero o una vez (coincidencia diferida): ??  
 El cuantificador `??` coincide con el elemento anterior cero o una vez, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo `?`.  
  
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
 El cuantificador `{`*n*`}?` coincide con el elemento anterior exactamente `n` veces, donde *n* es un entero. Es el equivalente diferido del cuantificador expansivo `{`*n*`}`.  
  
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
 El cuantificador `{`*n*`,}?` coincide con el elemento anterior al menos `n` veces, donde *n* es un entero, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo `{`*n*`,}`.  
  
 Vea el ejemplo del cuantificador `{`*n*`}?` en la sección anterior para obtener una ilustración. La expresión regular de ese ejemplo usa el cuantificador `{`*n*`,}` para coincidir con una cadena que tenga al menos tres caracteres seguidos de un punto.  
  
### <a name="match-between-n-and-m-times-lazy-match-nm"></a>Coincidir de n a m veces (coincidencia diferida): {n,m}?  
 El cuantificador `{`*n*`,`*m*`}?` coincide con el elemento anterior de `n` a `m` veces, donde *n* y *m* son enteros, pero el menor número de veces posible. Es el equivalente diferido del cuantificador expansivo `{`*n*`,`*m*`}`.  
  
 En el ejemplo siguiente, la expresión regular `\b[A-Z](\w*?\s*?){1,10}[.!?]` coincide con las frases que contengan de una a diez palabras. Coincidencia con todas las frases de la cadena de entrada, excepto con una frase que contiene 18 palabras.  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 El patrón de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`[A-Z]`|Coincide con cualquier letra mayúscula de la A a la Z.|  
|`(\w*?\s*?)`|Coincide con cero o más caracteres de palabra, seguidos de uno o más caracteres de espacio en blanco, pero el menor número de veces posible. Este es el primer grupo de capturas.|  
|`{1,10}`|Coincide con el patrón anterior entre una y diez veces.|  
|`[.!?]`|Coincide con cualquiera de los caracteres de puntuación ".", "!" o "?".|  
  
<a name="Greedy"></a>
## <a name="greedy-and-lazy-quantifiers"></a>Cuantificadores expansivos y diferidos  
 Varios cuantificadores tienen dos versiones:  
  
- Una versión expansiva.  
  
     Un cuantificador expansivo intenta coincidir con un elemento tantas veces como sea posible.  
  
- Una versión no expansiva o diferida.  
  
     Un cuantificador no expansivo intenta coincidir con un elemento el menor número de veces que sea posible. Para convertir un cuantificador expansivo en un cuantificador diferido con tan solo agregar el signo `?`.  
  
 Considere una expresión regular simple diseñada para extraer los cuatro últimos dígitos de una cadena de números, como un número de tarjeta de crédito. La versión de la expresión regular que usa el cuantificador expansivo `*` es `\b.*([0-9]{4})\b`. Pero si una cadena contiene dos números, esta expresión regular coincide con los cuatro últimos dígitos del segundo número, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 La expresión regular no coincide con el primer número porque el cuantificador `*` intenta coincidir con el elemento anterior tantas veces como sea posible en toda la cadena y, por tanto, encuentra una coincidencia al final de la cadena.  
  
 Este no es el comportamiento deseado. En su lugar, puede usar el cuantificador diferido `*?` para extraer los dígitos de ambos números, tal como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 En la mayoría de los casos, las expresiones regulares con cuantificadores expansivos y diferidos devuelven las mismas coincidencias. Suelen devolver resultados diferentes cuando se usan con el metacarácter comodín (`.`), que coincide con cualquier carácter.  
  
## <a name="quantifiers-and-empty-matches"></a>Cuantificadores y coincidencias vacías  
 Los cuantificadores `*`, `+` y `{`*n*`,`*m*`}` y sus equivalentes diferidos nunca se repiten tras una coincidencia vacía cuando no se ha encontrado el número mínimo de capturas. Esta regla impide que los cuantificadores entren en bucles infinitos en coincidencias de subexpresiones vacías cuando el número máximo de posibles capturas de grupo es infinito o cerca de infinito.  
  
 Por ejemplo, en el código siguiente se muestra el resultado de una llamada al método <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> con el patrón de expresión regular `(a?)*` que coincide cero o más veces con cero o un carácter "a". Observe que el único grupo de captura realiza una captura de todos los caracteres "a", así como de <xref:System.String.Empty?displayProperty=nameWithType>, pero no hay una segunda coincidencia vacía, ya que la primera coincidencia vacía hace que el cuantificador deje de repetirse.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 Para ver la diferencia práctica entre un grupo de captura que define un número mínimo y máximo de capturas y otro que define un número fijo de capturas, tenga en cuenta los patrones de expresiones regulares `(a\1|(?(1)\1)){0,2}` y `(a\1|(?(1)\1)){2}`. Ambas expresiones regulares constan de un único grupo de captura, que se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|-------------|-----------------|  
|`(a\1`|Coincide con "a", junto con el valor del primer grupo capturado...|  
|<code>&#124;(?(1)</code>|… o bien, prueba si se ha definido el primer grupo capturado. (Tenga en cuenta que la construcción `(?(1)` no define un grupo de captura).|  
|`\1))`|Si el primer grupo capturado existe, coincide con su valor. Si el grupo no existe, el grupo coincidirá con <xref:System.String.Empty?displayProperty=nameWithType>.|  
  
 La primera expresión regular intenta coincidir con este patrón de cero a dos veces; el segundo, exactamente dos veces. Dado que el primer modelo alcanza el número mínimo de capturas con su primera captura de <xref:System.String.Empty?displayProperty=nameWithType>, nunca se repite para intentar coincidir con `a\1`; el cuantificador `{0,2}` solo permite las coincidencias vacías en la última iteración. En cambio, la segunda expresión regular coincide con "a" porque evalúa `a\1` una segunda vez. El número mínimo de iteraciones (dos) obliga al motor a repetirse tras una coincidencia vacía.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Lenguaje de expresiones regulares: referencia rápida](regular-expression-language-quick-reference.md)
- [Retroceso](backtracking-in-regular-expressions.md)
