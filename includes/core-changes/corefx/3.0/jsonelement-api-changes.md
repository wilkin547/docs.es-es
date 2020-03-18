---
ms.openlocfilehash: 79901d0b57816915ca7ea73cfe7fa3d40820434e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568142"
---
### <a name="jsonelement-api-changes"></a><span data-ttu-id="bd806-101">Cambios en la API de JsonElement</span><span class="sxs-lookup"><span data-stu-id="bd806-101">JsonElement API changes</span></span>

<span data-ttu-id="bd806-102">A partir de la versión preliminar 7 de .NET Core 3.0, algunas API de <xref:System.Text.Json.JsonElement> han cambiado para permitir una detección más sencilla y una mayor facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="bd806-102">Starting with .NET Core 3.0 Preview 7, some <xref:System.Text.Json.JsonElement> APIs have changed to allow for easier discovery and greater usability.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bd806-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="bd806-103">Change description</span></span>

<span data-ttu-id="bd806-104">En la versión preliminar 7 de .NET Core 3.0, las API de <xref:System.Text.Json.JsonElement> han cambiado de la manera siguiente para permitir una detección más sencilla y una mayor facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="bd806-104">In .NET Core 3.0 Preview 7, <xref:System.Text.Json.JsonElement> APIs have changed as follows to allow for easier discovery and greater usability.</span></span>

1. <span data-ttu-id="bd806-105">Todas las sobrecargas del método `WriteProperty` se han quitado de <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="bd806-105">All `WriteProperty` method overloads were removed from <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="bd806-106">Esto afecta a código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd806-106">This affects code such as the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. <span data-ttu-id="bd806-107">Se ha cambiado el nombre de `WriteValue` a <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd806-107">`WriteValue` was renamed as <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span></span> <span data-ttu-id="bd806-108">Esto afecta a código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd806-108">This affects code such as the following:</span></span>

   ```csharp
    using (JsonDocument doc = JsonDocument.Parse(jsonString))
    {
        JsonElement root = doc.RootElement;
        root.WriteValue(writer);
    }
    ```

1. <span data-ttu-id="bd806-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> produce ahora una <xref:System.ArgumentNullException> cuando su parámetro de método es `null`.</span><span class="sxs-lookup"><span data-stu-id="bd806-109"><xref:System.Text.Json.JsonElement.WriteTo%2A> now throws an <xref:System.ArgumentNullException> when its method parameter is `null`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bd806-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="bd806-110">Version introduced</span></span>

<span data-ttu-id="bd806-111">3.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="bd806-111">3.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bd806-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="bd806-112">Recommended action</span></span>

<span data-ttu-id="bd806-113">Si el código se ve afectado por estos cambios, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd806-113">If your code is affected by these changes, you can do the following:</span></span>

- <span data-ttu-id="bd806-114">No hay ninguna API de reemplazo para las sobrecargas de `WriteProperty` en <xref:System.Text.Json.JsonElement>.</span><span class="sxs-lookup"><span data-stu-id="bd806-114">There is no replacement API for the `WriteProperty` overloads in <xref:System.Text.Json.JsonElement>.</span></span> <span data-ttu-id="bd806-115">En su lugar, puede llamar a una de las sobrecargas de <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> junto con el método <xref:System.Text.Json.JsonElement.WriteTo%2A> para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="bd806-115">Instead, you can call one of the <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType> overloads along with the <xref:System.Text.Json.JsonElement.WriteTo%2A> method to achieve the same result.</span></span> <span data-ttu-id="bd806-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bd806-116">For example:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="bd806-117">Cambie el nombre del método `WriteValue` a <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span><span class="sxs-lookup"><span data-stu-id="bd806-117">Rename the `WriteValue` method to <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)>.</span></span> <span data-ttu-id="bd806-118">El parámetro de método permanece sin cambios.</span><span class="sxs-lookup"><span data-stu-id="bd806-118">The method parameter remains unchanged.</span></span> <span data-ttu-id="bd806-119">Por ejemplo, el código anterior debe cambiarse por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd806-119">For example, the previous code should be changed to the following:</span></span>

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- <span data-ttu-id="bd806-120">Controle la <xref:System.ArgumentNullException> en llamadas al método <xref:System.Text.Json.JsonElement.WriteTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="bd806-120">Handle the <xref:System.ArgumentNullException> in calls to the <xref:System.Text.Json.JsonElement.WriteTo%2A> method.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bd806-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="bd806-121">Affected APIs</span></span>

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
