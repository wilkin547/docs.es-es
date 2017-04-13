---
title: "Detalles del comportamiento de expresiones regulares | Microsoft Docs"
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
  - "expresiones regulares, comportamiento"
  - "expresiones regulares de .NET Framework, comportamiento"
ms.assetid: 0ee1a6b8-caac-41d2-917f-d35570021b10
caps.latest.revision: 27
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 27
---
# Detalles del comportamiento de expresiones regulares
El motor de búsqueda de expresiones regulares de .NET Framework es un buscador de coincidencias de expresiones regulares con retroceso que incorpora un motor de búsqueda NFA \(autómata finito no determinista\) tradicional, como el que utiliza Perl, Python, Emacs y Tcl.  Esto lo distingue de los motores de búsqueda DFA \(autómatas finitos deterministas\) de expresiones regulares puras, que son más rápidos, pero también más limitados, como los de awk, egrep o lex.  Esto también lo distingue de los NFA POSIX estandarizados, que son más lentos.  En la siguiente sección se describen los tres tipos de motores de expresiones regulares y se explica por qué en .NET Framework las expresiones regulares se implementan mediante un motor NFA tradicional.  
  
## Ventajas del motor NFA  
 Cuando los motores DFA realizan la coincidencia de modelos, la cadena de entrada controla su orden de procesamiento.  El motor comienza al principio de la cadena de entrada y sigue determinando secuencialmente si el carácter siguiente coincide con el modelo de expresión regular.  Estos motores de búsqueda garantizan también la búsqueda de la cadena coincidente más larga posible.  Dado que nunca prueban dos veces el mismo carácter, los motores DFA no permiten retroceder.  Sin embargo, dado que los motores de búsqueda DFA solo contienen estados finitos, no pueden buscar las coincidencias de un patrón con referencias inversas, y puesto que no crean una expansión explícita, no pueden capturar subexpresiones.  
  
 A diferencia de los motores DFA, cuando los motores NFA tradicionales realizan la coincidencia de modelos, el modelo de expresión regular controla su orden de procesamiento.  Cuando procesa un elemento del lenguaje determinado, el motor utiliza la concordancia expansiva; es decir, busca la mayor parte posible de la cadena de entrada.  Pero también guarda su estado después de hallar una coincidencia correcta con una subexpresión.  Si más adelante no se produce ninguna coincidencia, el motor puede regresar a un estado guardado para intentar otras coincidencias.  Este proceso de abandonar una coincidencia de subexpresión correcta para que los elementos del lenguaje subsiguientes de la expresión regular también puedan coincidir se denomina *retroceder*.  Los motores NFA utilizan el retroceso para probar todas las posibles expansiones de una expresión regular en un orden concreto y aceptar la primera coincidencia.  Como los motores de búsqueda NFA tradicionales crean una expansión específica de la expresión regular para lograr encontrar una coincidencia, son capaces de capturar subexpresiones y referencias inversas coincidentes.  No obstante, como los motores de búsqueda NFA tradicionales tienen capacidad de retroceso, pueden visitar exactamente el mismo estado varias veces, si a dicho estado se llega por distintos caminos.  Por consiguiente, pueden presentar un funcionamiento exponencialmente más lento, en el peor de los casos.  Dado que los motores de búsqueda NFA tradicionales aceptan la primera coincidencia que encuentran, es posible que no encuentren otras coincidencias \(probablemente más largas\).  
  
 Los motores de búsqueda NFA POSIX son como los motores de búsqueda NFA tradicionales, con la excepción de que continúan el retroceso hasta que son capaces de garantizar que han encontrado la cadena coincidente más larga posible.  Por tanto, un motor de búsqueda NFA POSIX es más lento que un motor de búsqueda NFA tradicional, y no permite dar prioridad a un cadena coincidente más corta frente a una más larga cambiando el orden de la búsqueda hacia atrás.  
  
 Los programadores suelen preferir los motores NFA tradicionales porque proporcionan mayor control sobre la coincidencia de cadenas que los motores DFA o NFA POSIX.  Aunque, en el peor de los casos, se pueden ejecutar con lentitud, se les puede dirigir para que busquen coincidencias en tiempo lineal o polinómico mediante patrones que reduzcan las ambigüedades y que limiten el retroceso.  En otras palabras, aunque los motores NFA sacrifican el rendimiento en aras de la eficacia y la flexibilidad, en la mayoría de los casos ofrecen un rendimiento aceptable si la expresión regular se escribe correctamente y evita los casos en que el retroceso degrada exponencialmente el rendimiento.  
  
