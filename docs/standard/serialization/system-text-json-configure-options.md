---
title: Creación de una instancia de JsonSerializerOptions con System.Text.Json
description: Obtenga información sobre cómo evitar problemas de rendimiento y cómo usar los constructores disponibles para instancias de JsonSerializerOptions.
ms.date: 12/02/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 5f32e1369e58dd9550f28abc822f187dee46c022
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009838"
---
# <a name="how-to-instantiate-jsonserializeroptions-instances-with-no-locsystemtextjson"></a>Creación de instancias de JsonSerializerOptions con System.Text.Json

En este artículo se explica cómo evitar problemas de rendimiento al usar <xref:System.Text.Json.JsonSerializerOptions>. También se muestra cómo usar los constructores con parámetros disponibles.

## <a name="reuse-jsonserializeroptions-instances"></a>Reutilización de instancias de JsonSerializerOptions

Si usa `JsonSerializerOptions` repetidas veces con las mismas opciones, no cree una instancia de `JsonSerializerOptions` cada vez que lo use. Reutilice la misma instancia para cada llamada. Esta instrucción se aplica al código que se escribe para convertidores personalizados y al llamar a <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> o <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>.

En el código siguiente se muestra la penalización de rendimiento al usar nuevas instancias de opciones.

:::code language="csharp" source="snippets/system-text-json-configure-options/csharp/ReuseOptionsInstances.cs":::

El código anterior serializa un objeto pequeño 100 000 veces mediante la misma instancia de opciones. A continuación, serializa el mismo objeto el mismo número de veces y crea una nueva instancia de opciones cada vez. Normalmente la diferencia en el tiempo de ejecución es de 190 milisegundos frente a 40 140. Esta será mayor cuantas más iteraciones se realicen.

El serializador pasa por una fase de preparación durante la primera serialización de cada tipo en el gráfico de objetos cuando se le pasa una nueva instancia de opciones. Esta preparación incluye la creación de una caché de metadatos necesaria para la serialización. Los metadatos incluyen delegados para captadores de propiedades, establecedores, argumentos de constructor, atributos especificados, etc. Esta caché de metadatos se almacena en la instancia de opciones. El mismo proceso de preparación y caché se aplica a la deserialización.

El tamaño de la memoria caché de metadatos en una instancia de `JsonSerializerOptions` depende del número de tipos que se van a serializar. Si pasa numerosos tipos (por ejemplo, tipos generados dinámicamente) al serializador, el tamaño de la caché seguirá creciendo y puede acabar produciendo una excepción `OutOfMemoryException`.

## <a name="copy-jsonserializeroptions"></a>Copia de JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Hay un [constructor de JsonSerializerOptions](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) que le permite crear una nueva instancia de con las mismas opciones que una instancia existente, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Un constructor de `JsonSerializerOptions` que toma una instancia existente no está disponible en .NET Core 3.1.
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a>Valores predeterminados web para JsonSerializerOptions

::: zone pivot="dotnet-5-0"
Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

Hay un [constructor de JsonSerializerOptions] (xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) que le permite crear una nueva instancia de con las opciones predeterminadas que ASP.NET Core utiliza para aplicaciones web, tal como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Estas son las opciones que tienen valores predeterminados diferentes para aplicaciones web:

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

Un constructor de `JsonSerializerOptions` que especifica un conjunto de valores predeterminados no está disponible en .NET Core 3.1.
::: zone-end

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Cómo serializar y deserializar JSON](system-text-json-how-to.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [Permiso del formato JSON no válido](system-text-json-invalid-json.md)
* [JSON de desbordamiento de control](system-text-json-handle-overflow.md)
* [Conservación de las referencias](system-text-json-preserve-references.md)
* [Tipos inmutables y descriptores de acceso no públicos](system-text-json-immutability.md)
* [Serialización polimórfica](system-text-json-polymorphism.md)
* [Migración desde Newtonsoft.Json a System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [Personalización de la codificación de caracteres](system-text-json-character-encoding.md)
* [Escritura de serializadores y deserializadores personalizados](write-custom-serializer-deserializer.md)
* [Escritura de convertidores personalizados para la serialización de JSON](system-text-json-converters-how-to.md)
* [Compatibilidad con DateTime y DateTimeOffset](../datetime/system-text-json-support.md)
* [Referencia de API de System.Text.Json](xref:System.Text.Json)
* [Referencia de API de System.Text.Json.Serialization](xref:System.Text.Json.Serialization)
