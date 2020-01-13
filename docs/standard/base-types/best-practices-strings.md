---
title: Procedimientos recomendados para el uso de cadenas en .NET
description: Obtenga información sobre cómo usar cadenas de forma eficaz en aplicaciones .NET.
ms.date: 05/01/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework],searching
- best practices,string comparison and sorting
- strings [.NET Framework],best practices
- strings [.NET Framework],basic string operations
- sorting strings
- strings [.NET Framework],sorting
- string comparison [.NET Framework],best practices
- string sorting
- comparing strings
- strings [.NET Framework],comparing
ms.assetid: b9f0bf53-e2de-4116-8ce9-d4f91a1df4f7
ms.openlocfilehash: c88776ea9d8ba17d86767b704e8b0eaff5b6cb89
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711485"
---
# <a name="best-practices-for-using-strings-in-net"></a>Procedimientos recomendados para el uso de cadenas en .NET

.NET proporciona una gran compatibilidad para desarrollar aplicaciones localizadas y globalizadas, y simplifica la aplicación de las convenciones de la referencia cultural actual o de una referencia cultural concreta al realizar operaciones comunes como ordenar y mostrar cadenas. Pero ordenar o comparar cadenas no es siempre una operación dependiente de la referencia cultural. Por ejemplo, las cadenas usadas internamente por una aplicación normalmente se deben administrar de forma idéntica en todas las referencias culturales. Cuando los datos de cadenas independientes de la referencia cultural (como etiquetas XML, etiquetas HTML, nombres de usuario, rutas de acceso de archivos y nombres de objetos del sistema) se interpretan como si fueran dependientes de la referencia cultural, el código de aplicación puede estar sujeto a errores imperceptibles, un rendimiento inadecuado y, en algunos casos, a problemas de seguridad.

En este tema, se examinan los métodos de ordenación, comparación y uso de mayúsculas y minúsculas de cadenas de .NET, se presentan recomendaciones para seleccionar un método adecuado de control de cadenas y se proporciona información adicional sobre los métodos de control de cadenas. También se examina cómo se usan para la presentación y el almacenamiento los datos con formato, como los datos numéricos y los datos de fecha y hora.

## <a name="recommendations-for-string-usage"></a>Recomendaciones sobre el uso de cadenas

Cuando desarrolle con .NET, siga estas recomendaciones sencillas a la hora de usar cadenas:

- Use sobrecargas que especifiquen explícitamente las reglas de comparación de cadenas para las operaciones de cadenas. Normalmente, esto implica llamar a una sobrecarga de método que tiene un parámetro de tipo <xref:System.StringComparison>.
- Use <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> o <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> para las comparaciones como su valor predeterminado seguro para la coincidencia de cadenas válidas para la referencia cultural.
- Use comparaciones con <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> o <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> para lograr un rendimiento mejor.
- Use operaciones de cadena basadas en <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType> al mostrar la salida al usuario.
- Use los valores <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> o <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> no lingüísticos en lugar de operaciones de cadena basadas en <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> cuando la comparación sea lingüísticamente no pertinente (por ejemplo, nombre simbólico).
- Emplee el método <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> en lugar del método <xref:System.String.ToLowerInvariant%2A?displayProperty=nameWithType> al normalizar cadenas para la comparación.
- Use una sobrecarga del método <xref:System.String.Equals%2A?displayProperty=nameWithType> para probar si dos cadenas son iguales.
- Use los métodos <xref:System.String.Compare%2A?displayProperty=nameWithType> y <xref:System.String.CompareTo%2A?displayProperty=nameWithType> para ordenar cadenas, no para comprobar la igualdad.
- Use el formato dependiente de la referencia cultural para mostrar datos que no son de cadena, como números y fechas, en una interfaz de usuario. Use el formato con la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture) para conservar datos que no son de cadena en forma de cadena.

Evite lo siguiente cuando use cadenas:

- No emplee sobrecargas que no especifiquen explícita o implícitamente las reglas de comparación de cadenas para las operaciones de cadena.
- No use operaciones de cadena basadas en <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> en la mayoría de los casos. Una de las pocas excepciones es cuando vaya a conservar datos lingüísticamente significativos pero válidos culturalmente.
- No emplee ninguna sobrecarga del método <xref:System.String.Compare%2A?displayProperty=nameWithType> o <xref:System.String.CompareTo%2A> y pruebe si se devuelve un valor cero para determinar si dos cadenas son iguales.
- No use el formato dependiente de la referencia cultural para conservar datos numéricos o datos de fecha y hora en formato de cadena.

## <a name="specifying-string-comparisons-explicitly"></a>Especificar comparaciones de cadenas explícitamente

La mayoría de los métodos de manipulación de cadenas de .NET están sobrecargados. Normalmente, una o más sobrecargas aceptan la configuración predeterminada, mientras que otras no aceptan ningún valor predeterminado y en su lugar definen la manera precisa en la que se van a comparar o manipular las cadenas. La mayoría de los métodos que no confían en los valores predeterminados incluye un parámetro de tipo <xref:System.StringComparison>, que es una enumeración que especifica explícitamente reglas para la comparación de cadenas por referencia cultural y uso de mayúsculas y minúsculas. En la tabla siguiente se describen los miembros de la enumeración <xref:System.StringComparison> .

