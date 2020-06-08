---
title: El modelo de objetos de expresión regular
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- searching with regular expressions, backreferences
- Regex class
- Match class
- pattern-matching with regular expressions, backreferences
- .NET Framework regular expressions, classes
- CaptureCollection class
- Group class
- characters [.NET Framework], backreferences
- substrings
- .NET Framework regular expressions, backreferences
- searching with regular expressions, classes
- backreferences
- Capture class
- repeating groups of characters
- MatchCollection class
- parsing text with regular expressions, backreferences
- regular expressions [.NET Framework]
- characters [.NET Framework], regular expressions
- classes [.NET Framework], regular expression
- regular expressions [.NET Framework], classes
- characters [.NET Framework], metacharacters
- metacharacters, regular expression classes
- metacharacters, backreferences
- parsing text with regular expressions, classes
- regular expressions [.NET Framework], backreferences
- strings [.NET Framework], regular expressions
- pattern-matching with regular expressions, classes
- GroupCollection class
ms.assetid: 49a21470-64ca-4b5a-a889-8e24e3c0af7e
ms.openlocfilehash: ad7957fd555c1de8fe47c092d3eb399a803fb1fb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290907"
---
# <a name="the-regular-expression-object-model"></a>El modelo de objetos de expresión regular
<a name="introduction"></a> En este tema se describe el modelo de objetos usado para trabajar con expresiones regulares de .NET. Contiene las siguientes secciones:  
  
