---
title: Migración desde Newtonsoft.Json a System.Text.Json - .NET
author: ''
ms.author: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: ''
helpviewer_keywords: []
ms.openlocfilehash: fe370b34d311816a815f3b2d419751ac7871f013
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703584"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Procedimiento para realizar la migración de Newtonsoft.Json a System.Text.Json

En este artículo se muestra cómo realizar la migración de [Newtonsoft.Json](https://www.newtonsoft.com/json) a <xref:System.Text.Json>.

El espacio de nombres `System.Text.Json` proporciona funcionalidad para serializar y deserializar desde JSON (notaciones de objetos JavaScript). La biblioteca de `System.Text.Json` se incluye en el marco compartido de [.NET Core 3.0](https://aka.ms/netcore3download). En cuanto a otros marcos de destino, instale el paquete NuGet [System.Text.Json](https://www.nuget.org/packages/System.Text.Json), que admite lo siguiente:

* .NET Standard 2.0 y versiones posteriores
* .NET Framework 4.7.2 y versiones posteriores
* .NET Core 2.0, 2.1 y 2.2

`System.Text.Json` se centra principalmente en el rendimiento, la seguridad y el cumplimiento de estándares. Tiene algunas diferencias clave en el comportamiento predeterminado y no pretende tener paridad de características con `Newtonsoft.Json`. En algunos escenarios, `System.Text.Json` no tiene ninguna funcionalidad integrada, pero se recomiendan algunas soluciones alternativas. En otros escenarios, las soluciones alternativas no son prácticas. Si su aplicación depende de una característica que falta, puede [presentar una incidencia](https://github.com/dotnet/runtime/issues/new) para averiguar si se puede agregar compatibilidad para su escenario.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

La mayor parte de este artículo trata sobre cómo usar la API de <xref:System.Text.Json.JsonSerializer>, pero también incluye instrucciones sobre cómo usar <xref:System.Text.Json.JsonDocument> (que representa los Document Object Model o DOM), <xref:System.Text.Json.Utf8JsonReader> y <xref:System.Text.Json.Utf8JsonWriter>.

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a>Tabla de diferencias entre Newtonsoft.Json y System.Text.Json

En la siguiente tabla se enumeran las características de `Newtonsoft.Json` y las equivalentes de `System.Text.Json`. Existen varias categorías de equivalentes:

* Compatible con la funcionalidad integrada. Para obtener un comportamiento similar al de `System.Text.Json` es posible que se requiera el uso de un atributo o una opción global.
* No compatible; hay disponible una solución alternativa. Las soluciones alternativas son [convertidores personalizados](system-text-json-converters-how-to.md), que puede que no proporcionen una paridad completa con la funcionalidad `Newtonsoft.Json`. En esos casos, se proporciona un código de ejemplo como muestra. Si confía en estas características de `Newtonsoft.Json`, la migración requerirá modificaciones en los modelos de objetos .NET u otros cambios de código.
* No compatible; la solución alternativa no es práctica o no es posible. Si confía en estas características de `Newtonsoft.Json`, no será posible realizar la migración sin cambios importantes.

| Característica: Newtonsoft.Json                               | Equivalente: System.Text.Json |
|---
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

----------------------------|--- title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

-
title: 'Migración de Newtonsoft.Json a System.Text.Json: .NET' author: ms.author: no-loc:
- "System.Text.Json"
- 'Newtonsoft.Json' ms.date: helpviewer_keywords:
- 
- 
- 
- 

---------------| | Deserialización sin diferencias entre mayúsculas y minúsculas de forma predeterminada           | ✔️ [Configuración global PropertyNameCaseInsensitive global](#case-insensitive-deserialization) | | Nombres de propiedades en formato camelCase                             | ✔️ [Configuración global PropertyNamingPolicy](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) | | Escapado de caracteres mínimo                            | ✔️ [Escapado de caracteres estricto y configurable](#minimal-character-escaping) | | Configuración global `NullValueHandling.Ignore`             | ✔️ [Opción global IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) | | Permiso para comentarios                                        | ✔️ [Opción global ReadCommentHandling](#comments) | | Permiso para comas finales                                 | ✔️ [Configuración global AllowTrailingCommas](#trailing-commas) | | Registro de convertidores personalizados                         | ✔️ [Diferencia en el orden de precedencia](#converter-registration-precedence) | | Ninguna profundidad máxima de forma predeterminada                           | ✔️ [Profundidad máxima predeterminada de 64 configurable](#maximum-depth) | | Compatibilidad con una gran variedad de tipos                    | ⚠️ [Requisito de convertidores personalizados para algunos tipos](#types-without-built-in-support) | | Deserialización de cadenas como números                        | ⚠️ [No se admite; solución alternativa; muestra](#quoted-numbers) | | Deserialización de `Dictionary` con una clave que no es una cadena          | ⚠️ [No se admite; solución alternativa; muestra](#dictionary-with-non-string-key) | | Serialización polimórfica                             | ⚠️ [No se admite; solución alternativa; muestra](#polymorphic-serialization) | | Deserialización polimórfica                           | ⚠️ [No se admite; solución alternativa; muestra](#polymorphic-deserialization) | | Deserialización de tipos inferidos en propiedades `object`      | ⚠️ [No se admite; solución alternativa; muestra](#deserialization-of-object-properties) | | Deserialización de literales JSON `null` en tipos de valores que no aceptan valores NULL | ⚠️ [No se admite; solución alternativa; muestra](#deserialize-null-to-non-nullable-type) | | Deserialización en clases y estructuras inmutables          | ⚠️ [No se admite; solución alternativa; muestra](#deserialize-to-immutable-classes-and-structs) | | Atributo `[JsonConstructor]`                         | ⚠️ [No se admite; solución alternativa; muestra](#specify-constructor-to-use) | | Configuración `Required` en el atributo `[JsonProperty]`        | ⚠️ [No se admite; solución alternativa; muestra](#required-properties) | | Configuración `NullValueHandling` en el atributo `[JsonProperty]` | ⚠️ [No se admite; solución alternativa; muestra](#conditionally-ignore-a-property) | | Configuración `DefaultValueHandling` en el atributo `[JsonProperty]` | ⚠️ [No se admite; solución alternativa; muestra](#conditionally-ignore-a-property) | | Configuración global `DefaultValueHandling`                 | ⚠️ [No se admite; solución alternativa; muestra](#conditionally-ignore-a-property) | | `DefaultContractResolver` para excluir propiedades       | ⚠️ [No se admite; solución alternativa; muestra](#conditionally-ignore-a-property) | | Configuraciones `DateTimeZoneHandling` y `DateFormatString`   | ⚠️ [No se admite; solución alternativa; muestra](#specify-date-format) | | Devoluciones de llamadas                                             | ⚠️ [No se admite; solución alternativa; muestra](#callbacks) | | Compatibilidad con campos públicos y no públicos              | ⚠️ [No se admite; solución alternativa](#public-and-non-public-fields) | | Compatibilidad con establecedores y obtenedores de propiedades internos y privados | ⚠️ [No se admite; solución alternativa](#internal-and-private-property-setters-and-getters) | | Método `JsonConvert.PopulateObject`                   | ⚠️ [No se admite; solución alternativa](#populate-existing-objects) | | Configuración global `ObjectCreationHandling`               | ⚠️ [No se admite; solución alternativa](#reuse-rather-than-replace-properties) | | Adición de colecciones sin establecedores                    | ⚠️ [No se admite; solución alternativa](#add-to-collections-without-setters) | | Configuración global `PreserveReferencesHandling`           | ❌ [No se admite](#preserve-object-references-and-handle-loops) | | Configuración global `ReferenceLoopHandling`                | ❌ [No se admite](#preserve-object-references-and-handle-loops) | | Compatibilidad con atributos `System.Runtime.Serialization` | ❌ [No se admite](#systemruntimeserialization-attributes) | | Configuración global `MissingMemberHandling`                | ❌ [No se admite](#missingmemberhandling) | | Permiso para nombres de propiedades sin comillas                   | ❌ [No se admite](#json-strings-property-names-and-string-values) | | Permiso para comillas simples alrededor de valores de cadenas              | ❌ [No se admite](#json-strings-property-names-and-string-values) | | Permiso para valores JSON que no son de cadena para propiedades de cadenas    | ❌ [No se admite](#non-string-values-for-string-properties) |

Esta no es una lista exhaustiva de características de `Newtonsoft.Json`. La lista incluye muchos de los escenarios que se han solicitado en publicaciones de [problemas de GitHub](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) o [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json). Si implementa una solución alternativa para uno de los escenarios que aquí se enumeran que no tenga actualmente un código de ejemplo, y si quiere compartir la solución, haga clic en **Esta página** en la sección **Comentarios** de la parte inferior de esta página. De esta forma se abre una incidencia en el repositorio de GitHub de esta documentación y también se muestra en la sección **Comentarios** de esta página.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>Diferencias en el comportamiento predeterminado de JsonSerializer en comparación con Newtonsoft.Json

<xref:System.Text.Json> es estricto de forma predeterminada y evita cualquier conjetura o interpretación en nombre del llamador, con lo que resalta el comportamiento determinista. La biblioteca se ha diseñado intencionadamente de esta manera por motivos de rendimiento y seguridad. De manera predeterminada, `Newtonsoft.Json` es flexible. Esta diferencia fundamental en el diseño es la responsable de muchas de las siguientes diferencias específicas en el comportamiento predeterminado.

### <a name="case-insensitive-deserialization"></a>Deserialización sin distinción entre mayúsculas y minúsculas

Durante la deserialización, `Newtonsoft.Json` realiza de forma predeterminada la coincidencia de nombres de propiedad sin distinción entre mayúsculas y minúsculas. El valor predeterminado de <xref:System.Text.Json> distingue entre mayúsculas y minúsculas, lo que proporciona un mejor rendimiento, ya que realiza una coincidencia exacta. Para obtener información sobre cómo realizar la coincidencia sin distinción entre mayúsculas y minúsculas, vea [Coincidencia de propiedades sin distinción entre mayúsculas y minúsculas](system-text-json-how-to.md#case-insensitive-property-matching).

Si usa `System.Text.Json` indirectamente mediante ASP.NET Core, no es necesario hacer nada para obtener un comportamiento como `Newtonsoft.Json`. ASP.NET Core especifica los valores para los [nombres de propiedad con grafía Camel](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) y la coincidencia sin distinción entre mayúsculas y minúsculas cuando usa `System.Text.Json`.

### <a name="minimal-character-escaping"></a>Mínimo escape de caracteres

Durante la serialización, `Newtonsoft.Json` es relativamente permisivo con respecto a si se permite que los caracteres queden sin escapar. Es decir, no los reemplaza por `\uxxxx` donde `xxxx` es el punto de código del carácter. En aquellos casos donde los escapa, lo hace emitiendo una `\` antes del carácter (por ejemplo, `"` se convierte en `\"`). De forma predeterminada, <xref:System.Text.Json> escapa más caracteres para proporcionar protecciones de defensa en profundidad contra los ataques de scripting entre sitios (XSS) o de divulgación de información, y lo hace mediante el uso de la secuencia de seis caracteres. `System.Text.Json` escapa todos los caracteres que no sean ASCII de forma predeterminada, por lo que no es necesario hacer nada si usa `StringEscapeHandling.EscapeNonAscii` en `Newtonsoft.Json`. `System.Text.Json` de forma predeterminada también escapa los caracteres que distinguen HTML. Para obtener información sobre cómo invalidar el comportamiento predeterminado de `System.Text.Json`, vea [Personalización de la codificación de caracteres](system-text-json-how-to.md#customize-character-encoding).

### <a name="comments"></a>Comentarios

Durante la deserialización, `Newtonsoft.Json` omite de forma predeterminada los comentarios en JSON. El valor predeterminado de <xref:System.Text.Json> es producir excepciones para los comentarios porque la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no los incluye. Para obtener información sobre cómo permitir comentarios, vea [Permitir comentarios y comas finales](system-text-json-how-to.md#allow-comments-and-trailing-commas).

### <a name="trailing-commas"></a>Comas finales

Durante la deserialización, `Newtonsoft.Json` omite de forma predeterminada las comas finales. También omite varias comas finales (por ejemplo, `[{"Color":"Red"},{"Color":"Green"},,]`). El valor predeterminado de <xref:System.Text.Json> es producir excepciones para las comas finales porque la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no las permite. Para obtener información sobre cómo hacer que `System.Text.Json` las acepte, vea [Permitir comentarios y comas finales](system-text-json-how-to.md#allow-comments-and-trailing-commas). No hay ninguna manera de permitir varias comas finales.

### <a name="converter-registration-precedence"></a>Precedencia de registro del convertidor

La precedencia de registro de `Newtonsoft.Json` para los convertidores personalizados es la siguiente:

* Atributo en la propiedad
* Atributo en el tipo
* Colección de [convertidores](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm)

Este orden implica que un convertidor que se registre aplicando un atributo en el nivel de tipo invalidará a un convertidor personalizado de la colección `Converters`, y un atributo en el nivel de propiedad invalidará a ambos registros.

La precedencia de registro de <xref:System.Text.Json> para los convertidores personalizados es diferente:

* Atributo en la propiedad
* Colección <xref:System.Text.Json.JsonSerializerOptions.Converters>
* Atributo en el tipo

En este caso, la diferencia es que un convertidor personalizado de la colección `Converters` invalida a un atributo en el nivel de tipo. La intención de este orden de precedencia es que los cambios de tiempo de ejecución invaliden las opciones de tiempo de diseño. No hay ninguna manera de cambiar la precedencia.

Para más información sobre el registro de convertidores personalizados, vea [Registro de un convertidor personalizado](system-text-json-converters-how-to.md#register-a-custom-converter).

### <a name="maximum-depth"></a>Profundidad máxima

De forma predeterminada, `Newtonsoft.Json` no tiene un límite de profundidad máxima. Par <xref:System.Text.Json> hay un límite predeterminado de 64, y se puede configurar mediante el valor <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>.

### <a name="json-strings-property-names-and-string-values"></a>Cadenas JSON (nombres de propiedad y valores de cadena)

Durante la deserialización, `Newtonsoft.Json` acepta nombres de propiedad entre comillas dobles, comillas simples o sin comillas. Acepta valores de cadena entre comillas dobles o comillas simples. Por ejemplo, `Newtonsoft.Json` acepta el siguiente código JSON:

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json` solo acepta nombres de propiedad y valores de cadena entre comillas dobles, ya que ese es el formato requerido por la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) y es el único formato que se considera JSON válido.

Un valor entre comillas simples da como resultado una [JsonException](xref:System.Text.Json.JsonException) con el siguiente mensaje:

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>Valores que no son de cadena para propiedades de cadena

`Newtonsoft.Json` acepta valores que no son de cadena, como un número o los literales `true` y `false` para la deserialización de las propiedades de tipo cadena. A continuación se muestra un ejemplo de JSON que deserializa correctamente `Newtonsoft.Json` en la clase siguiente:

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

`System.Text.Json` no deserializa valores que no son de cadena en propiedades de cadena. Un valor que no sea de cadena recibido para un campo de cadena da como resultado una [JsonException](xref:System.Text.Json.JsonException) con el siguiente mensaje:

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>Escenarios con JsonSerializer que requieren soluciones alternativas

Los escenarios siguientes no son compatibles con la funcionalidad integrada, pero hay disponibles soluciones alternativas. Las soluciones alternativas son [convertidores personalizados](system-text-json-converters-how-to.md), que puede que no proporcionen una paridad completa con la funcionalidad `Newtonsoft.Json`. En esos casos, se proporciona un código de ejemplo como muestra. Si confía en estas características de `Newtonsoft.Json`, la migración requerirá modificaciones en los modelos de objetos .NET u otros cambios de código.

### <a name="types-without-built-in-support"></a>Tipos sin compatibilidad integrada

<xref:System.Text.Json> no proporciona compatibilidad integrada con los siguientes tipos:

* <xref:System.Data.DataTable> y tipos relacionados
* Tipos en F#, como las [uniones discriminadas](../../fsharp/language-reference/discriminated-unions.md), los [tipos de registro](../../fsharp/language-reference/records.md) y los [tipos de registros anónimos](../../fsharp/language-reference/anonymous-records.md).
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> y sus tipos genéricos asociados

Se pueden implementar convertidores personalizados para tipos que no tienen compatibilidad integrada.

### <a name="quoted-numbers"></a>Números entrecomillados

`Newtonsoft.Json` puede serializar o deserializar los números representados por cadenas JSON (entre comillas). Por ejemplo, puede aceptar: `{"DegreesCelsius":"23"}` en lugar de `{"DegreesCelsius":23}`. Para habilitar ese comportamiento en <xref:System.Text.Json>, implemente un convertidor personalizado como el ejemplo siguiente. El convertidor controla las propiedades definidas como `long`:

* Las serializa como cadenas JSON.
* Acepta números de JSON y números entre comillas durante la deserialización.

[!code-csharp[](snippets/system-text-json-how-to/csharp/LongToStringConverter.cs)]

Registre este convertidor personalizado [usando un atributo](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) en propiedades individuales de `long` o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters>.

### <a name="dictionary-with-non-string-key"></a>Diccionario con clave que no es de cadena

`Newtonsoft.Json` admite colecciones de tipo `Dictionary<TKey, TValue>`. La compatibilidad integrada con colecciones de diccionarios en <xref:System.Text.Json> se limita a `Dictionary<string, TValue>`. Por lo tanto, la clave debe ser una cadena.

Para admitir un diccionario con un entero o algún otro tipo como clave, cree un convertidor como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key).

### <a name="polymorphic-serialization"></a>Serialización polimórfica

`Newtonsoft.Json` realiza automáticamente la serialización polimórfica. Para obtener información sobre las capacidades limitadas de serialización polimórfica de <xref:System.Text.Json>, vea [Serialización de propiedades de clases derivadas](system-text-json-how-to.md#serialize-properties-of-derived-classes).

La solución alternativa que se describe aquí es para definir propiedades que pueden contener clases derivadas como el tipo `object`. Si eso no es posible, otra opción es crear un convertidor con un método `Write` para toda la jerarquía de tipo de herencia, como en el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="polymorphic-deserialization"></a>Deserialización polimórfica

`Newtonsoft.Json` tiene un valor `TypeNameHandling` que agrega metadatos de nombre de tipo al JSON durante la serialización. Usa los metadatos durante la deserialización para realizar la deserialización polimórfica. <xref:System.Text.Json> puede realizar un intervalo limitado de [serialización polimórfica](system-text-json-how-to.md#serialize-properties-of-derived-classes), pero no deserialización polimórfica.

Para admitir la deserialización polimórfica, cree un convertidor como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#support-polymorphic-deserialization).

### <a name="deserialization-of-object-properties"></a>Deserialización de propiedades de objeto

Cuando `Newtonsoft.Json` deserializa en <xref:System.Object>:

* infiere el tipo de valores primitivos en la carga JSON (excepto `null`) y devuelve los valores `string`, `long`, `double`, `boolean` o `DateTime` almacenados como un objeto al que se ha aplicado la conversión boxing. Los *valores primitivos* son valores JSON únicos, como un número JSON, una cadena, un valor `true`, `false` o `null`.
* Devuelve `JObject` o `JArray` para valores complejos en la carga de JSON. Los *valores complejos* son colecciones de pares clave-valor JSON entre llaves (`{}`) o listas de valores entre corchetes (`[]`). Las propiedades y los valores entre llaves o corchetes pueden tener propiedades o valores adicionales.
* Devuelve una referencia nula cuando la carga útil tiene el literal JSON `null`.

<xref:System.Text.Json> almacena un objeto `JsonElement` al que se ha aplicado la conversión boxing para valores primitivos y los complejos, siempre que se deserialice en <xref:System.Object>; por ejemplo:

* Propiedad `object`.
* Un valor de diccionario `object`.
* Un valor de matriz `object`.
* Una raíz `object`.

Pero `System.Text.Json` trata `null` igual que `Newtonsoft.Json`, y devuelve una referencia nula cuando la carga útil tiene el literal JSON `null` en ella.

Para implementar la inferencia de tipos para las propiedades `object`, cree un convertidor como el ejemplo de [Cómo escribir convertidores personalizados](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties).

### <a name="deserialize-null-to-non-nullable-type"></a>Deserialización de null en un tipo que no acepta valores NULL

`Newtonsoft.Json` no provoca una excepción en el escenario siguiente:

* `NullValueHandling` se establece en `Ignore` y,
* durante la deserialización, el archivo JSON contiene un valor NULL para un tipo de valor que no acepta valores NULL.

En el mismo escenario, <xref:System.Text.Json> produce una excepción. (La configuración de control de valores NULL correspondiente es <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>).

Si es el propietario del tipo de destino, la mejor solución alternativa posible es hacer que la propiedad en cuestión acepte valores NULL (por ejemplo, cambiar `int` a `int?`).

Otra solución alternativa consiste en crear un convertidor para el tipo, como en el ejemplo siguiente, en el que se tratan los valores NULL de los tipos `DateTimeOffset`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs)]

Registre este convertidor personalizado [usando un atributo en la propiedad](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters>.

**Nota:** El convertidor anterior **trata los valores NULL de manera diferente** de como lo hace `Newtonsoft.Json` para los POCO que especifican valores predeterminados. Por ejemplo, suponga que el siguiente código representa su objeto de destino:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Y suponga que el siguiente código JSON se deserializa con el convertidor anterior:

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Después de la deserialización, la propiedad `Date` tiene 1/1/0001 (`default(DateTimeOffset)`), es decir, se sobrescribe el valor establecido en el constructor. Dados los mismos objetos POCO y JSON, la deserialización de `Newtonsoft.Json` dejaría 1/1/2001 en la propiedad `Date`.

### <a name="deserialize-to-immutable-classes-and-structs"></a>Deserialización en clases y estructuras inmutables

`Newtonsoft.Json` se puede deserializar en clases y estructuras inmutables, ya que puede usar constructores que tengan parámetros. <xref:System.Text.Json> solo admite constructores públicos carentes de parámetros. Como solución alternativa, puede llamar a un constructor con parámetros en un convertidor personalizado.

A continuación se muestra una estructura inmutable con varios parámetros de constructor:

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePoint.cs#ImmutablePoint)]

Y este es un convertidor que serializa y deserializa esta estructura:

[!code-csharp[](snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs)]

Registre este convertidor personalizado [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Para obtener un ejemplo de un convertidor similar que controla las propiedades genéricas abiertas, vea el [convertidor integrado para pares clave-valor](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs).

### <a name="specify-constructor-to-use"></a>Especificación del constructor que se va a usar

El atributo `[JsonConstructor]` de `Newtonsoft.Json` le permite especificar el constructor al que se llamará al deserializar en un objeto POCO. <xref:System.Text.Json> solo admite constructores carentes de parámetros. Como solución alternativa, puede llamar al constructor que necesite en un convertidor personalizado. Vea el ejemplo para [deserialización en clases y estructuras inmutables](#deserialize-to-immutable-classes-and-structs).

### <a name="required-properties"></a>Propiedades obligatorias

En `Newtonsoft.Json`, especifica que se requiere una propiedad estableciendo `Required` en el atributo `[JsonProperty]`. `Newtonsoft.Json` produce una excepción si no se recibe ningún valor en el objeto JSON para una propiedad marcada como requerida.

<xref:System.Text.Json> no produce una excepción si no se recibe ningún valor para una de las propiedades del tipo de destino. Por ejemplo, si tiene una clase `WeatherForecast`:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

El siguiente JSON se deserializa sin errores:

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

Para que se produzca un error en la deserialización si no hay una propiedad `Date` en el objeto JSON, implemente un convertidor personalizado. El siguiente código de convertidor de ejemplo produce una excepción si no se establece la propiedad `Date` cuando se completa la deserialización:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs)]

Registre este convertidor personalizado [usando un atributo en la clase POCO](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Si sigue este patrón, no pase el objeto de opciones cuando llame a <xref:System.Text.Json.JsonSerializer.Serialize%2A> o <xref:System.Text.Json.JsonSerializer.Deserialize%2A>de forma recursiva. El objeto de opciones contiene la colección <xref:System.Text.Json.JsonSerializerOptions.Converters%2A>. Si lo pasa a `Serialize` o `Deserialize`, el convertidor personalizado se llama a sí mismo, con lo que se crea un bucle infinito que produce una excepción de desbordamiento de pila. Si las opciones predeterminadas no son factibles, cree una nueva instancia de las opciones con la configuración que necesite. Este enfoque será lento, ya que cada instancia nueva se almacena en caché de forma independiente.

El código de convertidor anterior es un ejemplo simplificado. Se requeriría lógica adicional si necesita controlar atributos (como [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) u otras opciones (como codificadores personalizados). Además, el código de ejemplo no controla las propiedades para las que se establece un valor predeterminado en el constructor, y este enfoque no distingue entre los siguientes escenarios:

* Falta una propiedad en el objeto JSON.
* Hay una propiedad para un tipo que no acepta valores NULL en el objeto JSON, pero el valor es el predeterminado para el tipo, como cero para `int`.
* Hay una propiedad para un tipo de valor que acepta valores NULL en el objeto JSON, pero el valor es NULL.

### <a name="conditionally-ignore-a-property"></a>Omitir condicionalmente una propiedad

`Newtonsoft.Json` ofrece varias formas de omitir condicionalmente una propiedad en la serialización o deserialización:

* `DefaultContractResolver` le permite seleccionar las propiedades que se van a incluir o excluir, en función de criterios arbitrarios.
* Los valores `NullValueHandling` y `DefaultValueHandling` de `JsonSerializerSettings` le permiten especificar que se deben omitir todas las propiedades de valores NULL o valores predeterminados.
* Los valores `NullValueHandling` y `DefaultValueHandling` del atributo `[JsonProperty]` le permiten especificar propiedades individuales que se deben omitir cuando se establecen en null o en el valor predeterminado.

<xref:System.Text.Json> proporciona las siguientes formas de omitir las propiedades durante la serialización:

* El atributo [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) de una propiedad hace que la propiedad se omita en el objeto JSON durante la serialización.
* La opción global [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) le permite excluir todas las propiedades de valores NULL.
* La opción global [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) le permite excluir todas las propiedades de solo lectura.

Estas opciones **no** le permiten:

* Omitir todas las propiedades que tienen el valor predeterminado para el tipo.
* Omitir todas las propiedades seleccionadas que tienen el valor predeterminado para el tipo.
* Omitir las propiedades seleccionadas si su valor es NULL.
* Omitir las propiedades seleccionadas en función de criterios arbitrarios evaluados en tiempo de ejecución.

Para esa funcionalidad, puede escribir un convertidor personalizado. Este es un POCO de ejemplo y un convertidor personalizado para él que ilustra este enfoque:

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

El convertidor hace que se omita la propiedad `Summary` de la serialización si su valor es NULL, una cadena vacía o "N/A".

Registre este convertidor personalizado [usando un atributo en la clase](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Este enfoque requiere lógica adicional en los siguientes casos:

* El objeto POCO incluye propiedades complejas.
* Debe controlar los atributos como `[JsonIgnore]`, o las opciones como los codificadores personalizados.

### <a name="specify-date-format"></a>Especificación del formato de fecha

`Newtonsoft.Json` proporciona varias maneras de controlar cómo se serializan y deserializan las propiedades de los tipos `DateTime` y `DateTimeOffset`:

* El valor `DateTimeZoneHandling` se puede usar para serializar todos los valores `DateTime` como fechas UTC.
* El valor `DateFormatString` y los convertidores de `DateTime` se pueden usar para personalizar el formato de las cadenas de fecha.

En <xref:System.Text.Json>, el único formato que tiene compatibilidad integrada es ISO 8601-1:2019, ya que se ha adoptado ampliamente, no es ambiguo, y realiza de forma precisa los recorridos de ida y vuelta. Para usar cualquier otro formato, cree un convertidor personalizado. Para obtener más información, consulte [Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md).

### <a name="callbacks"></a>Devoluciones de llamada

`Newtonsoft.Json` le permite ejecutar código personalizado en varios puntos en el proceso de serialización o deserialización:

* OnDeserializing: al empezar a deserializar un objeto
* OnDeserialized: al finalizar la deserialización de un objeto
* OnSerializing: al empezar a serializar un objeto
* OnSerialized: al finalizar la serialización de un objeto

En <xref:System.Text.Json>, puede simular devoluciones de llamada escribiendo un convertidor personalizado. En el ejemplo siguiente se muestra un convertidor personalizado para un objeto POCO. El convertidor incluye código que muestra un mensaje en cada punto que corresponde a una devolución de llamada de `Newtonsoft.Json`.

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs)]

Registre este convertidor personalizado [usando un atributo en la clase](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) o [agregando el convertidor](system-text-json-converters-how-to.md#registration-sample---converters-collection) a la colección <xref:System.Text.Json.JsonSerializerOptions.Converters>.

Si usa un convertidor personalizado que sigue el ejemplo anterior:

* El código `OnDeserializing` no tiene acceso a la nueva instancia POCO. Para manipular la nueva instancia POCO al inicio de la deserialización, coloque ese código en el constructor POCO.
* No pase el objeto de opciones cuando llame a `Serialize` o `Deserialize`de forma recursiva. El objeto de opciones contiene la colección `Converters`. Si lo pasa a `Serialize` o `Deserialize`, se usará el convertidor, con lo que se crea un bucle infinito que produce una excepción de desbordamiento de pila.

### <a name="public-and-non-public-fields"></a>Campos públicos y no públicos

`Newtonsoft.Json` puede serializar y deserializar los campos, así como las propiedades. <xref:System.Text.Json> solo funciona con propiedades públicas. Los convertidores personalizados no proporcionan esta funcionalidad.

### <a name="internal-and-private-property-setters-and-getters"></a>Captadores y establecedores de propiedades internos y privados

`Newtonsoft.Json` puede usar captadores y establecedores de propiedades internos y privados a través del atributo `JsonProperty`. <xref:System.Text.Json> solo admite establecedores públicos. Los convertidores personalizados no proporcionan esta funcionalidad.

### <a name="populate-existing-objects"></a>Rellenar objetos existentes

El método `JsonConvert.PopulateObject` de `Newtonsoft.Json` deserializa un documento JSON en una instancia existente de una clase, en lugar de crear una nueva instancia. <xref:System.Text.Json> siempre crea una nueva instancia del tipo de destino mediante el constructor sin parámetros público predeterminado. Los convertidores personalizados se pueden deserializar en una instancia existente.

### <a name="reuse-rather-than-replace-properties"></a>Reutilización en lugar de reemplazo de propiedades

El valor `ObjectCreationHandling` de `Newtonsoft.Json` le permite especificar que los objetos de las propiedades deben reutilizarse en lugar de reemplazarse durante la deserialización. <xref:System.Text.Json> siempre reemplaza los objetos en las propiedades.  Los convertidores personalizados no proporcionan esta funcionalidad.

### <a name="add-to-collections-without-setters"></a>Agregar a colecciones sin establecedores

Durante la deserialización, `Newtonsoft.Json` agrega objetos a una colección, incluso si la propiedad no tiene ningún establecedor. <xref:System.Text.Json> omite las propiedades que no tienen establecedores. Los convertidores personalizados no proporcionan esta funcionalidad.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Escenarios que JsonSerializer no admite actualmente

En los escenarios siguientes, no hay ninguna solución alternativa que sea práctica o posible. Si confía en estas características de `Newtonsoft.Json`, no será posible realizar la migración sin cambios importantes.

### <a name="preserve-object-references-and-handle-loops"></a>Conservación de referencias a objetos y procesado de bucles

De forma predeterminada, `Newtonsoft.Json` realiza la serialización por valor. Por ejemplo, si un objeto contiene dos propiedades que contienen una referencia al mismo objeto `Person`, los valores de las propiedades de dicho objeto `Person` se duplican en JSON.

`Newtonsoft.Json` tiene un valor `PreserveReferencesHandling` en `JsonSerializerSettings` que le permite realizar serializaciones por referencia:

* Los metadatos de un identificador se agregan al JSON creado para el primer objeto `Person`.
* El JSON que se crea para el segundo objeto `Person` contiene una referencia a ese identificador en lugar de los valores de propiedad.

`Newtonsoft.Json` también tiene un valor `ReferenceLoopHandling` que le permite omitir las referencias circulares en lugar de producir una excepción.

<xref:System.Text.Json> solo admite la serialización por valor y produce una excepción para las referencias circulares.

### <a name="systemruntimeserialization-attributes"></a>Atributos de System.Runtime.Serialization

<xref:System.Text.Json> no admite atributos del espacio de nombres `System.Runtime.Serialization`, como `DataMemberAttribute` y `IgnoreDataMemberAttribute`.

### <a name="octal-numbers"></a>Números octales

`Newtonsoft.Json` trata los números con un cero a la izquierda como números octales. <xref:System.Text.Json> no permite ceros a la izquierda porque la especificación [RFC 8259](https://tools.ietf.org/html/rfc8259) no los permite.

### <a name="missingmemberhandling"></a>MissingMemberHandling

`Newtonsoft.Json` se puede configurar para producir excepciones durante la deserialización si el archivo JSON incluye propiedades que faltan en el tipo de destino. <xref:System.Text.Json> omite las propiedades adicionales en el archivo JSON, excepto cuando se usa el atributo [[JsonExtensionData]](system-text-json-how-to.md#handle-overflow-json). No hay ninguna solución alternativa para la característica de miembro que falta.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json` le permite realizar la depuración mediante el uso de un `TraceWriter` para ver los registros generados por la serialización o deserialización. <xref:System.Text.Json> no realiza el registro.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument y JsonElement en comparación con JToken (como JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> proporciona la capacidad de analizar y compilar un Document Object Model (DOM) **de solo lectura** a partir de cargas JSON existentes. DOM proporciona acceso aleatorio a los datos en una carga JSON. A los elementos JSON que componen los datos se puede acceder mediante el tipo <xref:System.Text.Json.JsonElement>. El tipo `JsonElement` proporciona las API para convertir texto JSON en tipos comunes de .NET. `JsonDocument` expone una propiedad <xref:System.Text.Json.JsonDocument.RootElement>.

### <a name="jsondocument-is-idisposable"></a>JsonDocument es IDisposable

`JsonDocument` compila una vista en memoria de los datos en un búfer agrupado. Por lo tanto, a diferencia de `JObject` o `JArray` de `Newtonsoft.Json`, el tipo `JsonDocument` implementa `IDisposable` y debe usarse dentro de un bloque Using.

Devuelva un `JsonDocument` desde la API solo si quiere transferir la propiedad de la duración y derivar la responsabilidad al autor de la llamada. En la mayoría de los escenarios, eso no es necesario. Si el autor de la llamada necesita trabajar con todo el documento JSON, devuelva el <xref:System.Text.Json.JsonElement.Clone%2A> del <xref:System.Text.Json.JsonDocument.RootElement%2A>, que es un <xref:System.Text.Json.JsonElement>. Si el autor de la llamada necesita trabajar con un elemento determinado dentro del documento JSON, devuelva el <xref:System.Text.Json.JsonElement.Clone%2A> de dicho <xref:System.Text.Json.JsonElement>. Si devuelve el `RootElement` o un subelemento directamente sin realizar un `Clone`, el autor de la llamada no podrá acceder al `JsonElement` devuelto después de que se elimine el `JsonDocument` que lo posee.

Este es un ejemplo en el que se le requiere que realice un `Clone`:

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

El código anterior espera un `JsonElement` que contiene una propiedad `fileName`. Abre el archivo JSON y crea un `JsonDocument`. El método supone que el autor de la llamada quiere trabajar con todo el documento, por lo que devuelve el `Clone` del `RootElement`.

Si recibe un `JsonElement` y está devolviendo un subelemento, no es necesario devolver un `Clone` del subelemento. El autor de la llamada es responsable de mantener activo el `JsonDocument` al que pertenece el `JsonElement` pasado. Por ejemplo:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JSonDocument es de solo lectura

El DOM <xref:System.Text.Json> no puede agregar, quitar o modificar elementos JSON. Está diseñado de esta manera para favorecer el rendimiento y para reducir las asignaciones para el análisis de los tamaños comunes de carga de JSON (es decir, < 1 MB). Si el escenario usa actualmente un DOM modificable, una de las siguientes soluciones alternativas podría ser factible:

* Para compilar un `JsonDocument` desde cero (es decir, sin pasar una carga de JSON existente al método `Parse`), escriba el texto JSON mediante `Utf8JsonWriter` y analice la salida del mismo para crear un nuevo `JsonDocument`.
* Para modificar un `JsonDocument` existente, úselo para escribir texto JSON, realizar cambios mientras escribe y analizar la salida del mismo para crear un nuevo `JsonDocument`.
* Para combinar documentos JSON existentes, equivalentes a las API de `JObject.Merge` o `JContainer.Merge` desde `Newtonsoft.Json`, vea [este problema de GitHub](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853).

### <a name="jsonelement-is-a-union-struct"></a>JsonElement es una estructura de unión

`JsonDocument` expone el `RootElement` como una propiedad de tipo <xref:System.Text.Json.JsonElement> (que es una unión), un tipo de estructura que abarca cualquier elemento JSON. `Newtonsoft.Json` utiliza tipos jerárquicos dedicados como `JObject`, `JArray`, `JToken`, etc. `JsonElement` es lo que puede buscar y enumerar, y puede usar `JsonElement` para materializar los elementos JSON en tipos de .NET.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>Cómo buscar subelementos en JsonDocument y JsonElement

Las búsquedas de tokens JSON mediante `JObject` o `JArray` desde `Newtonsoft.Json` suelen ser relativamente rápidas porque son búsquedas en algunos diccionarios. Por comparación, las búsquedas en `JsonElement` requieren una búsqueda secuencial de las propiedades y, por lo tanto, son relativamente lentas (por ejemplo, al usar `TryGetProperty`). <xref:System.Text.Json> está diseñado para minimizar el tiempo de análisis inicial en lugar del tiempo de búsqueda. Por lo tanto, use los enfoques siguientes para optimizar el rendimiento al buscar en un objeto `JsonDocument`:

* Use los enumeradores integrados (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> y <xref:System.Text.Json.JsonElement.EnumerateObject%2A>) en lugar de crear sus propios bucles o índices.
* No realice una búsqueda secuencial en todo el `JsonDocument` a través de todas las propiedades mediante `RootElement`. En su lugar, busque objetos JSON anidados en función de la estructura conocida de los datos JSON. Por ejemplo, si busca una propiedad `Grade` en objetos `Student`, recorra los objetos `Student` y obtenga el valor de `Grade` para cada uno, en lugar de buscar en todos los objetos `JsonElement` en busca de propiedades `Grade`. Si lo hace, se pasará innecesariamente sobre los mismos datos.

Para obtener un ejemplo de código, vea [Uso de JsonDocument para acceder a los datos](system-text-json-how-to.md#use-jsondocument-for-access-to-data).

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader en comparación con JsonTextReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) o [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601). `Utf8JsonReader` es un tipo de bajo nivel que se puede usar para compilar analizadores y deserializadores personalizados.

En las siguientes secciones se explican los patrones de programación recomendados para el uso de `Utf8JsonReader`.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader es una estructura de referencia

Dado que el tipo `Utf8JsonReader` es una *estructura de referencia*, tiene [ciertas limitaciones](../../csharp/language-reference/builtin-types/struct.md#ref-struct). Por ejemplo, no se puede almacenar como un campo en una clase o estructura que no sea una estructura de referencia. Para lograr un alto rendimiento, este tipo debe ser `ref struct` porque necesita almacenar en caché la entrada [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) que, a su vez, es una estructura de referencia. Además, este tipo es mutable ya que contiene el estado; por tanto, **páselo por referencia** en lugar de por valor. Si se pasa por valor, se producirá una copia de la estructura y los cambios de estado no serán visibles para el autor de la llamada. Esto difiere de `Newtonsoft.Json` debido a que el `JsonTextReader` de `Newtonsoft.Json` es una clase. Para más información sobre el uso de las estructuras de referencia, vea [Escritura de código C# seguro y eficaz](../../csharp/write-safe-efficient-code.md).

### <a name="read-utf-8-text"></a>Lectura de texto UTF-8

Para lograr el mejor rendimiento posible mientras usa `Utf8JsonReader`, lea cargas de JSON ya codificadas como texto UTF-8 en lugar de como cadenas UTF-16. Para obtener un ejemplo de código, vea [Filtrado de datos mediante Utf8JsonReader](system-text-json-how-to.md#filter-data-using-utf8jsonreader).

### <a name="read-with-a-stream-or-pipereader"></a>Lectura con Stream o PipeReader

`Utf8JsonReader` admite la lectura desde [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) o [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) con codificación UTF-8 (que es el resultado de la lectura de un <xref:System.IO.Pipelines.PipeReader>).

Para la lectura sincrónica, puede leer la carga de JSON hasta el final de la secuencia en una matriz de bytes y pasarla al lector. Para leer de una cadena (que tiene codificación UTF-16), llame a <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A> para transcodificar primero la cadena en una matriz de bytes con codificación UTF-8. Después, páselo a `Utf8JsonReader`.

Dado que `Utf8JsonReader` considera que la entrada es texto JSON, se considera que una marca de orden de bytes (BOM) de UTF-8 no es válida. El autor de la llamada debe filtrarla antes de pasar los datos al lector.

Para obtener códigos de ejemplo, vea [Uso de Utf8JsonReader](system-text-json-how-to.md#use-utf8jsonreader).

### <a name="read-with-multi-segment-readonlysequence"></a>Lectura con ReadOnlySequence de varios segmentos

Si la entrada JSON es una [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601), se puede acceder a cada elemento JSON desde la propiedad `ValueSpan` en el lector a medida que avance por el bucle de lectura. Pero si la entrada es [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601) (que es el resultado de la lectura de <xref:System.IO.Pipelines.PipeReader>), algunos elementos JSON podrían ocupar varios segmentos del objeto `ReadOnlySequence<byte>`. No se puede acceder a estos elementos desde <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> en un bloque de memoria contiguo. En su lugar, siempre que tenga un `ReadOnlySequence<byte>` de varios segmentos como entrada, sondee la propiedad <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> en el lector para averiguar cómo acceder al elemento JSON actual. Este es un patrón recomendado:

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

### <a name="use-valuetextequals-for-property-name-lookups"></a>Uso de ValueTextEquals para las búsquedas de nombres de propiedad

No use <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> para realizar comparaciones byte a byte mediante una llamada a <xref:System.MemoryExtensions.SequenceEqual%2A> para las búsquedas de nombres de propiedad. En su lugar, llame a <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>, ya que ese método anula el escape de caracteres que se van a escapar en JSON. Este es un ejemplo en el que se muestra cómo buscar una propiedad denominada "name":

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Lectura de valores NULL en tipos de valor que aceptan valores NULL

`Newtonsoft.Json` proporciona las API que devuelven <xref:System.Nullable%601>, como `ReadAsBoolean`, que controla un `TokenType` `Null` por usted devolviendo un valor `bool?`. Las API integradas de `System.Text.Json` solo devuelven tipos de valor que no aceptan valores NULL. Por ejemplo, <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> devuelve `bool`. Si encuentra `Null` en el elemento JSON, inicia una excepción. En los siguientes ejemplos se muestran dos formas de controlar valores NULL: una devolviendo un tipo de valor que acepta valores NULL y otra devolviendo el valor predeterminado:

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

Si necesita seguir usando `Newtonsoft.Json` para determinadas plataformas de destino, puede tener varias versiones y dos implementaciones. Pero esto no es algo trivial y requeriría algunos `#ifdefs` y la duplicación de orígenes. Una manera de compartir todo el código posible es crear un contenedor de `ref struct` alrededor de `Utf8JsonReader` y `Newtonsoft.Json` `JsonTextReader`. Dicho contenedor unificaría el área expuesta pública mientras aísla las diferencias de comportamiento. Esto le permite aislar los cambios principalmente en la construcción del tipo, junto con pasar el nuevo tipo por referencia. Este es el patrón que sigue la biblioteca de [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/):

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter en comparación con JsonTextWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ofrece una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`. El escritor es un tipo de bajo nivel que se puede usar para compilar serializadores personalizados.

En las siguientes secciones se explican los patrones de programación recomendados para el uso de `Utf8JsonWriter`.

### <a name="write-with-utf-8-text"></a>Escritura con texto UTF-8

Para lograr el mejor rendimiento posible mientras usa `Utf8JsonWriter`, escriba cargas de JSON ya codificadas como texto UTF-8 en lugar de como cadenas UTF-16. Utilice <xref:System.Text.Json.JsonEncodedText> para almacenar en caché y codificar previamente los nombres y valores de las propiedades de cadena conocidas como estáticos y pasarlos al escritor, en lugar de usar literales de cadena UTF-16. Esto es más rápido que el almacenamiento en caché y el uso de matrices de bytes UTF-8.

Este enfoque también funciona si necesita realizar un escape personalizado. `System.Text.Json` no permite deshabilitar el escape mientras se escribe una cadena, pero podría pasar su propio <xref:System.Text.Encodings.Web.JavaScriptEncoder> personalizado como una opción al escritor, o crear su propio `JsonEncodedText` que use su `JavascriptEncoder` para realizar el escape y, después, escribir el `JsonEncodedText` en lugar de la cadena. Para más información, vea [Personalización de la codificación de caracteres](system-text-json-how-to.md#customize-character-encoding).

### <a name="write-raw-values"></a>Escritura de valores sin formato

El método `WriteRawValue` de `Newtonsoft.Json` escribe el JSON sin formato donde se espera un valor. <xref:System.Text.Json> no tiene equivalente directo, pero esta es una solución alternativa que garantiza que solo se escribe un JSON válido:

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>Personalización del escape de caracteres

El valor [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) de `JsonTextWriter` ofrece opciones para escapar todos los caracteres que no sean ASCII **o** caracteres HTML. De forma predeterminada, `Utf8JsonWriter` convierte todos los caracteres que no son ASCII **y** HTML. Este escape se hace por motivos de seguridad de defensa en profundidad. Para especificar una directiva de escape diferente, cree un <xref:System.Text.Encodings.Web.JavaScriptEncoder> y configure <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>. Para más información, vea [Personalización de la codificación de caracteres](system-text-json-how-to.md#customize-character-encoding).

### <a name="customize-json-format"></a>Personalización del formato JSON

`JsonTextWriter` incluye la configuración siguiente, para la cual `Utf8JsonWriter` no tiene ningún equivalente:

* [Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm): especifica el número de caracteres a los que se va a aplicar sangría. `Utf8JsonWriter` siempre realiza una sangría de dos caracteres.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm): especifica el carácter que se va a utilizar para la sangría.  `Utf8JsonWriter` siempre usa el espacio en blanco.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm): especifica el carácter que se va a usar para rodear los valores de cadena.  `Utf8JsonWriter` siempre usa comillas dobles.
* [QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm): especifica si los nombres de propiedad deben encerrarse entre comillas.  `Utf8JsonWriter` siempre los coloca entrecomillados.

No hay ninguna solución alternativa que permita personalizar el JSON generado por `Utf8JsonWriter` de estas maneras.

### <a name="write-null-values"></a>Escritura de valores NULL

Para escribir valores NULL mediante `Utf8JsonWriter`, llame a:

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> para escribir un par clave-valor con NULL como valor.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> para escribir NULL como un elemento de una matriz JSON.

En el caso de una propiedad de cadena, si la cadena es NULL, <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> y <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> son equivalentes a `WriteNull` y `WriteNullValue`.

### <a name="write-timespan-uri-or-char-values"></a>Escritura de valores TimeSpan, URI o char

`JsonTextWriter` proporciona métodos `WriteValue` para los valores [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [URI](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)y [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm). `Utf8JsonWriter` no tiene métodos equivalentes. En su lugar, dé formato a estos valores como cadenas (por ejemplo, llamando a `ToString()`) y llame a <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>.

### <a name="multi-targeting"></a>Compatibilidad con múltiples versiones

Si necesita seguir usando `Newtonsoft.Json` para determinadas plataformas de destino, puede tener varias versiones y dos implementaciones. Pero esto no es algo trivial y requeriría algunos `#ifdefs` y la duplicación de orígenes. Una manera de compartir todo el código posible es crear un contenedor alrededor de `Utf8JsonWriter` y `Newtonsoft` `JsonTextWriter`. Dicho contenedor unificaría el área expuesta pública mientras aísla las diferencias de comportamiento. Esto le permite aislar los cambios principalmente en la construcción del tipo. La biblioteca de [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) sigue:

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>Recursos adicionales

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [Información general de System.Text.Json](system-text-json-overview.md)
* [Modo de uso de System.Text.Json](system-text-json-how-to.md)
* [Procedimientos para escribir convertidores personalizados](system-text-json-converters-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset en System.Text.Json](../datetime/system-text-json-support.md)
* [Referencia de API de System.Text.Json](xref:System.Text.Json)
* [Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