|Miembro de StringComparison|Descripción|
|-----------------------------|-----------------|
|<xref:System.StringComparison.CurrentCulture>|Realiza una comparación con distinción entre mayúsculas y minúsculas usando la referencia cultural actual.|
|<xref:System.StringComparison.CurrentCultureIgnoreCase>|Realiza una comparación sin distinción entre mayúsculas y minúsculas usando la referencia cultural actual.|
|<xref:System.StringComparison.InvariantCulture>|Realiza una comparación con distinción entre mayúsculas y minúsculas usando la referencia cultural de todos los idiomas.|
|<xref:System.StringComparison.InvariantCultureIgnoreCase>|Realiza una comparación sin distinción entre mayúsculas y minúsculas usando la referencia cultural de todos los idiomas.|
|<xref:System.StringComparison.Ordinal>|Realiza una comparación ordinal.|
|<xref:System.StringComparison.OrdinalIgnoreCase>|Realiza una comparación ordinal sin distinción entre mayúsculas y minúsculas.|

Por ejemplo, el método <xref:System.String.IndexOf%2A> , que devuelve el índice de una subcadena en un objeto <xref:System.String> que coincide con un carácter o una cadena, tiene nueve sobrecargas:

- <xref:System.String.IndexOf%28System.Char%29>, <xref:System.String.IndexOf%28System.Char%2CSystem.Int32%29>y <xref:System.String.IndexOf%28System.Char%2CSystem.Int32%2CSystem.Int32%29>, que de forma predeterminada realizan una búsqueda ordinal (con distinción entre mayúsculas y minúsculas e independiente de la referencia cultural) de un carácter de la cadena.
- <xref:System.String.IndexOf%28System.String%29>, <xref:System.String.IndexOf%28System.String%2CSystem.Int32%29>y <xref:System.String.IndexOf%28System.String%2CSystem.Int32%2CSystem.Int32%29>, que de forma predeterminada realizan una búsqueda con distinción entre mayúsculas y minúsculas y dependiente de la referencia cultural de una subcadena de la cadena.
- <xref:System.String.IndexOf%28System.String%2CSystem.StringComparison%29>, <xref:System.String.IndexOf%28System.String%2CSystem.Int32%2CSystem.StringComparison%29>y <xref:System.String.IndexOf%28System.String%2CSystem.Int32%2CSystem.Int32%2CSystem.StringComparison%29>, que incluyen un parámetro de tipo <xref:System.StringComparison> que permite especificar el formato de la comparación.

Se recomienda seleccionar una sobrecarga que no use valores predeterminados, por las razones siguientes:

