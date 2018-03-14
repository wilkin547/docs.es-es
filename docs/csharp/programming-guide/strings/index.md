---
title: "Cadenas (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, strings
- strings [C#]
ms.assetid: 21580405-cb25-4541-89d5-037846a38b07
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 24b3db01047a9f9a47182e0e1ac105f69562c316
ms.sourcegitcommit: d95a91d685565f4d95c8773b558752864a6a3d7e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2018
---
# <a name="strings-c-programming-guide"></a>Cadenas (Guía de programación de C#)
Una cadena es un objeto de tipo <xref:System.String> cuyo valor es texto. Internamente, el texto se almacena como una colección secuencial de solo lectura de objetos <xref:System.Char>. No hay ningún carácter que finaliza en null al final de una cadena de C#; por lo tanto, la cadena de C# puede contener cualquier número de caracteres nulos insertados ('\0'). La propiedad <xref:System.String.Length%2A> de una cadena representa el número de objetos `Char` que contiene, no el número de caracteres Unicode. Para obtener acceso a los puntos de código Unicode individuales de una cadena, use el objeto <xref:System.Globalization.StringInfo>.  
  
## <a name="string-vs-systemstring"></a>cadena frente System.String  
 En C#, la palabra clave `string` es un alias de <xref:System.String>. Por lo tanto, `String` y `string` son equivalentes y se puede utilizar la convención de nomenclatura que prefiera. La clase `String` proporciona muchos métodos para crear, manipular y comparar cadenas de forma segura. Además, el lenguaje C# sobrecarga algunos operadores para simplificar las operaciones de cadena comunes. Para más información sobre la palabra clave, consulte [string](../../../csharp/language-reference/keywords/string.md). Para obtener más información sobre el tipo y sus métodos, vea <xref:System.String>.  
  
## <a name="declaring-and-initializing-strings"></a>Declaración e inicialización de cadenas  
 Puede declarar e inicializar cadenas de varias maneras, tal como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStrings#1](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_1.cs)]  
  
 Tenga en cuenta que no se usa el operador [new](../../../csharp/language-reference/keywords/new-operator.md) para crear un objeto de cadena, salvo cuando se inicialice la cadena con una matriz de caracteres.  
  
 Inicialice una cadena con el valor constante <xref:System.String.Empty> para crear un objeto <xref:System.String> cuya cadena tenga longitud cero. La representación literal de la cadena de una cadena de longitud cero es "". Mediante la inicialización de las cadenas con el valor <xref:System.String.Empty> en lugar de [null](../../../csharp/language-reference/keywords/null.md), puede reducir las posibilidades de que se produzca una excepción <xref:System.NullReferenceException>. Use el método estático <xref:System.String.IsNullOrEmpty%28System.String%29> para comprobar el valor de una cadena antes de intentar obtener acceso a ella.  
  
## <a name="immutability-of-string-objects"></a>Inmutabilidad de los objetos de cadena  
 Los objetos de cadena son *inmutables*: no se pueden cambiar después de haberse creado. Todos los métodos <xref:System.String> y operadores de C# que parecen modificar una cadena en realidad devuelven los resultados en un nuevo objeto de cadena. En el siguiente ejemplo, cuando el contenido de `s1` y `s2` se concatena para formar una sola cadena, las dos cadenas originales no se modifican. El operador `+=` crea una nueva cadena que contiene el contenido combinado. Este nuevo objeto se asigna a la variable `s1` y el objeto original que se asignó a `s1` se libera para la recolección de elementos no utilizados porque ninguna otra variable contiene una referencia a él.  
  
 [!code-csharp[csProgGuideStrings#2](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_2.cs)]  
  
 Dado que una "modificación" de cadena es en realidad una creación de cadena, debe tener cuidado al crear referencias a las cadenas. Si crea una referencia a una cadena y después "modifica" la cadena original, la referencia seguirá apuntando al objeto original en lugar de al objeto nuevo creado al modificarse la cadena. El código siguiente muestra este comportamiento:  
  
 [!code-csharp[csProgGuideStrings#25](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_3.cs)]  
  
 Para más información acerca de cómo crear cadenas nuevas basadas en modificaciones como las operaciones de buscar y reemplazar en la cadena original, consulte [Cómo: Modificar el contenido de cadenas](../../how-to/modify-string-contents.md).  
  
## <a name="regular-and-verbatim-string-literals"></a>Literales de cadena regulares y textuales  
 Utilice literales de cadena regulares cuando tenga que insertar caracteres de escape proporcionados por C#, tal como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStrings#3](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_4.cs)]  
  
 Utilice cadenas textuales para mayor comodidad y mejor legibilidad cuando el texto de la cadena contenga caracteres de barra diagonal inversa, por ejemplo, en rutas de acceso de archivo. Como las cadenas textuales conservan los caracteres de nueva línea como parte del texto de la cadena, pueden utilizarse para inicializar cadenas multilíneas. Utilice comillas dobles para insertar una comilla simple dentro de una cadena textual. En el ejemplo siguiente se muestran algunos usos habituales de las cadenas textuales:  
  
 [!code-csharp[csProgGuideStrings#4](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_5.cs)]  
  
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
|\U|Secuencia de escape Unicode para pares suplentes.|\Unnnnnnnn|  
|\u|Secuencia de escape Unicode|\u0041 = "A"|  
|\v|Tabulación vertical|0x000B|  
|\x|Secuencia de escape Unicode similar a "\u" excepto con longitud variable.|\x0041 = "A"|  
  
> [!NOTE]
>  En tiempo de compilación, las cadenas textuales se convierten en cadenas normales con las mismas secuencias de escape. Por lo tanto, si se muestra una cadena textual en la ventana Inspección del depurador, verá los caracteres de escape agregados por el compilador, no la versión textual del código fuente. Por ejemplo, la cadena textual @"C:\files.txt" aparecerá en la ventana Inspección, como "C:\\\files.txt".  
  
## <a name="format-strings"></a>Cadenas de formato  
 Una cadena de formato es una cadena cuyo contenido puede determinarse de manera dinámica en tiempo de ejecución. Puede crear una cadena de formato mediante el método estático <xref:System.String.Format%2A> e insertar los marcadores de posición entre llaves que se reemplazarán por otros valores en tiempo de ejecución. En el ejemplo siguiente se utiliza una cadena de formato para generar el resultado de cada iteración de un bucle:  
  
 [!code-csharp[csProgGuideStrings#26](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_6.cs)]  
  
 Una sobrecarga del método <xref:System.Console.WriteLine%2A> toma una cadena de formato como un parámetro. Por lo tanto, solo se puede insertar un literal de cadena de formato sin una llamada explícita al método. Pero si usa el método <xref:System.Diagnostics.Trace.WriteLine%2A> para mostrar la salida de la depuración en la ventana **Salida** de Visual Studio, debe llamar explícitamente al método <xref:System.String.Format%2A> porque <xref:System.Diagnostics.Trace.WriteLine%2A> solo acepta una cadena, no una cadena de formato. Para más información sobre las cadenas de formato, consulte [Formatting Types](../../../standard/base-types/formatting-types.md) (Tipos de formato).  
  
## <a name="substrings"></a>Subcadenas  
 Una subcadena es cualquier secuencia de caracteres que se encuentra en una cadena. Use el método <xref:System.String.Substring%2A> para crear una nueva cadena de una parte de la cadena original. Puede buscar una o más apariciones de una subcadena con el método <xref:System.String.IndexOf%2A>. Use el método <xref:System.String.Replace%2A> para reemplazar todas las apariciones de una subcadena especificada por una nueva cadena. Al igual que el método <xref:System.String.Substring%2A>, <xref:System.String.Replace%2A> devuelve una cadena nueva y no modifica la cadena original. Para más información, consulte [Cómo: Buscar cadenas](../../how-to/search-strings.md) y [Cómo: Modificar el contenido de cadenas](../../how-to/modify-string-contents.md).  
  
 [!code-csharp[csProgGuideStrings#7](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_7.cs)]  
  
## <a name="accessing-individual-characters"></a>Acceso a caracteres individuales  
 Puede utilizar la notación de matriz con un valor de índice para adquirir acceso de solo lectura a caracteres individuales, como en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideStrings#9](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_8.cs)]  
  
 Si el método <xref:System.String> no proporciona la funcionalidad que debe tener para modificar los caracteres individuales de una cadena, puede usar un objeto <xref:System.Text.StringBuilder> para modificar los caracteres individuales "en contexto" y, después, crear una cadena para almacenar los resultados mediante el método <xref:System.Text.StringBuilder>. En el ejemplo siguiente, se supone que debe modificar la cadena original de una manera determinada y, después, almacenar los resultados para un uso futuro:  
  
 [!code-csharp[csProgGuideStrings#8](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_9.cs)]  
  
## <a name="null-strings-and-empty-strings"></a>Cadenas nulas y cadenas vacías  
 Una cadena vacía es una instancia de un objeto <xref:System.String?displayProperty=nameWithType> que contiene cero caracteres. Las cadenas vacías se utilizan a menudo en distintos escenarios de programación para representar un campo de texto en blanco. Puede llamar a métodos en cadenas vacías porque son objetos <xref:System.String?displayProperty=nameWithType> válidos. Las cadenas vacías se inicializan como sigue:  
  
```  
string s = String.Empty;  
```  
  
 En cambio, una cadena nula no hace referencia a una instancia de un objeto <xref:System.String?displayProperty=nameWithType> y cualquier intento de llamar a un método en una cadena nula produce una excepción <xref:System.NullReferenceException>. Sin embargo, puede utilizar cadenas nulas en operaciones de comparación y concatenación con otras cadenas. Los ejemplos siguientes muestran algunos casos en que una referencia a una cadena nula provoca y no provoca una excepción:  
  
 [!code-csharp[csProgGuideStrings#27](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_10.cs)]  
  
## <a name="using-stringbuilder-for-fast-string-creation"></a>Uso de StringBuilder para la creación rápida de cadenas  
 Las operaciones de cadena en .NET están muy optimizadas y en la mayoría de los casos no afectan significativamente al rendimiento. Sin embargo, en algunos escenarios, como los bucles de pequeñas dimensiones que se ejecutan cientos o miles de veces, las operaciones de cadena pueden afectar al rendimiento. La clase <xref:System.Text.StringBuilder> crea un búfer de cadena que proporciona un mejor rendimiento si el programa realiza muchas manipulaciones de cadenas. La cadena <xref:System.Text.StringBuilder> también permite reasignar caracteres individuales, algo que el tipo de datos de cadena integrado no admite. Por ejemplo, este código cambia el contenido de una cadena sin crear una nueva:  
  
 [!code-csharp[csProgGuideStrings#20](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_11.cs)]  
  
 En este ejemplo, se usa un objeto <xref:System.Text.StringBuilder> para crear una cadena a partir de un conjunto de tipos numéricos:  
  
 [!code-csharp[csProgGuideStrings#15](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_12.cs)]  
  
## <a name="strings-extension-methods-and-linq"></a>Cadenas, métodos de extensión y LINQ  
 Dado que el tipo <xref:System.String> implementa <xref:System.Collections.Generic.IEnumerable%601>, puede usar los métodos de extensión definidos en la clase <xref:System.Linq.Enumerable> en cadenas. Para evitar el desorden visual, estos métodos se excluyen de IntelliSense para el tipo <xref:System.String>, pero aun así están disponibles. También puede utilizar expresiones de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] en cadenas. Para más información, consulte [LINQ and Strings](../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) (LINQ y cadenas).  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Tema|Description|  
|-----------|-----------------|  
|[Cómo: Modificar el contenido de cadenas](../../how-to/modify-string-contents.md)|Muestra técnicas para transformar cadenas y modificar el contenido de estas.|  
|[Cómo: Concatenar varias cadenas](../../../csharp/programming-guide/strings/how-to-concatenate-multiple-strings.md)|Muestra técnicas para combinar varias cadenas en una sola durante el tiempo de compilación y el tiempo de ejecución.|  
|[Cómo: Comparar cadenas](../../../csharp/programming-guide/strings/how-to-compare-strings.md)|Muestra cómo realizar comparaciones ordinales de las cadenas.|  
|[Cómo: Analizar cadenas mediante String.Split](../../how-to/parse-strings-using-split.md)|Contiene un ejemplo de código que muestra cómo utilizar el método `String.Split` para analizar cadenas.|  
|[Cómo: Buscar cadenas](../../how-to/search-strings.md)|Explica cómo usar la búsqueda para especificar texto o patrones en cadenas.|  
|[Cómo: Determinar si una cadena representa un valor numérico](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)|Muestra cómo analizar de forma segura una cadena para ver si tiene un valor numérico válido.|  
|[Cómo: Convertir una cadena en un valor DateTime](../../../csharp/programming-guide/strings/how-to-convert-a-string-to-a-datetime.md)|Muestra cómo convertir una cadena como "24/01/2008" en un objeto <xref:System.DateTime?displayProperty=nameWithType>.|  
|[Operaciones básicas de cadenas](../../../../docs/standard/base-types/basic-string-operations.md)|Proporciona vínculos a temas que usan los métodos <xref:System.String?displayProperty=nameWithType> y <xref:System.Text.StringBuilder?displayProperty=nameWithType> para realizar operaciones básicas de cadenas.|  
|[Analizar cadenas](../../../../docs/standard/base-types/parsing-strings.md)|Describe cómo insertar caracteres o espacios vacíos en una cadena.|  
|[Comparar cadenas](../../../../docs/standard/base-types/comparing.md)|Incluye información sobre cómo comparar cadenas y proporciona ejemplos de C# y Visual Basic.|  
|[Utilizar la clase StringBuilder](../../../standard/base-types/stringbuilder.md)|Describe cómo crear y modificar objetos de cadena dinámicos con la clase <xref:System.Text.StringBuilder>.|  
|[LINQ y cadenas](../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)|Proporciona información sobre cómo realizar varias operaciones de cadena utilizando consultas LINQ.|  
|[Guía de programación de C#](../../../csharp/programming-guide/index.md)|Proporciona vínculos a temas que explican las construcciones de programación en C#.|  
