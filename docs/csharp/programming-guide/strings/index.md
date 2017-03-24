---
title: "Cadenas (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, cadenas"
  - "cadenas [C#]"
ms.assetid: 21580405-cb25-4541-89d5-037846a38b07
caps.latest.revision: 41
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 41
---
# Cadenas (Gu&#237;a de programaci&#243;n de C#)
Una cadena es un objeto de tipo <xref:System.String> cuyo valor es texto.  Internamente, el texto se almacena como una colección secuencial de solo lectura de objetos <xref:System.Char>.  Al final de una cadena de C\# no hay un carácter null de terminación; por lo tanto, una cadena de C\# puede contener cualquier número de caracteres null incrustados \('\\0'\).  La propiedad <xref:System.String.Length%2A> de una cadena representa el número de objetos `Char` que contiene, no el número de caracteres Unicode.  Para obtener acceso a los puntos de código Unicode individuales de una cadena, utilice el objeto <xref:System.Globalization.StringInfo>.  
  
## string frente aSystem.String  
 En C\#, la palabra clave `string` es un alias de <xref:System.String>.  Por lo tanto, `String` y `string` son equivalentes y puede utilizar la convención de nomenclatura que prefiera.  La clase `String` proporciona numerosos métodos para crear, manipular y comparar cadenas de forma segura.  Además, el lenguaje C\# sobrecarga algunos operadores para simplificar operaciones comunes de las cadenas.  Para obtener más información sobre la palabra clave, vea [string](../../../csharp/language-reference/keywords/string.md).  Para obtener más información sobre el tipo y sus métodos, vea <xref:System.String>.  
  
## Declarar e inicializar cadenas  
 Puede declarar e inicializar cadenas de varias maneras, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStrings#1](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_1.cs)]  
  
 Tenga en cuenta que el operador [new](../../../csharp/language-reference/keywords/new-operator.md) no se utiliza para crear un objeto de cadena, salvo cuando se inicialice la cadena con una matriz de caracteres.  
  
 Inicialice una cadena con el valor constante <xref:System.String.Empty> para crear un nuevo objeto <xref:System.String> cuya cadena tiene una longitud cero.  La representación literal de cadena de una cadena de longitud cero es "".  Mediante la inicialización de cadenas con el valor <xref:System.String.Empty> en lugar de [null](../../../csharp/language-reference/keywords/null.md), puede reducir las posibilidades de que se produzca una excepción <xref:System.NullReferenceException>.  Utilice el método estático <xref:System.String.IsNullOrEmpty%28System.String%29> para comprobar el valor de una cadena antes de intentar tener acceso a ésta.  
  
