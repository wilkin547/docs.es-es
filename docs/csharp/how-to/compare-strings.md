---
title: Cómo comparar cadenas - Guía de C#
description: Aprenda a comparar y ordenar valores de cadena, ya sea con caso o sin él, o con orden específico de referencia cultural o sin él.
ms.date: 10/03/2018
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.openlocfilehash: dda3ec8cb6a0131867e6ea3bb0cf7199d86058ff
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73973320"
---
# <a name="how-to-compare-strings-in-c"></a>Cómo comparar cadenas en C\#

Se comparan cadenas para responder a una de estas dos preguntas: "¿Son iguales estas dos cadenas?" o "¿En qué orden deben colocarse estas cadenas al ordenarlas?"

Esas dos preguntas se complican por factores que influyen en las comparaciones de cadenas:

- Puede elegir una comparación ordinal o lingüística.
- Puede elegir si distingue entre mayúsculas y minúsculas.
- Puede elegir comparaciones específicas de referencia cultural.
- Las comparaciones lingüísticas dependen de la plataforma y la referencia cultural.

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Cuando se comparan cadenas, se define un orden entre ellas. Las comparaciones se usan para ordenar una secuencia de cadenas. Una vez que la secuencia está en un orden conocido, es más fácil hacer búsquedas, tanto para el software como para las personas. Otras comparaciones pueden comprobar si las cadenas son iguales. Estas comprobaciones de similitud son parecidas a la igualdad, pero pueden omitirse algunas diferencias, como las diferencias entre mayúsculas y minúsculas.

## <a name="default-ordinal-comparisons"></a>Comparaciones de ordinales predeterminadas

De forma predeterminada, las operaciones más comunes:

