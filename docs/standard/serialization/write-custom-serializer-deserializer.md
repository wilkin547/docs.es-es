---
title: Escritura de serializadores y deserializadores personalizados con System.Text.Json
description: Aprenda a escribir serializadores y deserializadores personalizados para JSON mediante el espacio de nombres System.Text.Json.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: a01d3c8dd18c114ea1c3aabc402bc841a6025ffe
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439876"
---
# <a name="how-to-write-custom-serializers-and-deserializers-with-no-locsystemtextjson"></a>Escritura de serializadores y deserializadores personalizados con System.Text.Json

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>` o `ReadOnlySequence<byte>`. `Utf8JsonReader` es un tipo de bajo nivel que se puede usar para compilar analizadores y deserializadores personalizados. El método <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> usa `Utf8JsonReader` en segundo plano.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ofrece una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`. El escritor es un tipo de bajo nivel que se puede usar para compilar serializadores personalizados. El método <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> usa `Utf8JsonWriter` en segundo plano.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> ofrece la posibilidad de crear una especificación Document Object Model de solo lectura (DOM) mediante `Utf8JsonReader`. La especificación DOM proporciona acceso aleatorio a los datos en una carga JSON. A los elementos JSON que componen la carga se puede acceder mediante el tipo <xref:System.Text.Json.JsonElement>. El tipo `JsonElement` contiene los enumeradores de matriz y objeto junto con las API para convertir texto JSON en tipos de .NET comunes. `JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.

En las secciones siguientes se muestra cómo usar estas herramientas para leer y escribir JSON.

## <a name="use-jsondocument-for-access-to-data"></a>Uso de JsonDocument para acceder a datos

En el ejemplo siguiente se muestra cómo usar la clase <xref:System.Text.Json.JsonDocument> para el acceso aleatorio a los datos de una cadena JSON:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades1":::

El código anterior:

* Supone que el JSON que se va a analizar está en una cadena denominada `jsonString`.
* Calcula la calificación media de los objetos de una matriz de `Students` que tienen una propiedad `Grade`.
* Asigna una calificación predeterminada de 70 a los alumnos que no tienen ninguna calificación.
* Cuenta los alumnos incrementando una variable `count` con cada iteración. Una alternativa es llamar a <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, tal y como se muestra en el ejemplo siguiente:

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades2":::

Aquí se muestra un ejemplo del código JSON que este código procesa:

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-jsondocument-to-write-json"></a>Uso de JsonDocument para escribir JSON

En el siguiente ejemplo se muestra cómo escribir JSON desde una <xref:System.Text.Json.JsonDocument>:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs" id="Serialize":::

El código anterior:

* Lee un archivo JSON, carga los datos en un `JsonDocument` y escribe JSON con formato (impreso correctamente) en un archivo.
* Utiliza <xref:System.Text.Json.JsonDocumentOptions> para especificar que se permiten los comentarios en el JSON de entrada, pero se omiten.
* Cuando termina, llama a <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> en el escritor. Una alternativa consiste en permitir el vaciado automático del escritor cuando se elimina.

Aquí se muestra un ejemplo de entrada JSON que el código de ejemplo va a procesar:

:::code language="json" source="snippets/system-text-json-how-to/csharp/Grades.json":::

El resultado es la siguiente salida JSON impresa correctamente:

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-utf8jsonwriter"></a>Uso de Utf8JsonWriter

En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonWriter>:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs" id="Serialize":::

## <a name="use-utf8jsonreader"></a>Uso de Utf8JsonReader

En el siguiente ejemplo, se muestra cómo utilizar la clase <xref:System.Text.Json.Utf8JsonReader>:

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs" id="Deserialize":::

En el código anterior se supone que la variable `jsonUtf8` es una matriz de bytes que contiene JSON válido, con codificación UTF-8.

### <a name="filter-data-using-utf8jsonreader"></a>Filtrado de datos con Utf8JsonReader

En el ejemplo siguiente se muestra cómo leer un archivo de forma sincrónica y buscar un valor.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs":::

Puede encontrar una versión asincrónica de este ejemplo en [Proyecto JSON de ejemplos de .NET](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs).

El código anterior:

* Supone que el JSON contiene una matriz de objetos y cada objeto puede contener una propiedad "name" de tipo cadena.
* Cuenta los objetos y los valores de propiedad "name" que terminan en "University".
* Supone que el archivo tiene codificación UTF-16 y lo transcodifica a UTF-8. Un archivo con codificación UTF-8 puede leerse directamente en `ReadOnlySpan<byte>` mediante el código siguiente:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Si el archivo contiene una marca BOM UTF-8, quítela antes de pasar los bytes a `Utf8JsonReader`, ya que el lector espera texto. De lo contrario, la marca BOM se considera JSON no válido y el lector inicia una excepción.

Aquí se muestra un ejemplo de JSON que el código anterior puede leer. El mensaje de resumen resultante es "2 de 4 tienen nombres que terminan en 'University'":

:::code language="json" source="snippets/system-text-json-how-to/csharp/Universities.json":::

### <a name="read-from-a-stream-using-utf8jsonreader"></a>Lectura de una secuencia mediante Utf8JsonReader

Al leer un archivo grande (un gigabyte o más de tamaño, por ejemplo), puede que desee evitar tener que cargar todo el archivo en la memoria de una vez. En este escenario, puede usar <xref:System.IO.FileStream>.

Al usar `Utf8JsonReader` para leer de una secuencia, se aplican las siguientes reglas:

* El búfer que contiene la carga parcial JSON debe ser al menos tan grande como el token JSON más grande que contiene para que el lector pueda avanzar.
* El búfer debe ser al menos tan grande como la secuencia más grande de espacio en blanco dentro del JSON.
* El lector no realiza un seguimiento de los datos que ha leído hasta que lea completamente el <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> siguiente en la carga JSON. Por tanto, cuando haya bytes restantes en el búfer, tendrá que volver a pasarlos al lector. Puede usar <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> para determinar el número de bytes que quedan.

El código siguiente muestra cómo leer desde una secuencia. Este ejemplo se muestra <xref:System.IO.MemoryStream>. Un código similar funcionará con <xref:System.IO.FileStream>, excepto cuando `FileStream` contenga una marca BOM UTF-8 al principio. En ese caso, debe quitar esos tres bytes del búfer antes de pasar los bytes restantes a `Utf8JsonReader`. En caso contrario, el lector produciría una excepción, ya que la marca BOM no se considera una parte válida del JSON.

El código de ejemplo comienza con un búfer de 4 KB y duplica el tamaño del búfer cada vez que encuentra que el tamaño no es lo suficientemente grande como para ajustarse a un token JSON completo, lo que es necesario para que el lector realice el progreso de la carga de JSON. El ejemplo de JSON proporcionado en el fragmento de código desencadena un aumento del tamaño del búfer solo si se establece un tamaño de búfer inicial muy pequeño, por ejemplo, 10 bytes. Si establece el tamaño de búfer inicial en 10, las instrucciones `Console.WriteLine` muestran la causa y el efecto de los aumentos del tamaño del búfer. En el tamaño de búfer inicial de 4 KB, se muestra todo el JSON de ejemplo en cada `Console.WriteLine` y el tamaño del búfer nunca se debe aumentar.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs":::

En el ejemplo anterior no se establece ningún límite para el tamaño del búfer. Si el tamaño del token es demasiado grande, se podría producir un error en el código con una excepción <xref:System.OutOfMemoryException>. Esto puede ocurrir si el archivo JSON contiene un token de aproximadamente 1 GB o más de tamaño, ya que la duplicación del tamaño de 1 GB da como resultado un tamaño demasiado grande para caber en un búfer de `int32`.

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Personalización de la codificación de caracteres](system-text-json-character-encoding.md)
* [Escritura de convertidores personalizados para la serialización de JSON](system-text-json-converters-how-to.md)
* [Referencia de la API System.Text.Json](xref:System.Text.Json)
