---
title: Migración de Newtonsoft.Json a System.Text.Json-.NET
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
ms.openlocfilehash: 588a36c70d31883f79a4449d69cb4ba3b4239b9f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741554"
---
# <a name="how-to-migrate-from-opno-locnewtonsoftjson-to-opno-locsystemtextjson"></a>Cómo migrar de [!OP.NO-LOC(Newtonsoft.Json)] a [!OP.NO-LOC(System.Text.Json)]

En este artículo se muestra cómo migrar de [[!OP.NO-LOC(Newtonsoft.Json)]](https://www.newtonsoft.com/json) a <xref:[!OP.NO-LOC(System.Text.Json)]>.

`[!OP.NO-LOC(System.Text.Json)]` se centra principalmente en el rendimiento, la seguridad y el cumplimiento de estándares. Tiene algunas diferencias clave en el comportamiento predeterminado y no pretende tener paridad de características con `[!OP.NO-LOC(Newtonsoft.Json)]`. En algunos escenarios, `[!OP.NO-LOC(System.Text.Json)]` no tiene ninguna funcionalidad integrada, pero se recomiendan las soluciones alternativas. En otros escenarios, las soluciones alternativas no son prácticas. Si su aplicación depende de una característica que falta, considere la posibilidad de [presentar un problema](https://github.com/dotnet/runtime/issues/new) para averiguar si se puede Agregar compatibilidad para su escenario.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/roadmap/README.md). [Restore this when the roadmap is updated.]-->

La mayor parte de este artículo trata sobre cómo usar la API de <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializer>, pero también incluye instrucciones sobre cómo usar el <xref:[!OP.NO-LOC(System.Text.Json)].JsonDocument> (que representa los tipos Document Object Model o DOM), <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonReader>y <xref:[!OP.NO-LOC(System.Text.Json)].Utf8JsonWriter>.

## <a name="table-of-differences-between-opno-locnewtonsoftjson-and-opno-locsystemtextjson"></a>Tabla de diferencias entre [!OP.NO-LOC(Newtonsoft.Json)] y [!OP.NO-LOC(System.Text.Json)]

En la tabla siguiente se enumeran `[!OP.NO-LOC(Newtonsoft.Json)]` características y `[!OP.NO-LOC(System.Text.Json)]` equivalentes. Los equivalentes se dividen en las siguientes categorías:

* Compatible con la funcionalidad integrada. La obtención de un comportamiento similar al de `[!OP.NO-LOC(System.Text.Json)]` puede requerir el uso de un atributo o una opción global.
* No se admite, es posible solucionar el problema. Las soluciones alternativas son [convertidores personalizados](system-text-json-converters-how-to.md), que puede que no proporcionen una paridad completa con funcionalidad `[!OP.NO-LOC(Newtonsoft.Json)]`. En algunos de estos ejemplos, se proporciona código de ejemplo. Si confía en estas características `[!OP.NO-LOC(Newtonsoft.Json)]`, la migración requerirá modificaciones en los modelos de objetos .NET u otros cambios de código.
* No se admite, la solución alternativa no es práctica o posible. Si confía en estas características `[!OP.NO-LOC(Newtonsoft.Json)]`, la migración no será posible sin cambios importantes.

| [!OP.NO-LOC(Newtonsoft.Json)] característica                               | [!OP.NO-LOC(System.Text.Json)] equivalente |
|-------------------------------------------------------|-----------------------------|
| Deserialización sin distinción entre mayúsculas y minúsculas de forma predeterminada           | ✔️ [configuración global de PropertyNameCaseInsensitive](#case-insensitive-deserialization) |
| Nombres de propiedades Case Camel                             | ✔️ [configuración global de PropertyNamingPolicy](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) |
| Escape de carácter mínimo                            | ✔️ el [escape estricto de caracteres, configurable](#minimal-character-escaping) |
| configuración global de `NullValueHandling.Ignore`             | ✔️ [opción global IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) |
| Permitir comentarios                                        | ✔️ [configuración global de ReadCommentHandling](#comments) |
| Permitir comas finales                                 | ✔️ [configuración global de AllowTrailingCommas](#trailing-commas) |
| Registro de convertidor personalizado                         | ✔️ [orden de prioridad difiere](#converter-registration-precedence) |
| Sin profundidad máxima de forma predeterminada                           | ✔️ [profundidad máxima predeterminada 64, configurable](#maximum-depth) |
| Compatibilidad con una amplia gama de tipos                    | ⚠️ [algunos tipos requieren convertidores personalizados](#types-without-built-in-support) |
| Deserializar cadenas como números                        | ⚠️ [no compatible, solución alternativa, ejemplo](#quoted-numbers) |
| Deserializar `Dictionary` con clave que no sea de cadena          | ⚠️ [no compatible, solución alternativa, ejemplo](#dictionary-with-non-string-key) |
| Serialización polimórfica                             | ⚠️ [no compatible, solución alternativa, ejemplo](#polymorphic-serialization) |
| Deserialización polimórfica                           | ⚠️ [no compatible, solución alternativa, ejemplo](#polymorphic-deserialization) |
| Deserializar el tipo deducido en `object` propiedades      | ⚠️ [no compatible, solución alternativa, ejemplo](#deserialization-of-object-properties) |
| Deserializar JSON `null` literal a tipos que no aceptan valores NULL | ⚠️ [no compatible, solución alternativa, ejemplo](#deserialize-null-to-non-nullable-type) |
| Deserializar en clases y Structs inmutables          | ⚠️ [no compatible, solución alternativa, ejemplo](#deserialize-to-immutable-classes-and-structs) |
| Atributo `[JsonConstructor]`                         | ⚠️ [no compatible, solución alternativa, ejemplo](#specify-constructor-to-use) |
| `Required` configuración de `[JsonProperty]` atributo        | ⚠️ [no compatible, solución alternativa, ejemplo](#required-properties) |
| `NullValueHandling` configuración de `[JsonProperty]` atributo | ⚠️ [no compatible, solución alternativa, ejemplo](#conditionally-ignore-a-property)  |
| `DefaultValueHandling` configuración de `[JsonProperty]` atributo | ⚠️ [no compatible, solución alternativa, ejemplo](#conditionally-ignore-a-property)  |
| configuración global de `DefaultValueHandling`                 | ⚠️ [no compatible, solución alternativa, ejemplo](#conditionally-ignore-a-property) |
| `DefaultContractResolver` para excluir propiedades       | ⚠️ [no compatible, solución alternativa, ejemplo](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, configuración de `DateFormatString`   | ⚠️ [no compatible, solución alternativa, ejemplo](#specify-date-format) |
| Devoluciones                                             | ⚠️ [no compatible, solución alternativa, ejemplo](#callbacks) |
| Compatibilidad con campos públicos y no públicos              | ⚠️ [no compatible, solución alternativa](#public-and-non-public-fields) |
| Compatibilidad para captadores y establecedores de propiedades internos y privados | ⚠️ [no compatible, solución alternativa](#internal-and-private-property-setters-and-getters) |
| Método `JsonConvert.PopulateObject`                   | ⚠️ [no compatible, solución alternativa](#populate-existing-objects) |
| configuración global de `ObjectCreationHandling`               | ⚠️ [no compatible, solución alternativa](#reuse-rather-than-replace-properties) |
| Agregar a colecciones sin establecedores                    | ⚠️ [no compatible, solución alternativa](#add-to-collections-without-setters) |
| configuración global de `PreserveReferencesHandling`           | ❌ [no compatible](#preserve-object-references-and-handle-loops) |
| configuración global de `ReferenceLoopHandling`                | ❌ [no compatible](#preserve-object-references-and-handle-loops) |
| Compatibilidad con atributos de `System.Runtime.Serialization` | ❌ [no compatible](#systemruntimeserialization-attributes) |
| configuración global de `MissingMemberHandling`                | ❌ [no compatible](#missingmemberhandling) |
| Permitir nombres de propiedad sin comillas                   | ❌ [no compatible](#json-strings-property-names-and-string-values) |
| Permitir comillas simples alrededor de los valores de cadena              | ❌ [no compatible](#json-strings-property-names-and-string-values) |
| Permitir valores JSON que no son de cadena para las propiedades de cadena    | ❌ [no compatible](#non-string-values-for-string-properties) |

Esta no es una lista exhaustiva de características de `[!OP.NO-LOC(Newtonsoft.Json)]`. La lista incluye muchos de los escenarios que se han solicitado en [problemas de github](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-[!OP.NO-LOC(System.Text.Json)]) o publicaciones de [stackoverflow](https://stackoverflow.com/questions/tagged/system.text.json) . Si implementa una solución alternativa para uno de los escenarios enumerados aquí que actualmente no tiene código de ejemplo, y si desea compartir la solución, seleccione **esta página** en la [sección Comentarios](/dotnet/standard/serialization/system-text-json-migrate-from-newtonsoft-how-to#feedback) de esta página. Esto crea un problema de GitHub y lo muestra en la parte inferior de esta página.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-opno-locnewtonsoftjson"></a>Diferencias en el comportamiento predeterminado de JsonSerializer en comparación con [!OP.NO-LOC(Newtonsoft.Json)]

<xref:[!OP.NO-LOC(System.Text.Json)]> es STRICT de forma predeterminada y evita cualquier adivinación o interpretación en nombre del llamador, resaltando el comportamiento determinista. La biblioteca se ha diseñado intencionadamente de esta manera para el rendimiento y la seguridad. de forma predeterminada, `[!OP.NO-LOC(Newtonsoft.Json)]` es flexible. Esta diferencia fundamental en el diseño está detrás de muchas de las siguientes diferencias específicas en el comportamiento predeterminado.

### <a name="case-insensitive-deserialization"></a>Deserialización sin distinción entre mayúsculas y minúsculas 

Durante la deserialización, `[!OP.NO-LOC(Newtonsoft.Json)]` realiza la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas de forma predeterminada. El valor predeterminado de <xref:[!OP.NO-LOC(System.Text.Json)]> distingue entre mayúsculas y minúsculas, lo que proporciona un mejor rendimiento, ya que realiza una coincidencia exacta. Para obtener información sobre cómo hacer coincidir la coincidencia sin distinción entre mayúsculas y minúsculas, vea [coincidencia de propiedades sin distinción entre mayúsculas y minúsculas](system-text-json-how-to.md#case-insensitive-property-matching).

Si usa `[!OP.NO-LOC(System.Text.Json)]` indirectamente mediante ASP.NET Core, no es necesario hacer nada para obtener el comportamiento como `[!OP.NO-LOC(Newtonsoft.Json)]`. ASP.NET Core especifica los valores para [los nombres de propiedad con grafía Camel](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) y la coincidencia sin distinción entre mayúsculas y minúsculas cuando usa `[!OP.NO-LOC(System.Text.Json)]`.

### <a name="minimal-character-escaping"></a>Escape de carácter mínimo

Durante la serialización, `[!OP.NO-LOC(Newtonsoft.Json)]` es relativamente permisiva si se permite que los caracteres queden sin escapar. Es decir, no los reemplaza por `\uxxxx` donde `xxxx` es el punto de código del carácter. Donde los escapa, lo hace emitiendo una `\` antes del carácter (por ejemplo, `"` se convierte en `\"`). <xref:[!OP.NO-LOC(System.Text.Json)]> escapa más caracteres de forma predeterminada para proporcionar protecciones de defensa en profundidad contra ataques de scripting entre sitios (XSS) o de divulgación de información, y lo hace mediante la secuencia de seis caracteres. `[!OP.NO-LOC(System.Text.Json)]` escapa a todos los caracteres no ASCII de forma predeterminada, por lo que no es necesario hacer nada si usa `StringEscapeHandling.EscapeNonAscii` en `[!OP.NO-LOC(Newtonsoft.Json)]`. de forma predeterminada, `[!OP.NO-LOC(System.Text.Json)]` también escapa los caracteres que distinguen entre HTML. Para obtener información sobre cómo invalidar el comportamiento predeterminado de `[!OP.NO-LOC(System.Text.Json)]`, vea [personalizar la codificación de caracteres](system-text-json-how-to.md#customize-character-encoding).

### <a name="comments"></a>Comentarios

Durante la deserialización, `[!OP.NO-LOC(Newtonsoft.Json)]` omite los comentarios en el JSON de forma predeterminada. El <xref:[!OP.NO-LOC(System.Text.Json)]> predeterminado es producir excepciones para los comentarios porque la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no los incluye. Para obtener información sobre cómo permitir comentarios, vea [permitir comentarios y comas finales](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Comas finales

Durante la deserialización, `[!OP.NO-LOC(Newtonsoft.Json)]` omite las comas finales de forma predeterminada. También omite varias comas finales (por ejemplo, `[{"Color":"Red"},{"Color":"Green"},,]`). El <xref:[!OP.NO-LOC(System.Text.Json)]> predeterminado es iniciar excepciones para las comas finales, ya que la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no las permite. Para obtener información sobre cómo hacer que `[!OP.NO-LOC(System.Text.Json)]` los acepte, consulte [permitir comentarios y comas finales](system-text-json-how-to.md#allow-comments-and-trailing-commas). No hay ninguna manera de permitir comas finales múltiples.

### <a name="converter-registration-precedence"></a>Prioridad de registro del convertidor

La prioridad de registro de `[!OP.NO-LOC(Newtonsoft.Json)]` para los convertidores personalizados es la siguiente:

* Atributo en la propiedad
* Atributo en tipo
* Colección de [convertidores](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Este orden significa que un convertidor personalizado de la colección `Converters` se reemplaza por un convertidor que se registra aplicando un atributo en el nivel de tipo. Los dos registros se reemplazan por un atributo en el nivel de propiedad.

La prioridad de registro de <xref:[!OP.NO-LOC(System.Text.Json)]> para los convertidores personalizados es diferente:

* Atributo en la propiedad
* <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters> colección
* Atributo en tipo

La diferencia es que un convertidor personalizado de la colección `Converters` invalida un atributo en el nivel de tipo. La intención de este orden de prioridad es que los cambios de tiempo de ejecución invaliden las opciones de tiempo de diseño. No hay ninguna manera de cambiar la prioridad.

Para obtener más información sobre el registro de convertidor personalizado, vea [registrar un convertidor personalizado](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Profundidad máxima

de forma predeterminada, `[!OP.NO-LOC(Newtonsoft.Json)]` no tiene un límite de profundidad máximo. Por <xref:[!OP.NO-LOC(System.Text.Json)]> hay un límite predeterminado de 64 y se puede configurar mediante la configuración de <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.

### <a name="json-strings-property-names-and-string-values"></a>Cadenas JSON (nombres de propiedad y valores de cadena)

Durante la deserialización, `[!OP.NO-LOC(Newtonsoft.Json)]` acepta nombres de propiedad entre comillas dobles, comillas simples o sin comillas. Acepta valores de cadena entre comillas dobles o comillas simples. Por ejemplo, `[!OP.NO-LOC(Newtonsoft.Json)]` acepta el siguiente código JSON:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`[!OP.NO-LOC(System.Text.Json)]` solo acepta nombres de propiedad y valores de cadena entre comillas, ya que el formato es necesario para la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) y es el único formato considerado JSON válido.

Un valor entre comillas simples da como resultado un [JsonException](xref:[!OP.NO-LOC(System.Text.Json)].JsonException) con el siguiente mensaje:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Valores que no son de cadena para las propiedades de cadena

`[!OP.NO-LOC(Newtonsoft.Json)]` acepta valores que no son de cadena, como un número o los literales `true` y `false`, para la deserialización de las propiedades de tipo cadena. A continuación se muestra un ejemplo de JSON que `[!OP.NO-LOC(Newtonsoft.Json)]` deserializa correctamente en la clase siguiente:

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

`[!OP.NO-LOC(System.Text.Json)]` no deserializa valores que no son de cadena en propiedades de cadena. Un valor que no sea de cadena recibido para un campo de cadena da como resultado un [JsonException](xref:[!OP.NO-LOC(System.Text.Json)].JsonException) con el siguiente mensaje:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Escenarios de uso de JsonSerializer que requieren soluciones alternativas

Los escenarios siguientes no son compatibles con la funcionalidad integrada, pero son posibles soluciones alternativas. Las soluciones alternativas son [convertidores personalizados](system-text-json-converters-how-to.md), que puede que no proporcionen una paridad completa con funcionalidad `[!OP.NO-LOC(Newtonsoft.Json)]`. En algunos de estos ejemplos, se proporciona código de ejemplo. Si confía en estas características `[!OP.NO-LOC(Newtonsoft.Json)]`, la migración requerirá modificaciones en los modelos de objetos .NET u otros cambios de código.

### <a name="types-without-built-in-support"></a>Tipos sin compatibilidad integrada

<xref:[!OP.NO-LOC(System.Text.Json)]> no proporciona compatibilidad integrada para los siguientes tipos:

* <xref:System.Data.DataTable> y tipos relacionados
* F#tipos, como [uniones discriminadas](../../fsharp/language-reference/discriminated-unions.md), [tipos de registros](../../fsharp/language-reference/records.md)y [tipos de registros anónimos](../../fsharp/language-reference/anonymous-records.md).
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> y sus tipos genéricos asociados

Se pueden implementar convertidores personalizados para tipos que no tienen compatibilidad integrada.

### <a name="quoted-numbers"></a>Números entre comillas

`[!OP.NO-LOC(Newtonsoft.Json)]` puede serializar o deserializar los números representados por cadenas JSON (entre comillas). Por ejemplo, puede aceptar: `{"DegreesCelsius":"23"}` en lugar de `{"DegreesCelsius":23}`. Para habilitar ese comportamiento en <xref:[!OP.NO-LOC(System.Text.Json)]>, implemente un convertidor personalizado como el ejemplo siguiente. El convertidor controla las propiedades definidas como `long`:

* Los serializa como cadenas JSON. 
* Acepta números de JSON y números entre comillas durante la deserialización.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

Registre este convertidor personalizado [mediante un atributo](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) en propiedades de `long` individuales o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección de <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters>.

### <a name="dictionary-with-non-string-key"></a>Diccionario con clave que no es de cadena

`[!OP.NO-LOC(Newtonsoft.Json)]` admite colecciones de tipo `Dictionary<TKey, TValue>`. La compatibilidad integrada con colecciones de diccionario en <xref:[!OP.NO-LOC(System.Text.Json)]> se limita a `Dictionary<string, TValue>`. Es decir, la clave debe ser una cadena.

Para admitir un diccionario con un entero o algún otro tipo como clave, cree un convertidor como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Serialización polimórfica

`[!OP.NO-LOC(Newtonsoft.Json)]` realiza automáticamente la serialización polimórfica. Para obtener información sobre las capacidades de serialización polimórficas limitadas de <xref:[!OP.NO-LOC(System.Text.Json)]>, vea [serializar propiedades de clases derivadas](system-text-json-how-to.md#serialize-properties-of-derived-classes).

La solución descrita es para definir propiedades que pueden contener clases derivadas como `object`de tipo. Si eso no es posible, otra opción es crear un convertidor con un método `Write` para toda la jerarquía de tipos de herencia, como en el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Deserialización polimórfica

`[!OP.NO-LOC(Newtonsoft.Json)]` tiene un valor de `TypeNameHandling` que agrega metadatos de nombre de tipo al JSON durante la serialización. Usa los metadatos durante la deserialización para realizar la deserialización polimórfica. <xref:[!OP.NO-LOC(System.Text.Json)]> puede hacer una gama limitada de [serialización polimórfica](system-text-json-how-to.md#serialize-properties-of-derived-classes) , pero no la deserialización polimórfica.

Para admitir la deserialización polimórfica, cree un convertidor como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Deserialización de propiedades de objeto

Cuando `[!OP.NO-LOC(Newtonsoft.Json)]` deserializa en `object` propiedades en POCO o en diccionarios de tipo `Dictionary<string, object>`, se:

* Infiere el tipo de valores primitivos en la carga JSON (excepto `null`) y devuelve los `string`almacenados, `long`, `double`, `boolean`o `DateTime` como un objeto con conversión boxing. *Los valores primitivos* son valores JSON únicos como un número JSON, una cadena, un `true`, un `false`o un `null`.
* Devuelve un `JObject` o `JArray` para valores complejos en la carga de JSON. *Los valores complejos* son colecciones de pares clave-valor JSON entre llaves (`{}`) o listas de valores entre corchetes (`[]`). Las propiedades y los valores entre llaves o corchetes pueden tener propiedades o valores adicionales.
* Devuelve una referencia nula cuando la carga útil tiene el `null` literal JSON.

<xref:[!OP.NO-LOC(System.Text.Json)]> almacena una `JsonElement` con conversión boxing para valores primitivos y complejos dentro de la propiedad `System.Object` o el valor del diccionario. Sin embargo, trata `null` igual que `[!OP.NO-LOC(Newtonsoft.Json)]` y devuelve una referencia nula cuando la carga útil tiene el literal `null` JSON.

Para implementar la inferencia de tipos para las propiedades de `object`, cree un convertidor como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Deserializar null en un tipo que no acepta valores NULL 

`[!OP.NO-LOC(Newtonsoft.Json)]` no produce una excepción en el escenario siguiente:

* `NullValueHandling` se establece en `Ignore`y
* Durante la deserialización, el archivo JSON contiene un valor null para un tipo que no acepta valores NULL.

En el mismo escenario, <xref:[!OP.NO-LOC(System.Text.Json)]> produce una excepción. (La configuración de control de valores NULL correspondiente es <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>).

Si es el propietario del tipo de destino, la mejor solución es hacer que la propiedad en cuestión acepte valores NULL (por ejemplo, cambiar `int` a `int?`).

Otra solución consiste en crear un convertidor para el tipo, como en el ejemplo siguiente, en el que se tratan los valores NULL de `DateTimeOffset` tipos:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Registre este convertidor personalizado [mediante un atributo en la propiedad](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección de <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters>.

**Nota:** El convertidor anterior **controla los valores NULL de forma distinta** a `[!OP.NO-LOC(Newtonsoft.Json)]` para poco que especifican valores predeterminados. Por ejemplo, supongamos que el código siguiente representa el objeto de destino:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Y Supongamos que el siguiente código JSON se deserializa con el convertidor anterior:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Después de la deserialización, la propiedad `Date` tiene 1/1/0001 (`default(DateTimeOffset)`), es decir, se sobrescribe el valor establecido en el constructor. Dado el mismo POCO y JSON, `[!OP.NO-LOC(Newtonsoft.Json)]` deserialización dejaría 1/1/2001 en la propiedad `Date`.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Deserializar en clases y Structs inmutables

`[!OP.NO-LOC(Newtonsoft.Json)]` se puede deserializar en clases y struct inmutables, ya que puede usar constructores que tengan parámetros. <xref:[!OP.NO-LOC(System.Text.Json)]> solo admite constructores públicos sin parámetros. Como solución alternativa, puede llamar a un constructor con parámetros en un convertidor personalizado.

A continuación se muestra una estructura inmutable con varios parámetros de constructor:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

Y este es un convertidor que serializa y deserializa este struct:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

Registre este convertidor personalizado [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección de <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters>.

Para obtener un ejemplo de un convertidor similar que controla las propiedades genéricas abiertas, vea el [convertidor integrado para los pares de clave y valor](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/[!OP.NO-LOC(System.Text.Json)]/src/[!OP.NO-LOC(System/Text/Json)]/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Especificar el constructor que se va a usar

El atributo `[!OP.NO-LOC(Newtonsoft.Json)]` `[JsonConstructor]` permite especificar el constructor al que se llamará al deserializar en un POCO. <xref:[!OP.NO-LOC(System.Text.Json)]> solo admite constructores sin parámetros. Como solución alternativa, puede llamar a cualquier constructor que necesite en un convertidor personalizado. Vea el ejemplo de [deserialización en clases y Structs inmutables](#deserialize-to-immutable-classes-and-structs).

### <a name="required-properties"></a>Propiedades obligatorias

En `[!OP.NO-LOC(Newtonsoft.Json)]`, se especifica que se requiere una propiedad estableciendo `Required` en el atributo `[JsonProperty]`. `[!OP.NO-LOC(Newtonsoft.Json)]` produce una excepción si no se recibe ningún valor en el JSON para una propiedad marcada como requerida.

<xref:[!OP.NO-LOC(System.Text.Json)]> no inicia una excepción si no se recibe ningún valor para una de las propiedades del tipo de destino. Por ejemplo, si tiene una clase `WeatherForecast`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

El siguiente JSON se deserializa sin error:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Para que se produzca un error de deserialización si no hay `Date` propiedad en JSON, implemente un convertidor personalizado. El siguiente código de convertidor de ejemplo produce una excepción si la propiedad `Date` no se establece una vez completada la deserialización:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Registre este convertidor personalizado mediante [un atributo en la clase poco](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección de <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters>.

Si sigue este patrón, no pase el objeto de opciones cuando llame a <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializer.Serialize%2A> o <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializer.Deserialize%2A>de forma recursiva. El objeto de opciones contiene la colección de <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters%2A>. Si lo pasa a `Serialize` o `Deserialize`, el convertidor personalizado llama a sí mismo, con lo que se crea un bucle infinito que produce una excepción de desbordamiento de pila. Si las opciones predeterminadas no son factibles, cree una nueva instancia de las opciones con la configuración que necesite. Este enfoque será lento, ya que cada instancia nueva se almacena en caché de forma independiente.

El código de convertidor anterior es un ejemplo simplificado. Se requeriría lógica adicional si necesita controlar atributos (como [[JsonIgnore]](xref:[!OP.NO-LOC(System.Text.Json)].Serialization.JsonIgnoreAttribute) o diferentes opciones (como codificadores personalizados). Además, el código de ejemplo no controla las propiedades para las que se establece un valor predeterminado en el constructor. Y este enfoque no distingue entre los siguientes escenarios:

* Falta una propiedad en el JSON.
* Una propiedad para un tipo que no acepta valores NULL está presente en el JSON, pero el valor es el predeterminado para el tipo, como cero para un `int`.
* Una propiedad para un tipo que acepta valores NULL está presente en el JSON, pero el valor es NULL.

### <a name="conditionally-ignore-a-property"></a>Omitir condicionalmente una propiedad

`[!OP.NO-LOC(Newtonsoft.Json)]` tiene varias maneras de omitir condicionalmente una propiedad en la serialización o deserialización:

* `DefaultContractResolver` permite seleccionar las propiedades que se van a incluir o excluir, en función de criterios arbitrarios. 
* La configuración de `NullValueHandling` y `DefaultValueHandling` de `JsonSerializerSettings` permite especificar que se deben omitir todas las propiedades de valores NULL o valores predeterminados.
* La configuración de `NullValueHandling` y `DefaultValueHandling` en el atributo `[JsonProperty]` permite especificar propiedades individuales que se deben omitir cuando se establece en null o en el valor predeterminado.

<xref:[!OP.NO-LOC(System.Text.Json)]> proporciona las siguientes formas de omitir las propiedades durante la serialización:

* El atributo [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) de una propiedad hace que la propiedad se omita del JSON durante la serialización.
* La opción global [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) permite excluir todas las propiedades de valores NULL.
* La opción global [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) permite excluir todas las propiedades de solo lectura.

Estas opciones **no** le permiten:

* Omitir todas las propiedades que tienen el valor predeterminado para el tipo.
* Omitir las propiedades seleccionadas que tienen el valor predeterminado para el tipo.
* Omitir las propiedades seleccionadas si su valor es NULL.
* Omitir las propiedades seleccionadas en función de criterios arbitrarios evaluados en tiempo de ejecución. 

Para esa funcionalidad, puede escribir un convertidor personalizado. Este es un ejemplo POCO y un convertidor personalizado para ello que ilustra este enfoque:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

El convertidor hace que se omita la propiedad `Summary` de la serialización si su valor es null, una cadena vacía o "N/A". 

Registre este convertidor personalizado [mediante un atributo en la clase](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección de <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters>.

Este enfoque requiere lógica adicional si:

* El POCO incluye propiedades complejas.
* Debe controlar atributos como `[JsonIgnore]` o opciones como los codificadores personalizados.

### <a name="specify-date-format"></a>Especificar el formato de fecha

`[!OP.NO-LOC(Newtonsoft.Json)]` proporciona varias maneras de controlar cómo se serializan y deserializan las propiedades de los tipos `DateTime` y `DateTimeOffset`:

* El valor `DateTimeZoneHandling` se puede usar para serializar todos los valores de `DateTime` como fechas UTC.
* La configuración de `DateFormatString` y los convertidores de `DateTime` se pueden usar para personalizar el formato de las cadenas de fecha.

En <xref:[!OP.NO-LOC(System.Text.Json)]>, el único formato que tiene compatibilidad integrada es ISO 8601-1:2019, ya que se ha adoptado ampliamente, no es ambiguo, y hace que los viajes de ida y vuelta sean precisamente. Para usar cualquier otro formato, cree un convertidor personalizado. Para obtener más información, vea [compatibilidad de DateTime y DateTimeOffset en [!OP.NO-LOC(System.Text.Json)]](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Devoluciones

`[!OP.NO-LOC(Newtonsoft.Json)]` permite ejecutar código personalizado en varios puntos del proceso de serialización o deserialización:

* OnDeserializing (al empezar a deserializar un objeto)
* OnDeserialized (cuando finalizó la deserialización de un objeto)
* Serialización (al principio de serializar un objeto)
* OnSerialized (al finalizar la serialización de un objeto)

En <xref:[!OP.NO-LOC(System.Text.Json)]>, puede simular devoluciones de llamada escribiendo un convertidor personalizado. En el ejemplo siguiente se muestra un convertidor personalizado para un POCO. El convertidor incluye código que muestra un mensaje en cada punto que corresponde a una devolución de llamada de `[!OP.NO-LOC(Newtonsoft.Json)]`.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

Registre este convertidor personalizado [mediante un atributo en la clase](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección de <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Si usa un convertidor personalizado que sigue el ejemplo anterior:

* El código `OnDeserializing` no tiene acceso a la nueva instancia POCO. Para manipular la nueva instancia POCO al inicio de la deserialización, coloque ese código en el constructor POCO.
* No pase el objeto de opciones cuando llame a `Serialize` o `Deserialize`de forma recursiva. El objeto de opciones contiene la colección de `Converters`. Si lo pasa a `Serialize` o `Deserialize`, se usará el convertidor, con lo que se crea un bucle infinito que produce una excepción de desbordamiento de pila.

### <a name="public-and-non-public-fields"></a>Campos públicos y no públicos

`Newtonsoft.Json` puede serializar y deserializar los campos, así como las propiedades. <xref:System.Text.Json> solo funciona con propiedades públicas. Los convertidores personalizados pueden proporcionar esta funcionalidad.

### <a name="internal-and-private-property-setters-and-getters"></a>Establecedores de propiedades internos y privados y captadores

`Newtonsoft.Json` puede usar los establecedores de propiedades privados e internos y los captadores a través del atributo `JsonProperty`. <xref:System.Text.Json> solo admite establecedores públicos. Los convertidores personalizados pueden proporcionar esta funcionalidad.

### <a name="populate-existing-objects"></a>Rellenar objetos existentes

El método `JsonConvert.PopulateObject` de `Newtonsoft.Json` deserializa un documento JSON a una instancia existente de una clase, en lugar de crear una nueva instancia. <xref:System.Text.Json> crea siempre una nueva instancia del tipo de destino mediante el constructor sin parámetros público predeterminado. Los convertidores personalizados se pueden deserializar en una instancia existente.

### <a name="reuse-rather-than-replace-properties"></a>Reutilización en lugar de reemplazar propiedades

La configuración de `ObjectCreationHandling` de `Newtonsoft.Json` permite especificar que los objetos de las propiedades deben reutilizarse en lugar de reemplazarse durante la deserialización. <xref:System.Text.Json> siempre reemplaza los objetos en las propiedades.  Los convertidores personalizados pueden proporcionar esta funcionalidad.

### <a name="add-to-collections-without-setters"></a>Agregar a colecciones sin establecedores

Durante la deserialización, `Newtonsoft.Json` agrega objetos a una colección incluso si la propiedad no tiene ningún establecedor. <xref:System.Text.Json> omite las propiedades que no tienen establecedores. Los convertidores personalizados pueden proporcionar esta funcionalidad.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Escenarios en los que JsonSerializer no admite actualmente

En los escenarios siguientes, las soluciones alternativas no son prácticas ni posibles. Si confía en estas características `Newtonsoft.Json`, la migración no será posible sin cambios importantes.

### <a name="preserve-object-references-and-handle-loops"></a>Conservar referencias a objetos y procesar bucles

De forma predeterminada, `Newtonsoft.Json` serializa por valor. Por ejemplo, si un objeto contiene dos propiedades que contienen una referencia al mismo `Person` objeto, los valores de ese `Person` propiedades de objeto se duplican en JSON.

`Newtonsoft.Json` tiene un valor `PreserveReferencesHandling` en `JsonSerializerSettings` que le permite serializar por referencia:

* Los metadatos de un identificador se agregan al JSON creado para el primer `Person` objeto.
* El JSON que se crea para el segundo objeto `Person` contiene una referencia a ese identificador en lugar de los valores de propiedad.

`Newtonsoft.Json` también tiene un valor `ReferenceLoopHandling` que le permite omitir las referencias circulares en lugar de producir una excepción.

<xref:System.Text.Json> solo admite la serialización por valor y produce una excepción para las referencias circulares.

### <a name="systemruntimeserialization-attributes"></a>System. Runtime. Serialization (atributos)

<xref:System.Text.Json> no admite atributos del espacio de nombres `System.Runtime.Serialization`, como `DataMemberAttribute` y `IgnoreDataMemberAttribute`.

### <a name="octal-numbers"></a>Números octales

`Newtonsoft.Json` trata los números con un cero a la izquierda como números octales. <xref:System.Text.Json> no permite ceros iniciales porque la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no los permite.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json` se pueden configurar para producir excepciones durante la deserialización si el archivo JSON incluye propiedades que faltan en el tipo de destino. <xref:System.Text.Json> omite las propiedades adicionales en el archivo JSON, excepto cuando se usa el [atributo [JsonExtensionData]](system-text-json-how-to.md#handle-overflow-json). No hay ninguna solución alternativa para la característica de miembro que falta.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json` le permite depurar mediante el uso de un `TraceWriter` para ver los registros generados por serialización o deserialización. <xref:System.Text.Json> no realiza el registro.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument y JsonElement comparado con JToken (como JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> proporciona la capacidad de analizar y compilar un Document Object Model (DOM) de **solo lectura** a partir de cargas JSON existentes. DOM proporciona acceso aleatorio a los datos en una carga JSON. Se puede tener acceso a los elementos JSON que componen la carga a través del tipo de <xref:System.Text.Json.JsonElement>. El tipo de `JsonElement` proporciona las API para convertir texto JSON en tipos comunes de .NET. `JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.

### <a name="jsondocument-is-idisposable"></a>JsonDocument es IDisposable

`JsonDocument` crea una vista en memoria de los datos en un búfer agrupado. Por lo tanto, a diferencia de `JObject` o `JArray` de `Newtonsoft.Json`, el tipo de `JsonDocument` implementa `IDisposable` y debe usarse dentro de un bloque using. 

Solo devuelve un `JsonDocument` de la API si quiere transferir la propiedad de la duración y eliminar la responsabilidad del autor de la llamada. En la mayoría de los escenarios, eso no es necesario. Si el autor de la llamada necesita trabajar con todo el documento JSON, devuelva el <xref:System.Text.Json.JsonElement.Clone%2A> del <xref:System.Text.Json.JsonDocument.RootElement%2A>, que es una <xref:System.Text.Json.JsonElement>. Si el autor de la llamada necesita trabajar con un elemento determinado dentro del documento JSON, devuelva el <xref:System.Text.Json.JsonElement.Clone%2A> de ese <xref:System.Text.Json.JsonElement>. Si devuelve el `RootElement` o un subelemento directamente sin realizar un `Clone`, el autor de la llamada no podrá tener acceso al `JsonElement` devuelto después de que se elimine el `JsonDocument` que posee el objeto.

A continuación se muestra un ejemplo que requiere la creación de un `Clone`:

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

El código anterior espera una `JsonElement` que contiene una propiedad `fileName`. Se abre el archivo JSON y se crea un `JsonDocument`. El método supone que el llamador desea trabajar con todo el documento, por lo que devuelve el `Clone` de la `RootElement`. 

Si recibe un `JsonElement` y está devolviendo un subelemento, no es necesario devolver un `Clone` del subelemento. El autor de la llamada es responsable de mantener activo el `JsonDocument` al que pertenece el `JsonElement` pasado. Por ejemplo:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument es de solo lectura

El <xref:System.Text.Json> DOM no puede Agregar, quitar o modificar elementos JSON. Está diseñado de esta manera para el rendimiento y para reducir las asignaciones para el análisis de los tamaños comunes de carga útil de JSON (es decir, < 1 MB). Si el escenario usa actualmente un DOM modificable, una de las siguientes soluciones alternativas podría ser factible:

* Para compilar un `JsonDocument` desde cero (es decir, sin pasar una carga de JSON existente al método de `Parse`), escriba el texto JSON mediante el `Utf8JsonWriter` y analice la salida de ese para crear una nueva `JsonDocument`.
* Para modificar un `JsonDocument`existente, úselo para escribir texto JSON, realizar cambios mientras escribe y analizar la salida de ese para crear un nuevo `JsonDocument`.
* Para combinar documentos JSON existentes, que son equivalentes a las API `JObject.Merge` o `JContainer.Merge` de `Newtonsoft.Json`, consulte [este problema de github](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>JsonElement es una estructura Union

`JsonDocument` expone el `RootElement` como una propiedad de tipo <xref:System.Text.Json.JsonElement>, que es un tipo de estructura de Unión que abarca cualquier elemento JSON. `Newtonsoft.Json` usa tipos jerárquicos dedicados como `JObject`,`JArray`, `JToken`, etc. `JsonElement` es lo que puede buscar y enumerar, y puede usar `JsonElement` para materializar los elementos JSON en tipos de .NET.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Cómo buscar subelementos JsonDocument y JsonElement

Las búsquedas de tokens JSON mediante `JObject` o `JArray` de `Newtonsoft.Json` suelen ser relativamente rápidas porque son búsquedas en algunos diccionarios. Por comparación, las búsquedas en `JsonElement` requieren una búsqueda secuencial de las propiedades y, por lo tanto, son relativamente lentas (por ejemplo, al usar `TryGetProperty`). <xref:System.Text.Json> está diseñado para minimizar el tiempo de análisis inicial en lugar del tiempo de búsqueda. Por lo tanto, use los métodos siguientes para optimizar el rendimiento al buscar a través de un objeto `JsonDocument`:

* Use los enumeradores integrados (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> y <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) en lugar de crear sus propios bucles o índices.
* No realice una búsqueda secuencial en todo el `JsonDocument` a través de todas las propiedades mediante `RootElement`. En su lugar, busque objetos JSON anidados basados en la estructura conocida de los datos JSON. Por ejemplo, si busca una propiedad `Grade` en `Student` objetos, recorra los objetos `Student` y obtenga el valor de `Grade` para cada uno, en lugar de buscar en todos los objetos de `JsonElement` que buscan propiedades de `Grade`. Si lo hace, se producirán pasos innecesarios sobre los mismos datos.

Para obtener un ejemplo de código, vea [usar JsonDocument para el acceso a los datos](system-text-json-how-to.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader comparado con JsonTextReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de alto rendimiento, baja asignación y de solo avance para texto JSON con codificación UTF-8, que se lee de un [> de bytes de\<ReadOnlySpan](xref:System.ReadOnlySpan%601) o de un [> de bytes de ReadOnlySequence\<](xref:System.Buffers.ReadOnlySequence%601). El `Utf8JsonReader` es un tipo de nivel bajo que se puede utilizar para crear analizadores y deserializadores personalizados.

En las siguientes secciones se explican los patrones de programación recomendados para el uso de `Utf8JsonReader`.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader es un struct de referencia

Dado que el tipo de `Utf8JsonReader` es un *struct de referencia*, tiene [ciertas limitaciones](../../csharp/language-reference/keywords/ref.md#ref-struct-types). Por ejemplo, no se puede almacenar como un campo en una clase o struct que no sea un struct Ref. Para lograr un alto rendimiento, este tipo debe ser una `ref struct` porque necesita almacenar en caché la entrada [ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601), que es una estructura de referencia. Además, este tipo es mutable ya que contiene el estado. Por lo tanto, **páselo por referencia** en lugar de por valor. Si se pasa por valor, se producirá una copia de la estructura y los cambios de estado no estarán visibles para el autor de la llamada. Esto difiere de `Newtonsoft.Json` debido a que el `JsonTextReader` de `Newtonsoft.Json` es una clase. Para obtener más información sobre cómo usar las estructuras de referencia, vea [escribir código seguro C# y eficaz](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>Leer texto UTF-8

Para lograr el mejor rendimiento posible mientras usa el `Utf8JsonReader`, lea cargas de JSON ya codificadas como texto UTF-8 en lugar de como cadenas UTF-16. Para obtener un ejemplo de código, vea [filtrar datos mediante Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Leer con una secuencia o PipeReader

El `Utf8JsonReader` admite la lectura desde un [ReadOnlySpan\<bytes](xref:System.ReadOnlySpan%601) con codificación UTF-8 > o [\<ReadOnlySequence > byte <xref:System.IO.Pipelines.PipeReader>](xref:System.Buffers.ReadOnlySequence%601) (que es el resultado de la lectura de un).

Para la lectura sincrónica, puede leer la carga de JSON hasta el final de la secuencia en una matriz de bytes y pasarla al lector. Para leer de una cadena (que está codificada como UTF-16), llame a <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A> para transcodificar primero la cadena en una matriz de bytes con codificación UTF-8. A continuación, páselo a la `Utf8JsonReader`. 

Dado que el `Utf8JsonReader` considera que la entrada es texto JSON, se considera que una marca de orden de bytes UTF-8 (BOM) no es válida. El autor de la llamada debe filtrarlo antes de pasar los datos al lector.

Para obtener ejemplos de código, vea [usar Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Leer con ReadOnlySequence de varios segmentos

Si la entrada JSON es una [> ReadOnlySpan\<byte](xref:System.ReadOnlySpan%601), se puede tener acceso a cada elemento JSON desde la propiedad `ValueSpan` en el lector a medida que avanza por el bucle de lectura. Sin embargo, si la entrada es una [ReadOnlySequence\<byte >](xref:System.Buffers.ReadOnlySequence%601) (que es el resultado de leer de un <xref:System.IO.Pipelines.PipeReader>), algunos elementos JSON podrían ocupar varios segmentos del objeto `ReadOnlySequence<byte>`. No se puede obtener acceso a estos elementos desde <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> en un bloque de memoria contiguo. En su lugar, siempre que tenga un `ReadOnlySequence<byte>` de varios segmentos como entrada, sondee la propiedad <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> en el lector para averiguar cómo tener acceso al elemento JSON actual. Este es un patrón recomendado:

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

No use <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> para realizar comparaciones byte a Byte mediante una llamada a <xref:System.MemoryExtensions.SequenceEqual%2A> para las búsquedas de nombres de propiedad. En su lugar, llame a <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>, ya que ese método anula la escape de los caracteres que se van a escapar en JSON. Este es un ejemplo que muestra cómo buscar una propiedad denominada "Name":

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Leer valores NULL en tipos de valor que aceptan valores NULL

`Newtonsoft.Json` proporciona API que devuelven <xref:System.Nullable%601>, como `ReadAsBoolean`, que controla una `TokenType` de `Null` para usted mediante la devolución de una `bool?`. Las API integradas de `System.Text.Json` devuelven solo tipos de valor que no aceptan valores NULL. Por ejemplo, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> devuelve un `bool`. Produce una excepción si encuentra `Null` en el archivo JSON. En los siguientes ejemplos se muestran dos formas de controlar valores NULL, uno devolviendo un tipo de valor que acepta valores NULL y otro devolviendo el valor predeterminado:

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

Si necesita seguir usando `Newtonsoft.Json` para determinadas plataformas de destino, puede usar varias implementaciones y tener dos. Sin embargo, esto no es trivial y requeriría algunos `#ifdefs` y la duplicación de origen. Una manera de compartir todo el código posible es crear un contenedor de `ref struct` alrededor de `Utf8JsonReader` y `Newtonsoft.Json` `JsonTextReader`. Este contenedor unificaría el área expuesta pública al aislar las diferencias de comportamiento. Esto le permite aislar los cambios principalmente en la construcción del tipo, junto con pasar el nuevo tipo por referencia. Este es el patrón que sigue la biblioteca [Microsoft. Extensions. DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) :

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter comparado con objeto JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> es una forma de alto rendimiento de escribir texto JSON con codificación UTF-8 de tipos comunes de .NET como `String`, `Int32`y `DateTime`. El escritor es un tipo de nivel bajo que se puede utilizar para crear serializadores personalizados.

En las siguientes secciones se explican los patrones de programación recomendados para el uso de `Utf8JsonWriter`.

### <a name="write-with-utf-8-text"></a>Escribir con texto UTF-8

Para lograr el mejor rendimiento posible mientras usa el `Utf8JsonWriter`, escriba cargas JSON ya codificadas como texto UTF-8 en lugar de como cadenas UTF-16. Utilice <xref:System.Text.Json.JsonEncodedText> para almacenar en caché y codificar previamente los nombres y valores de las propiedades de cadena conocidas como estáticas, y pasarlos al escritor, en lugar de usar literales de cadena UTF-16. Esto es más rápido que el almacenamiento en caché y el uso de matrices de bytes UTF-8.

Este enfoque también funciona si necesita realizar un escape personalizado. `System.Text.Json` no permite deshabilitar el escape mientras se escribe una cadena. Sin embargo, podría pasar su propio <xref:System.Text.Encodings.Web.JavaScriptEncoder> personalizado como una opción al escritor, o crear su propia `JsonEncodedText` que use su `JavascriptEncoder` para realizar el escape y, a continuación, escribir el `JsonEncodedText` en lugar de la cadena. Para obtener más información, vea [personalizar la codificación de caracteres](system-text-json-how-to.md#customize-character-encoding).

### <a name="write-raw-values"></a>Escribir valores sin formato

El método `Newtonsoft.Json` `WriteRawValue` escribe el JSON sin formato en el que se espera un valor. <xref:System.Text.Json> no tiene ningún equivalente directo, pero esta es una solución alternativa que garantiza que solo se escribe un JSON válido:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Personalizar el escape de caracteres

El valor [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) de `JsonTextWriter` ofrece opciones para escapar todos los caracteres que no sean ASCII **o** caracteres HTML. De forma predeterminada, `Utf8JsonWriter` escapa a todos los caracteres no ASCII **y** HTML. Este escape se hace por motivos de seguridad de defensa en profundidad. Para especificar una directiva de escape diferente, cree una <xref:System.Text.Encodings.Web.JavaScriptEncoder> y establezca <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>. Para obtener más información, vea [personalizar la codificación de caracteres](system-text-json-how-to.md#customize-character-encoding).

### <a name="customize-json-format"></a>Personalizar el formato JSON

`JsonTextWriter` incluye la configuración siguiente, para la que `Utf8JsonWriter` no tiene ningún equivalente:

* [Indentación](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) : especifica el número de caracteres que se van a aplicar sangría. `Utf8JsonWriter` siempre realiza la sangría de 2 caracteres.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) : especifica el carácter que se va a utilizar para la sangría.  `Utf8JsonWriter` usa siempre el espacio en blanco.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) : especifica el carácter que se va a usar para rodear valores de cadena.  `Utf8JsonWriter` siempre usa comillas dobles.
* [QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) : especifica si los nombres de propiedad deben encerrarse entre comillas.  `Utf8JsonWriter` siempre se coloca entre comillas.

No hay ninguna solución alternativa que permita personalizar el JSON generado por `Utf8JsonWriter` de estas maneras.

### <a name="write-null-values"></a>Escribir valores NULL

Para escribir valores NULL mediante `Utf8JsonWriter`, llame a:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> para escribir un par clave-valor con NULL como valor.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> para escribir NULL como un elemento de una matriz JSON.

En el caso de una propiedad de cadena, si la cadena es null, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> y <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> son equivalentes a `WriteNull` y `WriteNullValue`.

### <a name="write-timespan-uri-or-char-values"></a>Escribir valores TimeSpan, Uri o char

`JsonTextWriter` proporciona métodos de `WriteValue` para los valores [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)y [Char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) . `Utf8JsonWriter` no tiene métodos equivalentes. En su lugar, dé formato a estos valores como cadenas (llamando `ToString()`, por ejemplo) y llame a <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.

### <a name="multi-targeting"></a>Compatibilidad con múltiples versiones

Si necesita seguir usando `Newtonsoft.Json` para determinadas plataformas de destino, puede usar varias implementaciones y tener dos. Sin embargo, esto no es trivial y requeriría algunos `#ifdefs` y la duplicación de origen. Una manera de compartir todo el código posible es crear un contenedor alrededor de `Utf8JsonWriter` y `Newtonsoft` `JsonTextWriter`. Este contenedor unificaría el área expuesta pública al aislar las diferencias de comportamiento. Esto le permite aislar los cambios principalmente en la construcción del tipo. A continuación se muestra la biblioteca [Microsoft. Extensions. DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) :

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Recursos adicionales

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [Información general de System.Text.Json](system-text-json-overview.md)
* [Cómo usar System.Text.Json](system-text-json-how-to.md)
* [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)
* [referencia de API de System.Text.Json](xref:System.Text.Json)
* [System.Text.Json. Referencia de API de serialización](xref:System.Text.Json.Serialization)