- Algunas sobrecargas con parámetros predeterminados (las que buscan un valor <xref:System.Char> en la instancia de la cadena) realizan una comparación ordinal, mientras que otras (las que buscan una cadena en la instancia de la cadena) son dependientes de la referencia cultural. Es difícil recordar qué método usa cada valor predeterminado y resulta fácil confundir las sobrecargas.
- La intención del código que usa valores predeterminados para las llamadas al método no está clara. En el ejemplo siguiente, en el cual se usan valores predeterminados, es difícil saber si el desarrollador pretendía realizar una comparación ordinal o lingüística de dos cadenas, o si había alguna diferencia al usar mayúsculas y minúsculas entre `protocol` y "http" que pudiera hacer que la prueba de igualdad devolviera el valor `false`.

     [!code-csharp[Conceptual.Strings.BestPractices#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/explicitargs1.cs#1)]
     [!code-vb[Conceptual.Strings.BestPractices#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/explicitargs1.vb#1)]

En general, se recomienda llamar a un método que no use los valores predeterminados, ya que hace que la intención del código no sea ambigua. Esto, a su vez, hace el código más legible y más fácil de depurar y mantener. En el ejemplo siguiente se abordan las cuestiones que se derivan del ejemplo anterior. Indica claramente que se usa la comparación ordinal y que se omiten las diferencias en cuanto al uso de mayúsculas y minúsculas.

[!code-csharp[Conceptual.Strings.BestPractices#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/explicitargs1.cs#2)]
[!code-vb[Conceptual.Strings.BestPractices#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/explicitargs1.vb#2)]

## <a name="the-details-of-string-comparison"></a>Detalles de la comparación de cadenas

La comparación de cadenas es el corazón de muchas operaciones relacionadas con cadenas, especialmente la ordenación y la comprobación de igualdad. Las cadenas se ordenan en un orden determinado: si "mi" aparece antes que "cadena" en una lista ordenada de cadenas, "mi" debe compararse como menor o igual que "cadena". Además, la comparación define la igualdad implícitamente. La operación de comparación devuelve cero para las cadenas que considera iguales. Una buena interpretación es que ninguna cadena es menor que otra. La mayoría de las operaciones significativas que implican cadenas incluyen uno o ambos de estos procedimientos: comparar con otra cadena y ejecutar una operación de ordenación bien definida.

> [!NOTE]
> Puede descargar las [tablas de pesos de ordenación](https://www.microsoft.com/download/details.aspx?id=10921), un conjunto de archivos de texto que contienen información sobre los pesos de caracteres que se usan en las operaciones de ordenación y comparación para los sistemas operativos Windows, además de la [tabla de elementos de intercalación Unicode predeterminada](https://www.unicode.org/Public/UCA/latest/allkeys.txt), que es la última versión de la tabla de pesos de ordenación para Linux y macOS. La versión específica de la tabla de pesos de ordenación en Linux y macOS depende de la versión de las bibliotecas de [componentes internacionales de Unicode](http://site.icu-project.org/) instaladas en el sistema. Para más información sobre las versiones de los componentes internacionales de Unicode y las versiones de Unicode que implementan, vea la información sobre la [descarga de componentes internacionales de Unicode](http://site.icu-project.org/download).

Sin embargo, la evaluación de dos cadenas para comprobar su igualdad o su criterio de ordenación no produce ningún resultado correcto único; el resultado depende de los criterios empleados para comparar las cadenas. En especial, las comparaciones de cadenas que son ordinales o que se basan en las convenciones de ordenación y uso de mayúsculas y minúsculas de la referencia cultural actual o de la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture) (una referencia cultural válida para la configuración regional basada en el idioma inglés) pueden producir resultados diferentes.

Además, las comparaciones de cadenas mediante las diferentes versiones de .NET o con .NET en distintos sistemas operativos o versiones de sistema operativo pueden devolver resultados diferentes. Para más información, vea [Las cadenas y el estándar Unicode](xref:System.String#Unicode).

### <a name="string-comparisons-that-use-the-current-culture"></a>Comparaciones de cadenas que usan la referencia cultural actual

Un criterio implica usar las convenciones de la referencia cultural actual a la hora de comparar cadenas. Las comparaciones que se basan en la referencia cultural actual usan la referencia cultural o la configuración regional actual del subproceso. Si el usuario no establece la referencia cultural, se usa como valor predeterminado la configuración de la ventana **Opciones regionales** del Panel de control. Siempre debe usar comparaciones basadas en la referencia cultural actual cuando los datos sean lingüísticamente pertinentes y cuando refleje una interacción con el usuario dependiente de la referencia cultural.

En cambio, el comportamiento de comparación y uso de mayúsculas y minúsculas de .NET cambia cuando la referencia cultural cambia. Esto ocurre cuando una aplicación se ejecuta en un equipo que tiene una referencia cultural diferente que el equipo en el que se desarrolló la aplicación o cuando el subproceso en ejecución cambia su referencia cultural. Este comportamiento es deliberado, pero sigue resultando no obvio para muchos desarrolladores. En el ejemplo siguiente, se muestran las diferencias en el criterio de ordenación entre las referencias culturales de inglés de EE. UU. ("en-US") y sueco ("sv-SE"). Tenga en cuenta que las palabras "ångström", "Windows" y "Visual Studio" aparecen en distintas posiciones en las matrices de cadenas ordenadas.

[!code-csharp[Conceptual.Strings.BestPractices#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/comparison1.cs#3)]
[!code-vb[Conceptual.Strings.BestPractices#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/comparison1.vb#3)]

Las comparaciones sin distinción entre mayúsculas y minúsculas que usan la referencia cultural actual son iguales que las comparaciones dependientes de la referencia cultural, excepto que omiten el uso de mayúsculas y minúsculas según indica la referencia cultural actual del subproceso. Este comportamiento también se puede manifestar en los criterios de ordenación.

Las comparaciones que usan semántica de la referencia cultural actual son el valor predeterminado para los métodos siguientes:

- Sobrecargas de<xref:System.String.Compare%2A?displayProperty=nameWithType> que no incluyen un parámetro <xref:System.StringComparison> .
- Sobrecargas de<xref:System.String.CompareTo%2A?displayProperty=nameWithType> .
- El método predeterminado <xref:System.String.StartsWith%28System.String%29?displayProperty=nameWithType> y el método <xref:System.String.StartsWith%28System.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType> con un parámetro `null`<xref:System.Globalization.CultureInfo> .
- El método predeterminado <xref:System.String.EndsWith%28System.String%29?displayProperty=nameWithType> y el método <xref:System.String.EndsWith%28System.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType> con un parámetro `null`<xref:System.Globalization.CultureInfo>.
- Sobrecargas de<xref:System.String.IndexOf%2A?displayProperty=nameWithType> que aceptan <xref:System.String> como un parámetro de búsqueda y que no tienen un parámetro <xref:System.StringComparison> .
- Sobrecargas de<xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> que aceptan <xref:System.String> como un parámetro de búsqueda y que no tienen un parámetro <xref:System.StringComparison> .

En cualquier caso, se recomienda llamar a una sobrecarga que tenga un parámetro <xref:System.StringComparison> para aclarar la intención de la llamada al método.

Pueden surgir errores imperceptibles y no tan imperceptibles cuando los datos de cadenas no lingüísticos se interpretan lingüísticamente, o cuando los datos de cadenas de una referencia cultural determinada se interpretan usando las convenciones de otra referencia cultural. El ejemplo canónico es el problema con I en turco.

Para casi todos los alfabetos latinos, incluso en inglés de EE. UU., el carácter "i" (\u0069) es la versión en minúsculas del carácter "I" (\u0049). Esta regla de mayúsculas y minúsculas se convierte rápidamente en el valor predeterminado para alguien que programe en esa referencia cultural. En cambio, el alfabeto turco ("tr-TR") incluye un carácter "I con punto" "İ" (\u0130), que es la versión en mayúsculas de "i". El turco también incluye un carácter "i sin punto" en minúscula, "ı" (\u0131), que en mayúsculas es "I". Este comportamiento también se produce en la referencia cultural de azerbaiyano ("az").

Por tanto, los supuestos sobre poner en mayúsculas "i" o escribir "I" en minúsculas no son válidas en todas las referencias culturales. Si usa las sobrecargas predeterminadas para las rutinas de comparación de cadenas, estarán sujetas a variaciones entre distintas referencias culturales. Si los datos que se van a comparar son no lingüísticos, el uso de las sobrecargas predeterminadas puede generar resultados no deseables, como ilustra el siguiente intento de realizar una comparación sin distinción entre mayúsculas y minúsculas de las cadenas "file" y "FILE".

[!code-csharp[Conceptual.Strings.BestPractices#11](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/turkish1.cs#11)]
[!code-vb[Conceptual.Strings.BestPractices#11](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/turkish1.vb#11)]

Esta comparación podría producir problemas importantes si la referencia cultural se usa involuntariamente en configuraciones que afectan a la seguridad, como en el ejemplo siguiente. Una llamada al método como `IsFileURI("file:")` devuelve `true` si la referencia cultural actual es inglés de EE. U.U., pero `false` si la referencia cultural actual es el turco. Así, en los sistemas turcos, alguien podría sortear las medidas de seguridad que bloquean el acceso a los URI sin distinción entre mayúsculas y minúsculas que comienzan con "FILE":.

[!code-csharp[Conceptual.Strings.BestPractices#12](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/turkish1.cs#12)]
[!code-vb[Conceptual.Strings.BestPractices#12](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/turkish1.vb#12)]

En este caso, como "file:" se debe interpretar como un identificador no lingüístico e independiente de la referencia cultural, el código se debe escribir como se muestra en el ejemplo siguiente:

[!code-csharp[Conceptual.Strings.BestPractices#13](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/turkish1.cs#13)]
[!code-vb[Conceptual.Strings.BestPractices#13](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/turkish1.vb#13)]

### <a name="ordinal-string-operations"></a>Operaciones de cadenas ordinales

Al especificar el valor <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> o <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> en una llamada al método, se indica una comparación no lingüística en la que se omiten las características de los lenguajes naturales. Los métodos que se invocan con estos valores <xref:System.StringComparison> basan las decisiones sobre las operaciones con cadenas en simples comparaciones de bytes en lugar de usos de mayúsculas y minúsculas o tablas de equivalencia parametrizadas por referencia cultural. En la mayoría de los casos, este enfoque se adapta mejor a la interpretación prevista de cadenas, y el código es más rápido y más confiable.

Las comparaciones ordinales son comparaciones de cadenas en las que cada byte de cada cadena se compara sin ninguna interpretación lingüística; por ejemplo, "windows" no coincide con "Windows". Esta es, esencialmente, una llamada a la función `strcmp` en tiempo de ejecución de C. Use esta comparación cuando el contexto indique que las cadenas deben coincidir exactamente o exija una directiva de coincidencia conservadora. Además, la comparación ordinal es la operación de comparación más rápida porque no aplica ninguna regla lingüística al determinar un resultado.

En .NET, las cadenas pueden contener caracteres nulos incrustados. Una de las diferencias más claras entre la comparación ordinal y dependiente de la referencia cultural (incluyendo las comparaciones que usan la referencia cultural de todos los idiomas) tiene que ver con el control de caracteres nulos incrustados en una cadena. Estos caracteres se omiten cuando usa métodos <xref:System.String.Compare%2A?displayProperty=nameWithType> y <xref:System.String.Equals%2A?displayProperty=nameWithType> para realizar comparaciones dependientes de la referencia cultural (incluyendo las comparaciones que usan la referencia cultural de todos los idiomas). Por tanto, en las comparaciones dependientes de la referencia cultural, las cadenas que contienen caracteres nulos incrustados pueden considerarse iguales que las cadenas que no los contienen.

> [!IMPORTANT]
> Aunque los métodos de comparación de cadenas hacen caso omiso de los caracteres nulos incrustados, los métodos de búsqueda de cadenas como <xref:System.String.Contains%2A?displayProperty=nameWithType>, <xref:System.String.EndsWith%2A?displayProperty=nameWithType>, <xref:System.String.IndexOf%2A?displayProperty=nameWithType>, <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType>y <xref:System.String.StartsWith%2A?displayProperty=nameWithType> sí los tienen en cuenta.

En el ejemplo siguiente se realiza una comparación dependiente de la referencia cultural de la cadena "Aa" con una cadena similar que contiene varios caracteres nulos insertados entre "A" y "a", y se muestra cómo las dos cadenas se consideran iguales:

[!code-csharp[Conceptual.Strings.BestPractices#19](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/embeddednulls1.cs#19)]
 [!code-vb[Conceptual.Strings.BestPractices#19](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/embeddednulls1.vb#19)]

Pero las cadenas no se consideran iguales cuando se usa la comparación ordinal, como se muestra en el ejemplo siguiente:
  
[!code-csharp[Conceptual.Strings.BestPractices#20](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/embeddednulls2.cs#20)]
[!code-vb[Conceptual.Strings.BestPractices#20](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/embeddednulls2.vb#20)]

Las comparaciones ordinales sin distinción entre mayúsculas y minúsculas son el siguiente enfoque más conservador. Estas comparaciones omiten la mayor parte del uso de mayúsculas y minúsculas; por ejemplo, "windows" coincide con "Windows". A la hora de tratar con caracteres ASCII, esta directiva es equivalente a <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>, salvo que omite el uso de mayúsculas y minúsculas habitual de ASCII. Por tanto, cualquier carácter de [A, Z] (\u0041-\u005A) coincide con el carácter correspondiente de [a, z] (\u0061-\007A). El uso de mayúsculas y minúsculas fuera del intervalo ASCII emplea las tablas de la referencia cultural de todos los idiomas. Por tanto, la siguiente comparación:

[!code-csharp[Conceptual.Strings.BestPractices#4](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/comparison2.cs#4)]
[!code-vb[Conceptual.Strings.BestPractices#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/comparison2.vb#4)]

es equivalente a esta comparación (pero más rápida):

[!code-csharp[Conceptual.Strings.BestPractices#5](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/comparison2.cs#5)]
[!code-vb[Conceptual.Strings.BestPractices#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/comparison2.vb#5)]

Estas comparaciones siguen siendo muy rápidas.

> [!NOTE]
> El comportamiento de las cadenas del sistema de archivos, claves del Registro y valores, y variables de entorno se representa mejor mediante <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType>.

Tanto <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> como <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> usan los valores binarios directamente y son más adecuados para la búsqueda de coincidencias. Si no sabe con seguridad qué configuración de comparación debe emplear, use uno de estos dos valores. Sin embargo, puesto que realizan una comparación byte a byte, no ordenan según un criterio de ordenación lingüístico (como un diccionario de inglés) sino según un criterio de ordenación binario. Los resultados pueden parecer extraños en la mayoría de los contextos si se muestran a los usuarios.

La semántica ordinal es el valor predeterminado para las sobrecargas de <xref:System.String.Equals%2A?displayProperty=nameWithType> que no incluyen un argumento <xref:System.StringComparison> (incluyendo el operador de igualdad). En cualquier caso, se recomienda llamar a una sobrecarga que tenga un parámetro <xref:System.StringComparison> .

### <a name="string-operations-that-use-the-invariant-culture"></a>Operaciones de cadenas que usan la referencia cultural invariable

Las comparaciones con la referencia cultural de todos los idiomas usan la propiedad <xref:System.Globalization.CultureInfo.CompareInfo%2A> devuelta por la propiedad estática <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> . Este comportamiento es igual en todos los sistemas; traduce cualquier carácter que esté fuera de su intervalo en lo que cree que son caracteres invariables equivalentes. Esta directiva puede ser útil para mantener un conjunto de comportamientos de las cadenas en distintas referencias culturales, pero a menudo proporciona resultados inesperados.

Las comparaciones sin distinción entre mayúsculas y minúsculas con la referencia cultural de todos los idiomas usan también la propiedad estática <xref:System.Globalization.CultureInfo.CompareInfo%2A> devuelta por la propiedad estática <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> para obtener información de comparación. Cualquier diferencia en el uso de mayúsculas y minúsculas entre estos caracteres traducidos se pasa por alto.

Las comparaciones que usan <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> y <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> funcionan de manera idéntica en cadenas ASCII. Sin embargo, <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> toma decisiones lingüísticas que podrían no ser adecuadas para las cadenas que tienen que interpretarse como un conjunto de bytes. El objeto `CultureInfo.InvariantCulture.CompareInfo` hace que el método <xref:System.String.Compare%2A> interprete ciertos conjuntos de caracteres como equivalentes. Por ejemplo, la siguiente equivalencia es válida en la referencia cultural de todos los idiomas:

InvariantCulture: a + ̊ = å

El carácter LETRA LATINA A MINÚSCULA "a" (\u0061), cuando está junto al carácter ANILLO SUPERIOR COMBINABLE "+ " ̊" (\u030a), se interpreta como el carácter LETRA LATINA MINÚSCULA A CON ANILLO SUPERIOR "å" (\u00e5). Como se muestra en el ejemplo siguiente, este comportamiento difiere de la comparación ordinal.

[!code-csharp[Conceptual.Strings.BestPractices#15](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/comparison3.cs#15)]
[!code-vb[Conceptual.Strings.BestPractices#15](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/comparison3.vb#15)]

A la hora de interpretar nombres de archivo, cookies u otros elementos donde pueda aparecer una combinación como "å", las comparaciones ordinales siguen ofreciendo el comportamiento más transparente y adecuado.

En conjunto, la referencia cultural de todos los idiomas tiene muy pocas propiedades que la hagan útil para la comparación. Realiza la comparación de manera lingüísticamente pertinente, lo que le impide garantizar una equivalencia simbólica completa, pero no es la opción ideal para la presentación en cualquier referencia cultural. Una de las pocas razones para usar <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType> con el fin de realizar una comparación es para conservar datos ordenados cuando se desea realizar una presentación idéntica transculturalmente. Por ejemplo, si un archivo de datos grande que contiene una lista de identificadores ordenados para su presentación acompaña una aplicación, al agregar datos a esta lista se necesitaría realizar una inserción con ordenación de estilo invariable.

## <a name="choosing-a-stringcomparison-member-for-your-method-call"></a>Elegir un miembro StringComparison para la llamada al método

En la tabla siguiente se describe la asignación del contexto de cadena semántico a un miembro de la enumeración <xref:System.StringComparison>:

|Datos|Comportamiento|Valor de System.StringComparison<br /><br /> value|
|----------|--------------|-----------------------------------------------------|
|Identificadores internos con distinción entre mayúsculas y minúsculas.<br /><br /> Identificadores con distinción entre mayúsculas y minúsculas en estándares como XML y HTTP.<br /><br /> Configuraciones relacionadas con la seguridad con distinción entre mayúsculas y minúsculas.|Identificador no lingüístico, donde los bytes coinciden exactamente.|<xref:System.StringComparison.Ordinal>|
|Identificadores internos sin distinción entre mayúsculas y minúsculas.<br /><br /> Identificadores sin distinción entre mayúsculas y minúsculas en estándares como XML y HTTP.<br /><br /> Rutas de acceso a archivos.<br /><br /> Claves del Registro y valores.<br /><br /> Variables de entorno.<br /><br /> Identificadores de recursos (por ejemplo, nombres de identificadores).<br /><br /> Configuraciones relacionadas con la seguridad sin distinción entre mayúsculas y minúsculas.|Identificador no lingüístico, donde el uso de mayúsculas y minúsculas no es pertinente; especialmente datos almacenados en la mayoría de los servicios del sistema de Windows.|<xref:System.StringComparison.OrdinalIgnoreCase>|
|Algunos datos almacenados lingüísticamente pertinentes.<br /><br /> Presentación de datos lingüísticos que necesitan un criterio de ordenación fijo.|Datos válidos culturalmente que siguen siendo lingüísticamente pertinentes.|<xref:System.StringComparison.InvariantCulture><br /><br /> o bien<br /><br /> <xref:System.StringComparison.InvariantCultureIgnoreCase>|
|Datos mostrados al usuario.<br /><br /> La mayoría de los datos proporcionados por el usuario.|Datos que necesitan personalizaciones lingüísticas locales.|<xref:System.StringComparison.CurrentCulture><br /><br /> o bien<br /><br /> <xref:System.StringComparison.CurrentCultureIgnoreCase>|

## <a name="common-string-comparison-methods-in-net"></a>Métodos comunes de comparación de cadenas en .NET

En las secciones siguientes se describen los métodos que se usan con más frecuencia para la comparación de cadenas.

### <a name="stringcompare"></a>String.Compare

Interpretación predeterminada: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Al ser la operación fundamental para la interpretación de cadenas, todas las instancias de estas llamadas al método se deben examinar para determinar si las cadenas se deben interpretar según la referencia cultural actual o se deben separar de la referencia cultural (simbólicamente). Normalmente, se trata del último caso y se debe usar en su lugar una comparación <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> .

La clase <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> , devuelta por la propiedad <xref:System.Globalization.CultureInfo.CompareInfo%2A?displayProperty=nameWithType> , también incluye un método <xref:System.Globalization.CompareInfo.Compare%2A> que proporciona un gran número de opciones de coincidencia (ordinal, omitir el espacio en blanco, omitir el tipo de kana, etc.) por medio de la enumeración de marca <xref:System.Globalization.CompareOptions> .

### <a name="stringcompareto"></a>String.CompareTo

Interpretación predeterminada: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Este método no ofrece actualmente una sobrecarga que especifique un tipo <xref:System.StringComparison> . Normalmente es posible convertir este método en el formato recomendado del método <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> .

Los tipos que implementan interfaces <xref:System.IComparable> y <xref:System.IComparable%601> implementan este método. Puesto que no ofrece la opción de un parámetro <xref:System.StringComparison> , la implementación de tipos suele permitir al usuario especificar <xref:System.StringComparer> en su constructor. En el ejemplo siguiente se define una clase `FileName` cuyo constructor de clase incluye un parámetro <xref:System.StringComparer> . Este objeto <xref:System.StringComparer> se usa entonces en el método `FileName.CompareTo` .

[!code-csharp[Conceptual.Strings.BestPractices#6](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/api1.cs#6)]
[!code-vb[Conceptual.Strings.BestPractices#6](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/api1.vb#6)]

### <a name="stringequals"></a>String.Equals

Interpretación predeterminada: <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>.

La clase <xref:System.String> le permite comprobar la igualdad llamando a las sobrecargas de método estático o de instancia <xref:System.String.Equals%2A> , o usando el operador de igualdad estático. Las sobrecargas y el operador usan la comparación ordinal de forma predeterminada. Sin embargo, todavía sigue siendo recomendable llamar a una sobrecarga que especifique explícitamente el tipo <xref:System.StringComparison> aunque desee realizar una comparación ordinal; esto facilita la búsqueda de cierta interpretación de la cadena en el código.

### <a name="stringtoupper-and-stringtolower"></a>String.ToUpper y String.ToLower

Interpretación predeterminada: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Debe tener cuidado al usar estos métodos, ya que forzar que una cadena esté en mayúsculas o en minúsculas se usa a menudo como una pequeña normalización para comparar cadenas independientemente del uso de mayúsculas y minúsculas. En tal caso, considere la posibilidad de emplear una comparación sin distinción entre mayúsculas y minúsculas.

También están disponibles los métodos <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> y <xref:System.String.ToLowerInvariant%2A?displayProperty=nameWithType> . <xref:System.String.ToUpperInvariant%2A> es la manera estándar de normalizar el uso de mayúsculas y minúsculas. Las comparaciones realizadas mediante <xref:System.StringComparison.OrdinalIgnoreCase?displayProperty=nameWithType> tienen un comportamiento que es la composición de dos llamadas: llamar a <xref:System.String.ToUpperInvariant%2A> en ambos argumentos de cadena y realizar una comparación mediante <xref:System.StringComparison.Ordinal?displayProperty=nameWithType>.

También hay sobrecargas para convertir a mayúsculas y minúsculas en una referencia cultural concreta, pasando al método un objeto <xref:System.Globalization.CultureInfo> que representa esa referencia cultural.

### <a name="chartoupper-and-chartolower"></a>Char.ToUpper y Char.ToLower

Interpretación predeterminada: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Estos métodos funcionan de manera similar a los métodos <xref:System.String.ToUpper%2A?displayProperty=nameWithType> y <xref:System.String.ToLower%2A?displayProperty=nameWithType> descritos en la sección anterior.

### <a name="stringstartswith-and-stringendswith"></a>String.StartsWith y String.EndsWith

Interpretación predeterminada: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

De forma predeterminada, estos dos métodos realizan una comparación dependiente de la referencia cultural.

### <a name="stringindexof-and-stringlastindexof"></a>String.IndexOf y String.LastIndexOf

Interpretación predeterminada: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

No hay coherencia en cómo las sobrecargas predeterminadas de estos métodos realizan las comparaciones. Todos los métodos <xref:System.String.IndexOf%2A?displayProperty=nameWithType> y <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> que incluyen un parámetro <xref:System.Char> realizan una comparación ordinal, pero los métodos <xref:System.String.IndexOf%2A?displayProperty=nameWithType> y <xref:System.String.LastIndexOf%2A?displayProperty=nameWithType> predeterminados que incluyen un parámetro <xref:System.String> realizan una comparación dependiente de la referencia cultural.

Si llama al método <xref:System.String.IndexOf%28System.String%29?displayProperty=nameWithType> o <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> y le pasa una cadena para ubicar en la instancia actual, se recomienda llamar a una sobrecarga que especifique explícitamente el tipo <xref:System.StringComparison> . Las sobrecargas que incluyen un argumento <xref:System.Char> no le permiten especificar un tipo <xref:System.StringComparison> .

## <a name="methods-that-perform-string-comparison-indirectly"></a>Métodos que realizan la comparación de cadenas indirectamente

Algunos métodos sin cadenas que tienen la comparación de cadenas como operación fundamental usan el tipo <xref:System.StringComparer> . La clase <xref:System.StringComparer> incluye seis propiedades estáticas que devuelven instancias de <xref:System.StringComparer> cuyos métodos <xref:System.StringComparer.Compare%2A?displayProperty=nameWithType> realizan los siguientes tipos de comparaciones de cadenas:

- Comparaciones de cadenas dependientes de la referencia cultural usando la referencia cultural actual. Este objeto <xref:System.StringComparer> está devuelto por la propiedad <xref:System.StringComparer.CurrentCulture%2A?displayProperty=nameWithType> .
- Comparaciones sin distinción entre mayúsculas y minúsculas usando la referencia cultural actual. Este objeto <xref:System.StringComparer> está devuelto por la propiedad <xref:System.StringComparer.CurrentCultureIgnoreCase%2A?displayProperty=nameWithType> .
- Comparaciones independientes de la referencia cultural usando las reglas de comparación de palabras de la referencia cultural de todos los idiomas. Este objeto <xref:System.StringComparer> está devuelto por la propiedad <xref:System.StringComparer.InvariantCulture%2A?displayProperty=nameWithType> .
- Comparaciones sin distinción entre mayúsculas y minúsculas e independientes de la referencia cultural usando las reglas de comparación de palabras de la referencia cultural de todos los idiomas. Este objeto <xref:System.StringComparer> está devuelto por la propiedad <xref:System.StringComparer.InvariantCultureIgnoreCase%2A?displayProperty=nameWithType> .
- Comparación ordinal. Este objeto <xref:System.StringComparer> está devuelto por la propiedad <xref:System.StringComparer.Ordinal%2A?displayProperty=nameWithType> .
- Comparación ordinal sin distinción entre mayúsculas y minúsculas. Este objeto <xref:System.StringComparer> está devuelto por la propiedad <xref:System.StringComparer.OrdinalIgnoreCase%2A?displayProperty=nameWithType> .

### <a name="arraysort-and-arraybinarysearch"></a>Array.Sort y Array.BinarySearch

Interpretación predeterminada: <xref:System.StringComparison.CurrentCulture?displayProperty=nameWithType>.

Cuando se almacenan datos en una colección, o cuando se leen datos almacenados de un archivo o una base de datos en una colección, el cambio de la referencia cultural actual puede invalidar los valores invariables de la colección. El método <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> supone que los elementos de la matriz que se van a buscar ya están ordenados. Para ordenar cualquier elemento de cadena de la matriz, el método <xref:System.Array.Sort%2A?displayProperty=nameWithType> llama al método <xref:System.String.Compare%2A?displayProperty=nameWithType> para ordenar los elementos individuales. El uso de un comparador dependiente de la referencia cultural puede ser peligroso si la referencia cultural cambia desde que se ordena la matriz hasta que se busca en su contenido. Por ejemplo, en el código siguiente, el almacenamiento y la recuperación funcionan en el comparador que la propiedad `Thread.CurrentThread.CurrentCulture` . Si la referencia cultural puede cambiar entre las llamadas a `StoreNames` y `DoesNameExist`, y especialmente si el contenido de la matriz se conserva en alguna parte entre las dos llamadas al método, se puede producir un error en la búsqueda binaria.

[!code-csharp[Conceptual.Strings.BestPractices#7](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/indirect1.cs#7)]
 [!code-vb[Conceptual.Strings.BestPractices#7](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/indirect1.vb#7)]

Aparece una variación recomendada en el ejemplo siguiente, que usa el mismo método de comparación ordinal (independiente de la referencia cultural) para ordenar y buscar en la matriz. El código cambiado se refleja en las líneas etiquetadas como `Line A` y `Line B` en los dos ejemplos.

[!code-csharp[Conceptual.Strings.BestPractices#8](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/indirect1.cs#8)]
[!code-vb[Conceptual.Strings.BestPractices#8](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/indirect1.vb#8)]

Si estos datos se conservan y mueven entre distintas referencias culturales, y se usa la ordenación para presentar estos datos al usuario, es mejor usar <xref:System.StringComparison.InvariantCulture?displayProperty=nameWithType>, que funciona lingüísticamente para obtener una mejor salida para el usuario pero no se ve afectado por los cambios en la referencia cultural. En el ejemplo siguiente se modifican los dos ejemplos anteriores para usar la referencia cultural de todos los idiomas con el fin de ordenar y buscar en la matriz.

[!code-csharp[Conceptual.Strings.BestPractices#9](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/indirect1.cs#9)]
[!code-vb[Conceptual.Strings.BestPractices#9](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/indirect1.vb#9)]

### <a name="collections-example-hashtable-constructor"></a>Ejemplo de colecciones: Constructor de tablas hash

Al aplicar un algoritmo hash a las cadenas se proporciona un segundo ejemplo de una operación que se ve afectada por la forma en que se comparan las cadenas.

En el ejemplo siguiente se crea una instancia de un objeto <xref:System.Collections.Hashtable> pasándole el objeto <xref:System.StringComparer> devuelto por la propiedad <xref:System.StringComparer.OrdinalIgnoreCase%2A?displayProperty=nameWithType> . Puesto que una clase <xref:System.StringComparer> que se deriva de <xref:System.StringComparer> implementa la interfaz <xref:System.Collections.IEqualityComparer> , su método <xref:System.Collections.IEqualityComparer.GetHashCode%2A> se usa para calcular el código hash de cadenas de la tabla hash.

[!code-csharp[Conceptual.Strings.BestPractices#10](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/indirect2.cs#10)]
[!code-vb[Conceptual.Strings.BestPractices#10](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/indirect2.vb#10)]

## <a name="displaying-and-persisting-formatted-data"></a>Mostrar y conservar datos con formato

Cuando muestre a los usuarios datos que no sean de cadena, como números, y fechas y horas, asígneles formato mediante la configuración de la referencia cultural del usuario. De forma predeterminada, los siguientes elementos usan la referencia cultural del subproceso actual al dar formato a las operaciones:

- Cadenas interpoladas compatibles con los compiladores [C#](../../csharp/language-reference/tokens/interpolated.md) y [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md).
- Operaciones de concatenación de cadenas que usan los operadores de concatenación [C#](../../csharp/language-reference/operators/addition-operator.md#string-concatenation) o [Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md ), o que llaman al método <xref:System.String.Concat%2A?displayProperty=nameWithType> directamente.
- El método <xref:System.String.Format%2A?displayProperty=nameWithType> .
- Métodos `ToString` de los tipos numéricos y tipos de fecha y hora.

Para especificar explícitamente que se debe dar formato a una cadena mediante las convenciones de una referencia cultural nombrada o la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture), se puede hacer lo siguiente:

- Cuando se usen los métodos <xref:System.String.Format%2A?displayProperty=nameWithType> y `ToString`, llame a una sobrecarga que tenga un parámetro `provider`, como <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> o <xref:System.DateTime.ToString%28System.IFormatProvider%29?displayProperty=nameWithType>, y pásela a la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>, a una instancia <xref:System.Globalization.CultureInfo> que represente la referencia cultural que se quiera o a la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType>.

- Para la concatenación de cadenas, no permita que el compilador realice ninguna de las conversiones implícitas. En su lugar, realice una conversión explícita mediante una llamada a una sobrecarga `ToString` que tenga un parámetro `provider`. Por ejemplo, el compilador utiliza implícitamente la referencia cultural actual cuando convierte un valor <xref:System.Double> en una cadena en el código de C# siguiente:

  [!code-csharp[Implicit String Conversion](~/samples/snippets/standard/base-types/string-practices/cs/tostring.cs#1)]

  En su lugar, se puede especificar explícitamente la referencia cultural cuyas convenciones de formato se usan en la conversión mediante una llamada al método <xref:System.Double.ToString(System.IFormatProvider)?displayProperty=nameWithType>, tal como hace el código de C# siguiente:

  [!code-csharp[Explicit String Conversion](~/samples/snippets/standard/base-types/string-practices/cs/tostring.cs#2)]

- Para la interpolación de cadenas, en lugar de asignar una cadena interpolada a una instancia <xref:System.String>, asígnela a un elemento <xref:System.FormattableString>. Después, se puede llamar al método <xref:System.FormattableString.ToString?displayProperty=nameWithType> para generar una cadena de resultado que refleje las convenciones de la referencia cultural actual, o bien puede llamar al método <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> para generar una cadena de resultado que refleje las convenciones de la referencia cultural especificada. También se puede pasar la cadena que admite formato al método estático <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> con el fin de generar una cadena de resultado que refleje las convenciones de la referencia cultural invariable. En el ejemplo siguiente se muestra este enfoque. (La salida del ejemplo refleja una referencia cultural actual de en-US).

  [!code-csharp[String interpolation](~/samples/snippets/standard/base-types/string-practices/cs/formattable.cs)]
  [!code-vb[String interpolation](~/samples/snippets/standard/base-types/string-practices/vb/formattable.vb)]

Puede conservar datos que no son de cadena como datos binarios o como datos con formato. Si decide guardarlos como datos con formato, debe llamar a una sobrecarga del método de formato que incluya un parámetro `provider` y pasarle la propiedad <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> . La referencia cultural de todos los idiomas proporciona un formato coherente para los datos con formato que es independiente de la referencia cultural y del equipo. En cambio, si se conservan datos a los que se aplica formato con referencias culturales distintas de la referencia cultural de todos los idiomas, se presentan varias limitaciones:

- Es probable que los datos no puedan usarse si se recuperan en un sistema que tiene una referencia cultural distinta, o si el usuario del sistema actual cambia la referencia cultural actual e intenta recuperar los datos.
- Las propiedades de una referencia cultural en un equipo específico pueden diferir de los valores estándar. En cualquier momento, un usuario puede personalizar la configuración de visualización que depende de la cultural. Debido a esto, es posible que los datos con formato que se guardan en un sistema no sean legibles después de que el usuario personalice la configuración de la referencia cultural. Es posible que la portabilidad de los datos con formato entre equipos sea incluso más limitada.
- Las normas internacionales, regionales o nacionales que rigen el formato de los números o las fechas y horas cambian con el tiempo, y estos cambios se incorporan en las actualizaciones de los sistemas operativos Windows. Cuando cambian las convenciones de formato, los datos a los que se aplicó formato usando las convenciones anteriores pueden llegar a ser ilegibles.

En el ejemplo siguiente se muestra la portabilidad limitada que se deriva de usar el formato dependiente de la referencia cultural para conservar los datos. En el ejemplo se guarda una matriz de valores de fecha y hora en un archivo. Se les da formato con las convenciones de la referencia cultural Inglés (Estados Unidos). Después de que la aplicación cambie la referencia cultural del subproceso actual a Francés (Suiza), intenta leer los valores guardados usando las convenciones de formato de la referencia cultural actual. El intento de leer dos de los elementos de datos genera una excepción <xref:System.FormatException> y la matriz de fechas ahora contiene dos elementos incorrectos que iguales a <xref:System.DateTime.MinValue>.

[!code-csharp[Conceptual.Strings.BestPractices#21](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.strings.bestpractices/cs/persistence.cs#21)]
[!code-vb[Conceptual.Strings.BestPractices#21](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.strings.bestpractices/vb/persistence.vb#21)]

Pero si reemplaza la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> por <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> en las llamadas a <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> y a <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, los datos persistentes de fecha y hora se restauran correctamente, como se muestra en la salida siguiente:

```console
06.05.1758 21:26
05.05.1818 07:19
22.04.1870 23:54
08.09.1890 06:47
18.02.1905 15:12
```

## <a name="see-also"></a>Vea también

- [Manipular cadenas](manipulating-strings.md)