- <xref:System.String.CompareTo%2A?displayProperty=nameWithType>
- <xref:System.String.Equals%2A?displayProperty=nameWithType>
- <xref:System.String.op_Equality%2A?displayProperty=nameWithType> y <xref:System.String.op_Inequality%2A?displayProperty=nameWithType>; es decir, los [operadores de igualdad`==` y `!=`](../language-reference/operators/equality-operators.md#string-equality), respectivamente,

realizan una comparación ordinal con distinción entre mayúsculas y minúsculas y, si es necesario, usan la referencia cultural actual. En el siguiente ejemplo se muestra que:

[!code-csharp-interactive[Comparing strings using an ordinal comparison](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#1)]

La comparación de ordinales predeterminada no tiene en cuenta reglas lingüísticas cuando se comparan cadenas. Compara el valor binario de cada objeto <xref:System.Char> en dos cadenas. Como resultado, la comparación de ordinales predeterminada también distingue mayúsculas de minúsculas.

Tenga en cuenta que la prueba de igualdad con <xref:System.String.Equals%2A?displayProperty=nameWithType> y los operadores `==` y `!=` es diferente de la comparación de cadenas que usa los métodos <xref:System.String.CompareTo%2A?displayProperty=nameWithType> y <xref:System.String.Compare(System.String,System.String)?displayProperty=nameWithType)>. Mientras que las pruebas de igualdad realizan una comparación ordinal que distingue mayúsculas de minúsculas, los métodos de comparación realizan una comparación que distingue mayúsculas de minúsculas y entre referencias culturales usando la referencia cultural actual. Puesto que los métodos de comparación predeterminados suelen realizan diferentes tipos de comparaciones, le recomendamos que especifique claramente la intención de su código llamando a una sobrecarga que especifique explícitamente el tipo de comparación que se realizará.

## <a name="case-insensitive-ordinal-comparisons"></a>Comparaciones de ordinales sin distinción entre mayúsculas y minúsculas

El método <xref:System.String.Equals(System.String,System.StringComparison)?displayProperty=nameWithType> le permite especificar un valor <xref:System.StringComparison> de <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType>
para una comparación ordinal sin distinción entre mayúsculas y minúsculas. También hay un método <xref:System.String.Compare(System.String,System.String,System.StringComparison)?displayProperty=nameWithType> estático que realiza una comparación ordinal que distingue mayúsculas de minúsculas. Para usarlo, debe especificar un valor de <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> para el argumento <xref:System.StringComparison>. Se muestran en este código:

[!code-csharp-interactive[Comparing strings ignoring case](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#2)]

Al realizar una comparación ordinal que distingue mayúsculas de minúsculas, estos métodos usarán las convenciones de mayúsculas y minúsculas de la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture).

## <a name="linguistic-comparisons"></a>Comparaciones lingüísticas

También se pueden ordenar cadenas mediante reglas lingüísticas para la referencia cultural actual.
Esto se conoce a veces como "criterio de ordenación por palabras". Cuando se realiza una comparación lingüística, algunos caracteres Unicode no alfanuméricos pueden tener asignados pesos especiales. Por ejemplo, el guion ("-") podría tener asignado un peso muy pequeño, por lo que las cadenas "coop" y "co-op" aparecerían una junto a la otra en una ordenación. Además, algunos caracteres Unicode pueden ser equivalentes a una secuencia de instancias de <xref:System.Char>. En este ejemplo se usa una frase en alemán que significa "Bailan en la calle", en alemán, con "ss" (U+0073 U+0073) en una cadena y "ß" (U+00DF) en otra. Lingüísticamente (en Windows), "ss" es igual que el carácter "ß" en alemán en las referencias culturales "en-US" y "de-DE".

[!code-csharp-interactive[Comparing strings using linguistic rules](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#3)]

Este ejemplo demuestra la naturaleza dependiente del sistema operativo de las comparaciones lingüísticas. El host de la ventana interactiva es un host Linux. Las comparaciones lingüísticas y ordinales producen el mismo resultado. Si se ejecutara este mismo ejemplo en un host de Windows, vería este resultado:

```console
<coop> is less than <co-op> using invariant culture
<coop> is greater than <co-op> using ordinal comparison
<coop> is less than <cop> using invariant culture
<coop> is less than <cop> using ordinal comparison
<co-op> is less than <cop> using invariant culture
<co-op> is less than <cop> using ordinal comparison
```

En Windows, el criterio de ordenación de "cop", "coop" y "co-op" cambia al cambiar de una comparación lingüística a una comparación ordinal. Las dos frases en alemán también se comparan de manera diferente mediante tipos de comparación diferentes.

## <a name="comparisons-using-specific-cultures"></a>Comparaciones con referencias culturales específicas

En esta muestra se almacenan los objetos <xref:System.Globalization.CultureInfo> de las referencias culturales en-US y de-DE.
Las comparaciones se realizan con el objeto <xref:System.Globalization.CultureInfo> para garantizar una comparación específica de la referencia cultural.

La referencia cultural usada afecta a las comparaciones lingüísticas. En este ejemplo se muestra el resultado de comparar las dos frases en alemán usando la referencia cultural "en-US" y la referencia cultural "de-DE":

[!code-csharp-interactive[Comparing strings across cultures](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#4)]

Las comparaciones dependientes de la referencia cultural se usan normalmente para comparar y ordenar cadenas escritas por usuarios con otras cadenas escritas por usuarios. Los caracteres y las convenciones de ordenación de estas cadenas pueden variar según la configuración regional del equipo del usuario. Incluso las cadenas que contienen caracteres idénticos podrían ordenarse de forma diferente en función de la referencia cultural del subproceso actual. Además, pruebe este código de ejemplo localmente en una máquina con Windows y obtendrá estos resultados:

```console
<coop> is less than <co-op> using en-US culture
<coop> is greater than <co-op> using ordinal comparison
<coop> is less than <cop> using en-US culture
<coop> is less than <cop> using ordinal comparison
<co-op> is less than <cop> using en-US culture
<co-op> is less than <cop> using ordinal comparison
```

Las comparaciones lingüísticas dependen de la referencia cultural actual y del sistema operativo. Debe tenerlo en cuenta cuando trabaje con comparaciones de cadenas.

## <a name="linguistic-sorting-and-searching-strings-in-arrays"></a>Ordenación lingüística y búsqueda de cadenas en matrices

En estos ejemplos se muestra cómo ordenar y buscar cadenas en una matriz mediante una comparación lingüística que depende de la referencia cultural actual. Use los métodos <xref:System.Array> estáticos que toman un parámetro <xref:System.StringComparer?displayProperty=nameWithType>.

En este ejemplo se muestra cómo ordenar una matriz de cadenas con la referencia cultural actual:

[!code-csharp-interactive[Sorting an array of strings](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#5)]

Una vez que se ordena la matriz, puede buscar entradas mediante una búsqueda binaria. Una búsqueda binaria empieza en medio de la colección para determinar qué mitad de la colección debe contener la cadena buscada. Cada comparación posterior divide la parte restante de la colección por la mitad.  La matriz se ordena con el elemento <xref:System.StringComparer.CurrentCulture?displayProperty=nameWithType>. La función local `ShowWhere` muestra información sobre dónde se encuentra la cadena. Si no se encuentra la cadena, el valor devuelto indica dónde estaría si se encontrara.

[!code-csharp-interactive[Searching in a sorted array](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#6)]

## <a name="ordinal-sorting-and-searching-in-collections"></a>Ordenación de ordinales y búsqueda en colecciones

Este código usa la clase de colección <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> para almacenar cadenas. Las cadenas se ordenan mediante el método <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>. Este método necesita un delegado que compare y ordene dos cadenas. El método <xref:System.String.CompareTo%2A?displayProperty=nameWithType> proporciona esa función de comparación. Ejecute el ejemplo y observe el orden. Esta operación de ordenación usa una ordenación ordinal con distinción entre mayúsculas y minúsculas. Tendría que usar los métodos estáticos <xref:System.String.Compare%2A?displayProperty=nameWithType> para especificar reglas de comparación distintas.

[!code-csharp-interactive[Sorting a list of strings](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#7)]

Una vez realizada la ordenación, se pueden hacer búsquedas en la lista de cadenas mediante una búsqueda binaria. En este ejemplo se muestra cómo buscar la lista ordenada usando la misma función de comparación. La función local `ShowWhere` muestra dónde está o debería estar el texto buscado:

[!code-csharp-interactive[csProgGuideStrings#11](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#8)]

Asegúrese siempre de usar el mismo tipo de comparación para la ordenación y la búsqueda. Si se usan distintos tipos de comparación para la ordenación y la búsqueda se producen resultados inesperados.

Las clases de colección como <xref:System.Collections.Hashtable?displayProperty=nameWithType>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> y <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> tienen constructores que toman un parámetro <xref:System.StringComparer?displayProperty=nameWithType> cuando el tipo de los elementos o claves es `string`. En general, debe usar estos constructores siempre que sea posible y especificar <xref:System.StringComparer.Ordinal?displayProperty=nameWithType> u <xref:System.StringComparer.OrdinalIgnoreCase?displayProperty=nameWithType>.

## <a name="reference-equality-and-string-interning"></a>Igualdad de referencia e internamiento de cadena

Ninguno de los ejemplos ha usado <xref:System.Object.ReferenceEquals%2A>. Este método determina si dos cadenas son el mismo objeto. Esto puede conducir a resultados incoherentes en comparaciones de cadenas. En este ejemplo se muestra la característica de *internamiento de cadenas* de C#. Cuando un programa declara dos o más variables de cadena idénticas, el compilador lo almacena todo en la misma ubicación. Mediante una llamada al método <xref:System.Object.ReferenceEquals%2A>, puede ver que las dos cadenas realmente hacen referencia al mismo objeto en memoria. Use el método <xref:System.String.Copy%2A?displayProperty=nameWithType> para evitar el internamiento. Después de hacer la copia, las dos cadenas tienen diferentes ubicaciones de almacenamiento, aunque tengan el mismo valor. Ejecute este ejemplo para mostrar que las cadenas `a` y `b` son *internadas*, lo que significa que comparten el mismo almacenamiento. Las cadenas `a` y `c` no lo son.

[!code-csharp-interactive[Demonstrating string interning](../../../samples/snippets/csharp/how-to/strings/CompareStrings.cs#9)]

> [!NOTE]
> Cuando se prueba la igualdad de cadenas, debe usar los métodos que especifican explícitamente el tipo de comparación que va a realizar. El código se vuelve mucho más legible y fácil de mantener. Use sobrecargas de los métodos de las clases <xref:System.String?displayProperty=nameWithType> y <xref:System.Array?displayProperty=nameWithType> que toman un parámetro de enumeración <xref:System.StringComparison>. Especifique qué tipo de comparación se va a realizar. Evite usar los operadores `==` y `!=` cuando pruebe la igualdad. Los métodos de instancia <xref:System.String.CompareTo%2A?displayProperty=nameWithType> siempre realizan una comparación ordinal con distinción entre mayúsculas y minúsculas. Son adecuados principalmente para ordenar alfabéticamente las cadenas.

Puede internalizar una cadena o recuperar una referencia a una cadena internalizada existente llamando al método <xref:System.String.Intern%2A?displayProperty=nameWithType>. Para determinar si una cadena se aplica el método Intern, llame al método <xref:System.String.IsInterned%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- [Cadenas](../programming-guide/strings/index.md)
- [Comparar cadenas](../../standard/base-types/comparing.md)
- [Globalizar y localizar aplicaciones](/visualstudio/ide/globalizing-and-localizing-applications)
