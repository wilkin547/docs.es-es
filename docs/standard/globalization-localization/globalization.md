---
title: Globalización
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- globalization [.NET Framework], about globalization
- global applications, globalization
- international applications [.NET Framework], globalization
- world-ready applications, globalization
- application development [.NET Framework], globalization
- culture, globalization
ms.assetid: 4e919934-6b19-42f2-b770-275a4fae87c9
ms.openlocfilehash: c08f4309d7673d7e7fb1c6bd84307e4323411d9e
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242691"
---
# <a name="globalization"></a>Globalización

La globalización implica diseñar y desarrollar una aplicación de uso internacional que admita interfaces localizadas y datos regionales para usuarios de varias referencias culturales. Antes de comenzar la fase de diseño, debe determinar qué referencias culturales admitirá la aplicación. Aunque una aplicación se dirige a una sola referencia cultural o región de forma predeterminada, puede diseñarla y escribirla de tal forma que se pueda ampliar fácilmente a los usuarios de otras referencias culturales o regiones.

Como desarrolladores, todos tenemos suposiciones sobre interfaces de usuario y datos que están formados por nuestras referencias culturales. Por ejemplo, para un desarrollador angloparlante de Estados Unidos, serializar datos de fecha y hora como una cadena en el formato `MM/dd/yyyy hh:mm:ss` parece perfectamente razonable. En cambio, si se deserializa esa cadena en un sistema de una referencia cultural diferente, es probable que se inicie una excepción <xref:System.FormatException> o que se produzcan datos inexactos. La globalización nos permite identificar esas suposiciones específicas de la referencia cultural y asegurarnos de que no afecten al diseño ni al código de nuestra aplicación.

En este artículo se describen algunos de los problemas más importantes que debe tener en cuenta y los procedimientos recomendados que puede seguir al manipular cadenas, valores de fecha y hora, y valores numéricos en una aplicación globalizada.

## <a name="strings"></a>Cadenas

El control de cadenas y caracteres es un eje central de la globalización, porque cada referencia cultural o región puede usar caracteres y juegos de caracteres diferentes y ordenarlos de forma diferente. En esta sección se proporcionan recomendaciones para el uso de cadenas en aplicaciones globalizadas.

### <a name="use-unicode-internally"></a>Uso interno de Unicode

De forma predeterminada, .NET usa cadenas Unicode. Una cadena Unicode está compuesta por cero, uno o más objetos <xref:System.Char>, cada uno de los cuales representa una unidad de código UTF-16. Hay una representación Unicode para casi todos los caracteres en cada juego de caracteres en uso en todo el mundo.

Muchas aplicaciones y sistemas operativos, incluido el sistema operativo Windows, pueden usar también páginas de códigos para representar juegos de caracteres. Las páginas de códigos contienen normalmente los valores ASCII estándar de 0x00 a 0x7F y asignan otros caracteres a los valores restantes de 0x80 a 0xFF. La interpretación de valores de 0x80 a 0xFF depende de la página de códigos específica. Por este motivo, debe evitar usar páginas de códigos en una aplicación globalizada si es posible.

En el siguiente ejemplo, se muestran los peligros de interpretar los datos de la página de códigos cuando la página de códigos predeterminada de un sistema es diferente de la página de códigos en la que se han guardado los datos. (Para simular este escenario, en el ejemplo se especifican de forma explícita páginas de códigos diferentes). En primer lugar, en el ejemplo se define una matriz que consta de los caracteres en mayúsculas del alfabeto griego. Los codifica en una matriz de bytes mediante la página de códigos 737 (también conocida como MS-DOS griego) y guarda la matriz de bytes en un archivo. Si se recupera el archivo y su matriz de bytes se descodifica mediante la página de códigos 737, se restauran los caracteres originales. En cambio, si se recupera el archivo y su matriz de bytes se descodifica mediante la página de códigos 1252 (o Windows-1252, que representa los caracteres del alfabeto latino), se pierden los caracteres originales.

