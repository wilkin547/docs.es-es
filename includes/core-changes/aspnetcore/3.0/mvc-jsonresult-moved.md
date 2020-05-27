---
ms.openlocfilehash: 1356f3eee5e2d8090d7d96aafc07a19507a1aff1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721638"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a><span data-ttu-id="ded41-101">MVC: JsonResult se ha trasladado a Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="ded41-101">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>

<span data-ttu-id="ded41-102">`JsonResult` se ha trasladado al ensamblado `Microsoft.AspNetCore.Mvc.Core`.</span><span class="sxs-lookup"><span data-stu-id="ded41-102">`JsonResult` has moved to the `Microsoft.AspNetCore.Mvc.Core` assembly.</span></span> <span data-ttu-id="ded41-103">Este tipo se ha usado para definirse en [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span><span class="sxs-lookup"><span data-stu-id="ded41-103">This type used to be defined in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json).</span></span> <span data-ttu-id="ded41-104">Se ha agregado un atributo [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) de nivel de ensamblado a `Microsoft.AspNetCore.Mvc.Formatters.Json` para solucionar este problema en la mayoría de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ded41-104">An assembly-level [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute) attribute was added to `Microsoft.AspNetCore.Mvc.Formatters.Json` to address this issue for the majority of users.</span></span> <span data-ttu-id="ded41-105">Las aplicaciones que usan bibliotecas de terceros pueden encontrar problemas.</span><span class="sxs-lookup"><span data-stu-id="ded41-105">Apps that use third-party libraries may encounter issues.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ded41-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ded41-106">Version introduced</span></span>

<span data-ttu-id="ded41-107">3.0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="ded41-107">3.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="ded41-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="ded41-108">Old behavior</span></span>

<span data-ttu-id="ded41-109">Una aplicación que usa una biblioteca basada en la versión 2.2 se compila correctamente.</span><span class="sxs-lookup"><span data-stu-id="ded41-109">An app using a 2.2-based library builds successfully.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="ded41-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="ded41-110">New behavior</span></span>

<span data-ttu-id="ded41-111">Una aplicación que usa una biblioteca basada en la versión 2.2 produce un error en la compilación.</span><span class="sxs-lookup"><span data-stu-id="ded41-111">An app using a 2.2-based library fails compilation.</span></span> <span data-ttu-id="ded41-112">Se proporciona un error que contiene una variación del texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="ded41-112">An error containing a variation of the following text is provided:</span></span>

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

<span data-ttu-id="ded41-113">Para obtener un ejemplo de este tipo de problema, consulte [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span><span class="sxs-lookup"><span data-stu-id="ded41-113">For an example of such an issue, see [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ded41-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="ded41-114">Reason for change</span></span>

<span data-ttu-id="ded41-115">Los cambios en el nivel de plataforma de la composición de ASP.NET Core como se describe en [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span><span class="sxs-lookup"><span data-stu-id="ded41-115">Platform-level changes to the composition of ASP.NET Core as described at [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ded41-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ded41-116">Recommended action</span></span>

<span data-ttu-id="ded41-117">Es posible que sea necesario volver a compilar las bibliotecas compiladas con la versión 2.2 de `Microsoft.AspNetCore.Mvc.Formatters.Json` para solucionar el problema de todos los consumidores.</span><span class="sxs-lookup"><span data-stu-id="ded41-117">Libraries compiled against the 2.2 version of `Microsoft.AspNetCore.Mvc.Formatters.Json` may need to recompile to address the problem for all consumers.</span></span> <span data-ttu-id="ded41-118">Si se ve afectado, póngase en contacto con el autor de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ded41-118">If affected, contact the library author.</span></span> <span data-ttu-id="ded41-119">Solicite volver a compilar la biblioteca para tener como destino ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="ded41-119">Request recompilation of the library to target ASP.NET Core 3.0.</span></span>

#### <a name="category"></a><span data-ttu-id="ded41-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="ded41-120">Category</span></span>

<span data-ttu-id="ded41-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ded41-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ded41-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ded41-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
