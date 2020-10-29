---
ms.openlocfilehash: a93856aac97af5c392a2e4698d2da42413cfc3c8
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434997"
---
### <a name="aspnet-core-apps-allow-deserializing-quoted-numbers"></a><span data-ttu-id="bf1e9-101">Las aplicaciones ASP.NET Core permiten deserializar los números entrecomillados</span><span class="sxs-lookup"><span data-stu-id="bf1e9-101">ASP.NET Core apps allow deserializing quoted numbers</span></span>

<span data-ttu-id="bf1e9-102">A partir de .NET 5.0, las aplicaciones ASP.NET Core usan las opciones predeterminadas de deserialización especificadas mediante <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-102">Starting in .NET 5.0, ASP.NET Core apps use the default deserialization options as specified by <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bf1e9-103">El conjunto de opciones <xref:System.Text.Json.JsonSerializerDefaults.Web> incluye el establecimiento de <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> en <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-103">The <xref:System.Text.Json.JsonSerializerDefaults.Web> set of options includes setting <xref:System.Text.Json.JsonSerializerOptions.NumberHandling> to <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bf1e9-104">Este cambio significa que las aplicaciones ASP.NET Core van a deserializar correctamente los números representados como cadenas JSON, en lugar de producir una excepción.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-104">This change means that ASP.NET Core apps will successfully deserialize numbers that are represented as JSON strings, instead of throwing an exception.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bf1e9-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="bf1e9-105">Change description</span></span>

<span data-ttu-id="bf1e9-106">En .NET Core 3.0-3.1, <xref:System.Text.Json.JsonSerializer> produce una <xref:System.Text.Json.JsonException> durante la deserialización si encuentra un número entrecomillado en una carga JSON.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-106">In .NET Core 3.0 - 3.1, <xref:System.Text.Json.JsonSerializer> throws a <xref:System.Text.Json.JsonException> during deserialization if it encounters a quoted number in a JSON payload.</span></span> <span data-ttu-id="bf1e9-107">Los números entrecomillados se usan para asignar con propiedades de número en gráficos de objetos.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-107">The quoted numbers are used to map with number properties in object graphs.</span></span> <span data-ttu-id="bf1e9-108">En .NET Core 3.0-3.1, los números solo se leen de tokens <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-108">In .NET Core 3.0 - 3.1, numbers are only read from <xref:System.Text.Json.JsonTokenType.Number?displayProperty=nameWithType> tokens.</span></span>

<span data-ttu-id="bf1e9-109">A partir de .NET 5.0, los números entrecomillados de las cargas JSON se consideran válidos, de manera predeterminada, para las aplicaciones ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-109">Starting in .NET 5.0, quoted numbers in JSON payloads are considered valid, by default, for ASP.NET Core apps.</span></span> <span data-ttu-id="bf1e9-110">No se produce ninguna excepción durante la deserialización de números entrecomillados.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-110">No exception is thrown during deserialization of quoted numbers.</span></span>

> [!TIP]
>
> - <span data-ttu-id="bf1e9-111">No hay ningún cambio de comportamiento en el elemento <xref:System.Text.Json.JsonSerializer> o <xref:System.Text.Json.JsonSerializerOptions> independiente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-111">There is no behavior change for the default, standalone <xref:System.Text.Json.JsonSerializer> or <xref:System.Text.Json.JsonSerializerOptions>.</span></span>
> - <span data-ttu-id="bf1e9-112">Técnicamente, esto no es un cambio importante, ya que hace que un escenario sea más permisivo en lugar de más restrictivo (es decir, que tiene éxito a la hora de forzar un número de una cadena JSON en lugar de producir una excepción).</span><span class="sxs-lookup"><span data-stu-id="bf1e9-112">This is technically not a breaking change, since it makes a scenario more permissive instead of more restrictive (that is, it succeeds in coercing a number from a JSON string instead of throwing an exception).</span></span> <span data-ttu-id="bf1e9-113">Pero, puesto que se trata de un cambio de comportamiento considerable que afecta a muchas aplicaciones ASP.NET Core, se documenta aquí.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-113">However, since this is a significant behavioral change that affects many ASP.NET Core apps, it is documented here.</span></span>
> - <span data-ttu-id="bf1e9-114">Los métodos de extensión <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> y <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> también usan el conjunto de opciones de serialización <xref:System.Text.Json.JsonSerializerDefaults.Web>.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-114">The <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpContentJsonExtensions.ReadFromJsonAsync%2A?displayProperty=nameWithType> extension methods also use the <xref:System.Text.Json.JsonSerializerDefaults.Web> set of serialization options.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bf1e9-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="bf1e9-115">Version introduced</span></span>

<span data-ttu-id="bf1e9-116">5.0</span><span class="sxs-lookup"><span data-stu-id="bf1e9-116">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bf1e9-117">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="bf1e9-117">Reason for change</span></span>

<span data-ttu-id="bf1e9-118">Varios usuarios han solicitado una opción para un control de los números más permisivo en <xref:System.Text.Json.JsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-118">Multiple users have requested an option for more permissive number handling in <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="bf1e9-119">Este comentario indica que muchos productores JSON (por ejemplo, servicios en la web) emiten números entrecomillados.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-119">This feedback indicates that many JSON producers (for example, services across the web) emit quoted numbers.</span></span> <span data-ttu-id="bf1e9-120">Al permitir que los números entrecomillados se lean (deserializados), las aplicaciones .NET pueden analizar correctamente estas cargas, de manera predeterminada, en contextos web.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-120">By allowing quoted numbers to be read (deserialized), .NET apps can successfully parse these payloads, by default, in web contexts.</span></span> <span data-ttu-id="bf1e9-121">La configuración se expone mediante <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> para que se puedan especificar las mismas opciones en diferentes capas de aplicación, por ejemplo, cliente, servidor y compartida.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-121">The configuration is exposed via <xref:System.Text.Json.JsonSerializerDefaults.Web?displayProperty=nameWithType> so that you can specify the same options across different application layers, for example, client, server, and shared.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bf1e9-122">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="bf1e9-122">Recommended action</span></span>

<span data-ttu-id="bf1e9-123">Si este cambio es problemático, por ejemplo, si depende del control de números estricto para la validación, puede volver a habilitar el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-123">If this change is disruptive, for example, if you depend on the strict number handling for validation, you can re-enable the previous behavior.</span></span> <span data-ttu-id="bf1e9-124">Establezca la opción <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> en <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bf1e9-124">Set the <xref:System.Text.Json.JsonSerializerOptions.NumberHandling?displayProperty=nameWithType> option to <xref:System.Text.Json.Serialization.JsonNumberHandling.Strict?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="bf1e9-125">En el caso de las aplicaciones de MVC de ASP.NET Core y API web, puede configurar la opción en `Startup` mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf1e9-125">For ASP.NET Core MVC and web API apps, you can configure the option in `Startup` by using the following code:</span></span>

```csharp
services.AddControllers()
   .AddJsonOptions(options.NumberHandling = JsonNumberHandling.Strict);
```

#### <a name="category"></a><span data-ttu-id="bf1e9-126">Categoría</span><span class="sxs-lookup"><span data-stu-id="bf1e9-126">Category</span></span>

- <span data-ttu-id="bf1e9-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="bf1e9-127">ASP.NET Core</span></span>
- <span data-ttu-id="bf1e9-128">Serialización</span><span class="sxs-lookup"><span data-stu-id="bf1e9-128">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bf1e9-129">API afectadas</span><span class="sxs-lookup"><span data-stu-id="bf1e9-129">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
