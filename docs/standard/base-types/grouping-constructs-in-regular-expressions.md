---
title: Construcciones de agrupamiento en expresiones regulares
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lookbehinds
- regular expressions, grouping constructs
- lookaheads
- .NET Framework regular expressions, grouping constructs
- constructs, grouping
- grouping constructs
ms.assetid: 0fc18634-f590-4062-8d5c-f0b71abe405b
ms.openlocfilehash: 5b2ea110837d9d5b905f97ab706af52a594f1c43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159226"
---
# <a name="grouping-constructs-in-regular-expressions"></a>Construcciones de agrupamiento en expresiones regulares
Las construcciones de agrupamiento definen las subexpresiones de una expresión regular y capturan las subcadenas de una cadena de entrada. Puede utilizar construcciones de agrupamiento para hacer lo siguiente:  
  
- Buscar una subexpresión que se repite en la cadena de entrada.  
  
- Aplicar un cuantificador a una subexpresión que tiene varios elementos del lenguaje de expresiones regulares. Para más información sobre los cuantificadores, vea [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
- Incluir una subexpresión en la cadena devuelta por los métodos <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> y <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> .  
  
- Recuperar subexpresiones individuales de la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> y procesarlas por separado del texto coincidente en su conjunto.  
  
 En la tabla siguiente se enumeran las construcciones de agrupamiento admitidas por el motor de expresiones regulares de .NET y se indica si son de captura o sin captura.  
  
|Construcción de agrupamiento|De captura o sin captura|  
|------------------------|-------------------------------|  
|[Subexpresiones coincidentes](#matched_subexpression)|Capturando|  
|[Subexpresiones coincidentes con nombre](#named_matched_subexpression)|Capturando|  
|[Definiciones de grupos de compensación](#balancing_group_definition)|Capturando|  
|[Grupos sin captura](#noncapturing_group)|Sin captura|  
|[Opciones de grupo](#group_options)|Sin captura|  
|[Aserciones de búsqueda anticipada positiva de ancho cero](#zerowidth_positive_lookahead_assertion)|Sin captura|  
|[Aserciones de búsqueda anticipada negativa de ancho cero](#zerowidth_negative_lookahead_assertion)|Sin captura|  
|[Aserciones de búsqueda tardía positiva de ancho cero](#zerowidth_positive_lookbehind_assertion)|Sin captura|  
|[Aserciones de búsqueda tardía negativa de ancho cero](#zerowidth_negative_lookbehind_assertion)|Sin captura|  
|[Grupos atómicos](#atomic_groups)|Sin captura|  
  
 Para obtener información sobre los grupos y el modelo de objetos de expresiones regulares, vea [Construcciones de agrupamiento y objetos de las expresiones regulares](#Objects).  
  
<a name="matched_subexpression"></a>
## <a name="matched-subexpressions"></a>Subexpresiones coincidentes  
 La construcción de agrupación siguiente captura una subexpresión coincidente:  
  
 `(` *subexpresión* `)`  
  
 donde *subexpresión* es cualquier patrón de expresión regular válido. Las capturas que usan paréntesis se numeran automáticamente de izquierda a derecha según el orden de los paréntesis de apertura de la expresión regular, empezando desde uno. La captura con el número cero es el texto coincidente con el patrón de la expresión regular completa.  
  
> [!NOTE]
> De manera predeterminada, el elemento de lenguaje `(`*subexpresión*`)` captura la subexpresión coincidente. No obstante, la subexpresión coincidente no se captura si el parámetro <xref:System.Text.RegularExpressions.RegexOptions> del método de coincidencia de patrones de una expresión regular incluye la marca <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType> o si se aplica la opción `n` a esta subexpresión (vea [Opciones de grupo](#group_options) más adelante en este tema).  
  
 Existen cuatro formas de tener acceso a los grupos capturados:  
  
- Usando la construcción de referencia inversa dentro de la expresión regular. Para hacer referencia a la subexpresión coincidente desde la misma expresión regular, se usa la sintaxis `\`*número*, donde *número* es el número ordinal de la subexpresión capturada.  
  
- Usando la construcción de referencia inversa con nombre dentro de la expresión regular. Para hacer referencia a la subexpresión coincidente desde la misma expresión regular, se usa la sintaxis `\k<`*nombre*`>`, donde *nombre* es el nombre de un grupo de captura, o `\k<`*número*`>`, donde *número* es el número ordinal de un grupo de captura. Un grupo de captura tiene un nombre predeterminado que es idéntico a su número ordinal. Para obtener más información, vea [Subexpresiones coincidentes con nombre](#named_matched_subexpression) más adelante en este tema.  
  
- Usando la secuencia de reemplazo `$`*número* en una llamada al método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> , donde *número* es el número ordinal de la subexpresión capturada.  
  
- Mediante programación, usando el objeto <xref:System.Text.RegularExpressions.GroupCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> . El miembro en la posición cero de la colección representa la coincidencia de la expresión regular completa. Cada miembro subsiguiente representa una subexpresión coincidente. Para más información, vea la sección [Grouping Constructs and Regular Expression Objects](#Objects) .  
  
 En el ejemplo siguiente se muestra una expresión regular que identifica las palabras duplicadas en el texto. Los dos grupos de captura del patrón de la expresión regular representan las dos instancias de la palabra duplicada. La segunda instancia se captura para notificar su posición inicial en la cadena de entrada.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/grouping1.cs#1)]
 [!code-vb[RegularExpressions.Language.Grouping#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/grouping1.vb#1)]  
  
 El patrón de la expresión regular es el siguiente:  
  
`(\w+)\s(\1)\W`  
  
 En la siguiente tabla se muestra cómo se interpreta el patrón de expresión regular.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`(\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`(\1)`|Coincide con la cadena del primer grupo capturado. Este es el segundo grupo de captura. El ejemplo lo asigna a un grupo capturado de forma que la posición inicial de la palabra duplicada se pueda recuperar de la propiedad `Match.Index` .|  
|`\W`|Coincide con un carácter que no se usa para formar palabras, como los espacios en blanco y los signos de puntuación. Esto evita que el patrón de la expresión regular coincida con una palabra que comience por la palabra del primer grupo capturado.|  
  
<a name="named_matched_subexpression"></a>
## <a name="named-matched-subexpressions"></a>Subexpresiones coincidentes con nombre  
 La construcción de agrupamiento siguiente captura una subexpresión coincidente y permite tener acceso a ella por nombre o por número:  
  
`(?<name>subexpression)`  
  
 O bien  
  
`(?'name'subexpression)`  
  
 donde *nombre* es un nombre de grupo válido, y *subexpresión* es cualquier patrón de expresión regular válido. *nombre* no debe contener ningún carácter de puntuación y no puede comenzar por un número.  
  
> [!NOTE]
> Si el parámetro <xref:System.Text.RegularExpressions.RegexOptions> del método de coincidencia de patrones de una expresión regular incluye la marca <xref:System.Text.RegularExpressions.RegexOptions.ExplicitCapture?displayProperty=nameWithType> o si se aplica la opción `n` a esta subexpresión (vea [Opciones de grupo](#group_options) más adelante en este tema), la única forma de capturar una subexpresión es asignar nombres explícitamente a los grupos de captura.  
  
 Puede tener acceso a los grupos capturados con nombre de las maneras siguientes:  
  
- Usando la construcción de referencia inversa con nombre dentro de la expresión regular. Para hacer referencia a la subexpresión coincidente desde la misma expresión regular, se usa la sintaxis `\k<`*nombre*`>`, donde *nombre* es el nombre de la subexpresión capturada.  
  
- Usando la construcción de referencia inversa dentro de la expresión regular. Para hacer referencia a la subexpresión coincidente desde la misma expresión regular, se usa la sintaxis `\`*número*, donde *número* es el número ordinal de la subexpresión capturada. Las subexpresiones coincidentes con nombre se numeran consecutivamente de izquierda a derecha después de las subexpresiones coincidentes.  
  
- Usando la secuencia de reemplazo `${`*nombre*`}` en una llamada al método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> , donde *nombre* es el nombre de la subexpresión capturada.  
  
- Usando la secuencia de reemplazo `$`*número* en una llamada al método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> o <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> , donde *número* es el número ordinal de la subexpresión capturada.  
  
- Mediante programación, usando el objeto <xref:System.Text.RegularExpressions.GroupCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> . El miembro en la posición cero de la colección representa la coincidencia de la expresión regular completa. Cada miembro subsiguiente representa una subexpresión coincidente. Los grupos capturados con nombre se almacenan en la colección después de los grupos capturados numerados.  
  
- Mediante programación, proporcionando el nombre de la subexpresión al indizador del objeto <xref:System.Text.RegularExpressions.GroupCollection> (en C#) o a su propiedad <xref:System.Text.RegularExpressions.GroupCollection.Item%2A> (en Visual Basic).  
  
 Un patrón de expresión regular simple muestra cómo se puede hacer referencia a los grupos numerados (sin nombre) y con nombre mediante programación o utilizando la sintaxis del lenguaje de expresiones regulares. La expresión regular `((?<One>abc)\d+)?(?<Two>xyz)(.*)` produce los siguientes grupos de captura por número y por nombre. El primer grupo de captura (el número 0) siempre hace referencia al patrón completo.  
  
|número|Name|Modelo|  
|------------|----------|-------------|  
|0|0 (nombre predeterminado)|`((?<One>abc)\d+)?(?<Two>xyz)(.*)`|  
|1|1 (nombre predeterminado)|`((?<One>abc)\d+)`|  
|2|2 (nombre predeterminado)|`(.*)`|  
|3|Uno|`(?<One>abc)`|  
|4|Dos|`(?<Two>xyz)`|  
  
 En el ejemplo siguiente se muestra una expresión regular que identifica las palabras duplicadas y la palabra que sigue inmediatamente a cada palabra duplicada. El patrón de la expresión regular define dos subexpresiones con nombre: `duplicateWord`, que representa la palabra duplicada; y `nextWord`, que representa la palabra que sigue a la palabra duplicada.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/grouping2.cs#2)]
 [!code-vb[RegularExpressions.Language.Grouping#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/grouping2.vb#2)]  
  
 El patrón de la expresión regular es el siguiente:  
  
`(?<duplicateWord>\w+)\s\k<duplicateWord>\W(?<nextWord>\w+)`  
  
 La tabla siguiente muestra cómo se interpreta la expresión regular.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`(?<duplicateWord>\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Este grupo de captura se denomina `duplicateWord`.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`\k<duplicateWord>`|Coincide con la cadena del grupo capturado denominada `duplicateWord`.|  
|`\W`|Coincide con un carácter que no se usa para formar palabras, como los espacios en blanco y los signos de puntuación. Esto evita que el patrón de la expresión regular coincida con una palabra que comience por la palabra del primer grupo capturado.|  
|`(?<nextWord>\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Este grupo de captura se denomina `nextWord`.|  
  
 Tenga en cuenta que un nombre de grupo se puede repetir en una expresión regular. Por ejemplo, es posible que más de un grupo se llame `digit`, como muestra el ejemplo siguiente. En el caso de nombres duplicados, el valor del objeto <xref:System.Text.RegularExpressions.Group> viene determinado por la última captura correcta en la cadena de entrada. Además, la colección <xref:System.Text.RegularExpressions.CaptureCollection> se rellena con información de cada captura igual que si el nombre de grupo no estuviera duplicado.  
  
 En el ejemplo siguiente, la expresión regular `\D+(?<digit>\d+)\D+(?<digit>\d+)?` incluye dos apariciones de un grupo llamado `digit`. El primer grupo llamado `digit` captura uno o más caracteres de dígito. El segundo grupo llamado `digit` captura cero o una aparición de uno o más caracteres de dígito. Tal y como muestra la salida del ejemplo, si el segundo grupo de captura coincide correctamente con el texto, el valor de ese texto define el valor del objeto <xref:System.Text.RegularExpressions.Group> . Si el segundo grupo de captura no coincide con la cadena de entrada, el valor de la última coincidencia correcta define el valor del objeto <xref:System.Text.RegularExpressions.Group> .  
  
 [!code-csharp[RegularExpressions.Language.Grouping#12](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/duplicate1.cs#12)]
 [!code-vb[RegularExpressions.Language.Grouping#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/duplicate1.vb#12)]  
  
 La tabla siguiente muestra cómo se interpreta la expresión regular.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\D+`|Coincide con uno o más caracteres de dígito no decimal.|  
|`(?<digit>\d+)`|Coincide con uno o más caracteres de dígito decimal. Asigna la coincidencia al grupo llamado `digit`.|  
|`\D+`|Coincide con uno o más caracteres de dígito no decimal.|  
|`(?<digit>\d+)?`|Coincide con ninguna o una aparición de uno o más caracteres de dígito decimal. Asigna la coincidencia al grupo llamado `digit`.|  
  
<a name="balancing_group_definition"></a>
## <a name="balancing-group-definitions"></a>Definiciones de grupos de compensación  
 Una definición de grupo de compensación elimina la definición de un grupo definido anteriormente y almacena, en el grupo actual, el intervalo entre el grupo definido anteriormente y el grupo actual. Esta construcción de agrupamiento tiene el formato siguiente:  
  
`(?<name1-name2>subexpression)`  
  
 O bien  
  
`(?'name1-name2' subexpression)`
  
 donde *nombre1* es el grupo actual (opcional), *nombre2* es un grupo definido previamente y *subexpresión* es cualquier patrón de expresión regular válido. La definición de grupo de compensación elimina la definición de *nombre2* y almacena el intervalo entre *nombre2* y *nombre1* en *nombre1*. Si no se ha definido el grupo *nombre2* , la búsqueda de coincidencias retrocede. Como al eliminar la última definición de *nombre2* se revela la definición anterior de *nombre2*, esta construcción permite usar la pila de capturas del grupo *nombre2* como contador para realizar el seguimiento de construcciones anidadas como paréntesis o corchetes de apertura y cierre.  
  
 La definición del grupo de compensación utiliza *nombre2* como pila. El carácter inicial de cada construcción anidada se coloca en el grupo y en su colección <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> . Cuando se encuentra una coincidencia con el carácter de cierre, el carácter de apertura correspondiente se quita del grupo, y la colección <xref:System.Text.RegularExpressions.Group.Captures%2A> disminuye en una unidad. Después de buscar las coincidencias con los caracteres de apertura y cierre de todas las construcciones anidadas, *nombre2* estará vacío.  
  
> [!NOTE]
> Después de modificar la expresión regular del ejemplo siguiente para que utilice el carácter de apertura y cierre adecuado de una construcción anidada, puede utilizarla con la mayoría de las estructuras anidadas, como expresiones matemáticas o líneas de código de programa que incluyen varias llamadas a métodos anidadas.  
  
 En el ejemplo siguiente se usa una definición de grupo de compensación para que coincida con los corchetes angulares de apertura y de cierre (<>) de una cadena de entrada. En el ejemplo se definen dos grupos con nombre, `Open` y `Close`, que se utilizan como una pila para realizar el seguimiento de los pares de corchetes angulares coincidentes. Cada corchete angular de apertura capturado se inserta en la colección de captura del grupo `Open` , y cada corchete angular de cierre capturado se inserta en la colección de captura del grupo `Close` . Mediante la definición del grupo de compensación se comprueba que haya un corchete angular de cierre para cada corchete angular de apertura. Si no lo hay, el subpatrón final, `(?(Open)(?!))`, se evalúa solo si el grupo `Open` no está vacío (y, por consiguiente, si no se han cerrado todas las construcciones anidadas). Si se evalúa el subpatrón final, la coincidencia produce un error, porque el subpatrón `(?!)` es una aserción de búsqueda anticipada negativa de ancho cero que siempre produce un error.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/grouping3.cs#3)]
 [!code-vb[RegularExpressions.Language.Grouping#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/grouping3.vb#3)]  
  
 El patrón de la expresión regular es:  
  
`^[^<>]*(((?'Open'<)[^<>]*)+((?'Close-Open'>)[^<>]*)+)*(?(Open)(?!))$`  
  
 La expresión regular se interpreta como sigue:  
  
|Modelo|Description|  
|-------------|-----------------|  
|`^`|Comienza al principio de la cadena.|  
|`[^<>]*`|Coincide con cero o más caracteres que no son corchetes angulares de apertura o cierre.|  
|`(?'Open'<)`|Coincide con un corchete angular de apertura y se lo asigna a un grupo denominado `Open`.|  
|`[^<>]*`|Coincide con cero o más caracteres que no son corchetes angulares de apertura o cierre.|  
|`((?'Open'<)[^<>]*)+`|Coincide con una o más apariciones de un corchete angular de apertura seguido de cero o más caracteres que no son corchetes angulares de apertura o cierre. Este es el segundo grupo de captura.|  
|`(?'Close-Open'>)`|Coincide con un corchete angular de cierre, asigna la subcadena entre el grupo `Open` y el grupo actual al grupo `Close` y elimina la definición del grupo `Open`.|  
|`[^<>]*`|Coincide con cero o más apariciones de cualquier carácter que no sea un corchete angular de apertura ni de cierre.|  
|`((?'Close-Open'>)[^<>]*)+`|Coincide con una o más apariciones de un corchete angular de cierre, seguido de cero o más apariciones de cualquier carácter que no sea un corchete angular de apertura ni de cierre. Al buscar una coincidencia con el corchete angular de cierre, asigna la subcadena entre el grupo `Open` y el grupo actual al grupo `Close` , y elimina la definición del grupo `Open` . Éste es el tercer grupo de captura.|  
|`(((?'Open'<)[^<>]*)+((?'Close-Open'>)[^<>]*)+)*`|Coincide con cero o más apariciones del patrón siguiente: una o varias apariciones de un corchete angular de apertura, seguidas de cero o más caracteres que no sean corchetes angulares, seguidas de una o más apariciones de un corchete angular de cierre, seguidas de cero o más apariciones de caracteres que no sean corchetes angulares. Al buscar una coincidencia con el corchete angular de cierre, borra la definición del grupo `Open` y asigna la subcadena entre el grupo `Open` y el grupo actual al grupo `Close` . Este es el primer grupo de captura.|  
|`(?(Open)(?!))`|Si existe el grupo `Open` , abandona la coincidencia si se encuentra una cadena vacía, pero no avanza la posición del motor de expresiones regulares en la cadena. Esta es una aserción de búsqueda anticipada negativa de ancho cero. Dado que siempre existe implícitamente una cadena vacía en una cadena de entrada, esta coincidencia siempre produce un error. Un error en esta coincidencia indica que no hay el mismo número de corchetes angulares de apertura y de cierre.|  
|`$`|Coincide con el final de la cadena de entrada.|  
  
 La subexpresión final, `(?(Open)(?!))`, indica si las construcciones de anidamiento de la cadena de entrada están compensadas correctamente (por ejemplo, si cada corchete angular de apertura coincide con un corchete angular de cierre). Utiliza la coincidencia condicional basada en un grupo capturado válido; para más información, vea [Construcciones de alternancia](../../../docs/standard/base-types/alternation-constructs-in-regular-expressions.md). Si se define el grupo `Open`, el motor de expresiones regulares intenta buscar la subexpresión `(?!)` en la cadena de entrada. El grupo `Open` solo se debería definir si las construcciones de anidamiento están descompensadas. Por consiguiente, el patrón que se va a comparar en la cadena de entrada debe ser uno que siempre produzca un error en la coincidencia. En este caso, `(?!)` es una aserción de búsqueda anticipada negativa de ancho cero que siempre produce un error, porque siempre existe implícitamente una cadena vacía en la posición siguiente de la cadena de entrada.  
  
 En el ejemplo, el motor de expresiones regulares evalúa la cadena de entrada "\<abc><mno\<xyz>>" como se muestra en la tabla siguiente.  
  
|Paso|Modelo|Resultado|  
|----------|-------------|------------|  
|1|`^`|Comienza la búsqueda de coincidencias al principio de la cadena de entrada|  
|2|`[^<>]*`|Busca caracteres que no sean corchetes angulares antes del corchete angular de apertura; no encuentra ninguna coincidencia.|  
|3|`(((?'Open'<)`|Encuentra el corchete angular de apertura de "\<abc" y se lo asigna al grupo `Open`.|  
|4|`[^<>]*`|Encuentra "abc".|  
|5|`)+`|"<abc" es el valor del segundo grupo capturado.<br /><br /> El carácter siguiente de la cadena de entrada no es un corchete angular de apertura, por lo que el motor de expresiones regulares no retrocede al subpatrón `(?'Open'<)[^<>]*)`.|  
|6|`((?'Close-Open'>)`|Encuentra el corchete angular de cierre de "\<abc>", asigna "abc", que es la subcadena entre el grupo `Open` y el corchete angular de cierre, al grupo `Close`, y elimina el valor actual ("<") del grupo `Open`, dejándolo vacío.|  
|7|`[^<>]*`|Busca caracteres que no sean corchetes angulares después del corchete angular de cierre; no encuentra ninguna coincidencia.|  
|8|`)+`|El valor del tercer grupo capturado es ">".<br /><br /> El carácter siguiente de la cadena de entrada no es un corchete angular de cierre, por lo que el motor de expresiones regulares no retrocede al subpatrón `((?'Close-Open'>)[^<>]*)` .|  
|9|`)*`|El valor del primer grupo capturado es "\<abc>".<br /><br /> El carácter siguiente de la cadena de entrada es un corchete angular de apertura, por lo que el motor de expresiones regulares retrocede al subpatrón `(((?'Open'<)` .|  
|10|`(((?'Open'<)`|Encuentra el corchete angular de apertura de "\<mno" y se lo asigna al grupo `Open`. Su colección <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> ahora tiene un solo valor, "<".|  
|11|`[^<>]*`|Encuentra "mno".|  
|12|`)+`|"<mno" es el valor del segundo grupo capturado.<br /><br /> El carácter siguiente de la cadena de entrada es un corchete angular de apertura, por lo que el motor de expresiones regulares retrocede al subpatrón `(?'Open'<)[^<>]*)` .|  
|13|`(((?'Open'<)`|Encuentra el corchete angular de apertura de "\<xyz>" y se lo asigna al grupo `Open`. La colección <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> del grupo `Open` ahora incluye dos capturas: el corchete angular de apertura de "\<mno" y el corchete angular de apertura de "\<xyz>".|  
|14|`[^<>]*`|Encuentra "xyz".|  
|15|`)+`|"<xyz" es el valor del segundo grupo capturado.<br /><br /> El carácter siguiente de la cadena de entrada no es un corchete angular de apertura, por lo que el motor de expresiones regulares no retrocede al subpatrón `(?'Open'<)[^<>]*)`.|  
|16|`((?'Close-Open'>)`|Coincide con el corchete angular de cierre de "\<xyz>". "xyz", asigna la subcadena entre el grupo `Open` y el corchete angular de cierre al grupo `Close`, y elimina el valor actual del grupo `Open`. El valor de la captura anterior (el corchete angular de apertura de "\<mno") se convierte en el valor actual del grupo `Open`. La colección <xref:System.Text.RegularExpressions.Group.Captures%2A> del grupo `Open` ahora incluye una única captura, el corchete angular de apertura de "\<xyz>".|  
|17|`[^<>]*`|Busca caracteres que no sean corchetes angulares; no encuentra ninguna coincidencia.|  
|18|`)+`|El valor del tercer grupo capturado es ">".<br /><br /> El carácter siguiente de la cadena de entrada es un corchete angular de cierre, por lo que el motor de expresiones regulares retrocede al subpatrón `((?'Close-Open'>)[^<>]*)` .|  
|19|`((?'Close-Open'>)`|Encuentra el último corchete angular de cierre de "xyz>>", asigna "mno\<xyz>" (la subcadena entre el grupo `Open` y el corchete angular de cierre) al grupo `Close` y elimina el valor actual del grupo `Open`. El grupo `Open` está ahora vacío.|  
|20|`[^<>]*`|Busca caracteres que no sean corchetes angulares; no encuentra ninguna coincidencia.|  
|21|`)+`|El valor del tercer grupo capturado es ">".<br /><br /> El carácter siguiente de la cadena de entrada no es un corchete angular de cierre, por lo que el motor de expresiones regulares no retrocede al subpatrón `((?'Close-Open'>)[^<>]*)` .|  
|22|`)*`|El valor del primer grupo capturado es "<mno\<xyz>>".<br /><br /> El carácter siguiente de la cadena de entrada no es un corchete angular de apertura, por lo que el motor de expresiones regulares no retrocede al subpatrón `(((?'Open'<)`.|  
|23|`(?(Open)(?!))`|El grupo `Open` no está definido, por lo que no se intenta encontrar ninguna coincidencia.|  
|24|`$`|Encuentra el final de la cadena de entrada.|  
  
<a name="noncapturing_group"></a>
## <a name="noncapturing-groups"></a>Grupos sin captura  
 La construcción de agrupamiento siguiente no captura la subcadena con la que coincide una subexpresión:  
  
`(?:subexpression)`
  
 donde *subexpresión* es cualquier patrón de expresión regular válido. La construcción de grupo sin captura se utiliza normalmente cuando un cuantificador se aplica a un grupo, pero las subcadenas capturadas por el grupo no tienen ningún interés.  
  
> [!NOTE]
> Si una expresión regular incluye construcciones de agrupamiento anidadas, no se aplica una construcción de grupo sin captura exterior a las construcciones de grupo anidadas interiores.  
  
 En el ejemplo siguiente se muestra una expresión regular que incluye grupos sin captura. Observe que la salida no incluye ningún grupo capturado.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/noncapture1.cs#5)]
 [!code-vb[RegularExpressions.Language.Grouping#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/noncapture1.vb#5)]  
  
 La expresión regular `(?:\b(?:\w+)\W*)+\.` coincide con una frase que termina en un punto. Dado que la expresión regular se centra en frases y no en palabras individuales, las construcciones de agrupamiento se usan exclusivamente como cuantificadores. El patrón de la expresión regular se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`(?:\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. No asigna el texto coincidente a un grupo capturado.|  
|`\W*`|Coincide con cero o más caracteres que no se usan para formar palabras.|  
|`(?:\b(?:\w+)\W*)+`|Coincide una o varias veces con el patrón de uno o varios caracteres que se usan para formar palabras comenzando por un límite de palabras, seguido de cero o más caracteres que no se usan para formar palabras. No asigna el texto coincidente a un grupo capturado.|  
|`\.`|Coincide con un punto.|  
  
<a name="group_options"></a>
## <a name="group-options"></a>Opciones de grupo  
 La siguiente construcción de agrupamiento aplica o deshabilita las opciones especificadas dentro de una subexpresión:  
  
 `(?imnsx-imnsx:` *subexpresión* `)`  
  
 donde *subexpresión* es cualquier patrón de expresión regular válido. Por ejemplo, `(?i-s:)` activa la opción que no hace distinción entre mayúsculas y minúsculas y deshabilita el modo de una sola línea. Para obtener más información sobre las opciones insertadas que puede especificar, vea [Opciones de expresiones regulares](../../../docs/standard/base-types/regular-expression-options.md).  
  
> [!NOTE]
> Puede especificar opciones que se apliquen a una expresión regular completa en lugar de a una subexpresión usando un constructor de la clase <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> o un método estático. También puede especificar opciones insertadas que se aplican después de un punto concreto en una expresión regular usando la construcción de lenguaje `(?imnsx-imnsx)` .  
  
 La construcción de opciones de grupo no es un grupo de captura. Es decir, aunque cualquier parte de una cadena capturada por *subexpresión* se incluye en la coincidencia, no se incluye en un grupo capturado ni se usa para rellenar el objeto <xref:System.Text.RegularExpressions.GroupCollection> .  
  
 Por ejemplo, la expresión regular `\b(?ix: d \w+)\s` del ejemplo siguiente utiliza opciones insertadas en una construcción de agrupamiento para habilitar la coincidencia sin distinción entre mayúsculas y minúsculas y omitir el espacio en blanco del patrón para identificar todas las palabras que comienzan por la letra "d". La expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`(?ix: d \w+)`|Usando una coincidencia sin distinción entre mayúsculas y minúsculas y omitiendo los espacios en blanco en este patrón, busca una "d" seguida de uno o varios caracteres que se usan para formar palabras.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
  
 [!code-csharp[Conceptual.Regex.Language.Options#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.options/cs/example1.cs#8)]
 [!code-vb[Conceptual.Regex.Language.Options#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.options/vb/example1.vb#8)]  
  
<a name="zerowidth_positive_lookahead_assertion"></a>
## <a name="zero-width-positive-lookahead-assertions"></a>Aserciones de búsqueda anticipada positiva de ancho cero  
 La construcción de agrupamiento siguiente define una aserción de búsqueda anticipada positiva de ancho cero:  
  
 `(?=` *subexpresión* `)`  
  
 donde *subexpresión* es cualquier patrón de expresión regular. Para que se produzca una coincidencia, la cadena de entrada debe coincidir con el patrón de expresión regular de *subexpresión*, aunque la subcadena coincidente no se incluya en el resultado de la coincidencia. Una aserción de búsqueda anticipada positiva de ancho cero no retrocede.  
  
 Normalmente, una aserción de búsqueda anticipada positiva de ancho cero se encuentra al final de un patrón de expresión regular. Define una subcadena que se debe encontrar al final de una cadena para que se produzca una coincidencia, pero que no debe incluirse en la coincidencia. También resulta útil para evitar un retroceso excesivo. Puede usar una aserción de búsqueda anticipada positiva de ancho cero para asegurarse de que un grupo capturado determinado comienza por un texto que coincide con un subconjunto del patrón definido para dicho grupo capturado. Por ejemplo, si un grupo de captura coincide con caracteres consecutivos que se usan para formar palabras, puede usar una aserción de búsqueda anticipada positiva de ancho cero para requerir que el primero de los caracteres sea alfabético y esté en mayúsculas.  
  
 En el ejemplo siguiente se usa una aserción de búsqueda anticipada positiva de ancho cero para buscar la palabra que precede al verbo "is" en la cadena de entrada.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#6](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/lookahead1.cs#6)]
 [!code-vb[RegularExpressions.Language.Grouping#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/lookahead1.vb#6)]  
  
 La expresión regular `\b\w+(?=\sis\b)` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|  
|`(?=\sis\b)`|Determina si los caracteres que se usan para formar palabras van seguidos de un carácter de espacio en blanco y la cadena "is", seguida de un límite de palabras. En ese caso, la coincidencia es correcta.|  
  
<a name="zerowidth_negative_lookahead_assertion"></a>
## <a name="zero-width-negative-lookahead-assertions"></a>Aserciones de búsqueda anticipada negativa de ancho cero  
 La construcción de agrupamiento siguiente define una aserción de búsqueda anticipada negativa de ancho cero:  
  
 `(?!` *subexpresión* `)`  
  
 donde *subexpresión* es cualquier patrón de expresión regular. Para que se produzca la coincidencia, la cadena de entrada no debe coincidir con el patrón de expresión regular de *subexpresión*, aunque la cadena coincidente no se incluya en el resultado de la coincidencia.  
  
 Una aserción de búsqueda anticipada negativa de ancho cero se utiliza normalmente al principio o al final de una expresión regular. Al principio de una expresión regular, puede definir un patrón concreto que no se debería buscar cuando el principio de la expresión regular define un patrón similar pero más general que se desea buscar. En este caso, se usa a menudo para limitar el retroceso. Al final de una expresión regular, puede definir una subexpresión que no se puede producir al final de una coincidencia.  
  
 En el ejemplo siguiente se define una expresión regular que utiliza una aserción de búsqueda anticipada negativa de ancho cero al principio de la expresión regular para buscar palabras que no comienzan por "un".  
  
 [!code-csharp[RegularExpressions.Language.Grouping#7](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/negativelookahead1.cs#7)]
 [!code-vb[RegularExpressions.Language.Grouping#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/negativelookahead1.vb#7)]  
  
 La expresión regular `\b(?!un)\w+\b` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`(?!un)`|Determina si los dos caracteres siguientes son "un". Si no lo son, es posible una coincidencia.|  
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
 En el ejemplo siguiente se define una expresión regular que utiliza una aserción de búsqueda anticipada negativa de ancho cero al final de la expresión regular para buscar palabras que no terminan por un carácter de puntuación.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#8](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/negativelookahead2.cs#8)]
 [!code-vb[RegularExpressions.Language.Grouping#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/negativelookahead2.vb#8)]  
  
 La expresión regular `\b\w+\b(?!\p{P})` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
|`\p{P})`|Si el carácter siguiente no es un signo de puntuación (como un punto o una coma), la coincidencia se realiza.|  
  
<a name="zerowidth_positive_lookbehind_assertion"></a>
## <a name="zero-width-positive-lookbehind-assertions"></a>Aserciones de búsqueda tardía positiva de ancho cero  
 La construcción de agrupamiento siguiente define una aserción de búsqueda tardía positiva de ancho cero:  
  
 `(?<=` *subexpresión* `)`  
  
 donde *subexpresión* es cualquier patrón de expresión regular. Para que se produzca una coincidencia, *subexpresión* debe encontrarse en la cadena de entrada a la izquierda de la posición actual, aunque `subexpression` no esté incluida en el resultado de la coincidencia. Una aserción de búsqueda tardía positiva de ancho cero no retrocede.  
  
 Las aserciones de búsqueda tardía positiva de ancho cero se usan normalmente al principio de las expresiones regulares. El patrón que definen es una condición previa de una coincidencia, aunque no forma parte del resultado de la coincidencia.  
  
 Por ejemplo, el ejemplo siguiente coincide con los dos últimos dígitos del año para el siglo XXI (es decir, requiere que los dígitos "20" precedan a la cadena coincidente).  
  
 [!code-csharp[RegularExpressions.Language.Grouping#9](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/lookbehind1.cs#9)]
 [!code-vb[RegularExpressions.Language.Grouping#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/lookbehind1.vb#9)]  
  
 El patrón de la expresión regular `(?<=\b20)\d{2}\b` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\d{2}`|Coincide con dos dígitos decimales.|  
|`(?<=\b20)`|Continúa la búsqueda si los dos dígitos decimales van precedidos de los dos dígitos decimales "20" en un límite de palabra.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
 Las aserciones de búsqueda tardía positiva de ancho cero también se usan para limitar el retroceso cuando el último carácter o caracteres de un grupo capturado debe ser un subconjunto de los caracteres que coincide con el patrón de la expresión regular de dicho grupo. Por ejemplo, si un grupo captura todos los caracteres que se usan para formar palabras consecutivos, puede usar una aserción de búsqueda tardía positiva de ancho cero para requerir que el último carácter sea alfabético.  
  
<a name="zerowidth_negative_lookbehind_assertion"></a>
## <a name="zero-width-negative-lookbehind-assertions"></a>Aserciones de búsqueda tardía negativa de ancho cero  
 La construcción de agrupamiento siguiente define una aserción de búsqueda tardía negativa de ancho cero:  
  
 `(?<!` *subexpresión* `)`  
  
 donde *subexpresión* es cualquier patrón de expresión regular. Para que se produzca una coincidencia, *subexpresión* no debe encontrarse en la cadena de entrada a la izquierda de la posición actual. Sin embargo, cualquier subcadena que no coincida con `subexpression` no se incluye en el resultado de la coincidencia.  
  
 Las aserciones de búsqueda tardía negativa de ancho cero se usan normalmente al principio de las expresiones regulares. El patrón que definen impide una coincidencia en la cadena que sigue. También se usan para limitar el retroceso cuando el último carácter o caracteres de un grupo capturado no debe ser uno o varios de los caracteres que coinciden con el patrón de expresión regular de dicho grupo. Por ejemplo, si un grupo captura todos los caracteres que se usan para formar palabras consecutivos, se puede usar una aserción de búsqueda tardía positiva de ancho cero para requerir que el último carácter no sea de subrayado (\_).  
  
 El ejemplo siguiente busca la fecha de cualquier día de la semana que no sea fin de semana (es decir, que no sea ni sábado ni domingo).  
  
 [!code-csharp[RegularExpressions.Language.Grouping#10](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/negativelookbehind1.cs#10)]
 [!code-vb[RegularExpressions.Language.Grouping#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/negativelookbehind1.vb#10)]  
  
 El patrón de la expresión regular `(?<!(Saturday|Sunday) )\b\w+ \d{1,2}, \d{4}\b` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`\w+`|Coincide con uno o varios caracteres que se usan para formar palabras seguidos de un carácter de espacio en blanco.|  
|`\d{1,2},`|Coincide con uno o dos dígitos decimales seguidos de un carácter de espacio en blanco y una coma.|  
|`\d{4}\b`|Coincide con cuatro dígitos decimales seguidos de un límite de palabras.|  
|<code>(?<!(Saturday&#124;Sunday) )</code>|Si la coincidencia va precedida por algo distinto de las cadenas "Saturday" o "Sunday" seguidas de un espacio, la coincidencia es correcta.|  
  
<a name="atomic_groups"></a>
## <a name="atomic-groups"></a>Grupos atómicos  
 La construcción de agrupamiento siguiente representa un grupo atómico (conocido en otros motores de expresiones regulares como subexpresión sin retroceso, subexpresión atómica o subexpresión de una sola vez):
  
 `(?>` *subexpresión* `)`  
  
 donde *subexpresión* es cualquier patrón de expresión regular.  
  
 Comúnmente, si una expresión regular incluye un patrón de coincidencia opcional o alternativo y no se produce una coincidencia, el motor de expresiones regulares puede crear una bifurcación en varias direcciones para buscar coincidencias de una cadena de entrada con un patrón. Si no se encuentra una coincidencia cuando toma la primera bifurcación, el motor de expresiones regulares puede regresar o retroceder al punto donde tomó la primera bifurcación e intentar la coincidencia usando la segunda bifurcación. Este proceso puede continuar hasta que se hayan probado todas las bifurcaciones.  
  
 El grupo `(?>`*subexpresión*`)` deshabilita el retroceso. El motor de expresiones regulares buscará coincidencias con tantos caracteres de la cadena de entrada como pueda. Cuando ya no sean posibles más coincidencias, no retrocederá para intentar coincidencias con patrones alternativos. (Es decir, la subexpresión solo busca cadenas que coincidan exclusivamente con la subexpresión; no intenta buscar una cadena basándose en la subexpresión y en cualquier subexpresión que la siga).  
  
 Se recomienda usar esta opción si se sabe que el retroceso no tendrá éxito. Si se evita que el motor de expresiones regulares realice búsquedas innecesarias, se mejora el rendimiento.  
  
 En el ejemplo siguiente se muestra cómo un grupo atómico modifica los resultados de una coincidencia de patrones. La expresión regular con retroceso coincide correctamente con una serie de caracteres repetidos seguidos de una o varias apariciones del mismo carácter en un límite de palabras, pero la expresión regular sin retroceso no lo hace.  
  
 [!code-csharp[RegularExpressions.Language.Grouping#11](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/nonbacktracking1.cs#11)]
 [!code-vb[RegularExpressions.Language.Grouping#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/nonbacktracking1.vb#11)]  
  
 La expresión regular sin retroceso `(?>(\w)\1+).\b` se define como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`(\w)`|Coincide con un único carácter que se usa para formar palabras y se lo asigna al primer grupo de captura.|  
|`\1+`|Coincide con el valor de la primera subcadena capturada una o varias veces.|  
|`.`|Coincide con cualquier carácter.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
|`(?>(\w)\1+)`|Coincide con una o varias apariciones de un carácter que se usa para formar palabras duplicado, pero no retrocede para buscar el último carácter de un límite de palabras.|  
  
<a name="Objects"></a>
## <a name="grouping-constructs-and-regular-expression-objects"></a>Construcciones de agrupamiento y objetos de las expresiones regulares  
 Las subcadenas con las que coincide un grupo de captura de una expresión regular se representan mediante objetos <xref:System.Text.RegularExpressions.Group?displayProperty=nameWithType> , que se pueden recuperar del objeto <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> que devuelve la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> . El objeto <xref:System.Text.RegularExpressions.GroupCollection> se rellena como sigue:  
  
- El primer objeto <xref:System.Text.RegularExpressions.Group> de la colección (el objeto con el índice cero) representa la coincidencia completa.  
  
- El siguiente conjunto de objetos <xref:System.Text.RegularExpressions.Group> representa los grupos de captura sin nombre (numerados). Aparecen en el orden en el que se definen en la expresión regular, de izquierda a derecha. Los valores de índice de estos grupos van de 1 al número de grupos de captura sin nombre de la colección. (El índice de un grupo determinado es equivalente a su referencia inversa numerada. Para más información sobre las referencias inversas, vea [Backreference Constructs](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md)).  
  
- El conjunto final de objetos <xref:System.Text.RegularExpressions.Group> representa los grupos de captura con nombre. Aparecen en el orden en el que se definen en la expresión regular, de izquierda a derecha. El valor de índice del primer grupo de captura con nombre es una unidad mayor que el índice del último grupo de captura sin nombre. Si no hay ningún grupo de captura sin nombre en la expresión regular, el valor de índice del primer grupo de captura con nombre es uno.  
  
 Si se aplica un cuantificador a un grupo de captura, las propiedades <xref:System.Text.RegularExpressions.Group> , <xref:System.Text.RegularExpressions.Capture.Value%2A?displayProperty=nameWithType>e <xref:System.Text.RegularExpressions.Capture.Index%2A?displayProperty=nameWithType>del objeto <xref:System.Text.RegularExpressions.Capture.Length%2A?displayProperty=nameWithType> correspondiente reflejarán la última subcadena capturada por un grupo de captura. Se puede recuperar un conjunto completo de subcadenas capturadas por grupos que tienen cuantificadores desde el objeto <xref:System.Text.RegularExpressions.CaptureCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> .  
  
 El ejemplo siguiente aclara la relación entre los objetos <xref:System.Text.RegularExpressions.Group> y <xref:System.Text.RegularExpressions.Capture> .  
  
 [!code-csharp[RegularExpressions.Language.Grouping#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.grouping/cs/objectmodel1.cs#4)]
 [!code-vb[RegularExpressions.Language.Grouping#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.grouping/vb/objectmodel1.vb#4)]  
  
 El patrón de expresión regular `(\b(\w+)\W+)+` extrae palabras individuales de una cadena. Se define como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`(\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Juntos, estos caracteres forman una palabra. Este es el segundo grupo de captura.|  
|`\W+`|Coincide con uno o varios caracteres que no se usan para formar palabras.|  
|`(\b(\w+)\W+)`|Coincide una o varias veces con el patrón de uno o varios caracteres que se usan para formar palabras seguidos de uno o varios caracteres que no se usan para formar palabras. Este es el primer grupo de captura.|  
  
 El segundo grupo de captura coincide con cada palabra de la frase. El primer grupo de captura coincide con cada palabra, junto con la puntuación y el espacio en blanco que siguen a la palabra. El objeto <xref:System.Text.RegularExpressions.Group> cuyo índice es 2 proporciona información sobre el texto coincidente con el segundo grupo de captura. El conjunto de palabras completo capturado por el grupo de captura está disponible desde el objeto <xref:System.Text.RegularExpressions.CaptureCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> .  
  
## <a name="see-also"></a>Vea también

- [Lenguaje de expresiones regulares: referencia rápida](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [Retroceso](../../../docs/standard/base-types/backtracking-in-regular-expressions.md)
