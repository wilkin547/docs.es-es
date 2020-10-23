---
ms.openlocfilehash: 1ddc2cea19872b44ff9659bcebd76117587ea89a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159499"
---
### <a name="targetframework-change-from-netcoreapp-to-net"></a><span data-ttu-id="260b2-101">Cambio de TargetFramework de netcoreapp a net</span><span class="sxs-lookup"><span data-stu-id="260b2-101">TargetFramework change from netcoreapp to net</span></span>

<span data-ttu-id="260b2-102">El valor de la propiedad `TargetFramework` de MSBuild ha cambiado de `netcoreapp3.1` a `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="260b2-102">The value for the MSBuild `TargetFramework` property changed from `netcoreapp3.1` to `net5.0`.</span></span> <span data-ttu-id="260b2-103">Esto puede interrumpir el código que se basa en el análisis del valor de `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="260b2-103">This can break code that relies on parsing the value of `TargetFramework`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="260b2-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="260b2-104">Version introduced</span></span>

<span data-ttu-id="260b2-105">5.0</span><span class="sxs-lookup"><span data-stu-id="260b2-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="260b2-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="260b2-106">Change description</span></span>

<span data-ttu-id="260b2-107">En .NET Core 1.0-3.1, el valor de la propiedad `TargetFramework` de MSBuild comienza con `netcoreapp`, por ejemplo, `netcoreapp3.1` para las aplicaciones destinadas a .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="260b2-107">In .NET Core 1.0 - 3.1, the value for the MSBuild `TargetFramework` property starts with `netcoreapp`, for example, `netcoreapp3.1` for apps that target .NET Core 3.1.</span></span> <span data-ttu-id="260b2-108">A partir de .NET 5.0, este valor se ha simplificado para que solo empiece por `net`, por ejemplo, `net5.0` para .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="260b2-108">Starting in .NET 5.0, this value is simplified to just start with `net`, for example, `net5.0` for .NET 5.0.</span></span>

<span data-ttu-id="260b2-109">Para obtener más información, vea [El futuro de .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) y [Nombres de plataforma de destino en .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span><span class="sxs-lookup"><span data-stu-id="260b2-109">For more information, see [The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) and [Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="260b2-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="260b2-110">Reason for change</span></span>

- <span data-ttu-id="260b2-111">Simplifica el valor de `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="260b2-111">Simplifies the `TargetFramework` value.</span></span>
- <span data-ttu-id="260b2-112">Permite a los proyectos incluir un objeto `TargetPlatform` en la propiedad `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="260b2-112">Enables projects to include a `TargetPlatform` in the `TargetFramework` property.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="260b2-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="260b2-113">Recommended action</span></span>

<span data-ttu-id="260b2-114">Si tiene lógica que analiza el valor de `TargetFramework`, tendrá que actualizarla.</span><span class="sxs-lookup"><span data-stu-id="260b2-114">If you have logic that parses the value of `TargetFramework`, you'll need to update it.</span></span> <span data-ttu-id="260b2-115">Por ejemplo, la siguiente condición de MSBuild se basa en el valor de `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="260b2-115">For example, the following MSBuild condition relies on the value of `TargetFramework`.</span></span>

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

<span data-ttu-id="260b2-116">Para este requisito, puede actualizar el código a fin de comparar el identificador de la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="260b2-116">For this requirement, you can update the code to compare the target framework identifier instead.</span></span>

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

#### <a name="category"></a><span data-ttu-id="260b2-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="260b2-117">Category</span></span>

<span data-ttu-id="260b2-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="260b2-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="260b2-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="260b2-119">Affected APIs</span></span>

<span data-ttu-id="260b2-120">N/D</span><span class="sxs-lookup"><span data-stu-id="260b2-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