[!code-csharp[Conceptual.Globalization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/codepages1.cs#1)]
[!code-vb[Conceptual.Globalization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/codepages1.vb#1)]

El uso de Unicode garantiza que se asignen siempre las mismas unidades de código a los mismos caracteres y que se asignen siempre los mismos caracteres a las mismas matrices de bytes.

### <a name="use-resource-files"></a>Uso de archivos de recursos

Incluso si está desarrollando una aplicación destinada a una sola referencia cultural o región, debe usar los archivos de recursos para almacenar cadenas y otros recursos que se muestran en la interfaz de usuario. Nunca debe agregarlos directamente al código. Usar archivos de recursos tiene una serie de ventajas:

- Todas las cadenas están en una sola ubicación. No tiene que buscar en todo el código fuente para identificar cadenas que tiene que modificar para un idioma o referencia cultural determinados.

- No tiene que duplicar las cadenas. Los desarrolladores que no usan archivos de recursos, definen frecuentemente la misma cadena en varios archivos de código fuente. Esta duplicación aumenta la probabilidad de que se pasen por alto una o más instancias al modificar una cadena.

- Puede incluir recursos que no sean de cadena, como imágenes o datos binarios, en el archivo de recursos en lugar de almacenarlos en un archivo independiente, para que se puedan recuperar fácilmente.

Usar archivos de recursos tiene algunas ventajas si está creando una aplicación localizada. Al implementar recursos en ensamblados satélite, Common Language Runtime selecciona automáticamente un recurso adecuado según la referencia cultural de la interfaz de usuario actual del usuario tal y como se define en la propiedad <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>. Siempre que proporcione un recurso específico de la referencia cultural adecuado y cree correctamente una instancia de un objeto <xref:System.Resources.ResourceManager> o use una clase de recurso fuertemente tipada, runtime controla los detalles de recuperación de los recursos adecuados.

Para más información sobre la creación de archivos de recursos, vea [Crear archivos de recursos](../../../docs/framework/resources/creating-resource-files-for-desktop-apps.md). Para obtener información sobre la creación e implementación de ensamblados satélite, vea [Crear ensamblados satélite](../../../docs/framework/resources/creating-satellite-assemblies-for-desktop-apps.md) y [Empaquetar e implementar recursos](../../../docs/framework/resources/packaging-and-deploying-resources-in-desktop-apps.md).

### <a name="search-and-compare-strings"></a>Búsqueda y comparación de cadenas

Cuando sea posible, debe tratar las cadenas como cadenas enteras en lugar de tratarlas como una serie de caracteres individuales. Esto es especialmente importante al ordenar o buscar subcadenas, para evitar problemas asociados con el análisis de caracteres combinados.

> [!TIP]
> Puede usar la clase <xref:System.Globalization.StringInfo> para trabajar con los elementos de texto en lugar de los caracteres individuales de una cadena.

En búsquedas y comparaciones de cadenas, un error común es tratar la cadena como una colección de caracteres, cada uno de ellos se representa mediante un objeto <xref:System.Char>. De hecho, un solo carácter puede estar formado por uno, dos o más objetos <xref:System.Char>. Estos caracteres se encuentran con más frecuencia en cadenas de referencias culturales cuyos alfabetos constan de caracteres fuera del intervalo de caracteres de latín básico de Unicode (U+0021 a U+007E). En el ejemplo siguiente se intenta encontrar el índice del carácter LETRA LATINA A MAYÚSCULA CON ACENTO GRAVE (U+00C0) en una cadena. Pero este carácter se puede representar de dos formas diferentes: como una única unidad de código (U+00C0), o bien como un carácter compuesto (dos unidades de código: U+0041 y U+0300). En este caso, el carácter se representa en la instancia de cadena mediante dos objetos <xref:System.Char>, U+0041 y U+0300. El código de ejemplo llama a las sobrecargas <xref:System.String.IndexOf%28System.Char%29?displayProperty=nameWithType> y <xref:System.String.IndexOf%28System.String%29?displayProperty=nameWithType> para buscar la posición de este carácter en la instancia de cadena, pero estas devuelven resultados diferentes. La primera llamada al método tiene un argumento <xref:System.Char>; realiza una comparación ordinal y, por tanto, no se puede encontrar una coincidencia. La segunda llamada tiene un argumento <xref:System.String>; realiza una comparación que tiene en cuenta la referencia cultural y, por tanto, se encuentra una coincidencia.

[!code-csharp[Conceptual.Globalization#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/search1.cs#18)]
[!code-vb[Conceptual.Globalization#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/search1.vb#18)]

Puede evitar la ambigüedad de este ejemplo (llamadas a dos sobrecargas similares de un método que devuelve resultados diferentes) mediante una llamada a una sobrecarga que incluya un parámetro <xref:System.StringComparison>, como el método <xref:System.String.IndexOf%28System.String%2CSystem.StringComparison%29?displayProperty=nameWithType> o <xref:System.String.LastIndexOf%28System.String%2CSystem.StringComparison%29?displayProperty=nameWithType>.

En cambio, las búsquedas no se realizan siempre según la referencia cultural. Si el propósito de la búsqueda es tomar una decisión de seguridad o permitir o denegar el acceso a algún recurso, la comparación debe ser ordinal, como se describe en la sección siguiente.

### <a name="test-strings-for-equality"></a>Prueba de la igualdad de cadenas

Si quiere probar la igualdad de dos cadenas en lugar de determinar cómo se comparan en el criterio de ordenación, use el método <xref:System.String.Equals%2A?displayProperty=nameWithType> en lugar de un método de comparación de cadenas como <xref:System.String.Compare%2A?displayProperty=nameWithType> o <xref:System.Globalization.CompareInfo.Compare%2A?displayProperty=nameWithType>.

Normalmente, se realizan las comparaciones de igualdad para acceder a algunos recursos de forma condicional. Por ejemplo, podría realizar una comparación de igualdad para comprobar una contraseña o para confirmar que existe un archivo. Estas comparaciones no lingüísticas siempre deben ser ordinales en lugar de según la referencia cultural. En general, debería llamar al método <xref:System.String.Equals%28System.String%2CSystem.StringComparison%29?displayProperty=nameWithType> de la instancia o al método <xref:System.String.Equals%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> estático con un valor de <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> para cadenas como contraseñas y un valor de <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> para cadenas como nombres de archivo o URI.

A veces, las comparaciones de igualdad implican búsquedas o comparaciones de subcadenas en lugar de llamadas al método <xref:System.String.Equals%2A?displayProperty=nameWithType>. En algunos casos, puede usar una búsqueda de subcadena para determinar si esa subcadena es igual a otra cadena. Si el propósito de esta comparación es no lingüístico, la búsqueda también debe ser ordinal en lugar de según la referencia cultural.

En el ejemplo siguiente, se muestra el peligro de una búsqueda según la referencia cultural en datos no lingüísticos. El método `AccessesFileSystem` está diseñado para prohibir el acceso al sistema de archivos a los URI que comienzan con la subcadena "FILE". Para ello, realiza una comparación según la referencia cultural que no diferencia mayúsculas de minúsculas del principio del URI con la cadena "FILE". Ya que un URI que accede al sistema de archivos puede comenzar con "FILE:" o "file:", la suposición implícita es que esa "i" (U+0069) es siempre el equivalente en minúsculas de "I" (U+0049). Sin embargo, en turco y azerbaiyano, la versión en mayúsculas de "i" es "İ" (0130). Debido a esta discrepancia, la comparación según la referencia cultural permite el acceso al sistema de archivos cuando debería estar prohibido.

[!code-csharp[Conceptual.Globalization#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/equals1.cs#12)]
[!code-vb[Conceptual.Globalization#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/equals1.vb#12)]

Para evitar este problema, realice una comparación ordinal que no distinga mayúsculas de minúsculas, como se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.Globalization#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/equals2.cs#13)]
[!code-vb[Conceptual.Globalization#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/equals2.vb#13)]

### <a name="order-and-sort-strings"></a>Ordenación de cadenas

Normalmente, las cadenas ordenadas que se muestran en la interfaz de usuario se deben ordenar en función de la referencia cultural. En su mayor parte, estas comparaciones de cadenas se tratan implícitamente mediante .NET al llamar a un método que ordena cadenas, como <xref:System.Array.Sort%2A?displayProperty=nameWithType> o <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType>. De manera predeterminada, las cadenas se ordenan mediante las convenciones de ordenación de la referencia cultural actual. En el ejemplo siguiente, se ilustra la diferencia cuando una matriz de cadenas se ordena mediante las convenciones de la referencia cultural del inglés (Estados Unidos) y la referencia cultural del sueco (Suecia).

[!code-csharp[Conceptual.Globalization#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/sort1.cs#14)]
[!code-vb[Conceptual.Globalization#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/sort1.vb#14)]

La comparación de cadenas según la referencia cultural se define mediante el objeto <xref:System.Globalization.CompareInfo>, que devuelve la propiedad <xref:System.Globalization.CultureInfo.CompareInfo%2A?displayProperty=nameWithType> de cada referencia cultural. Las comparaciones de cadenas según la referencia cultural que usan las sobrecargas del método <xref:System.String.Compare%2A?displayProperty=nameWithType> usan también el objeto <xref:System.Globalization.CompareInfo>.

.NET usa tablas para realizar ordenaciones según la referencia cultural de los datos de las cadenas. El contenido de estas tablas, que contienen datos en prioridades de ordenación y normalización de cadenas, viene determinado por la versión del estándar Unicode que se implementa mediante una versión concreta de .NET. En la tabla siguiente se enumeran las versiones de Unicode implementadas por las versiones de .NET Framework especificadas y .NET Core. Tenga en cuenta que esta lista de versiones compatibles de Unicode se aplica solo a la comparación y ordenación de caracteres; no se aplica a la clasificación de caracteres Unicode por categoría. Para obtener más información, consulte la sección "Las cadenas y el estándar Unicode" en el artículo <xref:System.String>.

|Versión de .NET Framework|Sistema operativo|Versión de Unicode|
|----------------------------|----------------------|---------------------|
|.NET Framework 2.0|Todos los sistemas operativos|Unicode 4.1|
|.NET Framework 3.0|Todos los sistemas operativos|Unicode 4.1|
|.NET Framework 3,5|Todos los sistemas operativos|Unicode 4.1|
|.NET Framework 4|Todos los sistemas operativos|Unicode 5.0|
|.NET Framework 4.5 y versiones posteriores en Windows 7|Unicode 5.0|
|.NET Framework 4.5 y versiones posteriores en Windows 8 y sistemas operativos posteriores|Unicode 6.3.0|
|.NET Core (todas las versiones)|Depende de la versión del estándar Unicode compatible con el sistema operativo subyacente.|

A partir de .NET Framework 4.5 y en todas las versiones de .NET Core, la ordenación y la comparación de cadenas dependen del sistema operativo. .NET Framework 4.5 y las versiones posteriores en Windows 7 recuperan los datos de sus propias tablas que implementan Unicode 5.0. .NET Framework 4.5 y las versiones posteriores en Windows 8 y ediciones subsiguientes recuperan los datos de tablas del sistema operativo que implementan Unicode 6.3. En .NET Core, la versión admitida de Unicode depende del sistema operativo subyacente. Si serializa datos ordenados según la referencia cultural, puede usar la clase <xref:System.Globalization.SortVersion> para determinar cuándo se deben ordenar los datos serializados de forma que sea coherente con el criterio de ordenación del sistema operativo y de .NET. Para obtener un ejemplo, consulte el tema de la clase <xref:System.Globalization.SortVersion>.

Si la aplicación realiza ordenaciones extensas específicas de la referencia cultural de los datos de cadena, puede trabajar con la clase <xref:System.Globalization.SortKey> para comparar cadenas. Un criterio de ordenación refleja las prioridades de ordenación específicas de la referencia cultural, incluidas las prioridades alfabéticas, de mayúsculas y minúsculas, y diacríticas de una cadena determinada. Dado que las comparaciones que usan criterios de ordenación son binarias, son más rápidas que las comparaciones que usan un objeto <xref:System.Globalization.CompareInfo> de forma implícita o explícita. Para crear un criterio de ordenación específico de la referencia cultural para una cadena determinada, pase la cadena al método <xref:System.Globalization.CompareInfo.GetSortKey%2A?displayProperty=nameWithType>.

El siguiente ejemplo es similar al ejemplo anterior. En cambio, en lugar de llamar al método <xref:System.Array.Sort%28System.Array%29?displayProperty=nameWithType>, que llama de forma implícita al método <xref:System.Globalization.CompareInfo.Compare%2A?displayProperty=nameWithType>, define una implementación <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> que compara los criterios de ordenación, que crea en una instancia y pasa al método <xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Collections.Generic.IComparer%7B%60%600%7D%29?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Globalization#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/sortkey1.cs#15)]
[!code-vb[Conceptual.Globalization#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/sortkey1.vb#15)]

### <a name="avoid-string-concatenation"></a>Evitación de la concatenación de cadenas

En lo posible, evite usar cadenas compuestas que se compilan en tiempo de ejecución a partir de frases concatenadas. La localización de las cadenas compuestas resulta difícil porque, a menudo, se da por supuesto un orden gramatical en el idioma original de la aplicación que no se aplica a otros idiomas localizados.

## <a name="handle-dates-and-times"></a>Control de las fechas y horas

El control de los valores de fecha y hora depende de si se muestran en la interfaz de usuario o si se conservan. En esta sección se examinan ambos usos. También se explica cómo puede controlar las diferencias de zona horaria y las operaciones aritméticas al trabajar con fechas y horas.

### <a name="display-dates-and-times"></a>Visualización de las fechas y horas

Normalmente, cuando las fechas y horas se muestran en la interfaz de usuario, debe usar las convenciones de formato de la referencia cultural del usuario, que definen la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> y el objeto <xref:System.Globalization.DateTimeFormatInfo> que devuelve la propiedad `CultureInfo.CurrentCulture.DateTimeFormat`. Las convenciones de formato de la referencia cultural actual se usan de forma automática al dar formato a una fecha mediante cualquiera de estos métodos:

- El método <xref:System.DateTime.ToString?displayProperty=nameWithType> sin parámetros

- El método <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>, que incluye una cadena de formato

- El método <xref:System.DateTimeOffset.ToString?displayProperty=nameWithType> sin parámetros

- <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType>, que incluye una cadena de formato

- La característica [formatos compuestos](../../../docs/standard/base-types/composite-formatting.md), cuando se usa con fechas

En el ejemplo siguiente, se muestran datos de amanecer y puesta de sol duplicados para el 11 de octubre de 2012. Primero, establece la referencia cultural actual a croata (Croacia) y, después, a inglés (Gran Bretaña). En cada caso, las fechas y horas se muestran en el formato adecuado para esa referencia cultural.

[!code-csharp[Conceptual.Globalization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/dates1.cs#2)]
[!code-vb[Conceptual.Globalization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/dates1.vb#2)]

### <a name="persist-dates-and-times"></a>Conservación de las fechas y horas

Nunca debe conservar datos de fecha y hora en un formato que puede variar según la referencia cultural. Se trata de un error de programación común que produce datos dañados o una excepción en tiempo de ejecución. En el ejemplo siguiente se serializan dos fechas, 9 de enero de 2013 y 18 de agosto de 2013, como cadenas mediante las convenciones de formato de la referencia cultural del inglés (Estados Unidos). Cuando los datos se recuperan y analizan mediante las convenciones de la referencia cultural del inglés (Estados Unidos), se restauran correctamente. En cambio, cuando se recuperan y analizan mediante las convenciones de la referencia cultural del inglés (Reino Unido), la primera fecha se interpreta de forma errónea como el 1 de septiembre y la segunda no se puede analizar porque el calendario gregoriano no tiene un decimoctavo mes.

[!code-csharp[Conceptual.Globalization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/dates2.cs#3)]
[!code-vb[Conceptual.Globalization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/dates2.vb#3)]

Puede evitar este problema de cualquiera de estas tres maneras:

- Serializar la fecha y hora en formato binario en lugar de como una cadena.

- Guardar y analizar la representación de la cadena de fecha y hora mediante una cadena de formato personalizado que sea el mismo independientemente de la referencia cultural del usuario.

- Guardar la cadena mediante las convenciones de formato de la referencia cultural invariable.

En el ejemplo siguiente se muestra el último enfoque. Usa las convenciones de formato de la referencia cultural invariable que devuelve la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> estática.

[!code-csharp[Conceptual.Globalization#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/dates3.cs#4)]
[!code-vb[Conceptual.Globalization#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/dates3.vb#4)]

### <a name="serialization-and-time-zone-awareness"></a>Reconocimiento de la serialización y la zona horaria

Un valor de fecha y hora puede tener varias interpretaciones, desde una hora general ("Las tiendas abren el 2 de enero de 2013 a las 9:00") hasta un momento específico en el tiempo ("Fecha de nacimiento: 2 de enero de 2013 a las 6:32:00"). Cuando un valor de tiempo representa un momento específico en el tiempo y lo restaura desde un valor serializado, debe asegurarse de que representa el mismo momento en el tiempo, independientemente de la ubicación geográfica o la zona horaria del usuario.

El siguiente ejemplo ilustra este problema. Guarda un solo valor de fecha y hora local como una cadena en tres [formatos estándar](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) ("G" para hora larga de fecha general, "s" para la fecha y hora que se puede ordenar y "o" para la fecha y hora de ida y vuelta), así como en formato binario.

[!code-csharp[Conceptual.Globalization#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/dates4.cs#10)]
[!code-vb[Conceptual.Globalization#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/dates4.vb#10)]

Cuando se restauran los datos en un sistema en la misma zona horaria que el sistema en el que se han serializado, los valores de fecha y hora deserializados reflejan exactamente el valor original, como muestra el resultado:

```console
'3/30/2013 6:00:00 PM' --> 3/30/2013 6:00:00 PM Unspecified
'2013-03-30T18:00:00' --> 3/30/2013 6:00:00 PM Unspecified
'2013-03-30T18:00:00.0000000-07:00' --> 3/30/2013 6:00:00 PM Local

3/30/2013 6:00:00 PM Local
```

En cambio, si restaura los datos en un sistema en una zona horaria diferente, solo el valor de fecha y hora con el formato de la cadena de formato estándar "o" (ida y vuelta) conserva la información de zona horaria y, por tanto, representa la misma instantánea en el tiempo. Este es el resultado cuando se restauran datos de fecha y hora en un sistema en la zona horaria estándar romance:

```console
'3/30/2013 6:00:00 PM' --> 3/30/2013 6:00:00 PM Unspecified
'2013-03-30T18:00:00' --> 3/30/2013 6:00:00 PM Unspecified
'2013-03-30T18:00:00.0000000-07:00' --> 3/31/2013 3:00:00 AM Local

3/30/2013 6:00:00 PM Local
```

Para reflejar con exactitud el valor de fecha y hora que representa un único momento de tiempo, independientemente de la zona horaria del sistema en el que se deserializan los datos, puede realizar cualquiera de las siguientes acciones:

- Guarde el valor como una cadena mediante la cadena de formato estándar "o" (ida y vuelta). Después, deserialícelo en el sistema de destino.

- Conviértalo en UTC y guárdelo como una cadena mediante la cadena de formato estándar "r" (RFC1123). Luego, deserialícelo en el sistema de destino y conviértalo a la hora local.

- Conviértalo en UTC y guárdelo como una cadena mediante la cadena de formato estándar "u" (universal que se puede ordenar). Luego, deserialícelo en el sistema de destino y conviértalo a la hora local.

- Conviértalo en UTC y guárdelo en formato binario. Luego, deserialícelo en el sistema de destino y conviértalo a la hora local.

En el siguiente ejemplo se ilustra cada técnica.

[!code-csharp[Conceptual.Globalization#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/dates8.cs#11)]
[!code-vb[Conceptual.Globalization#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/dates8.vb#11)]

Cuando los datos se serializan en un sistema en la zona horaria estándar del Pacífico y se deserializan en un sistema en la zona horaria estándar romance, el ejemplo muestra el siguiente resultado:

```console
'2013-03-30T18:00:00.0000000-07:00' --> 3/31/2013 3:00:00 AM Local
'Sun, 31 Mar 2013 01:00:00 GMT' --> 3/31/2013 3:00:00 AM Local
'2013-03-31 01:00:00Z' --> 3/31/2013 3:00:00 AM Local

3/31/2013 3:00:00 AM Local
```

Para más información, vea [Convertir horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md).

### <a name="perform-date-and-time-arithmetic"></a>Realización de operaciones aritméticas con fechas y horas

Los tipos <xref:System.DateTime> y <xref:System.DateTimeOffset> admiten operaciones aritméticas. Puede calcular la diferencia entre dos valores de fecha, o puede agregar o restar intervalos de tiempo determinados a o de un valor de fecha. En cambio, las operaciones aritméticas en valores de fecha y hora no tienen en cuenta las zonas horarias ni las reglas de ajuste de zona horaria. Por este motivo, la fecha y hora aritméticas en valores que representan momentos en el tiempo pueden devolver resultados inexactos.

Por ejemplo, la transición de la hora estándar del Pacífico a la hora de verano del Pacífico tiene lugar el segundo domingo de marzo, que, en el año 2013, es el 10 de marzo. Como se muestra en el ejemplo siguiente, si calcula la fecha y hora 48 horas después del 9 de marzo de 2013 a las 10:30 a. m. en un sistema en la zona horaria estándar del Pacífico, el resultado, el 11 de marzo de 2013 a las 10:30 a. m., no tiene en cuenta el ajuste de hora de intervención.

[!code-csharp[Conceptual.Globalization#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/dates5.cs#8)]
[!code-vb[Conceptual.Globalization#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/dates5.vb#8)]

Para asegurarse de que una operación aritmética en valores de fecha y hora produce resultados precisos, siga estos pasos:

1. Convierta la hora en la zona horaria de origen a UTC.

2. Realice la operación aritmética.

3. Si el resultado es un valor de fecha y hora, conviértalo de la hora UTC a la hora de la zona horaria de origen.

El ejemplo siguiente es similar al anterior, salvo que sigue estos tres pasos para agregar de forma correcta 48 horas al 9 de marzo de 2013 a las 10:30 a. m.

[!code-csharp[Conceptual.Globalization#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/dates6.cs#9)]
[!code-vb[Conceptual.Globalization#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/dates6.vb#9)]

Para más información, vea [Efectuar operaciones aritméticas con fechas y horas](../../../docs/standard/datetime/performing-arithmetic-operations.md).

### <a name="use-culture-sensitive-names-for-date-elements"></a>Uso de nombres que tienen en cuenta las referencias culturales para elementos de fecha

Puede que su aplicación tenga que mostrar el nombre del mes o el día de la semana. Para ello, es común código como el siguiente.

[!code-csharp[Conceptual.Globalization#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/monthname1.cs#19)]
[!code-vb[Conceptual.Globalization#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/monthname1.vb#19)]

En cambio, este código devuelve siempre los nombres de los días de la semana en inglés. El código que extrae el nombre del mes es, a menudo, aún más inflexible. Con frecuencia, asume un calendario de doce meses con nombres de meses en un idioma específico.

Mediante el uso de [cadenas de formato de fecha y hora personalizadas](../../../docs/standard/base-types/custom-date-and-time-format-strings.md) o las propiedades del objeto <xref:System.Globalization.DateTimeFormatInfo>, es fácil extraer cadenas que muestran los nombres de días de la semana o meses en la referencia cultural del usuario, como se muestra en el ejemplo siguiente. Cambia la referencia cultural actual al francés (Francia) y muestra el nombre del día de la semana y el nombre del mes del 1 de julio de 2013.

[!code-csharp[Conceptual.Globalization#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/monthname2.cs#20)]
[!code-vb[Conceptual.Globalization#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/monthname2.vb#20)]

## <a name="numeric-values"></a>Valores numéricos

El control de los números depende de si se muestran en la interfaz de usuario o si se conservan. En esta sección se examinan ambos usos.

> [!NOTE]
> En operaciones de formato y análisis, .NET reconoce solo los caracteres latinos básicos de 0 a 9 (U+0030 a U+0039) como dígitos numéricos.

### <a name="display-numeric-values"></a>Visualización de los valores numéricos

Normalmente, cuando los números se muestran en la interfaz de usuario, debe usar las convenciones de formato de la referencia cultural del usuario, que definen la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> y el objeto <xref:System.Globalization.NumberFormatInfo> que devuelve la propiedad `CultureInfo.CurrentCulture.NumberFormat`. Las convenciones de formato de la referencia cultural actual se usan de forma automática al dar formato a una fecha mediante cualquiera de los siguientes métodos:

- El método `ToString` sin parámetros de cualquier tipo numérico

- El método `ToString(String)` de cualquier tipo numérico, que incluye una cadena de formato como un argumento

- La característica [formatos compuestos](../../../docs/standard/base-types/composite-formatting.md), cuando se usa con valores numéricos

En el ejemplo siguiente se muestra el promedio de temperatura por mes en París, Francia. Primero, establece la referencia cultural actual al francés (Francia) antes de mostrar los datos y, después, la establece en inglés (Estados Unidos). En cada caso, los nombres de meses y las temperaturas se muestran en el formato adecuado para esa referencia cultural. Tenga en cuenta que las dos referencias culturales usan separadores decimales diferentes en el valor de temperatura. Tenga en cuenta también que en el ejemplo se usa la cadena de formato de fecha y hora "MMMM" personalizada para mostrar el nombre completo del mes y que asigna la cantidad de espacio adecuada para el nombre del mes en la cadena de resultado al determinar la longitud del nombre del mes más largo en la matriz <xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A?displayProperty=nameWithType>.

[!code-csharp[Conceptual.Globalization#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/numbers1.cs#5)]
[!code-vb[Conceptual.Globalization#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/numbers1.vb#5)]

### <a name="persist-numeric-values"></a>Conservación de los valores numéricos

Nunca debe conservar datos numéricos en un formato específico de la referencia cultural. Se trata de un error de programación común que produce datos dañados o una excepción en tiempo de ejecución. En el ejemplo siguiente, se generan diez números de punto flotante aleatorios y, después, se serializan como cadenas mediante las convenciones de formato de la referencia cultural de inglés (Estados Unidos). Cuando los datos se recuperan y analizan mediante las convenciones de la referencia cultural del inglés (Estados Unidos), se restauran correctamente. En cambio, cuando se recuperan y analizan mediante las convenciones de la referencia cultural de francés (Francia), no se puede analizar ninguno de los números porque las referencias culturales usan separadores decimales diferentes.

[!code-csharp[Conceptual.Globalization#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/numbers2.cs#6)]
[!code-vb[Conceptual.Globalization#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/numbers2.vb#6)]

Para evitar este problema, puede usar una de estas técnicas:

- Guardar y analizar la representación de la cadena del número mediante una cadena de formato personalizado que sea el mismo independientemente de la referencia cultural del usuario.

- Guardar el número como una cadena mediante las convenciones de formato de la referencia cultural, que devuelve la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.

- Serializar el número en formato binario en lugar del formato de cadena.

En el ejemplo siguiente se muestra el último enfoque. Serializa la matriz de valores <xref:System.Double> y, después, los deserializa y muestra mediante las convenciones de formato de las referencias culturales de francés (Francia) e inglés (Estados Unidos).

[!code-csharp[Conceptual.Globalization#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/numbers3.cs#7)]
[!code-vb[Conceptual.Globalization#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/numbers3.vb#7)]

La serialización de valores de moneda es un caso especial. Dado que un valor de moneda depende de la unidad de moneda en que se expresa, no tiene sentido tratarlo como un valor numérico independiente. En cambio, si guarda un valor de moneda como una cadena con formato que incluye un símbolo de moneda, no se puede deserializar en un sistema cuya referencia cultural predeterminada use otro símbolo de moneda, como se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.Globalization#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/currency1.cs#16)]
[!code-vb[Conceptual.Globalization#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/currency1.vb#16)]

En su lugar, debe serializar el valor numérico junto con alguna información de referencia cultural, como el nombre de la referencia cultural, para que se puedan deserializar el valor y el símbolo de moneda independientemente de la referencia cultural actual. En el ejemplo siguiente, se hace mediante la definición de una estructura `CurrencyValue` con dos miembros: el valor <xref:System.Decimal> y el nombre de la referencia cultural a la que pertenece el valor.

[!code-csharp[Conceptual.Globalization#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.globalization/cs/currency2.cs#17)]
[!code-vb[Conceptual.Globalization#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.globalization/vb/currency2.vb#17)]

## <a name="work-with-culture-specific-settings"></a>Trabajo con configuraciones específicas de la referencia cultural

En .NET, la clase <xref:System.Globalization.CultureInfo> representa una referencia cultural o región determinada. Algunas de sus propiedades devuelven objetos que proporcionan información específica sobre algún aspecto de una referencia cultural:

- La propiedad <xref:System.Globalization.CultureInfo.CompareInfo%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Globalization.CompareInfo> que contiene información sobre cómo compara y ordena las cadenas la referencia cultural.

- La propiedad <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Globalization.DateTimeFormatInfo> que proporciona información específica de la referencia cultural usada en el formato de fecha y hora.

- La propiedad <xref:System.Globalization.CultureInfo.NumberFormat%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Globalization.NumberFormatInfo> que proporciona información específica de la referencia cultural usada en el formato de datos numéricos.

- La propiedad <xref:System.Globalization.CultureInfo.TextInfo%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Globalization.TextInfo> que proporciona información sobre el sistema de escritura de la referencia cultural.

En general, no realice ninguna suposición sobre los valores de propiedades <xref:System.Globalization.CultureInfo> específicas y sus objetos relacionados. En su lugar, debería ver datos específicos de la referencia cultural como sujetos a cambios, por estos motivos:

- Los valores de propiedad individual están sujetos a cambios y revisión con el tiempo, ya que los datos se corrigen, hay mejores datos disponibles, o se cambian las convenciones específicas de la referencia cultural.

- Los valores de propiedad individual pueden variar entre las versiones de .NET o del sistema operativo.

- .NET es compatible con referencias culturales de reemplazo. Esto permite definir una nueva referencia cultural personalizada que complementa las referencias culturales estándares existentes o reemplaza por completo una referencia cultural estándar existente.

- En sistemas Windows, el usuario puede personalizar la configuración específica de la referencia cultural mediante la aplicación **Región e idioma** del Panel de control. Al crear una instancia de un objeto <xref:System.Globalization.CultureInfo>, puede determinar si muestra estas personalizaciones de usuario mediante una llamada al constructor <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29>. Normalmente, en las aplicaciones de usuario final hay que respetar las preferencias del usuario para que este pueda ver los datos en un formato que espera.

## <a name="see-also"></a>Vea también

- [Globalización y localización](../../../docs/standard/globalization-localization/index.md)
- [Procedimientos recomendados para el uso de cadenas](../../../docs/standard/base-types/best-practices-strings.md)