## Inmutabilidad de los objetos de cadena  
 Los objetos de cadena son *inmutables*, es decir, no pueden modificarse una vez creados.  Todos los métodos <xref:System.String> y los operadores de C\# que parecen modificar una cadena, en realidad devuelven los resultados en un nuevo objeto de cadena.  En el ejemplo siguiente, cuando el contenido de `s1` y `s2` se concatena para formar una sola cadena, las dos cadenas originales no se modifican.  El operador `+=` crea una nueva cadena que contiene el contenido combinado.  Ese nuevo objeto se asigna a la variable `s1` y el objeto original asignado a `s1` se libera para la recolección de elementos no utilizados, ya que ninguna otra variable contiene una referencia a él.  
  
 [!code-cs[csProgGuideStrings#2](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_2.cs)]  
  
 Dado que "modificar" una cadena consiste en realidad en crear una cadena nueva, debe actuar con precaución al crear referencias a las cadenas.  Si crea una referencia a una cadena y después "modifica" la cadena original, la referencia seguirá señalando al objeto original en lugar de al nuevo objeto que se creó cuando se modificó la cadena.  En el siguiente código se muestra este comportamiento:  
  
 [!code-cs[csProgGuideStrings#25](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_3.cs)]  
  
 Para obtener más información sobre cómo crear cadenas nuevas basadas en modificaciones como operaciones de búsqueda y reemplazo en la cadena original, vea [Cómo: Modificar el contenido de cadenas](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md).  
  
## Literales de cadena regulares y textuales  
 Utilice literales de cadena regulares cuando tenga que incrustar caracteres de escape proporcionados por C\#, como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStrings#3](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_4.cs)]  
  
 Utilice cadenas textuales para mayor comodidad y una mejor legibilidad cuando el texto de la cadena contiene caracteres de barra diagonal inversa, por ejemplo en rutas de acceso de archivo.  Dado que las cadenas textuales conservan los caracteres de nueva línea como parte del texto de la cadena, pueden utilizarse para inicializar cadenas de múltiples líneas.  Utilice las comillas dobles para incrustar comillas en una cadena textual.  En el ejemplo siguiente se muestran algunos usos habituales de las cadenas textuales:  
  
 [!code-cs[csProgGuideStrings#4](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_5.cs)]  
  
## Secuencias de escape de cadena  
  
|Secuencia de escape|Nombre del carácter|Codificación Unicode|  
|-------------------------|-------------------------|--------------------------|  
|\\'|Comilla simple|0x0027|  
|\\"|Comilla doble|0x0022|  
|\\\\|Barra diagonal inversa|0x005C|  
|\\0|Null|0x0000|  
|\\a|Alerta|0x0007|  
|\\b|Retroceso|0x0008|  
|\\f|Avance de página|0x000C|  
|\\n|Nueva línea|0x000A|  
|\\r|Retorno de carro|0x000D|  
|\\t|Tabulación horizontal|0x0009|  
|\\U|Secuencia de escape Unicode para pares suplentes.|\\Unnnnnnnn|  
|\\u|Secuencia de escape Unicode|\\u0041 \= "A"|  
|\\v|Tabulación vertical|0x000B|  
|\\x|Secuencia de escape Unicode similar a "\\u" a excepción de la longitud variable.|\\x0041 \= "A"|  
  
> [!NOTE]
>  En tiempo de compilación, las cadenas textuales se convierten en cadenas normales con las mismas secuencias de escape.  Así, si aparece una cadena textual en la ventana Inspección del depurador, verá los caracteres de escape agregados por el compilador, no la versión literal del código fuente.  Por ejemplo, la cadena textual @"C:\\files.txt" aparecerá como "C:\\\\files.txt" en la ventana Inspección.  
  
## Cadenas de formato  
 Una cadena de formato es una cadena cuyo contenido puede determinarse dinámicamente en tiempo de ejecución.  Para crear una cadena de formato se utiliza el método estático <xref:System.String.Format%2A> y se incrustan marcadores de posición entre llaves que se reemplazarán por otros valores en tiempo de ejecución.  En el ejemplo siguiente se utiliza una cadena de formato para generar el resultado de cada iteración de un bucle:  
  
 [!code-cs[csProgGuideStrings#26](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_6.cs)]  
  
 Una sobrecarga del método <xref:System.Console.WriteLine%2A> toma una cadena de formato como parámetro.  Por lo tanto, puede incrustar simplemente un literal de cadena de formato sin una llamada explícita al método.  Sin embargo, si utiliza el método <xref:System.Diagnostics.Trace.WriteLine%2A> para mostrar el resultado de la depuración en la ventana de **salida** de Visual Studio, tiene que llamar explícitamente al método <xref:System.String.Format%2A> porque <xref:System.Diagnostics.Trace.WriteLine%2A> sólo acepta una cadena, no una cadena de formato.  Para obtener más información sobre las cadenas de formato, vea [Aplicar formato a tipos](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md).  
  
## Subcadenas  
 Una subcadena es una secuencia de caracteres cualquiera incluida en una cadena.  Utilice el método <xref:System.String.Substring%2A> para crear una nueva cadena a partir de un segmento de la cadena original.  Puede buscar una o más apariciones de una subcadena con el método <xref:System.String.IndexOf%2A>.  Utilice el método <xref:System.String.Replace%2A> para reemplazar todas las apariciones de una subcadena especificada por una cadena nueva.  Al igual que el método <xref:System.String.Substring%2A>, <xref:System.String.Replace%2A> devuelve en realidad una cadena nueva y no modifica la cadena original.  Para obtener más información, vea [Cómo: Buscar cadenas mediante los métodos String](../../../csharp/programming-guide/strings/how-to-search-strings-using-string-methods.md) y [Cómo: Modificar el contenido de cadenas](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md).  
  
 [!code-cs[csProgGuideStrings#7](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_7.cs)]  
  
## Tener acceso a los caracteres individuales  
 Puede utilizar la notación de matrices con un valor de índice para obtener acceso de sólo lectura a caracteres individuales, como en el ejemplo siguiente:  
  
 [!code-cs[csProgGuideStrings#9](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_8.cs)]  
  
 Si los métodos <xref:System.String> no proporcionan la funcionalidad necesaria para modificar caracteres individuales en una cadena, puede utilizar un objeto <xref:System.Text.StringBuilder> para modificar los caracteres individuales "en contexto" y crear a continuación una nueva cadena para almacenar los resultados mediante los métodos <xref:System.Text.StringBuilder>.  En el ejemplo siguiente, suponga que debe modificar la cadena original de una forma determinada y almacenar a continuación los resultados para su uso futuro:  
  
 [!code-cs[csProgGuideStrings#8](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_9.cs)]  
  
## Cadenas nulas y cadenas vacías  
 Una cadena vacía es una instancia de un objeto <xref:System.String?displayProperty=fullName> que contiene cero caracteres.  Las cadenas vacías se utilizan habitualmente en distintos escenarios de programación para representar un campo de texto en blanco.  Puede realizar llamadas a métodos en cadenas vacías porque son objetos <xref:System.String?displayProperty=fullName> válidos.  Las cadenas vacías se inicializan tal y como se indica a continuación:  
  
```  
string s = String.Empty;  
```  
  
 Por el contrario, una cadena nula no hace referencia a una instancia de un objeto <xref:System.String?displayProperty=fullName> y cualquier intento de llamar a un método en una cadena nula provoca una excepción <xref:System.NullReferenceException>.  Sin embargo, puede utilizar cadenas nulas en operaciones de concatenación y comparación con otras cadenas.  Los ejemplos siguientes muestran algunos casos en los que se hace referencia a una cadena nula y no se produce una excepción:  
  
 [!code-cs[csProgGuideStrings#27](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_10.cs)]  
  
## Utilizar StringBuilder para crear cadenas de forma rápida  
 Las operaciones de cadena en .NET están muy optimizadas y, en la mayoría de los casos, no tienen un impacto significativo en el rendimiento.  Sin embargo, en algunos escenarios, como en bucles de pequeñas dimensiones que se ejecutan cientos o miles de veces, las operaciones de cadena pueden afectar al rendimiento.  La clase <xref:System.Text.StringBuilder> crea un búfer de cadena que proporciona un mayor rendimiento si el programa realiza muchas manipulaciones de cadenas.  La cadena <xref:System.Text.StringBuilder> también permite reasignar los caracteres individuales, algo que el tipo de datos String integrado no admite.  Por ejemplo, este código cambia el contenido de una cadena sin crear una nueva cadena:  
  
 [!code-cs[csProgGuideStrings#20](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_11.cs)]  
  
 En este ejemplo, se utiliza un objeto <xref:System.Text.StringBuilder> para crear una cadena a partir de un conjunto de tipos numéricos:  
  
 [!code-cs[csProgGuideStrings#15](../../../csharp/programming-guide/strings/codesnippet/CSharp/index_12.cs)]  
  
## Cadenas, métodos de extensión y LINQ  
 Dado que el tipo <xref:System.String> implementa <xref:System.Collections.Generic.IEnumerable%601>, puede utilizar los métodos de extensión definidos en la clase <xref:System.Linq.Enumerable> en las cadenas.  Para evitar el desorden visual, estos métodos se excluyen de IntelliSense para el tipo <xref:System.String>, pero están disponibles de todas formas.  También puede utilizar expresiones de consulta [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] en las cadenas.  Para obtener más información, vea [LINQ and Strings](../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md).  
  
## Temas relacionados  
  
|Tema|Descripción|  
|----------|-----------------|  
|[Cómo: Modificar el contenido de cadenas](../../../csharp/programming-guide/strings/how-to-modify-string-contents.md)|Proporciona un ejemplo de código que muestra cómo modificar el contenido de las cadenas.|  
|[Cómo: Concatenar varias cadenas](../../../csharp/programming-guide/strings/how-to-concatenate-multiple-strings.md)|Muestra cómo utilizar el operador `+` y la clase `Stringbuilder` para combinar cadenas en tiempo de compilación y en tiempo de ejecución.|  
|[Cómo: Comparar cadenas](../../../csharp/programming-guide/strings/how-to-compare-strings.md)|Muestra cómo realizar comparaciones ordinales de las cadenas.|  
|[Cómo: Analizar cadenas mediante String.Split ](../../../csharp/programming-guide/strings/how-to-parse-strings-using-string-split.md)|Contiene un ejemplo de código que muestra cómo utilizar el método `String.Split` para analizar cadenas.|  
|[Cómo: Buscar cadenas mediante los métodos String](../../../csharp/programming-guide/strings/how-to-search-strings-using-string-methods.md)|Explica cómo utilizar métodos específicos para buscar cadenas.|  
|[Cómo: Buscar cadenas mediante expresiones regulares](../../../csharp/programming-guide/strings/how-to-search-strings-using-regular-expressions.md)|Explica cómo utilizar expresiones regulares para buscar cadenas.|  
|[Cómo: Determinar si una cadena representa un valor numérico](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)|Muestra cómo analizar una cadena de forma segura para comprobar si tiene un valor numérico válido.|  
|[Cómo: Convertir una cadena en un valor DateTime](../../../csharp/programming-guide/strings/how-to-convert-a-string-to-a-datetime.md)|Muestra cómo convertir una cadena como "01\/24\/2008" en un objeto <xref:System.DateTime?displayProperty=fullName>.|  
|[Operaciones básicas de cadenas](../Topic/Basic%20String%20Operations%20in%20the%20.NET%20Framework.md)|Proporciona vínculos a temas en los que se utilizan los métodos <xref:System.Text.StringBuilder?displayProperty=fullName> y <xref:System.String?displayProperty=fullName> para realizar operaciones básicas con cadenas.|  
|[Analizar cadenas](../Topic/Parsing%20Strings%20in%20the%20.NET%20Framework.md)|Describe cómo insertar caracteres o espacios vacíos en una cadena.|  
|[Comparar cadenas](../Topic/Comparing%20Strings%20in%20the%20.NET%20Framework.md)|Incluye información sobre cómo comparar cadenas y proporciona ejemplos de C\# y Visual Basic.|  
|[Utilizar la clase StringBuilder](../Topic/Using%20the%20StringBuilder%20Class%20in%20the%20.NET%20Framework.md)|Describe cómo crear y modificar objetos de cadena dinámicos mediante la clase <xref:System.Text.StringBuilder>.|  
|[LINQ and Strings](../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)|Proporciona información sobre cómo realizar varias operaciones de cadenas utilizando consultas LINQ.|  
|[Guía de programación de C\#](../../../csharp/programming-guide/index.md)|Proporciona vínculos a temas que explican construcciones de programación en C\#.|  
  
## Capítulo destacado del libro  
 [Más información sobre variables](http://go.microsoft.com/fwlink/?LinkId=221230) en [Principio Visual c\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)