- [Motor de expresiones regulares](#Engine)  
  
- [Objetos MatchCollection y Match](#Match_and_MCollection)  
  
- [Colección de grupos](#GroupCollection)  
  
- [Grupo capturado](#the_captured_group)  
  
- [Colección de capturas](#CaptureCollection)  
  
- [Captura individual](#the_individual_capture)  
  
<a name="Engine"></a>
## <a name="the-regular-expression-engine"></a>El motor de expresiones regulares  
 La clase <xref:System.Text.RegularExpressions.Regex> representa el motor de expresiones regulares de .NET. El motor de expresiones regulares es responsable de analizar y compilar una expresión regular y de realizar operaciones en las que coinciden el patrón de expresión regular con una cadena de entrada. El motor es el componente central del modelo de objetos de expresión regular de .NET.  
  
 Puede utilizar el motor de expresiones regulares en una de estas dos formas:  
  
- Creando métodos estáticos de la clase <xref:System.Text.RegularExpressions.Regex>. Los parámetros de método incluyen la cadena de entrada y el patrón de expresión regular. El motor de expresiones regulares almacena en memoria caché las expresiones regulares que se utilizan en llamadas de métodos estáticos, por lo que las llamadas repetidas a métodos de expresiones regulares estáticos que usan la misma expresión regular ofrecen un rendimiento relativamente bueno.  
  
- Creando instancias de un objeto <xref:System.Text.RegularExpressions.Regex>, al pasar una expresión regular al constructor de clase. En este caso, el objeto <xref:System.Text.RegularExpressions.Regex> es inmutable (de solo lectura) y representa un motor de expresiones regulares estrechamente acoplado a una expresión regular única. Dado que las expresiones regulares utilizadas por instancias <xref:System.Text.RegularExpressions.Regex> no están almacenadas en memoria caché, no debe crear varias veces instancias de un objeto <xref:System.Text.RegularExpressions.Regex> con la misma expresión regular.  
  
 Puede llamar a los métodos de la clase <xref:System.Text.RegularExpressions.Regex> para realizar las operaciones siguientes:  
  
- Determinar si una cadena coincide con un patrón de expresión regular.  
  
- Extraer una coincidencia única o la primera coincidencia.  
  
- Extraer todas las coincidencias.  
  
- Reemplazar una subcadena coincidente.  
  
- Dividir una cadena única en una matriz de cadenas.  
  
 Estas operaciones se describen en las siguientes secciones.  
  
### <a name="matching-a-regular-expression-pattern"></a>Buscar coincidencias con un patrón de expresión regular  
 Este método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> devuelve `true` si la cadena coincide con el patrón o `false` en caso contrario. El método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> se utiliza a menudo para validar una entrada de cadena. Por ejemplo, el siguiente código garantiza que una cadena coincide con un número válido de la seguridad social en los Estados Unidos.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/validate1.cs#1)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/validate1.vb#1)]  
  
 El patrón de la expresión regular `^\d{3}-\d{2}-\d{4}$` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`^`|Buscar coincidencias con el principio de la cadena de entrada.|  
|`\d{3}`|Coincide con tres dígitos decimales.|  
|`-`|Buscar coincidencias con un guion.|  
|`\d{2}`|Coincide con dos dígitos decimales.|  
|`-`|Buscar coincidencias con un guion.|  
|`\d{4}`|Buscar coincidencias con cuatro dígitos decimales.|  
|`$`|Coincide con el final de la cadena de entrada.|  
  
### <a name="extracting-a-single-match-or-the-first-match"></a>Extraer una coincidencia única o la primera coincidencia.  
 El método <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Text.RegularExpressions.Match> que contiene información sobre la primera subcadena que coincida con un patrón de expresión regular. Si la propiedad `Match.Success` devuelve `true`, lo que indica que se encontró una coincidencia, puede recuperar información sobre las coincidencias subsiguientes llamando al método <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>. Estas llamadas a métodos pueden seguir hasta que la propiedad `Match.Success` devuelva `false`. Por ejemplo, el código siguiente utiliza el método <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%29?displayProperty=nameWithType> para buscar la primera aparición de una palabra duplicada en una cadena. A continuación, llama al método <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> para encontrar cualquier aparición adicional. El ejemplo examina la propiedad `Match.Success` después de cada llamada al método para determinar si la coincidencia actual ha sido correcta y si debe seguir una llamada al método <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match1.cs#2)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match1.vb#2)]  
  
 El patrón de la expresión regular `\b(\w+)\W+(\1)\b` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Comienza la búsqueda de coincidencias en un límite de palabras.|  
|`(\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.|  
|`\W+`|Coincide con uno o varios caracteres que no se usan para formar palabras.|  
|`(\1)`|Buscar coincidencias con la primera cadena capturada. Este es el segundo grupo de captura.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
### <a name="extracting-all-matches"></a>Extraer todas las coincidencias  
 El método <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Text.RegularExpressions.MatchCollection> que contiene información sobre todas las coincidencias que el motor de expresiones regulares encontró en la cadena de entrada. Por ejemplo, se podría escribir de nuevo el ejemplo anterior para que llamara al método <xref:System.Text.RegularExpressions.Regex.Matches%2A> en lugar de a los métodos <xref:System.Text.RegularExpressions.Regex.Match%2A> y <xref:System.Text.RegularExpressions.Match.NextMatch%2A>.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/matches1.cs#3)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/matches1.vb#3)]  
  
### <a name="replacing-a-matched-substring"></a>Reemplazar una subcadena coincidente  
 El método <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> reemplaza cada subcadena que hace coincidir el patrón de expresión regular con una cadena o patrón de expresión regular especificados, y devuelve la cadena de entrada completa con reemplazos. Por ejemplo, el código siguiente agrega un símbolo de la divisa de EE. UU. antes de un número decimal en una cadena.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/replace1.cs#4)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/replace1.vb#4)]  
  
 El patrón de la expresión regular `\b\d+\.\d{2}\b` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`\.`|Coincide con un punto.|  
|`\d{2}`|Coincide con dos dígitos decimales.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
 El patrón de reemplazo `$$$&` se interpreta como se muestra en la siguiente tabla.  
  
|Modelo|Cadena de reemplazo|  
|-------------|------------------------|  
|`$$`|El carácter del signo de dólar ($).|  
|`$&`|La subcadena coincidente completa.|  
  
### <a name="splitting-a-single-string-into-an-array-of-strings"></a>Dividir una cadena única en una matriz de cadenas  
 El método <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> divide la cadena de entrada en las posiciones definidas por una coincidencia de expresión regular. Por ejemplo, el siguiente código coloca los elementos de una lista numerada en una matriz de cadena.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/split1.cs#5)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/split1.vb#5)]  
  
 El patrón de la expresión regular `\b\d{1,2}\.\s` se interpreta como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`\d{1,2}`|Buscar coincidencias con uno o dos dígitos decimales.|  
|`\.`|Coincide con un punto.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
  
<a name="Match_and_MCollection"></a>
## <a name="the-matchcollection-and-match-objects"></a>Objetos MatchCollection y Match  
 Los métodos Regex devuelven dos objetos que forman parte del modelo de objetos de expresión regular: el objeto <xref:System.Text.RegularExpressions.MatchCollection> y el objeto <xref:System.Text.RegularExpressions.Match>.  
  
<a name="the_match_collection"></a>
### <a name="the-match-collection"></a>La colección de coincidencias  
 El método <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Text.RegularExpressions.MatchCollection> que contiene objetos <xref:System.Text.RegularExpressions.Match> que representan todas las coincidencias que encontró el motor de expresiones regulares, en el orden en el que aparecen en la cadena de entrada. Si no hay ninguna coincidencia, el método devuelve un objeto <xref:System.Text.RegularExpressions.MatchCollection> sin miembros. La propiedad <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType> proporciona acceso a miembros individuales de la colección por índice, desde cero hasta uno menos que el valor de la propiedad <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType>. <xref:System.Text.RegularExpressions.MatchCollection.Item%2A> es el indizador de la colección (en C#) y la propiedad predeterminada (en Visual Basic).  
  
 De forma predeterminada, la llamada al método <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> utiliza la evaluación diferida para rellenar el objeto <xref:System.Text.RegularExpressions.MatchCollection>. El acceso a propiedades que requieren una colección totalmente rellenada, como las propiedades <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType> y <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType>, puede implicar una reducción del rendimiento. En consecuencia, recomendamos tener acceso a la colección utilizando el objeto <xref:System.Collections.IEnumerator> devuelto por el método <xref:System.Text.RegularExpressions.MatchCollection.GetEnumerator%2A?displayProperty=nameWithType>. Los lenguajes individuales proporcionan construcciones, como `For Each` en Visual Basic y `foreach` en C#, que ajustan la interfaz <xref:System.Collections.IEnumerator> de la colección.  
  
 En el siguiente ejemplo se utiliza el método <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%29?displayProperty=nameWithType> para rellenar un objeto <xref:System.Text.RegularExpressions.MatchCollection> con todas las coincidencias encontradas en una cadena de entrada. El ejemplo enumera la colección, copia las coincidencias en una matriz de cadena y registra las posiciones de caracteres en una matriz entera.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/matchcollection1.cs#6)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/matchcollection1.vb#6)]  
  
<a name="the_match"></a>
### <a name="the-match"></a>La coincidencia  
 La clase <xref:System.Text.RegularExpressions.Match> representa el resultado de una coincidencia de expresión regular única. Puede tener acceso a los objetos <xref:System.Text.RegularExpressions.Match> de dos formas:  
  
- Recuperándolos del objeto <xref:System.Text.RegularExpressions.MatchCollection> devuelto por el método <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>. Para recuperar objetos <xref:System.Text.RegularExpressions.Match> individuales, itere la colección utilizando una construcción `foreach` (en C#) o `For Each`...`Next` (en Visual Basic) o use la propiedad <xref:System.Text.RegularExpressions.MatchCollection.Item%2A?displayProperty=nameWithType> para recuperar un determinado objeto <xref:System.Text.RegularExpressions.Match> por índice o por nombre. También puede recuperar objetos <xref:System.Text.RegularExpressions.Match> individuales de la colección iterando la colección por índice, desde cero a uno menos que el número de objetos de la colección. Sin embargo, este método no saca partido de la evaluación diferida, porque tiene acceso a la propiedad <xref:System.Text.RegularExpressions.MatchCollection.Count%2A?displayProperty=nameWithType>.  
  
     En el siguiente ejemplo se recuperan objetos <xref:System.Text.RegularExpressions.Match> individuales de un objeto <xref:System.Text.RegularExpressions.MatchCollection> iterando la colección mediante la construcción `foreach` o `For Each`...`Next`. La expresión regular simplemente coincide con la cadena "abc" de la cadena de entrada.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match2.cs#7)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match2.vb#7)]  
  
- Llamando al método <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType>, que devuelve un objeto <xref:System.Text.RegularExpressions.Match> que representa la primera coincidencia en una cadena o una parte de una cadena. Puede determinar si la coincidencia se ha encontrado recuperando el valor de la propiedad `Match.Success`. Para recuperar objetos <xref:System.Text.RegularExpressions.Match> que representan las coincidencias subsiguientes, llame repetidamente al método <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType>, hasta que la propiedad `Success` del objeto <xref:System.Text.RegularExpressions.Match> devuelto sea `false`.  
  
     En el siguiente ejemplo se utilizan los métodos <xref:System.Text.RegularExpressions.Regex.Match%28System.String%2CSystem.String%29?displayProperty=nameWithType> y <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> para buscar coincidencias con la cadena "abc" en la cadena de entrada.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/match3.cs#8)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/match3.vb#8)]  
  
 Dos propiedades de la clase <xref:System.Text.RegularExpressions.Match> devuelven objetos de colección:  
  
- La propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Text.RegularExpressions.GroupCollection> que contiene información sobre las subcadenas que coinciden con grupos de captura en el patrón de expresión regular.  
  
- La propiedad `Match.Captures` devuelve un objeto <xref:System.Text.RegularExpressions.CaptureCollection> que es de uso limitado. La colección no se rellena para un objeto <xref:System.Text.RegularExpressions.Match> cuya propiedad `Success` es `false`. De lo contrario, contiene un único objeto <xref:System.Text.RegularExpressions.Capture> que tiene la misma información que el objeto <xref:System.Text.RegularExpressions.Match>.  
  
 Para obtener más información sobre estos objetos, vea las secciones [Colección de grupos](#GroupCollection) y [Colección de capturas](#CaptureCollection) más adelante en este tema.  
  
 Dos propiedades adicionales de la clase <xref:System.Text.RegularExpressions.Match> proporcionan información sobre la coincidencia. La propiedad `Match.Value` devuelve la subcadena en la cadena de entrada que coincide con el patrón de expresión regular. La propiedad `Match.Index` devuelve la posición inicial basada en cero de la cadena coincidente en la cadena de entrada.  
  
 La clase <xref:System.Text.RegularExpressions.Match> también tiene dos métodos de coincidencia de patrones:  
  
- El método <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> encuentra la coincidencia según la coincidencia representada por el objeto <xref:System.Text.RegularExpressions.Match> actual y devuelve un objeto <xref:System.Text.RegularExpressions.Match> que representa esa coincidencia.  
  
- El método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> realiza una operación de reemplazo especificada en la cadena coincidente y devuelve el resultado.  
  
 En el siguiente ejemplo se utiliza el método <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> para anteponer un símbolo $ y un espacio antes de cada número que incluye dos dígitos fraccionarios.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/result1.cs#9)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/result1.vb#9)]  
  
 El patrón de expresión regular `\b\d+(,\d{3})*\.\d{2}\b` se define como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`\d+`|Buscar coincidencias con uno o más dígitos decimales.|  
|`(,\d{3})*`|Buscar coincidencias con cero o más apariciones de una coma seguida de tres dígitos decimales.|  
|`\.`|Buscar coincidencias con el carácter de separador decimal.|  
|`\d{2}`|Coincide con dos dígitos decimales.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
 El patrón de reemplazo `$$ $&` indica que la subcadena debe ser reemplazada por un símbolo de signo de dólar ($) (el patrón `$$`), un espacio y el valor de la coincidencia (el patrón `$&`).  
  
 [Volver al principio](#introduction)  
  
<a name="GroupCollection"></a>
## <a name="the-group-collection"></a>La colección de grupos  
 La propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Text.RegularExpressions.GroupCollection> que contiene objetos <xref:System.Text.RegularExpressions.Group> que representan los grupos capturados en una coincidencia única. El primer objeto <xref:System.Text.RegularExpressions.Group> de la colección (en el índice 0) representa la coincidencia completa. Cada objeto que sigue representa los resultados de un grupo de captura único.  
  
 Puede recuperar objetos <xref:System.Text.RegularExpressions.Group> individuales en la colección utilizando la propiedad <xref:System.Text.RegularExpressions.GroupCollection.Item%2A?displayProperty=nameWithType>. Puede recuperar los grupos sin nombre por su posición ordinal en la colección y recuperar grupos con nombre por nombre o por posición ordinal. Las capturas sin nombre aparecen primero en la colección y se indizan de izquierda a derecha en el orden en el que aparecen en el patrón de expresión regular. Las capturas con nombre se indizan después de las capturas sin nombre, de izquierda a derecha en el orden en el que aparecen en el patrón de expresión regular. Para determinar qué grupos numerados están disponibles en la colección devuelta para un determinado método de coincidencia de expresión regular, puede llamar al método <xref:System.Text.RegularExpressions.Regex.GetGroupNumbers%2A?displayProperty=nameWithType> de instancia. Para determinar qué grupos con nombre están disponibles en la colección, puede llamar al método <xref:System.Text.RegularExpressions.Regex.GetGroupNames%2A?displayProperty=nameWithType> de instancia. Ambos métodos son especialmente útiles en rutinas de uso general que analizan las coincidencias encontradas por cualquier expresión regular.  
  
 La propiedad <xref:System.Text.RegularExpressions.GroupCollection.Item%2A?displayProperty=nameWithType> es el indizador de la colección en C# y la propiedad predeterminada del objeto de la colección en Visual Basic. Esto significa que se puede tener acceso a los objetos <xref:System.Text.RegularExpressions.Group> individuales por índice (o por nombre, en el caso de grupos con nombre) del modo siguiente:  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/groupsyntax1.cs#13)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/groupsyntax1.vb#13)]  
  
 En el siguiente ejemplo se define una expresión regular que usa construcciones de agrupación para capturar el mes, día y año de una fecha.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/groupcollection1.cs#10)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/groupcollection1.vb#10)]  
  
 El patrón de expresión regular `\b(\w+)\s(\d{1,2}),\s(\d{4})\b` se define como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\b`|Iniciar la búsqueda de coincidencias en un límite de palabras.|  
|`(\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. Este es el primer grupo de captura.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`(\d{1,2})`|Buscar coincidencias con uno o dos dígitos decimales. Este es el segundo grupo de captura.|  
|`,`|Coincide con una coma.|  
|`\s`|Coincide con un carácter de espacio en blanco.|  
|`(\d{4})`|Buscar coincidencias con cuatro dígitos decimales. Éste es el tercer grupo de captura.|  
|`\b`|Finalizar la búsqueda de coincidencias en un límite de palabras.|  
  
 [Volver al principio](#introduction)  
  
<a name="the_captured_group"></a>
## <a name="the-captured-group"></a>El grupo capturado  
 La clase <xref:System.Text.RegularExpressions.Group> representa el resultado de un único grupo de captura. La propiedad <xref:System.Text.RegularExpressions.GroupCollection.Item%2A> del objeto <xref:System.Text.RegularExpressions.GroupCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType> devuelve objetos de grupo que representan grupos de captura definidos en una expresión regular. La propiedad <xref:System.Text.RegularExpressions.GroupCollection.Item%2A> es el indizador (en C#) y la propiedad predeterminada (en Visual Basic) de la clase <xref:System.Text.RegularExpressions.Group>. También puede recuperar miembros individuales mediante la iteración de la colección con la construcción `foreach` o `For Each`. Para obtener un ejemplo, vea la sección anterior.  
  
 En el siguiente ejemplo se utilizan construcciones de agrupación anidadas para capturar subcadenas en grupos. El patrón de expresión regular `(a(b))c` coincide con la cadena "abc". Asigna la subcadena "ab" al primer grupo de captura y la subcadena "b" al segundo grupo de captura.  
  
 [!code-csharp[RegularExpressions.Classes#6](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#6)]
 [!code-vb[RegularExpressions.Classes#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#6)]  
  
 En el siguiente ejemplo se utilizan construcciones de agrupación con nombre para capturar subcadenas de una cadena que contiene datos en el formato "NOMBREDATOS:VALOR" que la expresión regular divide por el signo de dos puntos (:).  
  
 [!code-csharp[RegularExpressions.Classes#8](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#8)]
 [!code-vb[RegularExpressions.Classes#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#8)]  
  
 El patrón de expresión regular `^(?<name>\w+):(?<value>\w+)` se define como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`^`|Iniciar la búsqueda de coincidencias con el principio de la cadena de entrada.|  
|`(?<name>\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. El nombre de este grupo de captura es `name`.|  
|`:`|Buscar coincidencia con un signo de dos puntos.|  
|`(?<value>\w+)`|Buscar coincidencias con uno o más caracteres alfabéticos. El nombre de este grupo de captura es `value`.|  
  
 Las propiedades de la clase <xref:System.Text.RegularExpressions.Group> proporcionan información sobre el grupo capturado: la propiedad `Group.Value` contiene la subcadena capturada, la propiedad `Group.Index` indica la posición inicial del grupo capturado en el texto de entrada, la propiedad `Group.Length` contiene la longitud del texto capturado y la propiedad `Group.Success` indica si una subcadena coincidió con el patrón definido por el grupo de captura.  
  
 Al aplicar cuantificadores a un grupo (para obtener más información, consulte [Cuantificadores](quantifiers-in-regular-expressions.md)), se modifica la relación de una captura por grupo de captura de dos maneras:  
  
- Si el cuantificador `*` o `*?` (qué especifica cero o más coincidencias) se aplica a un grupo, es posible que un grupo de captura no tenga una coincidencia en la cadena de entrada. Cuando no haya texto capturado, las propiedades del objeto <xref:System.Text.RegularExpressions.Group> se establecen como se muestran en la siguiente tabla.  
  
    |Propiedades de grupo|Valor|  
    |--------------------|-----------|  
    |`Success`|`false`|  
    |`Value`|<xref:System.String.Empty?displayProperty=nameWithType>|  
    |`Length`|0|  
  
     Esto se muestra en el ejemplo siguiente. En el patrón de expresión regular `aaa(bbb)*ccc`, se pueden buscar coincidencias para el primer grupo de captura (la subcadena "bbb") cero o varias veces. Dado que la cadena de entrada "aaaccc" coincide con el patrón, el grupo de captura no tiene una coincidencia.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/nocapture1.cs#11)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/nocapture1.vb#11)]  
  
- Los cuantificadores pueden coincidir con varias apariciones de un patrón definido por un grupo de captura. En este caso, las propiedades `Value` y `Length` de un objeto <xref:System.Text.RegularExpressions.Group> solo contienen información sobre la última subcadena capturada. Por ejemplo, la siguiente coincidencia de expresión regular coincide con una frase única que finaliza con un punto. Utiliza dos construcciones de agrupación: el primero captura palabras individuales junto con un carácter de espacio en blanco; el segundo captura palabras individuales. Como lo muestra el resultado del ejemplo, aunque la expresión regular logre capturar una frase completa, el segundo grupo de captura solo captura la última palabra.  
  
     [!code-csharp[Conceptual.RegularExpressions.ObjectModel#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/lastcapture1.cs#12)]
     [!code-vb[Conceptual.RegularExpressions.ObjectModel#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/lastcapture1.vb#12)]  
  
 [Volver al principio](#introduction)  
  
<a name="CaptureCollection"></a>
## <a name="the-capture-collection"></a>La colección de capturas  
 El objeto <xref:System.Text.RegularExpressions.Group> solo contiene información sobre la última captura. Sin embargo, el conjunto completo de capturas realizado por un grupo de captura sigue aún disponible en el objeto <xref:System.Text.RegularExpressions.CaptureCollection> devuelto por la propiedad <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>. Cada miembro de la colección es un objeto <xref:System.Text.RegularExpressions.Capture> que representa una captura realizada por este grupo de captura, en el orden en el que se capturaron (y, por consiguiente, en el orden en el que las cadenas capturadas coincidían de izquierda a derecha en la cadena de entrada). Puede recuperar objetos <xref:System.Text.RegularExpressions.Capture> individuales de la colección de estas dos formas:  
  
- Mediante la iteración de la colección con el uso de una construcción como `foreach` (en C#) o `For Each` (en Visual Basic).  
  
- Utilizando la propiedad <xref:System.Text.RegularExpressions.CaptureCollection.Item%2A?displayProperty=nameWithType> para recuperar un objeto específico por índice. La propiedad <xref:System.Text.RegularExpressions.CaptureCollection.Item%2A> es la propiedad predeterminada del objeto <xref:System.Text.RegularExpressions.CaptureCollection> (en Visual Basic) o el indizador (en C#).  
  
 Si no se aplica un cuantificador a un grupo de captura, el objeto <xref:System.Text.RegularExpressions.CaptureCollection> contiene un objeto <xref:System.Text.RegularExpressions.Capture> único que es de escaso interés, porque proporciona información sobre la misma coincidencia que su objeto <xref:System.Text.RegularExpressions.Group>. Si se aplica un cuantificador a un grupo de captura, el objeto <xref:System.Text.RegularExpressions.CaptureCollection> contiene todas las capturas realizadas por el grupo de captura y el último miembro de la colección representa la misma captura que el objeto <xref:System.Text.RegularExpressions.Group>.  
  
 Si utiliza, por ejemplo, el patrón de expresión regular `((a(b))c)+` (donde el cuantificador + indica una o varias coincidencias) para capturar coincidencias de la cadena "abcabcabc", el objeto <xref:System.Text.RegularExpressions.CaptureCollection> para cada objeto <xref:System.Text.RegularExpressions.Group> contiene tres miembros.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/capturecollection1.cs#14)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/capturecollection1.vb#14)]  
  
 En el siguiente ejemplo se utiliza la expresión regular `(Abc)+` para buscar una o más ejecuciones consecutivas de la cadena "Abc" en la cadena "XYZAbcAbcAbcXYZAbcAb". El ejemplo ilustra la forma en que se utiliza la propiedad <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> para que devuelva varios grupos de subcadenas capturadas.  
  
 [!code-csharp[RegularExpressions.Classes#5](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Classes/cs/Example.cs#5)]
 [!code-vb[RegularExpressions.Classes#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Classes/vb/Example.vb#5)]  
  
 [Volver al principio](#introduction)  
  
<a name="the_individual_capture"></a>
## <a name="the-individual-capture"></a>La captura individual  
 La clase <xref:System.Text.RegularExpressions.Capture> contiene el resultado de una única captura de subexpresiones. La propiedad <xref:System.Text.RegularExpressions.Capture.Value%2A?displayProperty=nameWithType> contiene el texto coincidente y la propiedad <xref:System.Text.RegularExpressions.Capture.Index%2A?displayProperty=nameWithType> indica la posición basada en cero en la cadena de entrada en la que la comienza la subcadena coincidente.  
  
 En el siguiente ejemplo se analiza una cadena de entrada para la temperatura de las ciudades seleccionadas. Se utiliza una coma (",") para separar una ciudad y su temperatura, y un punto y coma (";"), para separar los datos de cada ciudad. La cadena de entrada completa representa una coincidencia única. En el patrón de expresión regular `((\w+(\s\w+)*),(\d+);)+`, que se utiliza para analizar la cadena, se asigna el nombre de la ciudad al segundo grupo de captura y la temperatura al cuarto grupo de captura.  
  
 [!code-csharp[Conceptual.RegularExpressions.ObjectModel#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/cs/capture1.cs#16)]
 [!code-vb[Conceptual.RegularExpressions.ObjectModel#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regularexpressions.objectmodel/vb/capture1.vb#16)]  
  
 La expresión regular se define como se muestra en la tabla siguiente.  
  
|Modelo|Description|  
|-------------|-----------------|  
|`\w+`|Buscar coincidencias con uno o más caracteres alfabéticos.|  
|`(\s\w+)*`|Coincide con cero o más apariciones de un carácter de espacio en blanco seguido de uno o varios caracteres que se usan para formar palabras. Este patrón busca coincidencias con nombres de ciudades de múltiples palabras. Éste es el tercer grupo de captura.|  
|`(\w+(\s\w+)*)`|Coincide con uno o varios caracteres que se usan para formar palabras seguidos de cero o más apariciones de un carácter de espacio en blanco seguidos de uno o varios caracteres que se usan para formar palabras. Este es el segundo grupo de captura.|  
|`,`|Coincide con una coma.|  
|`(\d+)`|Buscar coincidencias con uno o más dígitos. Este es el cuarto grupo de captura.|  
|`;`|Buscar coincidencias con un signo de punto y coma.|  
|`((\w+(\s\w+)*),(\d+);)+`|Buscar coincidencias con el patrón de una palabra seguido de cualquier palabra adicional seguida de una coma, uno o más dígitos y un punto y coma, una o más veces. Este es el primer grupo de captura.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Text.RegularExpressions>
- [Expresiones regulares de .NET](regular-expressions.md)
- [Lenguaje de expresiones regulares: referencia rápida](regular-expression-language-quick-reference.md)