> [!NOTE]
>  Para obtener información sobre la disminución del rendimiento producida por un retroceso excesivo y las maneras de crear una expresión regular para evitarlo, vea [Retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md).  
  
## Funciones del motor de .NET Framework  
 Para aprovechar las ventajas de un motor de búsqueda NFA tradicional, el motor de búsqueda de expresiones regulares de .NET Framework incluye un conjunto completo de construcciones que permite a los programadores dirigir el motor de retroceso.  Estas construcciones sirven para buscar cadenas coincidentes con mayor rapidez o para favorecer determinadas expansiones frente a otras.  
  
 Otras características del motor de expresiones regulares de .NET Framework son:  
  
-   Los cuantificadores no expansivos: `??`, `*?`, `+?`, `{`*n*`,`*m*`}?`.  Estas construcciones indican al motor de retroceso cómo buscar primero el número mínimo de repeticiones.  A diferencia de los cuantificadores avariciosos normales, que intentan buscar primero el número máximo de repeticiones.  En el siguiente ejemplo se muestra la diferencia entre los dos casos.  Una expresión regular busca una frase que termine por un número y hay un grupo que captura previsto para extraer ese número.  La expresión regular `.+(\d+)\.` incluye el cuantificador expansivo `.+`, de modo que el motor de expresiones regulares capture solamente el último dígito del número.  En cambio, la expresión regular `.+?(\d+)\.` incluye el cuantificador no expansivo `.+?`, que hace que el motor de expresiones regulares capture el número completo.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lazy1.cs#1)]
     [!code-vb[Conceptual.RegularExpressions.Design#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lazy1.vb#1)]  
  
     Las versiones expansiva y no expansiva de esta expresión regular se definen como se muestra en la siguiente tabla.\`  
  
    |Modelo|Descripción|  
    |------------|-----------------|  
    |`.+` \(cuantificador expansivo\)|Buscar por lo menos una aparición de cualquier carácter.  Esto hace que el motor de expresiones regulares busque la cadena completa y, a continuación, retroceda según sea necesario para buscar el resto del modelo.|  
    |`.+?` \(cuantificador no expansivo\)|Buscar por lo menos una aparición de cualquier carácter, pero la mínima cantidad de caracteres posible.|  
    |`(\d+)`|Buscar por lo menos un carácter numérico y asignárselo al primer grupo de captura.|  
    |`\.`|Buscar coincidencias con un punto.|  
  
     Para obtener más información sobre los cuantificadores no expansivos, vea [Cuantificadores](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
-   Búsqueda anticipada positiva: `(?=`*subexpression*`)`.  Esta característica permite que el motor de retroceso vuelva a la misma posición de texto después de encontrar una subexpresión coincidente.  Sirve para buscar a lo largo del texto comprobando varios modelos que empiezan en la misma posición.  También permite al motor comprobar que una subcadena existe al final de la coincidencia sin incluir la subcadena en el texto coincidente.  En el siguiente ejemplo se utiliza la búsqueda anticipada positiva para extraer de una frase las palabras que no van seguidas de símbolos de puntuación.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead1.cs#2)]
     [!code-vb[Conceptual.RegularExpressions.Design#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead1.vb#2)]  
  
     La expresión regular `\b[A-Z]+\b(?=\P{P})` se define como se muestra en la tabla siguiente.  
  
    |Modelo|Descripción|  
    |------------|-----------------|  
    |`\b`|Comienza la búsqueda de coincidencias en un límite de palabras.|  
    |`[A-Z]+`|Buscar cualquier carácter alfabético una o más veces.  Dado que se llama al método <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=fullName> con la opción <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>, la comparación no realiza distinción entre mayúsculas y minúsculas.|  
    |`\b`|Finaliza la búsqueda de coincidencias en un límite de palabras.|  
    |`(?=\P{P})`|Buscar hacia delante para determinar si el siguiente carácter es un símbolo de puntuación.  Si no es, se determina la coincidencia correctamente.|  
  
     Para obtener más información sobre las aserciones de búsqueda anticipada positiva, vea [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Búsqueda anticipada negativa: `(?!`*subexpression*`)`.  Esta característica permite buscar una expresión coincidente únicamente si no se encuentra ninguna subexpresión que coincida.  Es especialmente eficaz a la hora de restringir una búsqueda, ya que normalmente resulta mucho más sencillo indicar las expresiones por eliminación que las expresiones por inclusión.  Por ejemplo, es difícil escribir una expresión para aquellas palabras que no empiezan con "in".  En el siguiente ejemplo se utiliza la búsqueda anticipada negativa para excluirlas.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookahead2.cs#3)]
     [!code-vb[Conceptual.RegularExpressions.Design#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookahead2.vb#3)]  
  
     El patrón de expresión regular `\b(?!non)\w+\b` se define como se muestra en la tabla siguiente.  
  
    |Modelo|Descripción|  
    |------------|-----------------|  
    |`\b`|Comienza la búsqueda de coincidencias en un límite de palabras.|  
    |`(?!non)`|Buscar hacia delante para asegurarse de que la cadena actual no empieza por "in".  Si empieza por "in", no se establece ninguna coincidencia.|  
    |`(\w+)`|Coincide con uno o varios caracteres que se usan para formar palabras.|  
    |`\b`|Finaliza la búsqueda de coincidencias en un límite de palabras.|  
  
     Para obtener más información sobre las aserciones de búsqueda anticipada negativa, vea [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Evaluación condicional: `(?(`*expression*`)`*yes* `|` *no* `)` y `(?(`*name*`)`*yes* `|` *no* `)`, donde una subexpresión *expression* a coincidir, *name* es el nombre de un grupo de captura, *yes* es la cadena que se buscará si coincide *expression* o *name* es un grupo capturado válido, no vacío, y *no* es la subexpresión coincida con si no coincide *expression* o *name* no es un grupo capturado válido, no vacío.  Esta característica permite al motor buscar mediante más de un modelo de alternativo, según el resultado de la búsqueda de coincidencias de la subexpresión anterior o el resultado de una aserción de ancho cero.  Esto permite una forma más eficaz de referencia inversa que permite, por ejemplo, buscar una subexpresión basándose en si se encontró previamente una subexpresión coincidente.  La expresión regular del siguiente ejemplo busca párrafos para uso público e interno.  Los párrafos que son exclusivamente para uso interno empiezan con la etiqueta `<PRIVATE>`.  El modelo de expresión regular `^(?<Pvt>\<PRIVATE\>\s)?(?(Pvt)((\w+\p{P}?\s)+)|((\w+\p{P}?\s)+))\r?$` usa evaluación condicional para asignar a grupos de captura independientes el contenido de los párrafos pensados para uso público y para uso interno.  De este modo, estos párrafos se pueden controlar de manera diferente.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/conditional1.cs#4)]
     [!code-vb[Conceptual.RegularExpressions.Design#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/conditional1.vb#4)]  
  
     El modelo de expresión regular se define como se muestra en la tabla siguiente.  
  
    |Modelo|Descripción|  
    |------------|-----------------|  
    |`^`|Comenzar la búsqueda al principio de una línea.|  
    |`(?<Pvt>\<PRIVATE\>\s)?`|Buscar cero o una aparición de la cadena `<PRIVATE>` seguida por un carácter de espacio en blanco.  Asignar la coincidencia a un grupo de captura con el nombre `Pvt`.|  
    |`(?(Pvt)((\w+\p{P}?\s)+)`|si el grupo de captura `Pvt` existe, buscar una o varias apariciones de uno o más caracteres alfabéticos seguidos por cero o un separador de puntuación, seguido por un carácter de espacio en blanco.  Asignar la subcadena al primer grupo de captura.|  
    |`&#124;((\w+\p{P}?\s)+))`|Si el grupo de captura `Pvt` no existe, buscar una o más apariciones de uno o más caracteres alfabéticos seguidos por cero o un separador de puntuación, seguido por un carácter de espacio en blanco.  Asignar la subcadena al tercer grupo de captura.|  
    |`\r?$`|Buscar el final de una línea o el final de la cadena.|  
  
     Para obtener más información sobre la evaluación condicional, vea [Construcciones de alternancia](../../../docs/standard/base-types/alternation-constructs-in-regular-expressions.md).  
  
-   Definiciones de equilibrio de grupo: `(?<`*name1*`-`*name2*`>` *subexpression*`)`.  Esta característica permite que el motor de expresiones regulares realice el seguimiento de construcciones anidadas como paréntesis o corchetes de apertura y cierre.  Para obtener un ejemplo, vea [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   Subexpresiones sin retroceso \(denominadas también subexpresiones expansivas\): `(?>`*subexpression*`)`.  Esta característica permite que el motor de retroceso se asegure de que una subexpresión coincida solo con la primera coincidencia encontrada para esa subexpresión, como si la expresión se ejecutara independientemente de la expresión que la contiene.  Si no se utiliza esta construcción, las búsquedas con retroceso de expresiones de gran tamaño podrían cambiar el comportamiento de una subexpresión.  Por ejemplo, la expresión regular `(a+)\w` busca uno o más caracteres "a", junto con un carácter alfabético que sigue a la secuencia de caracteres "a", y asigna la secuencia de caracteres "a" caracteres al primer grupo de captura. Sin embargo, si el último carácter de la cadena de entrada también es una "a", coincide con el elemento del lenguaje `\w` y no se incluye en el grupo capturado.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking2.cs#7)]
     [!code-vb[Conceptual.RegularExpressions.Design#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking2.vb#7)]  
  
     La expresión regular `((?>a+))\w` evita este comportamiento.  Como todos los caracteres "a" consecutivos se buscan sin retroceder, el primer grupo de captura incluye todos los caracteres "a" consecutivos.  Si el carácter "a" no va seguido por al menos un carácter más que no sea "a", la coincidencia no se produce.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/nonbacktracking1.cs#8)]
     [!code-vb[Conceptual.RegularExpressions.Design#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/nonbacktracking1.vb#8)]  
  
     Para obtener más información sobre las subexpresiones sin retroceso, vea [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
-   La búsqueda de coincidencias de derecha a izquierda, que se especifica proporcionando la opción <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> a un constructor de clase <xref:System.Text.RegularExpressions.Regex> o a un método de instancia de coincidencia estática.  Esta característica resulta útil para buscar de derecha a izquierda en lugar de hacerlo de izquierda a derecha, o en los casos en los que es más eficaz iniciar una búsqueda de coincidencias en la parte derecha del modelo, en lugar de en la parte izquierda.  Como se muestra en el ejemplo siguiente, utilizar la coincidencia de derecha a izquierda puede cambiar el comportamiento de los cuantificadores expansivos.  En el ejemplo se realizan dos búsquedas de una frase que finaliza en un número.  La búsqueda de izquierda a derecha que utiliza el cuantificador expansivo `+` halla uno de los seis dígitos de la frase, mientras que el de derecha a izquierda halla los seis.  Para obtener una descripción del modelo de expresión regular, vea el ejemplo ilustrativo de los cuantificadores no expansivos previamente en esta sección.  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/rtl1.cs#6)]
     [!code-vb[Conceptual.RegularExpressions.Design#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/rtl1.vb#6)]  
  
     Para obtener más información sobre la coincidencia de derecha a izquierda, vea [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
-   Búsqueda tardía positiva y negativa: `(?<=`*subexpression*`)` para la búsqueda tardía positiva; y `(?<!`*subexpression*`)` para la búsqueda tardía negativa.  Esta característica es similar a la búsqueda anticipada, que se ha abordado antes en este mismo tema.  Dado que el motor de búsqueda de expresiones regulares permite realizar búsquedas de coincidencias completas de derecha a izquierda, las expresiones regulares permiten realizar búsquedas tardías no restringidas.  Las búsquedas tardías positivas y negativas se pueden utilizar también para evitar anidar los cuantificadores cuando la subexpresión anidada es un supraconjunto de una expresión exterior.  Las expresiones regulares con cuantificadores anidados suelen presentar un bajo rendimiento.  Por ejemplo, en el siguiente ejemplo se comprueba que una cadena comienza y finaliza con un carácter alfanumérico, y que todos los demás caracteres de la cadena pertenecen a un subconjunto mayor.  Constituye una parte de la expresión regular utilizada para validar las direcciones de correo electrónico; para obtener más información, vea [Cómo: Comprobar si las cadenas tienen un formato de correo electrónico válido](../../../docs/standard/base-types/how-to-verify-that-strings-are-in-valid-email-format.md).  
  
     [!code-csharp[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.design/cs/lookbehind1.cs#5)]
     [!code-vb[Conceptual.RegularExpressions.Design#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.design/vb/lookbehind1.vb#5)]  
  
     La expresión regular `^[A-Z0-9]([-!#$%&'.*+/=?^`{}|~\w])*(?<=[A-Z0-9])$` se define como se muestra en la tabla siguiente.  
  
    |Modelo|Descripción|  
    |------------|-----------------|  
    |`^`|Iniciar la búsqueda de coincidencias con el principio de la cadena.|  
    |`[A-Z0-9]`|Buscar una coincidencia con cualquier carácter numérico o alfanumérico. \(En la comparación no se distingue entre mayúsculas y minúsculas.\)|  
    |`([-!#$%&'.*+/=?^`{}&#124;~\w])*`|Buscar coincidencias con cero o más apariciones de cualquier carácter alfabético, o cualquiera de los siguientes caracteres:  ¡\-\! , \#, $, % &, '. ¿, \*, \+,\/, \=? , ^, \`, {,}, &#124;, o ~.|  
    |`(?<=[A-Z0-9])`|Realizar la búsqueda tardía del carácter anterior, que debe ser numérico o alfanumérico. \(En la comparación no se distingue entre mayúsculas y minúsculas.\)|  
    |`$`|Finalizar la búsqueda al final de la cadena.|  
  
     Para obtener más información sobre la búsqueda tardía positiva y negativa, vea [Construcciones de agrupamiento](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
## Temas relacionados  
  
|Título|Descripción|  
|------------|-----------------|  
|[Retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)|Ofrece información acerca de cómo se bifurcan las expresiones regulares con retroceso para buscar coincidencias alternativas.|  
|[Compilar y volver a utilizar](../../../docs/standard/base-types/compilation-and-reuse-in-regular-expressions.md)|Ofrece información sobre cómo compilar y volver a utilizar expresiones regulares para aumentar el rendimiento.|  
|[Seguridad para subprocesos](../../../docs/standard/base-types/thread-safety-in-regular-expressions.md)|Ofrece información acerca de la seguridad de las expresiones regulares respecto a los subprocesos y explica cuándo se debe sincronizar el acceso a los objetos de expresiones regulares.|  
|[Expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md)|Proporciona información general sobre el aspecto del lenguaje de programación de expresiones regulares.|  
|[El modelo de objetos de expresión regular](../../../docs/standard/base-types/the-regular-expression-object-model.md)|Proporciona información y ejemplos de código que muestran cómo utilizar las clases de expresiones regulares.|  
|[Ejemplos de expresiones regulares](../../../docs/standard/base-types/regular-expression-examples.md)|Contiene ejemplos de código que ilustran el uso de expresiones regulares en aplicaciones comunes.|  
|[Lenguaje de expresiones regulares \- Referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)|Ofrece información acerca del juego de caracteres, operadores y construcciones que se pueden utilizar para definir expresiones regulares.|  
  
## Reference  
 <xref:System.Text.RegularExpressions?displayProperty=fullName>