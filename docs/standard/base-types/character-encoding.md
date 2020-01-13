---
title: Codificación de caracteres de .NET
description: Obtenga información sobre la codificación y descodificación de caracteres en .NET.
ms.date: 12/22/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoding, understanding
- encoding, choosing
- encoding, fallback strategy
ms.assetid: bf6d9823-4c2d-48af-b280-919c5af66ae9
ms.openlocfilehash: 3cd461d8c56c3f31bf3ffe04acf239ecd32fe328
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711446"
---
# <a name="character-encoding-in-net"></a>Codificación de caracteres de .NET

Los caracteres son entidades abstractas que se pueden representar de muchas maneras diferentes. Una codificación de caracteres es un sistema que empareja cada carácter de un juego de caracteres compatible con algún valor que representa ese carácter. Por ejemplo, el código Morse es una codificación de caracteres que empareja cada carácter del alfabeto latino con un patrón de puntos y guiones que son adecuados para la transmisión a través de las líneas de telégrafo. Una codificación de caracteres para los equipos empareja cada carácter de un juego de caracteres compatible con un valor numérico que representa ese carácter. Una codificación de caracteres tiene dos componentes distintos:

- Un codificador, que traduce una secuencia de caracteres en una secuencia de valores numéricos (bytes).

- Un descodificador, que traduce una secuencia de bytes en una secuencia de caracteres.

La codificación de caracteres describe las reglas por las que funcionan un codificador y un descodificador. Por ejemplo, la clase <xref:System.Text.UTF8Encoding> describe las reglas para codificar y descodificar del Formato de transformación Unicode de 8 bits (UTF-8), que usa de uno a cuatro bytes para representar un único carácter Unicode. La codificación y la descodificación también pueden incluir validación. Por ejemplo, la clase <xref:System.Text.UnicodeEncoding> comprueba todos los suplentes para asegurarse de que constituyen pares suplentes válidos. (Un par suplente consta de un carácter con un punto de código que va de U+D800 a U+DBFF, seguido de un carácter con un punto de código que va de U+DC00 a U+DFFF.)  Una estrategia de reserva determina cómo trata un codificador los caracteres no válidos o cómo trata un descodificador los bytes no válidos.

> [!WARNING]
> Las clases de codificación de .NET proporcionan una manera de almacenar y convertir datos de caracteres. No se deben usar para almacenar datos binarios en formato de cadena. Dependiendo de la codificación empleada, la conversión de datos binarios al formato de cadena con las clases de codificación puede presentar un comportamiento inesperado y mostrar datos inexactos o dañados. Para convertir datos binarios en un formato de cadena, use el método <xref:System.Convert.ToBase64String%2A?displayProperty=nameWithType> .

.NET usa la codificación UTF-16 (representada por la clase <xref:System.Text.UnicodeEncoding>) para representar caracteres y cadenas. Las aplicaciones cuyo destino es Common Language Runtime usan descodificadores para asignar representaciones de caracteres Unicode admitidas por Common Language Runtime a otros esquemas de codificación. Usan descodificadores para asignar caracteres de codificaciones no Unicode a Unicode.

Este tema consta de las siguientes secciones:

