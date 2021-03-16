---
title: 'Cambio importante: Las aplicaciones ASP.NET Core permiten deserializar los números entrecomillados'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde las aplicaciones ASP.NET Core deserializarán correctamente los números representados como cadenas JSON, en lugar de iniciar una excepción.
ms.date: 10/21/2020
ms.openlocfilehash: f541af5bf5f0a519fd5205f44d68a9b401569909
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256314"
---
# <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a>Las aplicaciones ASP.NET Core permiten deserializar los números entrecomillados

A partir de .NET 5, las aplicaciones ASP.NET Core usan las opciones predeterminadas de deserialización especificadas mediante <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>. El conjunto de opciones <xref:System.Text.Json.JsonSerializerDefaults.Web> incluye el establecimiento de <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> en <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>. Este cambio significa que las aplicaciones ASP.NET Core van a deserializar correctamente los números representados como cadenas JSON, en lugar de iniciar una excepción.

## <a name="change-description"></a>Descripción del cambio

En .NET Core 3.0-3.1, <xref:System.Text.Json.JsonSerializer> produce una <xref:System.Text.Json.JsonException> durante la deserialización si encuentra un número entrecomillado en una carga JSON. Los números entrecomillados se usan para asignar con propiedades de número en gráficos de objetos. En .NET Core 3.0-3.1, los números solo se leen de tokens <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType>.

A partir de .NET 5, los números entrecomillados de las cargas JSON se consideran válidos, de manera predeterminada, para las aplicaciones ASP.NET Core. No se produce ninguna excepción durante la deserialización de números entrecomillados.

> [!TIP]
>
> - No hay ningún cambio de comportamiento en el elemento <xref:System.Text.Json.JsonSerializer> o <xref:System.Text.Json.JsonSerializerOptions> independiente predeterminado.
> - Técnicamente, esto no es un cambio importante, ya que hace que un escenario sea más permisivo en lugar de más restrictivo (es decir, que tiene éxito a la hora de forzar un número de una cadena JSON en lugar de producir una excepción). Pero, puesto que se trata de un cambio de comportamiento considerable que afecta a muchas aplicaciones ASP.NET Core, se documenta aquí.
> - Los métodos de extensión <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> y <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> también usan el conjunto de opciones de serialización <xref:System.Text.Json.JsonSerializerDefaults.Web>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="reason-for-change"></a>Motivo del cambio

Varios usuarios han solicitado una opción para un control de los números más permisivo en <xref:System.Text.Json.JsonSerializer>. Este comentario indica que muchos productores JSON (por ejemplo, servicios en la web) emiten números entrecomillados. Al permitir que los números entrecomillados se lean (deserializados), las aplicaciones .NET pueden analizar correctamente estas cargas, de manera predeterminada, en contextos web. La configuración se expone mediante <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> para que se puedan especificar las mismas opciones en diferentes capas de aplicación, por ejemplo, cliente, servidor y compartida.

## <a name="recommended-action"></a>Acción recomendada

Si este cambio es problemático, por ejemplo, si depende del control de números estricto para la validación, puede volver a habilitar el comportamiento anterior. Establezca la opción <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> en <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.

En el caso de las aplicaciones de MVC de ASP.NET Core y API web, puede configurar la opción en `Startup` mediante el código siguiente:

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

## <a name="affected-apis"></a>API afectadas

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

- ASP.NET Core
- Serialization

-->
