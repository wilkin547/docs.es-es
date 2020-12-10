---
title: Uso de tipos inmutables y descriptores de acceso no públicos con System.Text.Json
description: Aprenda a usar tipos inmutables y descriptores de acceso no públicos durante la serialización y deserialización de JSON en .NET.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: d3e61d44ce22b7f50838b6d3ba9cf64004bd3725
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439832"
---
# <a name="how-to-use-immutable-types-and-non-public-accessors-with-no-locsystemtextjson"></a>Uso de tipos inmutables y descriptores de acceso no públicos con System.Text.Json

En este artículo, aprenderá a usar tipos inmutables, como registros, con el espacio de nombres `System.Text.Json`.

## <a name="immutable-types-and-records"></a>Tipos y registros inmutables

::: zone pivot="dotnet-5-0"
`System.Text.Json` puede utilizar un constructor con parámetros, lo que hace posible deserializar una clase o estructura inmutable. En el caso de una clase, si el único constructor está parametrizado, se utilizará ese constructor. En el caso de una estructura o una clase con varios constructores, especifique el que se va a usar aplicando el atributo [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A). Cuando no se utiliza el atributo, siempre se usa un constructor sin parámetros público si está presente. El atributo solo se puede usar con constructores públicos. En el ejemplo siguiente se usa el atributo `[JsonConstructor]`:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

También se admiten registros en C# 9, como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

En el caso de los tipos que son inmutables porque todos sus establecedores de propiedad son no públicos, vea la siguiente sección sobre [los descriptores de acceso de propiedad no públicos](#non-public-property-accessors).
::: zone-end

::: zone pivot="dotnet-core-3-1"
`JsonConstructorAttribute` y la compatibilidad con los registros en C# 9 no están disponibles en .NET Core 3.1.
::: zone-end

## <a name="non-public-property-accessors"></a>Descriptores de acceso de propiedad no públicos

::: zone pivot="dotnet-5-0"
Para habilitar el uso de un descriptor de acceso de propiedad no público, use el atributo [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute), como se muestra en el ejemplo siguiente:

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
Los descriptores de acceso de propiedad no públicos no se admiten en .NET Core 3.1. Para obtener más información, consulte [el artículo de migración de Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).
::: zone-end

## <a name="see-also"></a>Vea también

* [Información general de System.Text.Json](system-text-json-overview.md)
* [Creación de una instancia de JsonSerializerOptions](system-text-json-configure-options.md)
* [Habilitación de la coincidencia sin distinción entre mayúsculas y minúsculas](system-text-json-character-casing.md)
* [Personalización de los nombres y valores de propiedad](system-text-json-customize-properties.md)
* [Omisión de propiedades](system-text-json-ignore-properties.md)
* [Permiso del formato JSON no válido](system-text-json-invalid-json.md)
* [JSON de desbordamiento de control](system-text-json-handle-overflow.md)
* [Conservación de referencias circulares](system-text-json-preserve-references.md)
* [Serialización polimórfica](system-text-json-polymorphism.md)
* [Referencia de la API System.Text.Json](xref:System.Text.Json)
