---
title: 'Cadenas: Guía de programación de C#'
ms.date: 06/27/2019
helpviewer_keywords:
- C# language, strings
- strings [C#]
ms.assetid: 21580405-cb25-4541-89d5-037846a38b07
ms.openlocfilehash: 7bf5cba51a2e72d3a648f795f018220a452e51f5
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226600"
---
# <a name="strings-c-programming-guide"></a>Cadenas (Guía de programación de C#)
Una cadena es un objeto de tipo <xref:System.String> cuyo valor es texto. Internamente, el texto se almacena como una colección secuencial de solo lectura de objetos <xref:System.Char>. No hay ningún carácter que finaliza en null al final de una cadena de C#; por lo tanto, la cadena de C# puede contener cualquier número de caracteres nulos insertados ('\0'). La propiedad <xref:System.String.Length%2A> de una cadena representa el número de objetos `Char` que contiene, no el número de caracteres Unicode. Para obtener acceso a los puntos de código Unicode individuales de una cadena, use el objeto <xref:System.Globalization.StringInfo>.  
  
## <a name="string-vs-systemstring"></a>cadena frente System.String  
 En C#, la palabra clave `string` es un alias de <xref:System.String>. Por lo tanto, `String` y `string` son equivalentes y se puede utilizar la convención de nomenclatura que prefiera. La clase `String` proporciona muchos métodos para crear, manipular y comparar cadenas de forma segura. Además, el lenguaje C# sobrecarga algunos operadores para simplificar las operaciones de cadena comunes. Para más información sobre la palabra clave, consulte [string](../../language-reference/builtin-types/reference-types.md). Para obtener más información sobre el tipo y sus métodos, vea <xref:System.String>.  
  
## <a name="declaring-and-initializing-strings"></a>Declaración e inicialización de cadenas  
 Puede declarar e inicializar cadenas de varias maneras, tal como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStrings#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#1)]  
  
 Tenga en cuenta que no se usa el operador [new](../../language-reference/operators/new-operator.md) para crear un objeto de cadena, salvo cuando se inicialice la cadena con una matriz de caracteres.  
  
 Inicialice una cadena con el valor constante <xref:System.String.Empty> para crear un objeto <xref:System.String> cuya cadena tenga longitud cero. La representación literal de la cadena de una cadena de longitud cero es "". Mediante la inicialización de las cadenas con el valor <xref:System.String.Empty> en lugar de [null](../../language-reference/keywords/null.md), puede reducir las posibilidades de que se produzca una excepción <xref:System.NullReferenceException>. Use el método estático <xref:System.String.IsNullOrEmpty%28System.String%29> para comprobar el valor de una cadena antes de intentar obtener acceso a ella.  
  
## <a name="immutability-of-string-objects"></a>Inmutabilidad de los objetos de cadena  
 Los objetos de cadena son *inmutables*: no se pueden cambiar después de haberse creado. Todos los métodos <xref:System.String> y operadores de C# que parecen modificar una cadena en realidad devuelven los resultados en un nuevo objeto de cadena. En el siguiente ejemplo, cuando el contenido de `s1` y `s2` se concatena para formar una sola cadena, las dos cadenas originales no se modifican. El operador `+=` crea una nueva cadena que contiene el contenido combinado. Este nuevo objeto se asigna a la variable `s1` y el objeto original que se asignó a `s1` se libera para la recolección de elementos no utilizados porque ninguna otra variable contiene una referencia a él.  
  
 [!code-csharp[csProgGuideStrings#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#2)]  
  
 Dado que una "modificación" de cadena es en realidad una creación de cadena, debe tener cuidado al crear referencias a las cadenas. Si crea una referencia a una cadena y después "modifica" la cadena original, la referencia seguirá apuntando al objeto original en lugar de al objeto nuevo creado al modificarse la cadena. El código siguiente muestra este comportamiento:  
  
 [!code-csharp[csProgGuideStrings#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#25)]  
  
 Para más información acerca de cómo crear cadenas nuevas basadas en modificaciones como las operaciones de buscar y reemplazar en la cadena original, consulte [Modificación del contenido de cadenas](../../how-to/modify-string-contents.md).  
  
## <a name="regular-and-verbatim-string-literals"></a>Literales de cadena regulares y textuales  
 Utilice literales de cadena regulares cuando tenga que insertar caracteres de escape proporcionados por C#, tal como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStrings#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#3)]  
  
 Utilice cadenas textuales para mayor comodidad y mejor legibilidad cuando el texto de la cadena contenga caracteres de barra diagonal inversa, por ejemplo, en rutas de acceso de archivo. Como las cadenas textuales conservan los caracteres de nueva línea como parte del texto de la cadena, pueden utilizarse para inicializar cadenas multilíneas. Utilice comillas dobles para insertar una comilla simple dentro de una cadena textual. En el ejemplo siguiente se muestran algunos usos habituales de las cadenas textuales:  
  
 [!code-csharp[csProgGuideStrings#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#4)]  
  
## <a name="string-escape-sequences"></a>Secuencias de escape de cadena  
  
|Secuencia de escape|Nombre de carácter|Codificación Unicode|  
|---------------------|--------------------|----------------------|  
|\\'|Comilla simple|0x0027|  
|\\"|Comilla doble|0x0022|  
|\\\\ |Barra diagonal inversa|0x005C|  
|\0|Null|0x0000|  
|\a|Alerta|0x0007|  
|\b|Retroceso|0x0008|  
|\f|Avance de página|0x000C|  
|\n|Nueva línea|0x000A|  
|\r|Retorno de carro|0x000D|  
|\t|Tabulación horizontal|0x0009|  
|\v|Tabulación vertical|0x000B|  
|\u|Secuencia de escape Unicode (UTF-16)|`\uHHHH` (intervalo: 0000 - FFFF; ejemplo: `\u00E7` = "ç")|  
|\U|Secuencia de escape Unicode (UTF-32)|`\U00HHHHHH` (intervalo: 000000 - 10FFFF; ejemplo: `\U0001F47D` = "&#x1F47D;")|  
|\x|Secuencia de escape Unicode similar a "\u" excepto con longitud variable|`\xH[H][H][H]` (intervalo: 0 - FFFF; ejemplo: `\x00E7` o `\x0E7` o `\xE7` = "ç")|  
  
> [!WARNING]
> Cuando se usa la secuencia de escape `\x` y se especifican menos de 4 dígitos hexadecimales, si los caracteres que van inmediatamente después de la secuencia de escape son dígitos hexadecimales válidos (es decir, 0-9, A-f y a-f), se interpretará que forman parte de la secuencia de escape. Por ejemplo, `\xA1` genera "&#161;", que es el punto de código U+00A1. Sin embargo, si el carácter siguiente es "A" o "a", la secuencia de escape se interpretará como `\xA1A` y producirá "&#x0A1A;", que es el punto de código U+0A1A. En casos así, se pueden especificar los 4 dígitos hexadecimales (por ejemplo, `\x00A1`) para evitar posibles errores de interpretación.  
  
> [!NOTE]
> En tiempo de compilación, las cadenas textuales se convierten en cadenas normales con las mismas secuencias de escape. Por lo tanto, si se muestra una cadena textual en la ventana Inspección del depurador, verá los caracteres de escape agregados por el compilador, no la versión textual del código fuente. Por ejemplo, la cadena textual `@"C:\files.txt"` aparecerá en la ventana Inspección, como "C:\\\files.txt".  
  
## <a name="format-strings"></a>Cadenas de formato  
 Una cadena de formato es una cadena cuyo contenido se determina de manera dinámica en tiempo de ejecución. Las cadenas de formato se crean mediante la inserción de *expresiones interpoladas* o marcadores de posición entre llaves dentro de una cadena. Todo lo incluido entre llaves (`{...}`) se resolverá en un valor y se generará como una cadena con formato en tiempo de ejecución. Existen dos métodos para crear cadenas de formato: interpolación de cadenas y formato compuesto.

### <a name="string-interpolation"></a>Interpolación de cadenas
Disponible en C# 6.0 y versiones posteriores, las [*cadenas interpoladas*](../../language-reference/tokens/interpolated.md) se identifican por el carácter especial `$` e incluyen expresiones interpoladas entre llaves. Si no está familiarizado con la interpolación de cadenas, consulte el tutorial interactivo [Interpolación de cadenas en C#](../../tutorials/exploration/interpolated-strings.yml) para obtener información general rápidamente.

Use la interpolación de cadenas para mejorar la legibilidad y el mantenimiento del código. Con la interpolación de cadenas se obtienen los mismos resultados que con el método `String.Format`, pero mejora la facilidad de uso y la claridad en línea.

[!code-csharp[csProgGuideFormatStrings](~/samples/snippets/csharp/programming-guide/strings/Strings_1.cs#StringInterpolation)]

### <a name="composite-formatting"></a>Formatos compuestos
<xref:System.String.Format%2A?displayProperty=nameWithType> emplea marcadores de posición entre llaves para crear una cadena de formato. Los resultados de este ejemplo son similares a la salida del método de interpolación de cadenas usado anteriormente.
  
[!code-csharp[csProgGuideFormatStrings](~/samples/snippets/csharp/programming-guide/strings/Strings_1.cs#StringFormat)]

Para más información sobre cómo dar formato a los tipos .NET, consulte [Aplicar formato a tipos en .NET](../../../standard/base-types/formatting-types.md).
  
## <a name="substrings"></a>Subcadenas  
 Una subcadena es cualquier secuencia de caracteres que se encuentra en una cadena. Use el método <xref:System.String.Substring%2A> para crear una nueva cadena de una parte de la cadena original. Puede buscar una o más apariciones de una subcadena con el método <xref:System.String.IndexOf%2A>. Use el método <xref:System.String.Replace%2A> para reemplazar todas las apariciones de una subcadena especificada por una nueva cadena. Al igual que el método <xref:System.String.Substring%2A>, <xref:System.String.Replace%2A> devuelve una cadena nueva y no modifica la cadena original. Para más información, consulte [Cómo: Buscar cadenas](../../how-to/search-strings.md) y [Procedimiento para modificar el contenido de cadenas](../../how-to/modify-string-contents.md).
  
 [!code-csharp[csProgGuideStrings#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#7)]  
  
## <a name="accessing-individual-characters"></a>Acceso a caracteres individuales  
 Puede utilizar la notación de matriz con un valor de índice para adquirir acceso de solo lectura a caracteres individuales, como en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStrings#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#8)]  
  
 Si el método <xref:System.String> no proporciona la funcionalidad que debe tener para modificar los caracteres individuales de una cadena, puede usar un objeto <xref:System.Text.StringBuilder> para modificar los caracteres individuales "en contexto" y, después, crear una cadena para almacenar los resultados mediante el método <xref:System.Text.StringBuilder>. En el ejemplo siguiente, se supone que debe modificar la cadena original de una manera determinada y, después, almacenar los resultados para un uso futuro:  
  
 [!code-csharp[csProgGuideStrings#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#27)]  
  
## <a name="null-strings-and-empty-strings"></a>Cadenas nulas y cadenas vacías  
 Una cadena vacía es una instancia de un objeto <xref:System.String?displayProperty=nameWithType> que contiene cero caracteres. Las cadenas vacías se utilizan a menudo en distintos escenarios de programación para representar un campo de texto en blanco. Puede llamar a métodos en cadenas vacías porque son objetos <xref:System.String?displayProperty=nameWithType> válidos. Las cadenas vacías se inicializan como sigue:  
  
```csharp  
string s = String.Empty;  
```  
  
 En cambio, una cadena nula no hace referencia a una instancia de un objeto <xref:System.String?displayProperty=nameWithType> y cualquier intento de llamar a un método en una cadena nula produce una excepción <xref:System.NullReferenceException>. Sin embargo, puede utilizar cadenas nulas en operaciones de comparación y concatenación con otras cadenas. Los ejemplos siguientes muestran algunos casos en que una referencia a una cadena nula provoca y no provoca una excepción:  
  
 [!code-csharp[csProgGuideStrings#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#20)]  
  
## <a name="using-stringbuilder-for-fast-string-creation"></a>Uso de StringBuilder para la creación rápida de cadenas  
 Las operaciones de cadena en .NET están muy optimizadas y en la mayoría de los casos no afectan significativamente al rendimiento. Sin embargo, en algunos escenarios, como los bucles de pequeñas dimensiones que se ejecutan cientos o miles de veces, las operaciones de cadena pueden afectar al rendimiento. La clase <xref:System.Text.StringBuilder> crea un búfer de cadena que proporciona un mejor rendimiento si el programa realiza muchas manipulaciones de cadenas. La cadena <xref:System.Text.StringBuilder> también permite reasignar caracteres individuales, algo que el tipo de datos de cadena integrado no admite. Por ejemplo, este código cambia el contenido de una cadena sin crear una nueva:  
  
 [!code-csharp[csProgGuideStrings#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#15)]  
  
 En este ejemplo, se usa un objeto <xref:System.Text.StringBuilder> para crear una cadena a partir de un conjunto de tipos numéricos:  
  
 [!code-csharp[TestStringBuilder#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/TestStringBuilder.cs)]
  
## <a name="strings-extension-methods-and-linq"></a>Cadenas, métodos de extensión y LINQ  
 Dado que el tipo <xref:System.String> implementa <xref:System.Collections.Generic.IEnumerable%601>, puede usar los métodos de extensión definidos en la clase <xref:System.Linq.Enumerable> en cadenas. Para evitar el desorden visual, estos métodos se excluyen de IntelliSense para el tipo <xref:System.String>, pero aun así están disponibles. También puede usar expresiones de consulta LINQ en cadenas. Para más información, consulte [LINQ y cadenas](../concepts/linq/linq-and-strings.md).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Procedimiento para modificar el contenido de cadenas](../../how-to/modify-string-contents.md)|Muestra técnicas para transformar cadenas y modificar el contenido de estas.|  
|[Comparación de cadenas](../../how-to/compare-strings.md)|Muestra cómo realizar comparaciones ordinales y culturales específicas de las cadenas.|  
|[Concatenación de varias cadenas](../../how-to/concatenate-multiple-strings.md)|Muestra diferentes maneras de combinar varias cadenas en una.|
|[Análisis de cadenas mediante String.Split](../../how-to/parse-strings-using-split.md)|Contiene ejemplos de código que muestran cómo utilizar el método `String.Split` para analizar cadenas.|  
|[Cómo: Buscar cadenas](../../how-to/search-strings.md)|Explica cómo usar la búsqueda para especificar texto o patrones en cadenas.|  
|[Determinación de si una cadena representa un valor numérico](./how-to-determine-whether-a-string-represents-a-numeric-value.md)|Muestra cómo analizar de forma segura una cadena para ver si tiene un valor numérico válido.|  
|[Interpolación de cadenas](../../language-reference/tokens/interpolated.md)|Describe la característica de interpolación de cadena que proporciona una sintaxis adecuada para dar formato a las cadenas.|
|[Operaciones básicas de cadenas](../../../standard/base-types/basic-string-operations.md)|Proporciona vínculos a temas que usan los métodos <xref:System.String?displayProperty=nameWithType> y <xref:System.Text.StringBuilder?displayProperty=nameWithType> para realizar operaciones básicas de cadenas.|  
|[Analizar cadenas](../../../standard/base-types/parsing-strings.md)|Describe cómo convertir las representaciones de cadena de los tipos base de .NET en las instancias de los tipos correspondientes.|  
|[Analizar cadenas de fecha y hora en .NET](../../../standard/base-types/parsing-datetime.md)|Muestra cómo convertir una cadena como "24/01/2008" en un objeto <xref:System.DateTime?displayProperty=nameWithType>.|  
|[Comparar cadenas](../../../standard/base-types/comparing.md)|Incluye información sobre cómo comparar cadenas y proporciona ejemplos de C# y Visual Basic.|  
|[Utilizar la clase StringBuilder](../../../standard/base-types/stringbuilder.md)|Describe cómo crear y modificar objetos de cadena dinámicos con la clase <xref:System.Text.StringBuilder>.|  
|[LINQ y cadenas](../concepts/linq/linq-and-strings.md)|Proporciona información sobre cómo realizar varias operaciones de cadena utilizando consultas LINQ.|  
|[Guía de programación de C#](../index.md)|Proporciona vínculos a temas que explican las construcciones de programación en C#.|  
