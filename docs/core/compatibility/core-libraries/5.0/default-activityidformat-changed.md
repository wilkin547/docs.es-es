---
title: 'Cambio importante: El valor predeterminado de ActivityIdFormat es W3C'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde el valor ActivityIdFormat predeterminado ahora es W3C.
ms.date: 11/01/2020
ms.openlocfilehash: f15c2d61443117cfbcb2be7de9561fecbff9a1d9
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257510"
---
# <a name="default-activityidformat-is-w3c"></a><span data-ttu-id="7a9b9-103">El valor predeterminado de ActivityIdFormat es W3C</span><span class="sxs-lookup"><span data-stu-id="7a9b9-103">Default ActivityIdFormat is W3C</span></span>

<span data-ttu-id="7a9b9-104">Ahora el formato de identificador predeterminado de la actividad (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) es <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-104">The default identifier format for activity (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) is now <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

## <a name="change-description"></a><span data-ttu-id="7a9b9-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7a9b9-105">Change description</span></span>

<span data-ttu-id="7a9b9-106">El formato de id. de actividad del W3C se presentó en .NET Core 3.0 como alternativa al formato de identificador jerárquico.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-106">The W3C activity ID format was introduced in .NET Core 3.0 as an alternative to the hierarchical ID format.</span></span> <span data-ttu-id="7a9b9-107">Pero para conservar la compatibilidad, el formato del W3C no se ha convertido en el predeterminado hasta .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-107">However, to preserve compatibility, the W3C format wasn't made the default until .NET 5.0.</span></span> <span data-ttu-id="7a9b9-108">El valor predeterminado se ha cambiado en .NET 5 porque el formato del W3C se ha [ratificado](https://www.w3.org/TR/trace-context/) y consolidado en las implementaciones de varios lenguajes.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-108">The default was changed in .NET 5 because the [W3C format has been ratified](https://www.w3.org/TR/trace-context/) and gained traction across multiple language implementations.</span></span>

<span data-ttu-id="7a9b9-109">Si la aplicación tiene como destino una plataforma distinta a .NET 5 o posterior, experimentará el comportamiento anterior, donde <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> es el formato predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-109">If your app targets a platform other than .NET 5 or later, it will experience the old behavior, where <xref:System.Diagnostics.ActivityIdFormat.Hierarchical> is the default format.</span></span> <span data-ttu-id="7a9b9-110">Este formato predeterminado. se aplica a las plataformas net45+, netstandard1.1+ y netcoreapp (1.x, 2.x y 3.x).</span><span class="sxs-lookup"><span data-stu-id="7a9b9-110">This default applies to platforms net45+, netstandard1.1+, and netcoreapp (1.x, 2.x, and 3.x).</span></span> <span data-ttu-id="7a9b9-111">En .NET 5 y versiones posteriores, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> se establece en <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-111">In .NET 5 and later, <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> is set to <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7a9b9-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7a9b9-112">Version introduced</span></span>

<span data-ttu-id="7a9b9-113">5.0</span><span class="sxs-lookup"><span data-stu-id="7a9b9-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7a9b9-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7a9b9-114">Recommended action</span></span>

<span data-ttu-id="7a9b9-115">Si la aplicación es independiente del identificador que se usa para el seguimiento distribuido, no es necesario realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-115">If your application is agnostic to the identifier that's used for distributed tracing, no action is needed.</span></span> <span data-ttu-id="7a9b9-116">Las bibliotecas como ASP.NET Core y <xref:System.Net.Http.HttpClient> pueden consumir o propagar las dos versiones de <xref:System.Diagnostics.ActivityIdFormat>.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-116">Libraries such as ASP.NET Core and <xref:System.Net.Http.HttpClient> can consume or propagate both versions of the <xref:System.Diagnostics.ActivityIdFormat>.</span></span>

<span data-ttu-id="7a9b9-117">Si requiere interoperabilidad con sistemas existentes, o los sistemas actuales dependen del formato del identificador, puede conservar el comportamiento anterior si establece <xref:System.Diagnostics.Activity.DefaultIdFormat> en <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-117">If you require interoperability with existing systems, or current systems rely on the format of the identifier, you can preserve the old behavior by setting <xref:System.Diagnostics.Activity.DefaultIdFormat> to <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7a9b9-118">Como alternativa, puede establecer un modificador AppContext de una de estas tres maneras:</span><span class="sxs-lookup"><span data-stu-id="7a9b9-118">Alternatively, you can set an AppContext switch in one of three ways:</span></span>

- <span data-ttu-id="7a9b9-119">En el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-119">In the project file.</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="7a9b9-120">En el archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-120">In the *runtimeconfig.json* file.</span></span>

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- <span data-ttu-id="7a9b9-121">A través de una variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-121">Through an environment variable.</span></span>

  <span data-ttu-id="7a9b9-122">Establezca `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` en `true` o 1.</span><span class="sxs-lookup"><span data-stu-id="7a9b9-122">Set `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` to `true` or 1.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7a9b9-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7a9b9-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
