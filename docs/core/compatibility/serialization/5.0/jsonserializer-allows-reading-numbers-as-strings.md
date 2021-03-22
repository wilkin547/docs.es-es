---
title: 'Cambio importante: Las aplicaciones ASP.NET Core permiten deserializar los números entrecomillados'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde las aplicaciones ASP.NET Core deserializarán correctamente los números representados como cadenas JSON, en lugar de iniciar una excepción.
ms.date: 10/21/2020
ms.openlocfilehash: bc1531bb9b159bfd9e80eafacafb50aa509973cc
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624154"
---
# <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a><span data-ttu-id="31ee1-103">Las aplicaciones ASP.NET Core permiten deserializar los números entrecomillados</span><span class="sxs-lookup"><span data-stu-id="31ee1-103">ASP.NET Core apps allow deserializing quoted numbers</span></span>

<span data-ttu-id="31ee1-104">A partir de .NET 5, las aplicaciones ASP.NET Core usan las opciones predeterminadas de deserialización especificadas mediante <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31ee1-104">Starting in .NET 5, ASP.NET Core apps use the default deserialization options as specified by <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span></span> <span data-ttu-id="31ee1-105">El conjunto de opciones <xref:System.Text.Json.JsonSerializerDefaults.Web> incluye el establecimiento de <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> en <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31ee1-105">The <xref:System.Text.Json.JsonSerializerDefaults.Web> set of options includes setting <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> to <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="31ee1-106">Este cambio significa que las aplicaciones ASP.NET Core van a deserializar correctamente los números representados como cadenas JSON, en lugar de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="31ee1-106">This change means that ASP.NET Core apps will successfully deserialize numbers that are represented as JSON strings instead of throwing an exception.</span></span>

## <a name="change-description"></a><span data-ttu-id="31ee1-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="31ee1-107">Change description</span></span>

<span data-ttu-id="31ee1-108">En .NET Core 3.0-3.1, <xref:System.Text.Json.JsonSerializer> produce una <xref:System.Text.Json.JsonException> durante la deserialización si encuentra un número entrecomillado en una carga JSON.</span><span class="sxs-lookup"><span data-stu-id="31ee1-108">In .NET Core 3.0 - 3.1, <xref:System.Text.Json.JsonSerializer> throws a <xref:System.Text.Json.JsonException> during deserialization if it encounters a quoted number in a JSON payload.</span></span> <span data-ttu-id="31ee1-109">Los números entrecomillados se usan para asignar con propiedades de número en gráficos de objetos.</span><span class="sxs-lookup"><span data-stu-id="31ee1-109">The quoted numbers are used to map with number properties in object graphs.</span></span> <span data-ttu-id="31ee1-110">En .NET Core 3.0-3.1, los números solo se leen de tokens <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31ee1-110">In .NET Core 3.0 - 3.1, numbers are only read from <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokens.</span></span>

<span data-ttu-id="31ee1-111">A partir de .NET 5, los números entrecomillados de las cargas JSON se consideran válidos, de manera predeterminada, para las aplicaciones ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="31ee1-111">Starting in .NET 5, quoted numbers in JSON payloads are considered valid, by default, for ASP.NET Core apps.</span></span> <span data-ttu-id="31ee1-112">No se produce ninguna excepción durante la deserialización de números entrecomillados.</span><span class="sxs-lookup"><span data-stu-id="31ee1-112">No exception is thrown during deserialization of quoted numbers.</span></span>

> [!TIP]
>
> - <span data-ttu-id="31ee1-113">No hay ningún cambio de comportamiento en el elemento <xref:System.Text.Json.JsonSerializer> o <xref:System.Text.Json.JsonSerializerOptions> independiente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="31ee1-113">There is no behavior change for the default, standalone <xref:System.Text.Json.JsonSerializer> or <xref:System.Text.Json.JsonSerializerOptions>.</span></span>
> - <span data-ttu-id="31ee1-114">Técnicamente, esto no es un cambio importante, ya que hace que un escenario sea más permisivo en lugar de más restrictivo (es decir, que tiene éxito a la hora de forzar un número de una cadena JSON en lugar de producir una excepción).</span><span class="sxs-lookup"><span data-stu-id="31ee1-114">This is technically not a breaking change, since it makes a scenario more permissive instead of more restrictive (that is, it succeeds in coercing a number from a JSON string instead of throwing an exception).</span></span> <span data-ttu-id="31ee1-115">Pero, puesto que se trata de un cambio de comportamiento considerable que afecta a muchas aplicaciones ASP.NET Core, se documenta aquí.</span><span class="sxs-lookup"><span data-stu-id="31ee1-115">However, since this is a significant behavioral change that affects many ASP.NET Core apps, it is documented here.</span></span>
> - <span data-ttu-id="31ee1-116">Los métodos de extensión <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> y <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> también usan el conjunto de opciones de serialización <xref:System.Text.Json.JsonSerializerDefaults.Web>.</span><span class="sxs-lookup"><span data-stu-id="31ee1-116">The <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> extension methods also use the <xref:System.Text.Json.JsonSerializerDefaults.Web> set of serialization options.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="31ee1-117">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="31ee1-117">Version introduced</span></span>

<span data-ttu-id="31ee1-118">5.0</span><span class="sxs-lookup"><span data-stu-id="31ee1-118">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="31ee1-119">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="31ee1-119">Reason for change</span></span>

<span data-ttu-id="31ee1-120">Varios usuarios han solicitado una opción para un control de los números más permisivo en <xref:System.Text.Json.JsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="31ee1-120">Multiple users have requested an option for more permissive number handling in <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="31ee1-121">Este comentario indica que muchos productores JSON (por ejemplo, servicios en la web) emiten números entrecomillados.</span><span class="sxs-lookup"><span data-stu-id="31ee1-121">This feedback indicates that many JSON producers (for example, services across the web) emit quoted numbers.</span></span> <span data-ttu-id="31ee1-122">Al permitir que los números entrecomillados se lean (deserializados), las aplicaciones .NET pueden analizar correctamente estas cargas, de manera predeterminada, en contextos web.</span><span class="sxs-lookup"><span data-stu-id="31ee1-122">By allowing quoted numbers to be read (deserialized), .NET apps can successfully parse these payloads, by default, in web contexts.</span></span> <span data-ttu-id="31ee1-123">La configuración se expone mediante <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> para que se puedan especificar las mismas opciones en diferentes capas de aplicación, por ejemplo, cliente, servidor y compartida.</span><span class="sxs-lookup"><span data-stu-id="31ee1-123">The configuration is exposed via <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> so that you can specify the same options across different application layers, for example, client, server, and shared.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="31ee1-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="31ee1-124">Recommended action</span></span>

<span data-ttu-id="31ee1-125">Si este cambio es problemático, por ejemplo, si depende del control de números estricto para la validación, puede volver a habilitar el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="31ee1-125">If this change is disruptive, for example, if you depend on the strict number handling for validation, you can re-enable the previous behavior.</span></span> <span data-ttu-id="31ee1-126">Establezca la opción <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> en <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="31ee1-126">Set the <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> option to <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="31ee1-127">En el caso de las aplicaciones de MVC de ASP.NET Core y API web, puede configurar la opción en `Startup` mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="31ee1-127">For ASP.NET Core MVC and web API apps, you can configure the option in `Startup` by using the following code:</span></span>

```csharp
services.AddControllers()
   .AddJsonOptions(options => options.JsonSerializerOptions.NumberHandling = JsonNumberHandling.Strict);
```

## <a name="affected-apis"></a><span data-ttu-id="31ee1-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="31ee1-128">Affected APIs</span></span>

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
