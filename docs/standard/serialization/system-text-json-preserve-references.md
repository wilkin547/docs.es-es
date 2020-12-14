---
title: Conservación de las referencias con System.Text.Json
description: Aprenda a conservar las referencias y controlar las referencias circulares durante la serialización y deserialización de JSON en .NET.
ms.date: 12/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d358c953c0979ca097c080fcd750d5ef95b07de0
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008739"
---
# <a name="how-to-preserve-references-and-handle-circular-references-with-no-locsystemtextjson"></a>Cómo conservar las referencias y administrar las referencias circulares con System.Text.Json

::: zone pivot="dotnet-5-0"

Para conservar las referencias y administrar las referencias circulares, establezca <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> en <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>. Este valor produce el comportamiento siguiente:

* Al serializar:

  Al escribir tipos complejos, el serializador también escribe propiedades de metadatos (`$id`, `$values` y `$ref`).

* Al deserializar:

  Se esperan metadatos (aunque no es obligatorio) y el deserializador intenta entenderlo.

En el siguiente código se muestra el uso del parámetro `Preserve`.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

Esta característica no se puede usar para conservar tipos de valor o tipos inmutables. En la deserialización, se crea la instancia de un tipo inmutable después de leer la carga completa. Por lo tanto, sería imposible deserializar la misma instancia si aparece una referencia a ella dentro de la carga de JSON.

En el caso de los tipos de valor, los tipos inmutables y las matrices, no se serializan los metadatos de referencia. En la deserialización, se produce una excepción si se encuentra `$ref` o `$id`. Sin embargo, los tipos de valor omiten `$id` (y `$values` en el caso de las colecciones) para que sea posible deserializar las cargas que se serializaron mediante Newtonsoft.Json.  Newtonsoft.Json serializa los metadatos de estos tipos.

Para determinar si los objetos son iguales, System.Text.Json usa <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, que usa la igualdad de referencia (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) en lugar de la igualdad de valores (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> cuando se comparan dos instancias de objeto.

Para obtener más información sobre cómo se serializan y deserializan las referencias, vea <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.

La clase <xref:System.Text.Json.Serialization.ReferenceResolver> define el comportamiento de conservar las referencias en la serialización y deserialización. Cree una clase derivada para especificar el comportamiento personalizado. Para obtener un ejemplo, vea [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).

::: zone-end

::: zone pivot="dotnet-core-3-1"
System.Text.Json en .NET Core 3.1 solo admite la serialización por valor y produce una excepción para las referencias circulares.
::: zone-end

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Cómo serializar y deserializar JSON](system-text-json-how-to.md)
* [Creación de instancias de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [Permiso del formato JSON no válido](system-text-json-invalid-json.md)
* [JSON de desbordamiento de control](system-text-json-handle-overflow.md)
* [Tipos inmutables y descriptores de acceso no públicos](system-text-json-immutability.md)
* [Serialización polimórfica](system-text-json-polymorphism.md)
* [Migración desde Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Personalización de la codificación de caracteres](system-text-json-character-encoding.md)
* [Escritura de serializadores y deserializadores personalizados](write-custom-serializer-deserializer.md)
* [Escritura de convertidores personalizados para la serialización de JSON](system-text-json-converters-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset](../datetime/system-text-json-support.md)
* [Referencia de API de System.Text.Json](xref:System.Text.Json)
* [Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