- [Codificaciones de .NET](../../../docs/standard/base-types/character-encoding.md#Encodings)

- [Seleccionar una clase de codificación](../../../docs/standard/base-types/character-encoding.md#Selecting)

- [Usar un objeto de codificación](../../../docs/standard/base-types/character-encoding.md#Using)

- [Elegir una estrategia de reinterpretación](../../../docs/standard/base-types/character-encoding.md#FallbackStrategy)

- [Implementing a Custom Fallback Strategy](../../../docs/standard/base-types/character-encoding.md#Custom)

<a name="Encodings"></a>

## <a name="encodings-in-net"></a>Codificaciones de .NET

Todas las clases de codificación de caracteres de .NET heredan de la clase <xref:System.Text.Encoding?displayProperty=nameWithType>, que es una clase abstracta que define la funcionalidad común a todas las codificaciones de caracteres. Para acceder a los objetos individuales de codificación implementados en .NET, haga lo siguiente:

- Use las propiedades estáticas de la clase <xref:System.Text.Encoding>, que devuelven objetos que representan las codificaciones de caracteres estándar disponibles en .NET (ASCII, UTF-7, UTF-8, UTF-16 y UTF-32). Por ejemplo, la propiedad <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> devuelve un objeto <xref:System.Text.UnicodeEncoding> : Cada objeto usa la reserva de reemplazo para controlar las cadenas que no puede codificar y los bytes que no puede descodificar. (Para obtener más información, vea la sección [Replacement Fallback](../../../docs/standard/base-types/character-encoding.md#Replacement) ).

- Llame al constructor de clase de la codificación. Se pueden crear instancias de los objetos para las codificaciones ASCII, UTF-7, UTF-8, UTF-16 y UTF-32 de esta manera. De forma predeterminada, cada objeto usa la reserva de reemplazo para controlar las cadenas que no puede codificar y los bytes que no puede descodificar, pero puede especificar que se debe producir una excepción en su lugar. (Para obtener más información, vea las secciones [Replacement Fallback](../../../docs/standard/base-types/character-encoding.md#Replacement) y [Exception Fallback](../../../docs/standard/base-types/character-encoding.md#Exception) ).

- Llame al constructor <xref:System.Text.Encoding.%23ctor%28System.Int32%29?displayProperty=nameWithType> y pásele un entero que represente la codificación. Los objetos de codificación estándar usan la reserva de reemplazo, y los objetos de codificación para la página de códigos y el juego de caracteres de doble byte (DBCS) usan el retroceso de ajuste perfecto para controlar las cadenas que no pueden codificar y los bytes que no pueden descodificar. (Para obtener más información, vea la sección [Best-Fit Fallback](../../../docs/standard/base-types/character-encoding.md#BestFit) ).

- Llame al método <xref:System.Text.Encoding.GetEncoding%2A?displayProperty=nameWithType>, que devuelve cualquier estándar, página de códigos o codificación DBCS disponible en .NET. Las sobrecargas permiten especificar un objeto de reserva para el codificador y para el descodificador.

> [!NOTE]
> El estándar Unicode asigna un punto de código (un número) y un nombre a cada carácter en todos los scripts admitidos. Por ejemplo, el carácter "A" está representado por el punto de código U+0041 y el nombre "LATIN CAPITAL LETTER A". Las codificaciones de Formato de transformación Unicode (UTF) definen formas de codificar ese punto de código en una secuencia de uno o más bytes. Un esquema de codificación Unicode simplifica el desarrollo de aplicaciones de uso internacional porque permite que los caracteres de cualquier juego de caracteres estén representados en una única codificación. Los desarrolladores de aplicaciones ya no tienen que realizar el seguimiento del esquema de codificación empleado para producir caracteres para un idioma o un sistema de escritura concreto, y se pueden compartir los datos internacionalmente entre sistemas sin dañarlos.
>
> .NET admite tres codificaciones definidas por el estándar Unicode: UTF-8, UTF-16 y UTF-32. Para obtener más información, vea el estándar Unicode en la [página principal de Unicode](https://www.unicode.org/).

Se puede recuperar información sobre todas las codificaciones disponibles en .NET llamando al método <xref:System.Text.Encoding.GetEncodings%2A?displayProperty=nameWithType>. .NET admite los sistemas de codificación de caracteres que se muestran en la tabla siguiente.

|Codificación|Clase|Descripción|Ventajas y desventajas|
|--------------|-----------|-----------------|-------------------------------|
|ASCII|<xref:System.Text.ASCIIEncoding>|Codifica un intervalo limitado de caracteres usando los siete bits inferiores de un byte.|Como esta codificación solo admite valores de caracteres de U+0000 a U+007F, en la mayoría de los casos no resulta suficiente para aplicaciones de uso internacional.|
|UTF-7|<xref:System.Text.UTF7Encoding>|Representa los caracteres como secuencias de caracteres ASCII de 7 bits. Los caracteres Unicode no ASCII se representan con una secuencia de escape de caracteres ASCII.|UTF-7 admite protocolos como los protocolos de correo electrónico y de grupos de noticias. Sin embargo, la codificación UTF-7 no es particularmente segura ni sólida. En algunos casos, cambiar un bit puede modificar radicalmente la interpretación de toda una cadena UTF-7. En otros casos, diferentes cadenas UTF-7 pueden codificar el mismo texto. Para las secuencias que incluyen caracteres no ASCII, UTF-7 necesita más espacio que UTF-8, y la codificación y descodificación son más lentas. Por tanto, debe usar UTF-8 en lugar de UTF-7 si es posible.|
|UTF-8|<xref:System.Text.UTF8Encoding>|Representa cada punto de código Unicode como una secuencia de uno a cuatro bytes.|UTF-8 admite tamaños de datos de 8 bits y funciona bien con muchos sistemas operativos existentes. Para el intervalo ASCII de caracteres, UTF-8 es idéntico a la codificación ASCII y permite un conjunto mayor de caracteres. Sin embargo, para los scripts de Chino-Japonés-Coreano (CJK), UTF-8 puede necesitar tres bytes para cada carácter y puede generar tamaños de datos mayores que UTF-16. Tenga en cuenta que, algunas veces, la cantidad de datos ASCII, como las etiquetas HTML, justifica el mayor tamaño para el intervalo de CJK.|
|UTF-16|<xref:System.Text.UnicodeEncoding>|Representa cada punto de código Unicode como una secuencia de uno o dos enteros de 16 bits. La mayoría de los caracteres Unicode comunes solo necesitan un punto de código UTF-16, aunque los caracteres Unicode suplementarios (U+10000 y posteriores) necesitan dos puntos de código UTF-16 suplentes. Se admiten tanto el orden de bytes little-endian como el big-endian.|Common Language Runtime usa la codificación UTF-16 para representar valores de tipo <xref:System.Char> y <xref:System.String> , y el sistema operativo Windows la usa para representar valores de tipo `WCHAR` .|
|UTF-32|<xref:System.Text.UTF32Encoding>|Representa cada punto de código Unicode como un entero de 32 bits. Se admiten tanto el orden de bytes little-endian como el big-endian.|La codificación UTF-32 se usa cuando las aplicaciones desean evitar el comportamiento de punto de código suplente de la codificación UTF-16 en sistemas operativos para los que el espacio codificado es muy importante. Los glifos únicos representados en una pantalla aún se pueden codificar con más de un carácter UTF-32.|
|Codificaciones ANSI/ISO||Proporciona compatibilidad con diversas páginas de códigos. En los sistemas operativos Windows, las páginas de códigos se usan para admitir un idioma o un grupo de idiomas concreto. Para obtener una tabla que muestra las páginas de códigos admitidas por .NET, vea la clase <xref:System.Text.Encoding>. Puede recuperar un objeto de codificación para una página de códigos determinada llamando al método <xref:System.Text.Encoding.GetEncoding%28System.Int32%29?displayProperty=nameWithType> .|Una página de códigos contiene 256 puntos de código y se basa en cero. En la mayoría de las páginas de códigos, los puntos de código 0 a 127 representan el juego de caracteres ASCII y los puntos de código 128 a 255 difieren de forma significativa entre las páginas de códigos. Por ejemplo, la página de códigos 1252 proporciona los caracteres para los sistemas de escritura latinos, incluidos el inglés, el alemán y el francés. Los últimos 128 puntos de código de la página de códigos 1252 contienen los caracteres de acento. La página de códigos 1253 proporciona códigos de caracteres necesarios en el sistema de escritura griego. Los últimos 128 puntos de código de la página de códigos 1253 contienen los caracteres griegos. Como resultado, una aplicación que se basa en páginas de códigos ANSI no puede almacenar griego y alemán en la misma secuencia de texto a menos que incluya un identificador que indique la página de códigos a la que se hace referencia.|
|Codificaciones de juegos de caracteres de doble byte (DBCS)||Admite idiomas que contienen más de 256 caracteres, como el chino, el japonés y el coreano. En un DBCS, un par de puntos de código (un byte doble) representa cada carácter. La propiedad <xref:System.Text.Encoding.IsSingleByte%2A?displayProperty=nameWithType> devuelve `false` para las codificaciones DBCS. Puede recuperar un objeto de codificación para un DBCS determinado llamando al método <xref:System.Text.Encoding.GetEncoding%28System.Int32%29?displayProperty=nameWithType> .|En un DBCS, un par de puntos de código (un byte doble) representa cada carácter. Cuando una aplicación controla datos DBCS, el primer byte de un carácter DBCS (el byte inicial) se procesa junto con el byte final que le sigue inmediatamente. Puesto que un único par de puntos de código de doble byte puede representar caracteres diferentes dependiendo de la página de códigos, este esquema aún no permite la combinación de dos idioma, como el japonés y el chino, en el mismo flujo de datos.|

Estas codificaciones permiten trabajar con caracteres Unicode, así como con codificaciones que son las más usadas en aplicaciones heredadas. Además, puede crear una codificación personalizada definiendo una clase que se deriva de <xref:System.Text.Encoding> e invalidar sus miembros.

### <a name="platform-notes-net-core"></a>Notas de la plataforma: .NET Core

De manera predeterminada, .NET Core no pone a disposición codificaciones de páginas de código que no sean la página de códigos 28591 y las codificaciones Unicode, como UTF-8 y UTF-16. Sin embargo, puede agregar que las codificaciones de páginas de código que se encuentran en las aplicaciones estándar de Windows que tienen como destino .NET a la aplicación. Para obtener información completa, consulte el tema <xref:System.Text.CodePagesEncodingProvider> .

<a name="Selecting"></a>

## <a name="selecting-an-encoding-class"></a>Seleccionar una clase de codificación

Si tiene la oportunidad de elegir la codificación que se usará en la aplicación, debe usar una codificación Unicode, preferiblemente <xref:System.Text.UTF8Encoding> o <xref:System.Text.UnicodeEncoding>. (.NET también admite una tercera codificación Unicode, <xref:System.Text.UTF32Encoding>).

Si piensa usar una codificación ASCII (<xref:System.Text.ASCIIEncoding>), elija <xref:System.Text.UTF8Encoding> en su lugar. Las dos codificaciones son idénticas para el juego de caracteres ASCII, pero <xref:System.Text.UTF8Encoding> presenta las ventajas siguientes:

- Puede representar todos los caracteres Unicode, mientras que <xref:System.Text.ASCIIEncoding> solo admite los valores de caracteres Unicode entre U+0000 y U+007F.

- Proporciona detección de errores y una mayor seguridad.

- Se ha mejorado en materia de velocidad y debe ser más rápida que cualquier otra codificación. Incluso cuando todo el contenido es ASCII, las operaciones realizadas con <xref:System.Text.UTF8Encoding> son más rápidas que las operaciones realizadas con <xref:System.Text.ASCIIEncoding>.

Debe considerar la posibilidad de usar <xref:System.Text.ASCIIEncoding> solo para las aplicaciones heredadas. Sin embargo, incluso para las aplicaciones heredadas, <xref:System.Text.UTF8Encoding> podría ser una opción mejor por las razones siguientes (suponiendo la configuración predeterminada):

- Si la aplicación tiene contenido que no es estrictamente ASCII y lo codifica con <xref:System.Text.ASCIIEncoding>, cada carácter no ASCII se codifica como un signo de interrogación (?). Si la aplicación descodifica después estos datos, la información se pierde.

- Si la aplicación tiene contenido que no es estrictamente ASCII y lo codifica con <xref:System.Text.UTF8Encoding>, el resultado parece ininteligible si se interpreta como ASCII. Sin embargo, si la aplicación usa un descodificador UTF-8 para descodificar estos datos, los datos realizan una acción de ida y vuelta correctamente.

En una aplicación web, los caracteres enviados al cliente como respuesta a una solicitud web deben reflejar la codificación empleada en el cliente. En la mayoría de los casos, debe establecer la propiedad <xref:System.Web.HttpResponse.ContentEncoding%2A?displayProperty=nameWithType> en el valor devuelto por la propiedad <xref:System.Web.HttpRequest.ContentEncoding%2A?displayProperty=nameWithType> para mostrar el texto en la codificación que el usuario espera.

<a name="Using"></a>

## <a name="using-an-encoding-object"></a>Usar un objeto de codificación

Un codificador convierte una cadena de caracteres (normalmente, caracteres Unicode) en su equivalente numérico (bytes). Por ejemplo, podría usar un codificador ASCII para convertir caracteres Unicode en ASCII de forma que se puedan mostrar en la consola. Para realizar la conversión, se llama al método <xref:System.Text.Encoding.GetBytes%2A?displayProperty=nameWithType> . Si desea determinar cuántos bytes son necesarios para almacenar los caracteres codificados antes de realizar la codificación, puede llamar al método <xref:System.Text.Encoding.GetByteCount%2A> .

En el ejemplo siguiente se usa una única matriz de bytes para codificar cadenas en dos operaciones independientes. Mantiene un índice que indica la posición inicial de la matriz de bytes para el siguiente conjunto de bytes codificados con ASCII. Llama al método <xref:System.Text.ASCIIEncoding.GetByteCount%28System.String%29?displayProperty=nameWithType> para asegurarse de que la matriz de bytes es suficiente para alojar la cadena codificada. A continuación, llama al método <xref:System.Text.ASCIIEncoding.GetBytes%28System.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Byte%5B%5D%2CSystem.Int32%29?displayProperty=nameWithType> para codificar los caracteres de la cadena.

[!code-csharp[Conceptual.Encoding#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/getbytes1.cs#8)]
[!code-vb[Conceptual.Encoding#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/getbytes1.vb#8)]

Un descodificador convierte una matriz de bytes que refleja una codificación de caracteres determinada en un juego de caracteres, ya sea en una matriz de caracteres o en una cadena. Para descodificar una matriz de bytes en una matriz de caracteres, se llama al método <xref:System.Text.Encoding.GetChars%2A?displayProperty=nameWithType> . Para descodificar una matriz de bytes en una cadena, se llama al método <xref:System.Text.Encoding.GetString%2A> . Si desea determinar cuántos caracteres son necesarios para almacenar los bytes descodificados antes de realizar la descodificación, puede llamar al método <xref:System.Text.Encoding.GetCharCount%2A> .

En el ejemplo siguiente se codifican tres cadenas y después se descodifican en una sola matriz de caracteres. Se mantiene un índice que indica la posición inicial de la matriz de caracteres para el siguiente juego de caracteres descodificados. Se llama al método <xref:System.Text.ASCIIEncoding.GetCharCount%2A> para asegurarse de que la matriz de caracteres es suficientemente grande para alojar todos los caracteres descodificados. A continuación, se llama al método <xref:System.Text.ASCIIEncoding.GetChars%28System.Byte%5B%5D%2CSystem.Int32%2CSystem.Int32%2CSystem.Char%5B%5D%2CSystem.Int32%29?displayProperty=nameWithType> para descodificar la matriz de bytes.

[!code-csharp[Conceptual.Encoding#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/getchars1.cs#9)]
[!code-vb[Conceptual.Encoding#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/getchars1.vb#9)]

Los métodos de codificación y descodificación de una clase derivada de <xref:System.Text.Encoding> están diseñados para funcionar en un conjunto completo de datos; es decir, todos los datos que se va a codificar o descodificar se proporciona en una única llamada al método. Sin embargo, en algunos casos, los datos están disponibles en una secuencia y los datos que se va a codificar o descodificar pueden estar disponibles solo desde operaciones de lectura independientes. Para ello, la operación de codificación o descodificación debe recordar cualquier estado guardado de su invocación anterior. Los métodos de clases derivadas de <xref:System.Text.Encoder> y <xref:System.Text.Decoder> pueden controlar las operaciones de codificación y descodificación que abarcan varias llamadas a métodos.

Hay disponible un objeto <xref:System.Text.Encoder> para una codificación determinada desde la propiedad <xref:System.Text.Encoding.GetEncoder%2A?displayProperty=nameWithType> de esa codificación. Hay disponible un objeto <xref:System.Text.Decoder> para una codificación determinada desde la propiedad <xref:System.Text.Encoding.GetDecoder%2A?displayProperty=nameWithType> de esa codificación. Para las operaciones de descodificación, tenga en cuenta que las clases derivadas de <xref:System.Text.Decoder> incluyen un método <xref:System.Text.Decoder.GetChars%2A?displayProperty=nameWithType> , pero no tienen un método que se corresponda con <xref:System.Text.Encoding.GetString%2A?displayProperty=nameWithType>.

En el ejemplo siguiente se muestra la diferencia entre el uso de los métodos <xref:System.Text.Encoding.GetChars%2A?displayProperty=nameWithType> y <xref:System.Text.Decoder.GetChars%2A?displayProperty=nameWithType> para descodificar una matriz de bytes Unicode. En el ejemplo se codifica una cadena que contiene algunos caracteres Unicode en un archivo y, a continuación, se usan los dos métodos de descodificación para descodificarlos de diez bytes en diez bytes. Puesto que hay un par suplente en los bytes décimo y undécimo, se descodifica en llamadas a métodos independientes. Como muestra el resultado, el método <xref:System.Text.Encoding.GetChars%2A?displayProperty=nameWithType> no puede descodificar los bytes correctamente y, en su lugar, los reemplaza con U+FFFD (carácter de reemplazo). Por otra parte, el método <xref:System.Text.Decoder.GetChars%2A?displayProperty=nameWithType> puede descodificar correctamente la matriz de bytes para obtener la cadena original.

[!code-csharp[Conceptual.Encoding#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/stream1.cs#10)]
[!code-vb[Conceptual.Encoding#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/stream1.vb#10)]

<a name="FallbackStrategy"></a>

## <a name="choosing-a-fallback-strategy"></a>Elegir una estrategia de reinterpretación

Cuando un método intenta codificar o descodificar un carácter pero no existe ninguna asignación, debe implementar una estrategia de reserva que determine cómo se debe tratar la asignación incorrecta. Hay tres tipos de estrategias de reserva:

- Best-Fit Fallback

- Replacement Fallback

- Exception Fallback

> [!IMPORTANT]
> Los problemas más frecuentes en las operaciones de codificación se producen cuando un carácter Unicode no se puede asignar a una codificación determinada de la página de códigos. Los problemas más comunes de las operaciones de descodificación se producen cuando las secuencias no válidas de bytes no se pueden traducir a caracteres Unicode válidos. Por estas razones, debe saber qué estrategia de reserva emplea un determinado objeto de codificación. Siempre que sea posible, debe especificar la estrategia de reserva usada por un objeto de codificación cuando se crea una instancia del objeto.

<a name="BestFit"></a>

### <a name="best-fit-fallback"></a>Best-Fit Fallback

Cuando un carácter no tiene una coincidencia exacta en la codificación de destino, el codificador puede intentar asignarle a un carácter similar. (La reserva con ajuste perfecto es principalmente un problema de codificación en lugar de un problema de descodificación. Hay muy pocas páginas de códigos que contengan caracteres que no se puedan asignar correctamente a Unicode.) La reserva con ajuste perfecto es el valor predeterminado para las codificaciones de páginas de códigos y de juegos de caracteres de doble byte recuperadas por las sobrecargas de <xref:System.Text.Encoding.GetEncoding%28System.Int32%29?displayProperty=nameWithType> y <xref:System.Text.Encoding.GetEncoding%28System.String%29?displayProperty=nameWithType>.

> [!NOTE]
> En teoría, las clases de codificación Unicode proporcionadas en .NET (<xref:System.Text.UTF8Encoding>, <xref:System.Text.UnicodeEncoding> y <xref:System.Text.UTF32Encoding>) admiten cada carácter de todos los juegos de caracteres, por lo que se pueden usar para eliminar los problemas de reserva con ajuste perfecto.

Las estrategias de ajuste perfecto varían en páginas de códigos diferentes. Por ejemplo, para algunas páginas de códigos, los caracteres latinos de ancho completo se asignarán a caracteres latinos de ancho medio, que son más comunes. Para otras páginas de códigos no se realiza esta asignación. Incluso con una estrategia de ajuste perfecto dinámica, algunos caracteres no tienen un ajuste imaginable en algunas codificaciones. Por ejemplo, un ideograma chino no tiene ninguna asignación razonable a la página de códigos 1252. En este caso, se emplea una cadena de reemplazo. De forma predeterminada, esta cadena es simplemente un carácter QUESTION MARK (U+003F).

> [!NOTE]
> Las estrategias de ajuste perfecto no están documentadas de forma detallada. Sin embargo, varias páginas de códigos se documentan en el sitio web de [Unicode Consortium](https://www.unicode.org/Public/MAPPINGS/VENDORS/MICSFT/WindowsBestFit/). Revise el archivo **Léame.txt** de esa carpeta para obtener una descripción de cómo interpretar los archivos de asignación.

En el ejemplo siguiente se usa la página de códigos 1252 (la página de códigos de Windows para los idiomas de Europa occidental) para mostrar la asignación con ajuste perfecto y sus desventajas. El método <xref:System.Text.Encoding.GetEncoding%28System.Int32%29?displayProperty=nameWithType> se usa para recuperar un objeto de codificación para la página de códigos 1252. De forma predeterminada, usa una asignación con ajuste perfecto para los caracteres Unicode que no admite. En el ejemplo se crea una instancia de una cadena que contiene tres caracteres no ASCII, CIRCLED LATIN CAPITAL LETTER S (U+24C8), SUPERSCRIPT FIVE (U+2075) e INFINITY (U+221E), separados por espacios en blanco. Como muestra el resultado del ejemplo, cuando se codifica la cadena, los tres caracteres originales que no son espacios en blanco se reemplazan con QUESTION MARK (U+003F), DIGIT FIVE (U+0035) y DIGIT EIGHT (U+0038). DIGIT EIGHT es un reemplazo especialmente deficiente para el carácter INFINITY no compatible y QUESTION MARK indica que no había ninguna asignación disponible para el carácter original.

[!code-csharp[Conceptual.Encoding#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/bestfit1.cs#1)]
[!code-vb[Conceptual.Encoding#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/bestfit1.vb#1)]

La asignación con ajuste perfecto es el comportamiento predeterminado para un objeto <xref:System.Text.Encoding> que codifica los datos Unicode en datos de página de códigos, y hay aplicaciones heredadas que se basan en este comportamiento. Sin embargo, la mayoría de las aplicaciones nuevas deben evitarlo por razones de seguridad. Por ejemplo, las aplicaciones no deben asignar nombres de dominio mediante una codificación con ajuste perfecto.

> [!NOTE]
> También puede implementar una asignación personalizada de reserva con ajuste perfecto para una codificación. Para más información, vea la sección [Implementing a Custom Fallback Strategy](../../../docs/standard/base-types/character-encoding.md#Custom) .

Si la reserva con ajuste perfecto es el valor predeterminado para un objeto de codificación, puede elegir otra estrategia de reserva cuando se recupera un objeto <xref:System.Text.Encoding> llamando a la sobrecarga de <xref:System.Text.Encoding.GetEncoding%28System.Int32%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> o <xref:System.Text.Encoding.GetEncoding%28System.String%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> . La próxima sección incluye un ejemplo que reemplaza con un asterisco (*) cada carácter que no se puede asignar a la página de códigos 1252.

[!code-csharp[Conceptual.Encoding#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/bestfit1a.cs#3)]
[!code-vb[Conceptual.Encoding#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/bestfit1a.vb#3)]

<a name="Replacement"></a>

### <a name="replacement-fallback"></a>Replacement Fallback

Cuando un carácter no tiene una coincidencia exacta en el esquema de destino, pero no hay ningún carácter adecuado al que se pueda asignar, la aplicación puede especificar un carácter o una cadena de reemplazo. Este es el comportamiento predeterminado del descodificador Unicode, que reemplaza cualquier secuencia de dos bytes que no pueda descodificar con REPLACEMENT_CHARACTER (U+FFFD). También es el comportamiento predeterminado de la clase <xref:System.Text.ASCIIEncoding> , que reemplaza cada carácter que no puede codificar o descodificar con un signo de interrogación. En el ejemplo siguiente se muestra el reemplazo de caracteres para la cadena Unicode del ejemplo anterior. Como muestra el resultado, cada carácter que no se puede descodificar en un valor de bytes ASCII se reemplaza con 0x3F, que es el código ASCII de un signo de interrogación.

[!code-csharp[Conceptual.Encoding#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/replacementascii.cs#2)]
[!code-vb[Conceptual.Encoding#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/replacementascii.vb#2)]

.NET incluye las clases <xref:System.Text.EncoderReplacementFallback> y <xref:System.Text.DecoderReplacementFallback>, que sustituyen una cadena de reemplazo si un carácter no se asigna exactamente en una operación de codificación o descodificación. De forma predeterminada, esta cadena de reemplazo es un signo de interrogación, pero puede llamar a una sobrecarga del constructor de clase para elegir otra cadena diferente. Normalmente, la cadena de reemplazo es un carácter único, aunque esto no es un requisito. En el ejemplo siguiente se cambia el comportamiento del codificador de la página de códigos 1252 creando una instancia de un objeto <xref:System.Text.EncoderReplacementFallback> que usa un asterisco (*) como cadena de reemplazo.

[!code-csharp[Conceptual.Encoding#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/bestfit1a.cs#3)]
[!code-vb[Conceptual.Encoding#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/bestfit1a.vb#3)]

> [!NOTE]
> También puede implementar una clase de reemplazo para una codificación. Para más información, vea la sección [Implementing a Custom Fallback Strategy](../../../docs/standard/base-types/character-encoding.md#Custom) .

Además de QUESTION MARK (U+003F), el REPLACEMENT CHARACTER de Unicode (U+FFFD) se suele usar como cadena de reemplazo, especialmente al descodificar secuencias de bytes que no se puede traducir correctamente a caracteres Unicode. Sin embargo, se puede elegir cualquier cadena de reemplazo y esta puede contener varios caracteres.

<a name="Exception"></a>

### <a name="exception-fallback"></a>Exception Fallback

En lugar de proporcionar una reserva con ajuste perfecto o una cadena de reemplazo, un codificador puede producir <xref:System.Text.EncoderFallbackException> si no puede codificar un juego de caracteres y un descodificador puede producir <xref:System.Text.DecoderFallbackException> si no puede descodificar una matriz de bytes. Para producir una excepción en operaciones de codificación y descodificación, se proporciona un objeto <xref:System.Text.EncoderExceptionFallback> y un objeto <xref:System.Text.DecoderExceptionFallback> , respectivamente, al método <xref:System.Text.Encoding.GetEncoding%28System.String%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> . En el ejemplo siguiente se muestra la reserva de excepción con la clase <xref:System.Text.ASCIIEncoding> .

[!code-csharp[Conceptual.Encoding#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/exceptionascii.cs#4)]
[!code-vb[Conceptual.Encoding#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/exceptionascii.vb#4)]

> [!NOTE]
> También puede implementar un controlador de excepciones personalizado para una operación de codificación. Para más información, vea la sección [Implementing a Custom Fallback Strategy](../../../docs/standard/base-types/character-encoding.md#Custom) .

Los objetos <xref:System.Text.EncoderFallbackException> y <xref:System.Text.DecoderFallbackException> proporcionan la siguiente información acerca de la condición que provocó la excepción:

- El objeto <xref:System.Text.EncoderFallbackException> incluye un método <xref:System.Text.EncoderFallbackException.IsUnknownSurrogate%2A> , que indica si el carácter o los caracteres que no se pueden codificar representan un par suplente desconocido (en este caso, el método devuelve `true`) o un único carácter desconocido (en este caso, el método devuelve `false`). Los caracteres del par suplente están disponibles a partir de las propiedades <xref:System.Text.EncoderFallbackException.CharUnknownHigh%2A?displayProperty=nameWithType> y <xref:System.Text.EncoderFallbackException.CharUnknownLow%2A?displayProperty=nameWithType> . El carácter único desconocido está disponible en la propiedad <xref:System.Text.EncoderFallbackException.CharUnknown%2A?displayProperty=nameWithType> . La propiedad <xref:System.Text.EncoderFallbackException.Index%2A?displayProperty=nameWithType> indica la posición de la cadena en la que se encontró el primer carácter que no se pudo codificar.

- El objeto <xref:System.Text.DecoderFallbackException> incluye una propiedad <xref:System.Text.DecoderFallbackException.BytesUnknown%2A> que devuelve una matriz de bytes que no se pueden descodificar. La propiedad <xref:System.Text.DecoderFallbackException.Index%2A?displayProperty=nameWithType> indica la posición inicial de los bytes desconocidos.

Aunque los objetos <xref:System.Text.EncoderFallbackException> y <xref:System.Text.DecoderFallbackException> proporcionan información suficiente de diagnóstico sobre la excepción, no proporcionan acceso al búfer de codificación o descodificación. Por tanto, no permiten reemplazar o corregir datos no válidos dentro del método de codificación o descodificación.

<a name="Custom"></a>

## <a name="implementing-a-custom-fallback-strategy"></a>Implementing a Custom Fallback Strategy

Además de la asignación con ajuste perfecto implementada internamente por las páginas de códigos, .NET incluye las siguientes clases para implementar una estrategia de reserva:

- Use <xref:System.Text.EncoderReplacementFallback> y <xref:System.Text.EncoderReplacementFallbackBuffer> para reemplazar caracteres en operaciones de codificación.

- Use <xref:System.Text.DecoderReplacementFallback> y <xref:System.Text.DecoderReplacementFallbackBuffer> para reemplazar caracteres en operaciones de descodificación.

- Use <xref:System.Text.EncoderExceptionFallback> y <xref:System.Text.EncoderExceptionFallbackBuffer> para producir <xref:System.Text.EncoderFallbackException> cuando un carácter no se puede codificar.

- Use <xref:System.Text.DecoderExceptionFallback> y <xref:System.Text.DecoderExceptionFallbackBuffer> para producir <xref:System.Text.DecoderFallbackException> cuando un carácter no se puede descodificar.

Además, puede implementar una solución personalizada que use reserva con ajuste perfecto, reserva de reemplazo o reserva de excepción siguiendo estos pasos:

1. Derive una clase de <xref:System.Text.EncoderFallback> para las operaciones de codificación y de <xref:System.Text.DecoderFallback> para las operaciones de descodificación.

2. Derive una clase de <xref:System.Text.EncoderFallbackBuffer> para las operaciones de codificación y de <xref:System.Text.DecoderFallbackBuffer> para las operaciones de descodificación.

3. Para la reserva de excepción, si las clases <xref:System.Text.EncoderFallbackException> y <xref:System.Text.DecoderFallbackException> predefinidas no satisfacen sus necesidades, derive una clase de un objeto de excepción como <xref:System.Exception> o <xref:System.ArgumentException>.

### <a name="deriving-from-encoderfallback-or-decoderfallback"></a>Derivar de EncoderFallback o DecoderFallback

Para implementar una solución de reserva personalizada, debe crear una clase que herede de <xref:System.Text.EncoderFallback> para las operaciones de codificación y de <xref:System.Text.DecoderFallback> para las operaciones de descodificación. Las instancias de estas clases se pasan al método <xref:System.Text.Encoding.GetEncoding%28System.String%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> y actúan como intermediario entre la clase de codificación y la implementación de reserva.

Cuando se crea una solución de reserva personalizada para un codificador o un descodificador, debe implementar los miembros siguientes:

- La propiedad <xref:System.Text.EncoderFallback.MaxCharCount%2A?displayProperty=nameWithType> o <xref:System.Text.DecoderFallback.MaxCharCount%2A?displayProperty=nameWithType> , que devuelve el número máximo de caracteres posible que el reemplazo con mejor ajuste o la reserva de excepción pueda devolver para reemplazar un único carácter. En el caso de la reserva de excepción personalizada, su valor es cero.

- El método <xref:System.Text.EncoderFallback.CreateFallbackBuffer%2A?displayProperty=nameWithType> o <xref:System.Text.DecoderFallback.CreateFallbackBuffer%2A?displayProperty=nameWithType> , que devuelve una implementación personalizada de <xref:System.Text.EncoderFallbackBuffer> o <xref:System.Text.DecoderFallbackBuffer> . El codificador llama al método cuando encuentra el primer carácter que no puede codificar correctamente o lo llama el decodificador cuando encuentra el primer byte que no puede descodificar correctamente.

### <a name="deriving-from-encoderfallbackbuffer-or-decoderfallbackbuffer"></a>Derivar de EncoderFallbackBuffer o DecoderFallbackBuffer

Para implementar una solución de reserva personalizada, debe crear también una clase que herede de <xref:System.Text.EncoderFallbackBuffer> para las operaciones de codificación y de <xref:System.Text.DecoderFallbackBuffer> para las operaciones de descodificación. El método <xref:System.Text.EncoderFallback.CreateFallbackBuffer%2A> de las clases <xref:System.Text.EncoderFallback> y <xref:System.Text.DecoderFallback> devuelve instancias de estas clases. El codificador llama al método <xref:System.Text.EncoderFallback.CreateFallbackBuffer%2A?displayProperty=nameWithType> cuando encuentra el primer carácter que no puede codificar y el descodificador llama al método <xref:System.Text.DecoderFallback.CreateFallbackBuffer%2A?displayProperty=nameWithType> cuando encuentra uno o más bytes que no puede descodificar. Las clases <xref:System.Text.EncoderFallbackBuffer> y <xref:System.Text.DecoderFallbackBuffer> proporcionan la implementación de reserva. Cada instancia representa un búfer que contiene los caracteres de reserva que reemplazarán el carácter que no se puede codificar o la secuencia de bytes que no se puede descodificar.

Cuando se crea una solución de reserva personalizada para un codificador o un descodificador, debe implementar los miembros siguientes:

- El método <xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> o <xref:System.Text.DecoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> . El codificador llama a<xref:System.Text.EncoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> para proporcionar el búfer de reserva con información sobre el carácter que no puede codificar. Puesto que el carácter que se va a codificar puede ser un par suplente, este método está sobrecargado. Se pasa a una sobrecarga el carácter que se va a codificar y su índice en la cadena. A la segunda sobrecarga se le pasa el suplente máximo y mínimo junto con su índice en la cadena. El descodificador llama al método <xref:System.Text.DecoderFallbackBuffer.Fallback%2A?displayProperty=nameWithType> para proporcionar el búfer de reserva con información sobre los bytes que no puede descodificar. Se pasa a este método una matriz de bytes que no puede descodificar, junto con el índice del primer byte. El método de reserva debe devolver `true` si el búfer de reserva puede proporcionar un carácter o caracteres de mejor ajuste o de reemplazo; de lo contrario, debe devolver `false`. En el caso de una reserva de excepción, el método de reserva debe producir una excepción.

- El método <xref:System.Text.EncoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> o <xref:System.Text.DecoderFallbackBuffer.GetNextChar%2A?displayProperty=nameWithType> , al que llama repetidamente el codificador o el descodificador para obtener el siguiente carácter del búfer de reserva. Cuando se han devuelto todos los caracteres de reserva, el método debe devolver U+0000.

- La propiedad <xref:System.Text.EncoderFallbackBuffer.Remaining%2A?displayProperty=nameWithType> o <xref:System.Text.DecoderFallbackBuffer.Remaining%2A?displayProperty=nameWithType> , que devuelve el número de caracteres que permanecen en el búfer de reserva.

- El método <xref:System.Text.EncoderFallbackBuffer.MovePrevious%2A?displayProperty=nameWithType> o <xref:System.Text.DecoderFallbackBuffer.MovePrevious%2A?displayProperty=nameWithType> , que mueve la posición actual en el búfer de reserva al carácter anterior.

- El método <xref:System.Text.EncoderFallbackBuffer.Reset%2A?displayProperty=nameWithType> o <xref:System.Text.DecoderFallbackBuffer.Reset%2A?displayProperty=nameWithType> , que se reinicializa el búfer de reserva.

Si la implementación de reserva es una reserva con ajuste perfecto o una reserva de reemplazo, las clases derivadas de <xref:System.Text.EncoderFallbackBuffer> y <xref:System.Text.DecoderFallbackBuffer> también mantienen dos campos de instancia privados: el número exacto de caracteres del búfer y el índice del carácter siguiente del búfer que se va a devolver.

### <a name="an-encoderfallback-example"></a>Ejemplo de EncoderFallback

En un ejemplo anterior se usaba la reserva de reemplazo para reemplazar caracteres Unicode que no correspondían a caracteres ASCII con un asterisco (*). En el ejemplo siguiente se usa una implementación personalizada de reserva con ajuste perfecto en su lugar para proporcionar una mejor asignación de caracteres no ASCII.

En el código siguiente se define una clase denominada `CustomMapper` que se deriva de <xref:System.Text.EncoderFallback> para controlar la asignación con ajuste perfecto de caracteres no ASCII. Su método `CreateFallbackBuffer` devuelve un objeto `CustomMapperFallbackBuffer` , que proporciona la implementación de <xref:System.Text.EncoderFallbackBuffer> . La clase `CustomMapper` usa un objeto <xref:System.Collections.Generic.Dictionary%602> para almacenar las asignaciones de caracteres Unicode no compatibles (el valor de clave) y sus caracteres de 8 bits correspondientes (que se almacenan en dos bytes consecutivos en un entero de 64 bits). Para que esta asignación esté disponible para el búfer de reserva, la instancia de `CustomMapper` se pasa como un parámetro al constructor de clase `CustomMapperFallbackBuffer` . Puesto que la asignación más larga es la cadena "INF" por el carácter Unicode U+221E, la propiedad `MaxCharCount` devuelve 3.

[!code-csharp[Conceptual.Encoding#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/custom1.cs#5)]
[!code-vb[Conceptual.Encoding#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/custom1.vb#5)]

En el código siguiente se define la clase `CustomMapperFallbackBuffer` , que se deriva de <xref:System.Text.EncoderFallbackBuffer>. El diccionario que contiene las asignaciones con ajuste perfecto y que se define en la instancia de `CustomMapper` está disponible desde su constructor de clase. Su método `Fallback` devuelve `true` si cualquiera de los caracteres Unicode que el codificador ASCII no puede codificar se definen en el diccionario de asignación; de lo contrario, devuelve `false`. Para cada reserva, la variable `count` privada indica el número de caracteres que quedan por devolver y la variable `index` privada indica la posición en el búfer de cadena, `charsToReturn`, del siguiente carácter que se va a devolver.

[!code-csharp[Conceptual.Encoding#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/custom1.cs#6)]
[!code-vb[Conceptual.Encoding#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/custom1.vb#6)]

En el código siguiente se crean instancias del objeto `CustomMapper` y se pasa una instancia del mismo al método <xref:System.Text.Encoding.GetEncoding%28System.String%2CSystem.Text.EncoderFallback%2CSystem.Text.DecoderFallback%29?displayProperty=nameWithType> . El resultado indica que la implementación de reserva con ajuste perfecto controla correctamente los tres caracteres no ASCII de la cadena original.

[!code-csharp[Conceptual.Encoding#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.encoding/cs/custom1.cs#7)]
[!code-vb[Conceptual.Encoding#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.encoding/vb/custom1.vb#7)]

## <a name="see-also"></a>Vea también

- <xref:System.Text.Encoder>
- <xref:System.Text.Decoder>
- <xref:System.Text.DecoderFallback>
- <xref:System.Text.Encoding>
- <xref:System.Text.EncoderFallback>
- [Globalización y localización](../../../docs/standard/globalization-localization/index.md)
