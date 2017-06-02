---
title: "Cuantificadores en expresiones regulares | Microsoft Docs"
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
  - "expresiones regulares, cuantificadores"
  - "metacaracteres, cuantificadores"
  - "cuantificadores de coincidencia mínima"
  - "cuantificadores en expresiones regulares"
  - "expresiones regulares de .NET Framework, cuantificadores"
  - "cuantificadores"
  - "cuantificadores perezosos"
ms.assetid: 36b81212-6511-49ed-a8f1-ff080415312f
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Cuantificadores en expresiones regulares
Los cuantificadores especifican cuántas instancias de un carácter, un grupo o una clase de caracteres debe haber en la entrada para que se encuentre una coincidencia.  En la tabla siguiente se enumeran los cuantificadores admitidos por .NET Framework.  
  
|Cuantificador expansivo|Cuantificador no expansivo|Descripción|  
|-----------------------------|--------------------------------|-----------------|  
|`*`|`*?`|Busca cero o más coincidencias.|  
|`+`|`+?`|Busca una o varias coincidencias.|  
|`?`|`??`|Busca cero o una coincidencia.|  
|`{` *n* `}`|`{` *n* `}?`|Match tiempos de *n* exactamente.|  
|`{` *n* `,}`|`{` *n* `,}?`|Tiempos de *n* match por lo menos.|  
|`{` *n* `,` *m* `}`|`{` *n* `,` *m* `}?`|Coincidencia de *n* los tiempos de *m* .|  
  
 Las cantidades `n` y `m` son constantes de tipo entero.  Normalmente, los cuantificadores son expansivos; hacen que el motor de expresiones regulares busca coincidencias con tantas apariciones de modelos concretos como sea posible.  Anexar el carácter `?` a un cuantificador lo hace no expansivo; hace que el motor de expresiones regulares coincida con el mínimo de apariciones posible.  Para obtener una descripción de las diferencias que existen entre los dos tipos de cuantificadores, vea la sección [Cuantificaciones expansivos y no expansivos](#Greedy) más adelante en este tema.  
  
> [!IMPORTANT]
>  La anidación de cuantificadores \(como hace, por ejemplo, el patrón de expresión regular `(a*)*`\) puede incrementar el número de comparaciones que debe realizar el motor de expresiones regulares, como función exponencial del número de caracteres de la cadena de entrada.  Para obtener más información sobre este comportamiento y sus soluciones alternativas, vea [Retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).  
  
## Cuantificadores de expresiones regulares  
 En las secciones siguientes se enumeran los cuantificadores admitidos en las expresiones regulares de .NET Framework.  
  
> [!NOTE]
>  Si se encuentran los caracteres \*, \+?, { y } en un modelo de expresión regular, el motor de expresiones regulares los interpretará como cuantificadores o como parte de construcciones de cuantificador, a menos que estén incluidos en una [clase de caracteres](../../../docs/standard/base-types/character-classes-in-regular-expressions.md).  Para interpretarlos como caracteres literales fuera de una clase de caracteres, debe aplicarlos una secuencia de escape precediéndolos con una barra diagonal inversa.  Por ejemplo, la cadena `\*` en un modelo de expresión regular se interpreta como un carácter de asterisco \("\*"\) literal.  
  
### Busca cero o más coincidencias: \*  
 El cuantificador `*` coincide cero o más veces con el elemento anterior.  Es equivalente al cuantificador `{0,}`.  `*` es un cuantificador expansivo cuyo equivalente no expansivo es `*?`.  
  
 En el siguiente ejemplo se muestra esta expresión regular.  De los nueve dígitos de la cadena de entrada, cinco coinciden con el modelo y cuatro, \(`95`, `929`, `9129` y `9919`\) no.  
  
 [!code-csharp[RegularExpressions.Quantifiers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#1)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`91*`|Busca una coincidencia con un "9" seguido de cero o más caracteres "1".|  
|`9*`|Busca una coincidencia con cero o más caracteres "9".|  
|`\b`|Finaliza en un límite de palabras.|  
  
### Busca una o varias coincidencias: \+  
 El cuantificador `+` coincide una o más veces con el elemento anterior.  Equivale a `{1,}`.  `+` es un cuantificador expansivo cuyo equivalente no expansivo es `+?`.  
  
 Por ejemplo, la expresión regular `\ban+\w*?\b` intenta encontrar coincidencias de palabras enteras que comienzan con la letra `a` seguida de una o varias instancias de la letra `n`.  En el siguiente ejemplo se muestra esta expresión regular.  La expresión regular coincide con las palabras `an`, `annual`, `announcement` y `antique` y, como cabía esperar, no coincide con `autumn` ni con `all`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#2)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`an+`|Busca una coincidencia de una "a" seguida de uno o varios caracteres "n".|  
|`\w*?`|Busca cero o más coincidencias de un carácter de palabra, pero limitando el número de coincidencias al menor número posible.|  
|`\b`|Finaliza en un límite de palabras.|  
  
### Busca cero o una coincidencia: ?  
 El cuantificador `?` coincide cero o una vez con el elemento anterior.  Equivale a `{0,1}`.  `?` es un cuantificador expansivo cuyo equivalente no expansivo es `??`.  
  
 Por ejemplo, la expresión regular `\ban?\b` intenta encontrar coincidencias de palabras enteras que comienzan con la letra `a` seguida de cero o una instancia de la letra `n`.  En otras palabras, intenta buscar coincidencias con las palabras `a` y `an`.  En el siguiente ejemplo se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#3)]
 [!code-vb[RegularExpressions.Quantifiers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#3)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`an?`|Busca una coincidencia de una "a" seguida de cero o un carácter "n".|  
|`\b`|Finaliza en un límite de palabras.|  
  
### Busca exactamente n coincidencias: {n}  
 Las coincidencias cuantificadoras de `{`*n*`}` que el elemento anterior *n* mide el tiempo exactamente, donde es cualquier entero *n* .  `{`*n*`}` es un cuantificador expansivo cuyo equivalente lazy es `{`*n*`}?`.  
  
 Por ejemplo, la expresión regular `\b\d+\,\d{3}\b` intenta encontrar coincidencias de un límite de palabra seguido de uno o varios dígitos decimales, que, a su vez, van seguidos por tres dígitos decimales seguidos por un límite de palabra.  En el siguiente ejemplo se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#4](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#4)]
 [!code-vb[RegularExpressions.Quantifiers#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#4)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`\,`|Busca una coincidencia con un carácter de coma.|  
|`\d{3}`|Buscar coincidencias con tres dígitos decimales.|  
|`\b`|Finaliza en un límite de palabras.|  
  
### Busca al menos n coincidencias: {n,}  
 Las coincidencias cuantificadoras de `{`*n*`,}` que el elemento anterior al menos *n* mide el tiempo, donde es cualquier entero *n* .  `{`*n*`,}` es un cuantificador expansivo cuyo equivalente lazy es `{`*n*`}?`.  
  
 Por ejemplo, la expresión regular `\b\d{2,}\b\D+` intenta encontrar coincidencias con un límite de palabra seguido por lo menos de dos dígitos, que, a su vez, van seguidos de un límite de palabra y un carácter no numérico.  En el siguiente ejemplo se muestra esta expresión regular.  La expresión regular no coincide con la frase `"7 days"` porque solo contiene un dígito decimal, pero coincide correctamente con las frases `"10 weeks and 300 years"`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#5)]
 [!code-vb[RegularExpressions.Quantifiers#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#5)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`\d{2,}`|Busca una coincidencia de al menos dos dígitos decimales.|  
|`\b`|Hacer coincidir con un límite de palabras.|  
|`\D+`|Busca una coincidencia de al menos un dígito no decimal.|  
  
### Busca de n a m coincidencias: {n,m}  
 Las coincidencias cuantificadoras de `{`*n*`,`*m*`}` que el elemento anterior al menos *n* mide el tiempo, pero no más de *m* mide el tiempo, donde enteros *n* y *m* .  `{`*n*`,`*m*`}` es un cuantificador expansivo cuyo equivalente lazy es `{`*n*`,`*m*`}?`.  
  
 En el ejemplo siguiente, la expresión regular `(00\s){2,4}` intenta encontrar coincidencias entre dos y cuatro ocurrencias de dos ceros seguidos de un espacio.  Observe que la parte final de la cadena de entrada incluye este modelo cinco veces en lugar del máximo de cuatro.  Sin embargo, solo la parte inicial de esta subcadena \(hasta el espacio y el quinto par de ceros\) coincide con el modelo de la expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#6)]
 [!code-vb[RegularExpressions.Quantifiers#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#6)]  
  
### Busca cero o más coincidencias \(coincidencia no expansiva\): \*?  
 El cuantificador `*?` coincide con el elemento anterior ninguna o alguna vez, pero el menor número de veces que sea posible.  Es el equivalente no expansivo del cuantificador expansivo `*`.  
  
 En el ejemplo siguiente, la expresión regular `\b\w*?oo\w*?\b` coincide con todas las palabras que contienen la cadena `oo`.  
  
 [!code-csharp[RegularExpressions.Quantifiers#7](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#7)]
 [!code-vb[RegularExpressions.Quantifiers#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#7)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`\w*?`|Busca una coincidencia con cero o más caracteres de palabra, pero con la menor cantidad posible de caracteres.|  
|`oo`|Busca una coincidencia con la cadena "oo".|  
|`\w*?`|Busca una coincidencia con cero o más caracteres de palabra, pero con la menor cantidad posible de caracteres.|  
|`\b`|Finalizar en un límite de palabras.|  
  
### Busca una o varias coincidencias \(coincidencia no expansiva\): \+?  
 El cuantificador `+?` coincide con el elemento anterior una o más veces, pero el menor número de veces que sea posible.  Es el equivalente no expansivo del cuantificador expansivo `+`.  
  
 Por ejemplo, la expresión regular `\b\w+?\b` coincide con uno o varios caracteres separados por límites de palabra.  En el siguiente ejemplo se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#8)]
 [!code-vb[RegularExpressions.Quantifiers#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#8)]  
  
### Busca cero o una coincidencia \(coincidencia no expansiva\): ??  
 El cuantificador `??` coincide con el elemento anterior ninguna o una vez, pero el menor número de veces que sea posible.  Es el equivalente no expansivo del cuantificador expansivo `?`.  
  
 Por ejemplo, la expresión regular `^\s*(System.)??Console.Write(Line)??\(??` intenta hacer coincidir las cadenas "Console.Write" o "Console.WriteLine".  La cadena también puede incluir "System." delante de "Console", y puede ir seguida de un paréntesis de apertura.  La cadena debe estar al comienzo de una línea, aunque puede ir precedida de un espacio en blanco.  En el siguiente ejemplo se muestra esta expresión regular.  
  
 [!code-csharp[RegularExpressions.Quantifiers#9](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#9)]
 [!code-vb[RegularExpressions.Quantifiers#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#9)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`^`|Busca una coincidencia con el comienzo del flujo de entrada.|  
|`\s*`|Busca coincidencias con cero o más caracteres de espacio en blanco.|  
|`(System.)??`|Busca cero o una coincidencia con la cadena "System.".|  
|`Console.Write`|Busca coincidencias con la cadena "Console.Write".|  
|`(Line)??`|Busca cero o una coincidencia con la cadena "Line".|  
|`\(??`|Busca cero o una coincidencia con el paréntesis de apertura.|  
  
### Busca exactamente n coincidencias \(coincidencia no expansiva\): {n}?  
 Las coincidencias cuantificadoras de `{`*n*`}?` que el elemento anterior `n` mide el tiempo exactamente, donde es cualquier entero *n* .  Es el equivalente del cuantificador expansivo `{`*n*`}+`.  
  
 En el ejemplo siguiente, la expresión regular `\b(\w{3,}?\.){2}?\w{3,}?\b` se usa para identificar una dirección de sitio web.  Observe que coincide con "www.microsoft.com" y "msdn.microsoft.com", pero no coincide con "mywebsite" ni "mycompany.com".  
  
 [!code-csharp[RegularExpressions.Quantifiers#10](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#10)]
 [!code-vb[RegularExpressions.Quantifiers#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#10)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`(\w{3,}?\.)`|Busca una coincidencia de al menos 3 caracteres de palabra, pero limitándolos al menor número de caracteres posible, seguidos de un carácter de punto.  Éste es el primer grupo de captura.|  
|`(\w{3,}?\.){2}?`|Busca dos coincidencias con el modelo en el primer grupo, reduciendo el número de coincidencias al menor número posible.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
### Busca al menos n coincidencias \(coincidencia no expansiva\): {n,}?  
 Las coincidencias cuantificadoras de `{`*n*`,}?` que el elemento anterior al menos `n` mide el tiempo, donde es cualquier entero *n* , pero el menor número de veces posible.  Es el equivalente del cuantificador expansivo `{`*n*`,}`.  
  
 Vea el ejemplo para el cuantificador de `{`*n*`}?` en la sección anterior para una ilustración.  La expresión regular en ese ejemplo utiliza el cuantificador de `{`*n*`,}` para una cadena que tiene al menos tres caracteres seguidos de un punto.  
  
### Busca de n a m coincidencias \(coincidencia no expansiva\): {n,m}?  
 Las coincidencias cuantificadoras de `{`*n*`,`*m*`}?` el elemento anterior entre `n` y `m` medir el tiempo, donde enteros *n* y *m* , pero el menor número de veces posible.  Es el equivalente del cuantificador expansivo `{`*n*`,`*m*`}`.  
  
 En el ejemplo siguiente, la expresión regular `\b[A-Z](../../../amples/snippets/visualbasic/VS_Snippets_Remoting/SoapAttributes1/VB/s.vb){1,10}?[.!?]` busca coincidencias con frases que contengan entre una y diez palabras.  Coincide con todas las frases de la cadena de entrada a excepción de una frase que contiene 18 palabras.  
  
 [!code-csharp[RegularExpressions.Quantifiers#12](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers/cs/Quantifiers1.cs#12)]
 [!code-vb[RegularExpressions.Quantifiers#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers/vb/Quantifiers1.vb#12)]  
  
 El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`\b`|Empieza en un límite de palabras.|  
|`[A-Z]`|Busca una coincidencia de una letra mayúscula de la A a la Z.|  
|`(\w*\s+)`|Busca una coincidencia con cero o más caracteres de palabra seguidos de uno o varios caracteres de espacio en blanco.  Este es el primer grupo de capturas.|  
|`{1,10}?`|Busca de 1 a 10 coincidencias con el modelo anterior, reduciendo el número de coincidencias al menor número posible.|  
|`[.!?]`|Busca una coincidencia de cualquiera de los caracteres de puntuación ".", "\!" o "?".|  
  
<a name="Greedy"></a>   
## Cuantificadores expansivos y no expansivos  
 Hay varios cuantificadores que tienen dos versiones:  
  
-   Una versión expansiva.  
  
     Un cuantificador expansivo intenta buscar coincidencias con el elemento tantas veces como sea posible.  
  
-   Una versión no expansiva.  
  
     Un cuantificador no expansivo intenta buscar coincidencias con el elemento el menor número de veces posible.  Puede convertir un cuantificador expansivo en un cuantificador no expansivo agregando simplemente un `?`.  
  
 Considere una expresión regular simple con la que se pretende extraer los cuatro últimos dígitos de una cadena de números como los de una tarjeta de crédito.  La versión de la expresión regular que utiliza el cuantificador `*` expansivo es `\b.*([0-9]{4})\b`.  Sin embargo, si una cadena contiene dos números, esta expresión regular buscará coincidencias solo con los cuatro últimos dígitos del segundo número, tal y como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#1)]  
  
 La expresión regular no coincide con el primer número porque el cuantificador `*` intenta buscar coincidencias con el elemento anterior tantas veces como sea posible en toda la cadena y, por tanto, encuentra su coincidencia al final de la cadena.  
  
 Éste no es el comportamiento deseado.  En su lugar, puede utilizar el cuantificador no expansivo `*?` ``  para extraer los dígitos de ambos números, tal y como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/cs/Greedy.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.Greedy#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Quantifiers.Greedy/vb/Greedy.vb#2)]  
  
 En la mayoría de los casos, las expresiones regulares con cuantificadores expansivos y no expansivos devuelven las mismas coincidencias.  La mayor parte de las veces, devuelven resultados diferentes cuando se utilizan con el metacarácter comodín \(`.`\), que coincide con cualquier carácter.  
  
## Cuantificadores y coincidencias vacías  
 Los cuantificadores `*`, `+`, y `{`*n*`,`*m*`}` y sus homólogos no expansivos nunca repiten después de que una coincidencia vacía cuando el número mínimo de capturas se ha encontrado.  Esta regla impide que los cuantificadores entren en bucles infinitos de coincidencias de subexpresión vacías cuando el número máximo de capturas posibles del grupo es infinito o casi infinito.  
  
 Por ejemplo, el código siguiente muestra el resultado de una llamada al método <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=fullName> con el modelo de expresión regular `(a?)*`, que coincide con cero o un carácter "a", cero o más veces.  Tenga en cuenta que el grupo de captura único captura todas las instancias de “a”, así como de <xref:System.String.Empty?displayProperty=fullName>, pero no hay una segunda coincidencia vacía, porque en la primera el cuantificador deja de repetirse.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch1.cs#1)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch1.vb#1)]  
  
 Para ver la diferencia práctica entre un grupo de captura que define un número mínimo y máximo de capturas y otro que define un número de capturas fijo, considere los patrones de expresiones regulares `(a\1|(?(1)\1)){0,2}` y `(a\1|(?(1)\1)){2}`.  Ambas expresiones regulares constan de un único grupo de capturas, que se define como se muestra en la tabla siguiente.  
  
|Modelo|Descripción|  
|------------|-----------------|  
|`(a\1`|Hacer coincidir “a” con el valor del primer grupo capturado...|  
|`&#124;(?(1)`|… o prueba si se ha definido el primer grupo capturado. \(Observe que la construcción `(?(1)` no define un grupo de captura\).|  
|`\1))`|Si el primer grupo capturado existe, coincide con su valor.  Si el grupo no existe, este coincidirá con <xref:System.String.Empty?displayProperty=fullName>.|  
  
 La primera expresión regular intenta coincidir con este modelo entre cero y dos veces; la segunda, exactamente dos veces.  Dado que el primer modelo alcanza el número mínimo de capturas con su primera captura de <xref:System.String.Empty?displayProperty=fullName>, nunca se repite para intentar hacer coincidir `a\1`; el cuantificador `{0,2}` sólo permite coincidencias vacías en la última iteración.  En cambio, la segunda expresión regular coincide con “a” porque evalúa `a\1` por segunda vez; el número mínimo de iteraciones, 2, obliga al motor a repetir después de una coincidencia vacía.  
  
 [!code-csharp[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/cs/emptymatch4.cs#2)]
 [!code-vb[RegularExpressions.Quantifiers.EmptyMatch#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.quantifiers.emptymatch/vb/emptymatch4.vb#2)]  
  
## Vea también  
 [Lenguaje de expresiones regulares \- Referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)   
 [Retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)