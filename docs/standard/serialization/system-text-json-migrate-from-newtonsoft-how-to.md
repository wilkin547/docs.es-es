---
title: Migrar Newtonsoft.Json de System.Text.Json - .NET
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 957bafcdf69d5792702962db6598458a0c8ec974
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291570"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Migración desde Newtonsoft.json a System.Text.Json

En este artículo se muestra cómo <xref:System.Text.Json>migrar de [Newtonsoft.Json](https://www.newtonsoft.com/json) a .

El `System.Text.Json` espacio de nombres proporciona funcionalidad para serializar y deserializar desde JavaScript Object Notation (JSON). La `System.Text.Json` biblioteca se incluye en el marco compartido de [.NET Core 3.0.](https://aka.ms/netcore3download) Para otros marcos de destino, instale el paquete NuGet [System.Text.Json.](https://www.nuget.org/packages/System.Text.Json) El paquete admite:

* .NET Standard 2.0 y versiones posteriores
* .NET Framework 4.7.2 y versiones posteriores
* .NET Core 2.0, 2.1 y 2.2

`System.Text.Json`se centra principalmente en el rendimiento, la seguridad y el cumplimiento de las normas. Tiene algunas diferencias clave en el comportamiento predeterminado y no `Newtonsoft.Json`pretende tener paridad de características con . Para algunos escenarios, `System.Text.Json` no tiene ninguna funcionalidad integrada, pero hay soluciones alternativas recomendadas. Para otros escenarios, las soluciones alternativas no son prácticas. Si la aplicación depende de una característica que falta, considere la posibilidad de [presentar un problema](https://github.com/dotnet/runtime/issues/new) para averiguar si se puede agregar compatibilidad con su escenario.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

La mayor parte de este <xref:System.Text.Json.JsonSerializer> artículo trata sobre cómo usar la API, pero también incluye instrucciones sobre cómo usar el <xref:System.Text.Json.JsonDocument> (que representa el modelo de objetos de documento o DOM) <xref:System.Text.Json.Utf8JsonReader>y <xref:System.Text.Json.Utf8JsonWriter> tipos.

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a>Tabla de diferencias entre Newtonsoft.Json y System.Text.Json

En la `Newtonsoft.Json` tabla `System.Text.Json` siguiente se enumeran las características y los equivalentes. Los equivalentes se clasifican en las siguientes categorías:

* Compatible con la funcionalidad integrada. Obtener un `System.Text.Json` comportamiento similar de puede requerir el uso de un atributo o una opción global.
* No se admite, la solución alternativa es posible. Las soluciones alternativas son [convertidores personalizados,](system-text-json-converters-how-to.md)que `Newtonsoft.Json` pueden no proporcionar una paridad completa con la funcionalidad. Para algunos de estos, el código de ejemplo se proporciona como ejemplos. Si confía en `Newtonsoft.Json` estas características, la migración requerirá modificaciones en los modelos de objetos de .NET u otros cambios de código.
* No se admite, la solución alternativa no es práctica ni posible. Si confía en `Newtonsoft.Json` estas características, la migración no será posible sin cambios significativos.

| Característica Newtonsoft.Json                               | System.Text.Json equivalente |
|-------------------------------------------------------|-----------------------------|
| Deserialización sin distinción de mayúsculas y minúsculas de forma predeterminada           | ✔️ [PropertyNameCaseInsensitive configuración global](#case-insensitive-deserialization) |
| Nombres de propiedades de camel-case                             | ✔️ [configuración global PropertyNamingPolicy](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) |
| Carácter mínimo que escapa                            | ✔️ El escape estricto [de caracteres, configurable](#minimal-character-escaping) |
| `NullValueHandling.Ignore`entorno global             | ✔️ [opción global IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) |
| Permitir comentarios                                        | ✔️ [configuración global ReadCommentHandling](#comments) |
| Permitir comas finales                                 | ✔️ [configuración global AllowTrailingCommas](#trailing-commas) |
| Registro del convertidor personalizado                         | ✔️ [Orden de prioridad difiere](#converter-registration-precedence) |
| Sin profundidad máxima por defecto                           | ✔️ [Profundidad máxima predeterminada 64, configurable](#maximum-depth) |
| Soporte para una amplia gama de tipos                    | ⚠️[Algunos tipos requieren convertidores personalizados](#types-without-built-in-support) |
| Deserializar cadenas como números                        | ⚠️[No soportado, solución, ejemplo](#quoted-numbers) |
| Deserializar `Dictionary` con clave que no es de cadena          | ⚠️[No soportado, solución, ejemplo](#dictionary-with-non-string-key) |
| Serialización polimórfica                             | ⚠️[No soportado, solución, ejemplo](#polymorphic-serialization) |
| Deserialización polimórfica                           | ⚠️[No soportado, solución, ejemplo](#polymorphic-deserialization) |
| Deserializar el `object` tipo deducido a las propiedades      | ⚠️[No soportado, solución, ejemplo](#deserialization-of-object-properties) |
| Deserializar `null` literalES JSON a tipos de valor que no aceptan valores NULL | ⚠️[No soportado, solución, ejemplo](#deserialize-null-to-non-nullable-type) |
| Deserializar a clases y estructuras inmutables          | ⚠️[No soportado, solución, ejemplo](#deserialize-to-immutable-classes-and-structs) |
| Atributo `[JsonConstructor]`                         | ⚠️[No soportado, solución, ejemplo](#specify-constructor-to-use) |
| `Required`establecer `[JsonProperty]` en el atributo        | ⚠️[No soportado, solución, ejemplo](#required-properties) |
| `NullValueHandling`establecer `[JsonProperty]` en el atributo | ⚠️[No soportado, solución, ejemplo](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`establecer `[JsonProperty]` en el atributo | ⚠️[No soportado, solución, ejemplo](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`entorno global                 | ⚠️[No soportado, solución, ejemplo](#conditionally-ignore-a-property) |
| `DefaultContractResolver`para excluir propiedades       | ⚠️[No soportado, solución, ejemplo](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, `DateFormatString` ajustes   | ⚠️[No soportado, solución, ejemplo](#specify-date-format) |
| Devoluciones de llamada                                             | ⚠️[No soportado, solución, ejemplo](#callbacks) |
| Apoyo a los campos públicos y no públicos              | ⚠️[No se admite, solución alternativa](#public-and-non-public-fields) |
| Soporte para establecedores y captadores de propiedades internos y privados | ⚠️[No se admite, solución alternativa](#internal-and-private-property-setters-and-getters) |
| Método `JsonConvert.PopulateObject`                   | ⚠️[No se admite, solución alternativa](#populate-existing-objects) |
| `ObjectCreationHandling`entorno global               | ⚠️[No se admite, solución alternativa](#reuse-rather-than-replace-properties) |
| Añadir a colecciones sin establecedores                    | ⚠️[No se admite, solución alternativa](#add-to-collections-without-setters) |
| `PreserveReferencesHandling`entorno global           | ❌[No soportado](#preserve-object-references-and-handle-loops) |
| `ReferenceLoopHandling`entorno global                | ❌[No soportado](#preserve-object-references-and-handle-loops) |
| Soporte `System.Runtime.Serialization` para atributos | ❌[No soportado](#systemruntimeserialization-attributes) |
| `MissingMemberHandling`entorno global                | ❌[No soportado](#missingmemberhandling) |
| Permitir nombres de propiedad sin comillas                   | ❌[No soportado](#json-strings-property-names-and-string-values) |
| Permitir comillas simples alrededor de los valores de cadena              | ❌[No soportado](#json-strings-property-names-and-string-values) |
| Permitir valores JSON que no sean de cadena para las propiedades de cadena    | ❌[No soportado](#non-string-values-for-string-properties) |

Esta no es una `Newtonsoft.Json` lista exhaustiva de características. La lista incluye muchos de los escenarios que se han solicitado en los problemas de [GitHub](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) o las publicaciones [stackOverflow.](https://stackoverflow.com/questions/tagged/system.text.json) Si implementa una solución alternativa para uno de los escenarios enumerados aquí que no tiene código de ejemplo actualmente y si desea compartir la solución, seleccione **Esta página** en la [sección Comentarios](/dotnet/standard/serialization/system-text-json-migrate-from-newtonsoft-how-to#feedback) de esta página. Esto crea un problema de GitHub y lo enumera en la parte inferior de esta página.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>Diferencias en el comportamiento predeterminado de JsonSerializer en comparación con Newtonsoft.Json

<xref:System.Text.Json>es estricto por defecto y evita cualquier conjetura o interpretación en nombre del autor de la llamada, haciendo hincapié en el comportamiento determinista. La biblioteca está diseñada intencionalmente de esta manera para el rendimiento y la seguridad. `Newtonsoft.Json`es flexible de forma predeterminada. Esta diferencia fundamental en el diseño está detrás de muchas de las siguientes diferencias específicas en el comportamiento predeterminado.

### <a name="case-insensitive-deserialization"></a>Deserialización sin distinción entre mayúsculas y minúsculas

Durante la `Newtonsoft.Json` deserialización, no distingue mayúsculas de minúsculas de la coincidencia de nombre de propiedad de forma predeterminada. El <xref:System.Text.Json> valor predeterminado distingue mayúsculas de minúsculas, lo que proporciona un mejor rendimiento, ya que está haciendo una coincidencia exacta. Para obtener información sobre cómo realizar la coincidencia sin distinción entre mayúsculas y minúsculas, vea Coincidencia de [propiedades sin distinción entre mayúsculas y minúsculas](system-text-json-how-to.md#case-insensitive-property-matching).

Si usas `System.Text.Json` indirectamente mediante ASP.NET Core, no necesitas hacer nada `Newtonsoft.Json`para obtener un comportamiento como . ASP.NET Core especifica la configuración de los nombres de propiedad de `System.Text.Json`mayúsculas y [minúsculas](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) y la coincidencia que no distingue mayúsculas de minúsculas cuando usa .

### <a name="minimal-character-escaping"></a>Carácter mínimo que escapa

Durante la `Newtonsoft.Json` serialización, es relativamente permisivo acerca de dejar pasar a los personajes sin escapar de ellos. Es decir, no los reemplaza `\uxxxx` `xxxx` con dónde está el punto de código del personaje. Cuando se escapa de ellos, `\` lo hace emitiendo `"` un `\"`antes del carácter (por ejemplo, se convierte en ). <xref:System.Text.Json>escapa a más caracteres de forma predeterminada para proporcionar protecciones de defensa en profundidad contra secuencias de comandos entre sitios (XSS) o ataques de divulgación de información y lo hace mediante la secuencia de seis caracteres. `System.Text.Json`escapa de todos los caracteres no ASCII de forma predeterminada, por `StringEscapeHandling.EscapeNonAscii` `Newtonsoft.Json`lo que no es necesario hacer nada si está utilizando en . `System.Text.Json`también escapa a caracteres sensibles al HTML, de forma predeterminada. Para obtener información sobre `System.Text.Json` cómo invalidar el comportamiento predeterminado, vea [Personalizar la codificación](system-text-json-how-to.md#customize-character-encoding)de caracteres .

### <a name="comments"></a>Comentarios

Durante la `Newtonsoft.Json` deserialización, omite los comentarios en el JSON de forma predeterminada. El <xref:System.Text.Json> valor predeterminado es producir excepciones para los comentarios porque la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no los incluye. Para obtener información sobre cómo permitir comentarios, consulte [Permitir comentarios y comas finales](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Comas finales

Durante la `Newtonsoft.Json` deserialización, omite las comas finales de forma predeterminada. También ignora varias comas finales (por ejemplo, `[{"Color":"Red"},{"Color":"Green"},,]`). El <xref:System.Text.Json> valor predeterminado es producir excepciones para las comas finales porque la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no las permite. Para obtener información `System.Text.Json` sobre cómo aceptarlos, consulte [Permitir comentarios y comas finales](system-text-json-how-to.md#allow-comments-and-trailing-commas). No hay manera de permitir varias comas finales.

### <a name="converter-registration-precedence"></a>Precedencia del registro del convertidor

La `Newtonsoft.Json` prioridad de registro para los convertidores personalizados es la siguiente:

* Atributo en la propiedad
* Atributo en el tipo
* [Colección de convertidores](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Este orden significa que un `Converters` convertidor personalizado de la colección se reemplaza por un convertidor que se registra aplicando un atributo en el nivel de tipo. Ambos registros se reemplazan por un atributo en el nivel de propiedad.

La <xref:System.Text.Json> prioridad de registro para los convertidores personalizados es diferente:

* Atributo en la propiedad
* <xref:System.Text.Json.JsonSerializerOptions.Converters>Colección
* Atributo en el tipo

La diferencia aquí es que `Converters` un convertidor personalizado en la colección reemplaza un atributo en el nivel de tipo. La intención detrás de este orden de prioridad es hacer que los cambios en tiempo de ejecución invaliden las opciones en tiempo de diseño. No hay forma de cambiar la prioridad.

Para obtener más información sobre el registro del convertidor personalizado, consulte [Registrar un convertidor personalizado](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Profundidad máxima

`Newtonsoft.Json`no tiene un límite de profundidad máximo de forma predeterminada. Para <xref:System.Text.Json> hay un límite predeterminado de 64, y <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>es configurable por la configuración .

### <a name="json-strings-property-names-and-string-values"></a>Cadenas JSON (nombres de propiedad y valores de cadena)

Durante la `Newtonsoft.Json` deserialización, acepta nombres de propiedad rodeados de comillas dobles, comillas simples o sin comillas. Acepta valores de cadena rodeados de comillas dobles o comillas simples. Por ejemplo, `Newtonsoft.Json` acepta el siguiente JSON:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json`solo acepta nombres de propiedad y valores de cadena entre comillas dobles porque ese formato es requerido por la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) y es el único formato considerado JSON válido.

Un valor entre comillas simples da como resultado una [excepción JsonException](xref:System.Text.Json.JsonException) con el siguiente mensaje:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Valores que no son de cadena para las propiedades de cadena

`Newtonsoft.Json`acepta valores que no son de cadena, `true` como `false`un número o los literales y , para la deserialización en propiedades de tipo string. Este es un ejemplo `Newtonsoft.Json` de JSON que se deserializa correctamente en la siguiente clase:

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

`System.Text.Json`no deserializa los valores que no son de cadena en propiedades de cadena. Un valor que no es de cadena recibido para un campo de cadena da como resultado una [excepción JsonException](xref:System.Text.Json.JsonException) con el siguiente mensaje:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Escenarios con JsonSerializer que requieren soluciones alternativas

La funcionalidad integrada no admite los siguientes escenarios, pero es posible realizar soluciones. Las soluciones alternativas son [convertidores personalizados,](system-text-json-converters-how-to.md)que `Newtonsoft.Json` pueden no proporcionar una paridad completa con la funcionalidad. Para algunos de estos, el código de ejemplo se proporciona como ejemplos. Si confía en `Newtonsoft.Json` estas características, la migración requerirá modificaciones en los modelos de objetos de .NET u otros cambios de código.

### <a name="types-without-built-in-support"></a>Tipos sin soporte integrado

<xref:System.Text.Json>no proporciona compatibilidad integrada para los siguientes tipos:

* <xref:System.Data.DataTable>y tipos relacionados
* Tipos de F, como [uniones discriminadas,](../../fsharp/language-reference/discriminated-unions.md)tipos de [registro](../../fsharp/language-reference/records.md)y tipos de [registros anónimos.](../../fsharp/language-reference/anonymous-records.md)
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple>y sus tipos genéricos asociados

Los convertidores personalizados se pueden implementar para tipos que no tienen compatibilidad integrada.

### <a name="quoted-numbers"></a>Números citados

`Newtonsoft.Json`puede serializar o deserializar números representados por cadenas JSON (rodeadas de comillas). Por ejemplo, puede `{"DegreesCelsius":"23"}` aceptar: `{"DegreesCelsius":23}`en lugar de . Para habilitar ese <xref:System.Text.Json>comportamiento en , implemente un convertidor personalizado como el siguiente ejemplo. El convertidor maneja `long`las propiedades definidas como:

* Las serializa como cadenas JSON.
* Acepta números Y números JSON entre comillas mientras se deserializa.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

Registre este convertidor personalizado [mediante un atributo](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) en propiedades individuales `long` o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la <xref:System.Text.Json.JsonSerializerOptions.Converters> colección.

### <a name="dictionary-with-non-string-key"></a>Diccionario con clave que no es de cadena

`Newtonsoft.Json`admite colecciones `Dictionary<TKey, TValue>`de tipo . La compatibilidad integrada para colecciones de diccionarios en <xref:System.Text.Json> se limita a `Dictionary<string, TValue>`. Es decir, la clave debe ser una cadena.

Para admitir un diccionario con un entero o algún otro tipo como clave, cree un convertidor como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Serialización polimórfica

`Newtonsoft.Json`automáticamente realiza la serialización polimórfica. Para obtener información acerca de las <xref:System.Text.Json>capacidades de serialización polimórfica limitadas de , vea [Serializar propiedades de clases derivadas](system-text-json-how-to.md#serialize-properties-of-derived-classes).

La solución alternativa que se describe es definir `object`propiedades que pueden contener clases derivadas como tipo . Si esto no es posible, otra opción es `Write` crear un convertidor con un método para toda la jerarquía de tipos de herencia como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Deserialización polimórfica

`Newtonsoft.Json`tiene `TypeNameHandling` una configuración que agrega metadatos de nombre de tipo al JSON durante la serialización. Utiliza los metadatos mientras se deserializa para realizar la deserialización polimórfica. <xref:System.Text.Json>puede hacer un rango limitado de [serialización polimórfica,](system-text-json-how-to.md#serialize-properties-of-derived-classes) pero no deserialización polimórfica.

Para admitir la deserialización polimórfica, cree un convertidor como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Deserialización de propiedades de objeto

Cuando `Newtonsoft.Json` se deserializa a <xref:System.Object>, se:

* Deduce el tipo de valores primitivos de `null`la carga JSON `string` `long`(que `boolean`no `DateTime` sea ) y devuelve el objeto almacenado , , `double`, o como un objeto en caja. *Los valores primitivos* son valores JSON únicos, como un número JSON, una cadena, `true`, `false`o `null`.
* Devuelve `JObject` a `JArray` o para valores complejos en la carga JSON. *Los valores complejos* son colecciones de`{}`pares clave-valor JSON entre`[]`llaves ( ) o listas de valores entre corchetes ( ). Las propiedades y valores de las llaves o corchetes pueden tener propiedades o valores adicionales.
* Devuelve una referencia nula `null` cuando la carga tiene el literal JSON.

<xref:System.Text.Json>almacena un `JsonElement` encajonado para valores primitivos y complejos cada vez que se deserializa en <xref:System.Object>, por ejemplo:

* Propiedad `object`.
* Un `object` valor de diccionario.
* Un `object` valor de matriz.
* Una `object`raíz .

Sin `System.Text.Json` `null` embargo, trata `Newtonsoft.Json` lo mismo que y devuelve `null` una referencia nula cuando la carga tiene el literal JSON en ella.

Para implementar la inferencia de tipos para `object` propiedades, cree un convertidor como el ejemplo de Cómo escribir [convertidores personalizados](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Deserializar null a tipo que no acepta valores NULL

`Newtonsoft.Json`no produce una excepción en el siguiente escenario:

* `NullValueHandling`está establecido `Ignore`en , y
* Durante la deserialización, el JSON contiene un valor null para un tipo de valor que no acepta valores NULL.

En el mismo <xref:System.Text.Json> escenario, produce una excepción. (La configuración de <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>control nulo correspondiente es .)

Si es propietario del tipo de destino, la mejor solución alternativa `int` es `int?`hacer que la propiedad en cuestión sea nullable (por ejemplo, cambiar a ).

Otra solución alternativa es crear un convertidor para el tipo, `DateTimeOffset` como el ejemplo siguiente que controla los valores nulos para los tipos:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Registre este convertidor personalizado [mediante un atributo en la propiedad](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la <xref:System.Text.Json.JsonSerializerOptions.Converters> colección.

**Nota:** El convertidor anterior controla los **valores nulos** de forma diferente que `Newtonsoft.Json` para los POCO que especifican valores predeterminados. Por ejemplo, supongamos que el código siguiente representa el objeto de destino:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Y supongamos que el siguiente JSON se deserializa mediante el convertidor anterior:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Después de `Date` la deserialización, la propiedad`default(DateTimeOffset)`tiene 1/1/0001 ( ), es decir, se sobrescribe el valor establecido en el constructor. Dado el mismo POCO `Newtonsoft.Json` y JSON, la deserialización dejaría `Date` 1/1/2001 en la propiedad.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Deserializar a clases y estructuras inmutables

`Newtonsoft.Json`puede deserializar a clases y estructuras inmutables porque puede usar constructores que tienen parámetros. <xref:System.Text.Json>solo admite constructores públicos sin parámetros. Como solución alternativa, puede llamar a un constructor con parámetros en un convertidor personalizado.

Aquí hay una estructura inmutable con varios parámetros de constructor:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

Y aquí hay un convertidor que serializa y deserializa esta estructura:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

Registre este convertidor personalizado [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la <xref:System.Text.Json.JsonSerializerOptions.Converters> colección.

Para obtener un ejemplo de un convertidor similar que controla las propiedades genéricas abiertas, consulte el [convertidor integrado para pares clave-valor](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Especifique el constructor que se va a utilizar

El `Newtonsoft.Json` `[JsonConstructor]` atributo permite especificar a qué constructor llamar al deserializar a un POCO. <xref:System.Text.Json>solo admite constructores sin parámetros. Como solución alternativa, puede llamar al constructor que necesite en un convertidor personalizado. Consulte el ejemplo [de Deserialize a clases y estructuras inmutables](#deserialize-to-immutable-classes-and-structs).

### <a name="required-properties"></a>Propiedades obligatorias

En `Newtonsoft.Json`, se especifica que se `Required` requiere `[JsonProperty]` una propiedad estableciendo en el atributo. `Newtonsoft.Json`produce una excepción si no se recibe ningún valor en el JSON para una propiedad marcada como necesaria.

<xref:System.Text.Json>no produce una excepción si no se recibe ningún valor para una de las propiedades del tipo de destino. Por ejemplo, si `WeatherForecast` tiene una clase:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

El siguiente JSON se deserializa sin errores:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Para que se produzca `Date` un error en la deserialización si no hay ninguna propiedad en el JSON, implemente un convertidor personalizado. El siguiente código de convertidor de `Date` ejemplo produce una excepción si la propiedad no se establece después de que se complete la deserialización:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Registre este convertidor personalizado [mediante un atributo en la clase POCO](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la <xref:System.Text.Json.JsonSerializerOptions.Converters> colección.

Si sigue este patrón, no pase el objeto options <xref:System.Text.Json.JsonSerializer.Serialize%2A> <xref:System.Text.Json.JsonSerializer.Deserialize%2A>cuando llame recursivamente o . El objeto options <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> contiene la colección. Si lo pasa `Serialize` a `Deserialize`o , el convertidor personalizado llama a sí mismo, lo que crea un bucle infinito que da como resultado una excepción de desbordamiento de pila. Si las opciones predeterminadas no son factibles, cree una nueva instancia de las opciones con la configuración que necesite. Este enfoque será lento, ya que cada nueva instancia se almacena en caché de forma independiente.

El código del convertidor anterior es un ejemplo simplificado. Se necesitaría lógica adicional si necesita controlar atributos (como [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) u opciones diferentes (como codificadores personalizados). Además, el código de ejemplo no controla las propiedades para las que se establece un valor predeterminado en el constructor. Y este enfoque no diferencia entre los siguientes escenarios:

* Falta una propiedad en el JSON.
* Una propiedad para un tipo que no acepta valores NULL está presente en el JSON, `int`pero el valor es el valor predeterminado para el tipo, como cero para un archivo .
* Una propiedad para un tipo de valor que acepta valores NULL está presente en el JSON, pero el valor es null.

### <a name="conditionally-ignore-a-property"></a>Ignorar condicionalmente una propiedad

`Newtonsoft.Json`tiene varias maneras de omitir condicionalmente una propiedad en la serialización o deserialización:

* `DefaultContractResolver`permite seleccionar propiedades para incluir o excluir, en función de criterios arbitrarios.
* La `NullValueHandling` `DefaultValueHandling` configuración `JsonSerializerSettings` y en le permiten especificar que se deben omitir todas las propiedades de valor nulo o valor predeterminado.
* La `NullValueHandling` `DefaultValueHandling` configuración y `[JsonProperty]` del atributo le permiten especificar propiedades individuales que se deben omitir cuando se establece en null o en el valor predeterminado.

<xref:System.Text.Json>proporciona las siguientes formas de omitir propiedades durante la serialización:

* El atributo [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) de una propiedad hace que la propiedad se omita del JSON durante la serialización.
* La opción global [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) permite excluir todas las propiedades de valor nulo.
* La opción global [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) permite excluir todas las propiedades de solo lectura.

Estas opciones **no** le permiten:

* Omita todas las propiedades que tienen el valor predeterminado para el tipo.
* Omita las propiedades seleccionadas que tienen el valor predeterminado para el tipo.
* Omita las propiedades seleccionadas si su valor es null.
* Omita las propiedades seleccionadas en función de criterios arbitrarios evaluados en tiempo de ejecución.

Para esa funcionalidad, puede escribir un convertidor personalizado. Aquí hay un ejemplo de POCO y un convertidor personalizado para él que ilustra este enfoque:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

El convertidor `Summary` hace que la propiedad se omita de la serialización si su valor es null, una cadena vacía o "N/A".

Registre este convertidor personalizado [mediante un atributo en la clase](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la <xref:System.Text.Json.JsonSerializerOptions.Converters> colección.

Este enfoque requiere lógica adicional si:

* El POCO incluye propiedades complejas.
* Debe controlar atributos `[JsonIgnore]` como u opciones como codificadores personalizados.

### <a name="specify-date-format"></a>Especificar el formato de fecha

`Newtonsoft.Json`proporciona varias maneras de `DateTime` `DateTimeOffset` controlar cómo se serializan y deserializan las propiedades de los tipos:

* La `DateTimeZoneHandling` configuración se puede `DateTime` utilizar para serializar todos los valores como fechas UTC.
* La `DateFormatString` configuración `DateTime` y los convertidores se pueden utilizar para personalizar el formato de las cadenas de fecha.

En <xref:System.Text.Json>, el único formato que tiene soporte integrado es ISO 8601-1:2019 ya que es ampliamente adoptado, inequívoco y hace viajes de ida y vuelta con precisión. Para utilizar cualquier otro formato, cree un convertidor personalizado. Para obtener más información, vea [Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Devoluciones de llamada

`Newtonsoft.Json`le permite ejecutar código personalizado en varios puntos del proceso de serialización o deserialización:

* OnDeserializing (cuando se empieza a deserializar un objeto)
* OnDeserialized (cuando haya terminado de serializar un objeto)
* OnSerializing (cuando se empieza a serializar un objeto)
* OnSerialized (cuando haya terminado de serializar un objeto)

En <xref:System.Text.Json>, puede simular devoluciones de llamada escribiendo un convertidor personalizado. En el ejemplo siguiente se muestra un convertidor personalizado para un POCO. El convertidor incluye código que muestra un mensaje `Newtonsoft.Json` en cada punto que corresponde a una devolución de llamada.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

Registre este convertidor personalizado [mediante un atributo en la clase](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la <xref:System.Text.Json.JsonSerializerOptions.Converters> colección.

Si utiliza un convertidor personalizado que sigue el ejemplo anterior:

* El `OnDeserializing` código no tiene acceso a la nueva instancia de POCO. Para manipular la nueva instancia de POCO al inicio de la deserialización, coloque ese código en el constructor POCO.
* No pase el objeto options cuando llame `Serialize` `Deserialize`recursivamente o . El objeto options `Converters` contiene la colección. Si lo pasa `Serialize` a `Deserialize`o , se utilizará el convertidor, lo que hace un bucle infinito que da como resultado una excepción de desbordamiento de pila.

### <a name="public-and-non-public-fields"></a>Campos públicos y no públicos

`Newtonsoft.Json`puede serializar y deserializar campos, así como propiedades. <xref:System.Text.Json>sólo trabaja con propiedades públicas. Los convertidores personalizados pueden proporcionar esta funcionalidad.

### <a name="internal-and-private-property-setters-and-getters"></a>Setters y captadores de propiedades internas y privadas

`Newtonsoft.Json`pueden usar establecedores de propiedades y captadores `JsonProperty` privados e internos a través del atributo. <xref:System.Text.Json>sólo admite setters públicos. Los convertidores personalizados pueden proporcionar esta funcionalidad.

### <a name="populate-existing-objects"></a>Rellenar objetos existentes

El `JsonConvert.PopulateObject` método `Newtonsoft.Json` en deserializa un documento JSON a una instancia existente de una clase, en lugar de crear una nueva instancia. <xref:System.Text.Json>siempre crea una nueva instancia del tipo de destino mediante el constructor público sin parámetros predeterminado. Los convertidores personalizados pueden deserializar se puede deserializar en una instancia existente.

### <a name="reuse-rather-than-replace-properties"></a>Reutilizar en lugar de reemplazar propiedades

La `Newtonsoft.Json` `ObjectCreationHandling` configuración permite especificar que los objetos de las propiedades se deben reutilizar en lugar de reemplazarse durante la deserialización. <xref:System.Text.Json>siempre reemplaza los objetos en las propiedades.  Los convertidores personalizados pueden proporcionar esta funcionalidad.

### <a name="add-to-collections-without-setters"></a>Añadir a colecciones sin establecedores

Durante la `Newtonsoft.Json` deserialización, agrega objetos a una colección incluso si la propiedad no tiene ningún establecedor. <xref:System.Text.Json>omite las propiedades que no tienen establecedores. Los convertidores personalizados pueden proporcionar esta funcionalidad.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Escenarios que JsonSerializer actualmente no admite

Para los escenarios siguientes, las soluciones alternativas no son prácticas ni posibles. Si confía en `Newtonsoft.Json` estas características, la migración no será posible sin cambios significativos.

### <a name="preserve-object-references-and-handle-loops"></a>Conservar referencias a objetos y controlar bucles

De forma `Newtonsoft.Json` predeterminada, serializa por valor. Por ejemplo, si un objeto contiene dos propiedades `Person` que contienen `Person` una referencia al mismo objeto, los valores de las propiedades de ese objeto se duplican en el JSON.

`Newtonsoft.Json`tiene `PreserveReferencesHandling` una `JsonSerializerSettings` configuración en la que le permite serializar por referencia:

* Se agrega un identificador de metadatos `Person` al JSON creado para el primer objeto.
* El JSON que se `Person` crea para el segundo objeto contiene una referencia a ese identificador en lugar de valores de propiedad.

`Newtonsoft.Json`también tiene `ReferenceLoopHandling` un valor que le permite omitir las referencias circulares en lugar de producir una excepción.

<xref:System.Text.Json>solo admite la serialización por valor y produce una excepción para las referencias circulares.

### <a name="systemruntimeserialization-attributes"></a>Atributos System.Runtime.Serialization

<xref:System.Text.Json>no admite atributos `System.Runtime.Serialization` del espacio `DataMemberAttribute` de `IgnoreDataMemberAttribute`nombres, como y .

### <a name="octal-numbers"></a>Números octales

`Newtonsoft.Json`trata los números con un cero a la izquierda como números octales. <xref:System.Text.Json>no permite ceros a la izquierda porque la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no los permite.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json`se puede configurar para producir excepciones durante la deserialización si el JSON incluye propiedades que faltan en el tipo de destino. <xref:System.Text.Json>omite las propiedades adicionales en el JSON, excepto cuando se utiliza el [atributo [JsonExtensionData].](system-text-json-how-to.md#handle-overflow-json) No hay ninguna solución alternativa para la característica de miembro que falta.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json`permite depurar mediante `TraceWriter` un para ver los registros generados por la serialización o deserialización. <xref:System.Text.Json>no hace el registro.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument y JsonElement en comparación con JToken (como JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>proporciona la capacidad de analizar y crear un modelo de objetos de documento (DOM) **de solo lectura** a partir de cargas JSON existentes. El DOM proporciona acceso aleatorio a los datos de una carga JSON. Se puede tener acceso a los <xref:System.Text.Json.JsonElement> elementos JSON que componen la carga a través del tipo. El `JsonElement` tipo proporciona API para convertir texto JSON en tipos comunes de .NET. `JsonDocument`expone una <xref:System.Text.Json.JsonDocument.RootElement> propiedad.

### <a name="jsondocument-is-idisposable"></a>JsonDocument es IDisposable

`JsonDocument`crea una vista en memoria de los datos en un búfer agrupado. Por lo `JObject` `JArray` tanto, `JsonDocument` a diferencia `IDisposable` o de `Newtonsoft.Json`, el tipo implementa y debe usarse dentro de un bloque using.

Solo devuelva una `JsonDocument` de la API si desea transferir la propiedad de por vida y eliminar la responsabilidad al autor de la llamada. En la mayoría de los escenarios, eso no es necesario. Si el autor de la llamada necesita <xref:System.Text.Json.JsonElement.Clone%2A> trabajar <xref:System.Text.Json.JsonDocument.RootElement%2A>con todo <xref:System.Text.Json.JsonElement>el documento JSON, devuelva el archivo , que es un archivo . Si el autor de la llamada necesita trabajar con <xref:System.Text.Json.JsonElement.Clone%2A> un <xref:System.Text.Json.JsonElement>elemento determinado dentro del documento JSON, devuelva el archivo . Si devuelve `RootElement` el o un subelemento `Clone`directamente sin crear un , `JsonElement` el `JsonDocument` autor de la llamada no podrá tener acceso al devuelto después de que se elimine el propietario.

Este es un ejemplo que requiere `Clone`que usted haga un :

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

El código anterior espera `JsonElement` un `fileName` que contiene una propiedad. Abre el archivo JSON `JsonDocument`y crea un archivo . El método supone que el autor de la llamada desea `Clone` trabajar `RootElement`con todo el documento, por lo que devuelve el archivo .

Si recibe `JsonElement` un y está devolviendo un subelemento, no `Clone` es necesario devolver un del subelemento. El autor de la llamada `JsonDocument` es responsable `JsonElement` de mantener vivo el que pertenece el pasado. Por ejemplo:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument es de solo lectura

El <xref:System.Text.Json> DOM no puede agregar, quitar ni modificar elementos JSON. Está diseñado de esta manera para el rendimiento y para reducir las asignaciones para analizar tamaños de carga JSON comunes (es decir, < 1 MB). Si su escenario utiliza actualmente un DOM modificable, una de las siguientes soluciones podría ser factible:

* Para crear `JsonDocument` un desde cero (es decir, sin `Parse` pasar una carga JSON `Utf8JsonWriter` existente al método), escriba el `JsonDocument`texto JSON mediante el uso de la salida y analice la salida de ese para crear un nuevo archivo .
* Para modificar `JsonDocument`un existente, utilícelo para escribir texto JSON, realizar cambios mientras `JsonDocument`escribe, y analizar la salida de la misma para crear un nuevo archivo .
* Para combinar documentos JSON `JObject.Merge` existentes, equivalentes a las API o `JContainer.Merge` , `Newtonsoft.Json`consulte este problema de [GitHub](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>JsonElement es una estructura sindical

`JsonDocument`expone la `RootElement` propiedad como <xref:System.Text.Json.JsonElement>una propiedad de tipo , que es una unión, tipo struct que abarca cualquier elemento JSON. `Newtonsoft.Json`utiliza tipos jerárquicos dedicados como `JObject`,`JArray`, `JToken`, etc. `JsonElement`es lo que puede buscar y enumerar, `JsonElement` y puede usar para materializar elementos JSON en tipos .NET.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Cómo buscar subelementos en Un JsonDocument y JsonElement

Las búsquedas de `JObject` `JArray` tokens `Newtonsoft.Json` JSON que usan o provienen tienden a ser relativamente rápidas porque son búsquedas en algún diccionario. En comparación, `JsonElement` las búsquedas requieren una búsqueda secuencial de las `TryGetProperty`propiedades y, por lo tanto, es relativamente lenta (por ejemplo, cuando se usa ). <xref:System.Text.Json>está diseñado para minimizar el tiempo de análisis inicial en lugar del tiempo de búsqueda. Por lo tanto, utilice los siguientes `JsonDocument` enfoques para optimizar el rendimiento al buscar en un objeto:

* Utilice los enumeradores integrados (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> y <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) en lugar de realizar su propia indexación o bucles.
* No realice una búsqueda secuencial `JsonDocument` en el conjunto `RootElement`a través de cada propiedad mediante el uso de . En su lugar, busque en objetos JSON anidados basados en la estructura conocida de los datos JSON. Por ejemplo, si está buscando `Grade` una `Student` propiedad en `Student` objetos, recorro los objetos y obtenga el valor de cada uno, en lugar de `Grade` buscar en todos los `JsonElement` objetos que buscan `Grade` propiedades. Hacer esto último dará lugar a pases innecesarios sobre los mismos datos.

Para obtener un ejemplo de código, vea [Usar JsonDocument para obtener acceso a los datos.](system-text-json-how-to.md#use-jsondocument-for-access-to-data)

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader en comparación con JsonTextReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>es un lector de alto rendimiento, baja asignación y solo avance para texto JSON codificado UTF-8, leído desde un [byte ReadOnlySpan\<>](xref:System.ReadOnlySpan%601) o byte [ReadOnlySequence\<>](xref:System.Buffers.ReadOnlySequence%601). Es `Utf8JsonReader` un tipo de bajo nivel que se puede usar para crear analizadores y deserializadores personalizados.

En las secciones siguientes se `Utf8JsonReader`explican los patrones de programación recomendados para el uso de .

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader es una estructura ref

Dado `Utf8JsonReader` que el tipo es un *ref struct*, tiene [ciertas limitaciones.](../../csharp/language-reference/keywords/ref.md#ref-struct-types) Por ejemplo, no se puede almacenar como un campo en una clase o estructura que no sea una estructura ref. Para lograr un alto rendimiento, `ref struct` este tipo debe ser un ya que necesita almacenar en caché la [entrada ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), que a su vez es una referencia struct. Además, este tipo es mutable ya que tiene estado. Por lo tanto, **páselo por ref** en lugar de por valor. Pasarlo por valor daría como resultado una copia de estructura y los cambios de estado no serían visibles para el autor de la llamada. Esto difiere `Newtonsoft.Json` de `Newtonsoft.Json` `JsonTextReader` ya que el es una clase. Para obtener más información acerca de cómo utilizar ref structs, vea Escribir código de [C. seguro y eficaz.](../../csharp/write-safe-efficient-code.md)

### <a name="read-utf-8-text"></a>Leer texto UTF-8

Para lograr el mejor rendimiento `Utf8JsonReader`posible mientras se utilizan las cargas JSON , lea ya codificadas como texto UTF-8 en lugar de como cadenas UTF-16. Para obtener un ejemplo de código, vea [Filtrar datos mediante Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Leer con un Stream o PipeReader

Admite `Utf8JsonReader` la lectura de un [byte\<ReadOnlySpan](xref:System.ReadOnlySpan%601) codificado UTF-8>o [\<ReadOnlySequence>](xref:System.Buffers.ReadOnlySequence%601) de bytes (que es el resultado de la lectura de un <xref:System.IO.Pipelines.PipeReader>).

Para la lectura sincrónica, puede leer la carga JSON hasta el final de la secuencia en una matriz de bytes y pasarla al lector. Para leer desde una cadena (que está codificada <xref:System.Text.Encoding.UTF8>como UTF-16), llame a .<xref:System.Text.Encoding.GetBytes%2A> para transcodificar primero la cadena a una matriz de bytes codificada UTF-8. A continuación, `Utf8JsonReader`pasar eso a la .

Dado `Utf8JsonReader` que la entrada es texto JSON, una marca de orden de bytes UTF-8 (BOM) se considera JSON no válido. El autor de la llamada debe filtrarlo antes de pasar los datos al lector.

Para ver ejemplos de código, vea [Usar Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Leer con ReadOnlySequence de varios segmentos

Si la entrada JSON es un [byte ReadOnlySpan\<>](xref:System.ReadOnlySpan%601), se puede tener acceso a cada elemento JSON desde la `ValueSpan` propiedad del lector a medida que avanza por el bucle de lectura. Sin embargo, si la entrada es un>de [bytes ReadOnlySequence\<](xref:System.Buffers.ReadOnlySequence%601) (que es el resultado `ReadOnlySequence<byte>` de la lectura de un <xref:System.IO.Pipelines.PipeReader>), algunos elementos JSON podrían recorrer varios segmentos del objeto. Estos elementos no <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> serían accesibles desde un bloque de memoria contiguo. En su lugar, siempre `ReadOnlySequence<byte>` que tenga un <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> segmento múltiple como entrada, sondee la propiedad en el lector para averiguar cómo obtener acceso al elemento JSON actual. Este es un patrón recomendado:

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a>Usar ValueTextEquals para las búsquedas de nombres de propiedad

No se <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> use para realizar comparaciones byte <xref:System.MemoryExtensions.SequenceEqual%2A> a byte llamando a búsquedas de nombre de propiedad. Llame <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> en su lugar, porque ese método desescape a los caracteres que se escapan en el JSON. Este es un ejemplo que muestra cómo buscar una propiedad denominada "name":

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Leer valores nulos en tipos de valor que aceptan valores NULL

`Newtonsoft.Json`proporciona API que <xref:System.Nullable%601>devuelven `ReadAsBoolean`, como `Null` `TokenType` , que controla un para usted devolviendo un `bool?`archivo . Las `System.Text.Json` API integradas devuelven solo tipos de valor que no aceptan valores NULL. Por ejemplo, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> `bool`devuelve un archivo . Produce una excepción si `Null` se encuentra en el JSON. En los ejemplos siguientes se muestran dos formas de controlar valores NULL, una devolviendo un tipo de valor que acepta valores NULL y otra devolviendo el valor predeterminado:

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a>Compatibilidad con múltiples versiones

Si necesita seguir usando `Newtonsoft.Json` para determinados marcos de destino, puede realizar varios objetivos y tener dos implementaciones. Sin embargo, esto no `#ifdefs` es trivial y requeriría cierta duplicación y fuente. Una forma de compartir tanto código como `ref struct` sea `Utf8JsonReader` `Newtonsoft.Json` `JsonTextReader`posible es crear un contenedor alrededor y . Este envoltorio unificaría el área de la superficie pública mientras aíslalas las diferencias de comportamiento. Esto le permite aislar los cambios principalmente en la construcción del tipo, junto con pasar el nuevo tipo por referencia. Este es el patrón que sigue la biblioteca [Microsoft.Extensions.DependencyModel:](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter en comparación con JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>es una forma de alto rendimiento de escribir texto JSON `String`codificado `Int32`en `DateTime`UTF-8 a partir de tipos comunes de .NET como , , y . El escritor es un tipo de bajo nivel que se puede usar para crear serializadores personalizados.

En las secciones siguientes se `Utf8JsonWriter`explican los patrones de programación recomendados para el uso de .

### <a name="write-with-utf-8-text"></a>Escribir con texto UTF-8

Para lograr el mejor rendimiento `Utf8JsonWriter`posible mientras se utilizan las cargas JSON , escriba ya codificadas como texto UTF-8 en lugar de como cadenas UTF-16. Se <xref:System.Text.Json.JsonEncodedText> usa para almacenar en caché y codificar previamente nombres y valores de propiedad de cadena conocidos como estáticos, y pasarlos al escritor, en lugar de usar literales de cadena UTF-16. Esto es más rápido que el almacenamiento en caché y el uso de matrices de bytes UTF-8.

Este enfoque también funciona si necesita realizar escapes personalizados. `System.Text.Json`no le permite deshabilitar el escape mientras escribe una cadena. Sin embargo, podría pasar <xref:System.Text.Encodings.Web.JavaScriptEncoder> su propia costumbre como una `JsonEncodedText` opción al `JavascriptEncoder` escritor, o crear la suya `JsonEncodedText` propia que use su para hacer el escape y, a continuación, escribir el en lugar de la cadena. Para obtener más información, consulte [Personalizar la codificación](system-text-json-how-to.md#customize-character-encoding)de caracteres .

### <a name="write-raw-values"></a>Escribir valores brutos

El `Newtonsoft.Json` `WriteRawValue` método escribe JSON sin formato donde se espera un valor. <xref:System.Text.Json>no tiene un equivalente directo, pero aquí hay una solución alternativa que garantiza que solo se escribe JSON válido:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Personalizar el escape de personajes

La configuración [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) de `JsonTextWriter` ofrece opciones para escapar de todos los caracteres no ASCII **o** caracteres HTML. De forma `Utf8JsonWriter` predeterminada, se escapan todos los caracteres QUE no son ASCII **y** HTML. Este escape se realiza por razones de seguridad en profundidad. Para especificar una directiva de escape <xref:System.Text.Encodings.Web.JavaScriptEncoder> diferente, cree un archivo y un conjunto <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>. Para obtener más información, consulte [Personalizar la codificación](system-text-json-how-to.md#customize-character-encoding)de caracteres .

### <a name="customize-json-format"></a>Personalizar el formato JSON

`JsonTextWriter`incluye los siguientes ajustes, para los que `Utf8JsonWriter` no tiene equivalente:

* [Sangría:](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) especifica cuántos caracteres se deben aplicar sangría. `Utf8JsonWriter`siempre hace sangría de 2 caracteres.
* [IndentChar:](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) especifica el carácter que se usará para la sangría.  `Utf8JsonWriter`siempre usa espacios en blanco.
* [QuoteChar:](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) especifica el carácter que se va a utilizar para rodear los valores de cadena.  `Utf8JsonWriter`siempre utiliza comillas dobles.
* [QuoteName:](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) especifica si se deben o no rodear los nombres de propiedad con comillas.  `Utf8JsonWriter`siempre los rodea de citas.

No hay soluciones alternativas que le permitieran `Utf8JsonWriter` personalizar el JSON generado de estas maneras.

### <a name="write-null-values"></a>Escribir valores nulos

Para escribir valores `Utf8JsonWriter`nulos mediante , llame a:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>para escribir un par clave-valor con null como valor.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>para escribir null como un elemento de una matriz JSON.

Para una propiedad de cadena, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> si <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> la `WriteNull` cadena `WriteNullValue`es null y es equivalente a y .

### <a name="write-timespan-uri-or-char-values"></a>Escribir valores de Timespan, Uri o char

`JsonTextWriter`proporciona `WriteValue` métodos para los valores [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)y [char.](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) `Utf8JsonWriter`no tiene métodos equivalentes. En su lugar, formatee `ToString()`estos valores como <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>cadenas (llamando a , por ejemplo) y llame a .

### <a name="multi-targeting"></a>Compatibilidad con múltiples versiones

Si necesita seguir usando `Newtonsoft.Json` para determinados marcos de destino, puede realizar varios objetivos y tener dos implementaciones. Sin embargo, esto no `#ifdefs` es trivial y requeriría cierta duplicación y fuente. Una forma de compartir tanto código como sea `Utf8JsonWriter` `Newtonsoft` `JsonTextWriter`posible es crear un contenedor alrededor y . Este envoltorio unificaría el área de la superficie pública mientras aíslalas las diferencias de comportamiento. Esto le permite aislar los cambios principalmente en la construcción del tipo. [A continuación, la biblioteca Microsoft.Extensions.DependencyModel:](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/)

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Recursos adicionales

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.Text.JsonVisión general](system-text-json-overview.md)
* [Cómo usarSystem.Text.Json](system-text-json-how-to.md)
* [Procedimientos para escribir convertidores personalizados](system-text-json-converters-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset enSystem.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.JsonReferencia de API](xref:System.Text.Json)
* [System.Text.Json. Referencia de la API de serialización](xref:System.Text.Json.Serialization)
