---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032076"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a><span data-ttu-id="7b735-101">Las propiedades UriBuilder ya no anteponen caracteres iniciales</span><span class="sxs-lookup"><span data-stu-id="7b735-101">UriBuilder properties no longer prepend leading characters</span></span>

<span data-ttu-id="7b735-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> ya no antepone un carácter `#` inicial y <xref:System.UriBuilder.Query?displayProperty=nameWithType> ya no antepone un carácter `?` inicial si ya existe uno.</span><span class="sxs-lookup"><span data-stu-id="7b735-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> no longer prepends a leading `#` character and <xref:System.UriBuilder.Query?displayProperty=nameWithType> no longer prepends a leading `?` character when one is already present.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7b735-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7b735-103">Change description</span></span>

<span data-ttu-id="7b735-104">En .NET Framework, las propiedades <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> y <xref:System.UriBuilder.Query?displayProperty=nameWithType> siempre anteponen un carácter `#` o `?`, respectivamente, al valor que se va a almacenar.</span><span class="sxs-lookup"><span data-stu-id="7b735-104">In .NET Framework, the <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> and <xref:System.UriBuilder.Query?displayProperty=nameWithType> properties always prepend a `#` or `?` character, respectively, to the value being stored.</span></span> <span data-ttu-id="7b735-105">Este comportamiento puede producir varios caracteres `#` o `?` en el valor almacenado si la cadena ya contiene uno de estos caracteres iniciales.</span><span class="sxs-lookup"><span data-stu-id="7b735-105">This behavior can result in multiple `#` or `?` characters in the stored value if the string already contains one of these leading characters.</span></span> <span data-ttu-id="7b735-106">Por ejemplo, el valor de <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> podría convertirse en `##main`.</span><span class="sxs-lookup"><span data-stu-id="7b735-106">For example, the value of <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> might become `##main`.</span></span>

<span data-ttu-id="7b735-107">A partir de .NET Core 1.0, estas propiedades ya no anteponen los caracteres `#` o `?` al valor almacenado si ya hay uno presente al principio de la cadena.</span><span class="sxs-lookup"><span data-stu-id="7b735-107">Starting in .NET Core 1.0, these properties no longer prepend the `#` or `?` characters to the stored value if one is already present at the beginning of the string.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7b735-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7b735-108">Version introduced</span></span>

<span data-ttu-id="7b735-109">1.0</span><span class="sxs-lookup"><span data-stu-id="7b735-109">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7b735-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7b735-110">Recommended action</span></span>

<span data-ttu-id="7b735-111">Ya no es necesario quitar explícitamente ninguno de estos caracteres iniciales al establecer los valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="7b735-111">You no longer need to explicitly remove any of these leading characters when setting the property values.</span></span> <span data-ttu-id="7b735-112">Esto es especialmente útil cuando se anexan valores, puesto que ya no es necesario quitar los caracteres `#` iniciales o `?` al anexar.</span><span class="sxs-lookup"><span data-stu-id="7b735-112">This is especially useful when you're appending values, because you no longer have to remove the leading `#` or `?` each time you append.</span></span>

<span data-ttu-id="7b735-113">Por ejemplo, en el siguiente fragmento de código puede verse la diferencia de comportamiento entre .NET Framework y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7b735-113">For example, the following code snippet shows the behavior difference between .NET Framework and .NET Core.</span></span>

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- <span data-ttu-id="7b735-114">En .NET Framework, el resultado es `????one=1&two=2&three=3&four=4`.</span><span class="sxs-lookup"><span data-stu-id="7b735-114">In .NET Framework, the output is `????one=1&two=2&three=3&four=4`.</span></span>
- <span data-ttu-id="7b735-115">En .NET Core, el resultado es `?one=1&two=2&three=3&four=4`.</span><span class="sxs-lookup"><span data-stu-id="7b735-115">In .NET Core, the output is `?one=1&two=2&three=3&four=4`.</span></span>

#### <a name="category"></a><span data-ttu-id="7b735-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="7b735-116">Category</span></span>

<span data-ttu-id="7b735-117">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="7b735-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7b735-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7b735-118">Affected APIs</span></span>

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
