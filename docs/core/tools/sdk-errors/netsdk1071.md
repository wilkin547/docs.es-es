---
title: 'NETSDK1071: Un elemento PackageReference establecido en "{0}" ha especificado una versión de `{1}`.'
description: Procedimiento para resolver el problema de un elemento PackageReference de un metapaquete incluido con el marco con una versión.
author: Forgind
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1071
ms.openlocfilehash: 852232cba04bb93a17872280e10848c2896991ae
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445708"
---
# <a name="netsdk1071-explicitly-versioned-packagereference-to-a-metapackage-that-would-be-included-with-the-framework"></a><span data-ttu-id="5bb48-103">NETSDK1071: Elemento PackageReference con una versión explícita a un metapaquete que se incluiría con el marco.</span><span class="sxs-lookup"><span data-stu-id="5bb48-103">NETSDK1071: Explicitly versioned PackageReference to a metapackage that would be included with the framework.</span></span>

<span data-ttu-id="5bb48-104">**Este artículo se aplica a:** ✔️ SDK de .NET 5.0.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="5bb48-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="5bb48-105">Si el SDK de .NET emite una advertencia NETSDK1071, sugiere que puede haber un conflicto de versiones en el futuro entre la versión de un metapaquete especificada en un elemento PackageReference y la versión de ese metapaquete a la que se hace referencia de forma implícita a través de una propiedad TargetFramework:</span><span class="sxs-lookup"><span data-stu-id="5bb48-105">When the .NET SDK issues warning NETSDK1071, it suggests there may be a version conflict in the future between the version of a metapackage specified in a PackageReference and the version of that metapackage as implicitly referenced via a TargetFramework property:</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="5bb48-106">Como TargetFramework aporta de forma automática una versión del metapaquete, las versiones entrarán en conflicto en caso de que difieran.</span><span class="sxs-lookup"><span data-stu-id="5bb48-106">Since the TargetFramework automatically brings in a version of the metapackage, the versions will conflict should they ever differ.</span></span>

<span data-ttu-id="5bb48-107">Para resolver este problema:</span><span class="sxs-lookup"><span data-stu-id="5bb48-107">To resolve this:</span></span>

1. <span data-ttu-id="5bb48-108">Al seleccionar como destino .NET Core o .NET Standard, considere la posibilidad de evitar referencias explícitas a `Microsoft.NETCore.App` o `NETStandard.Library` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5bb48-108">Consider, when targeting .NET Core or .NET Standard, avoiding explicit references to `Microsoft.NETCore.App` or `NETStandard.Library` in your project file.</span></span>
2. <span data-ttu-id="5bb48-109">Si necesita una versión concreta del entorno de ejecución cuando el destino es .NET Core, use la propiedad `<RuntimeFrameworkVersion>` en lugar de hacer referencia de forma directa al metapaquete.</span><span class="sxs-lookup"><span data-stu-id="5bb48-109">If you need a specific version of the runtime when targeting .NET Core, use the `<RuntimeFrameworkVersion>`property instead of referencing the metapackage directly.</span></span> <span data-ttu-id="5bb48-110">Por ejemplo, esto puede ocurrir si usa [implementaciones independientes](../../deploying/index.md#publish-self-contained) y necesita una versión específica del entorno de ejecución de LTS 1.0.0.</span><span class="sxs-lookup"><span data-stu-id="5bb48-110">As an example, this could happen if you're using [self-contained deployments](../../deploying/index.md#publish-self-contained) and need a specific patch of the 1.0.0 LTS runtime.</span></span>
3. <span data-ttu-id="5bb48-111">Si necesita una versión concreta de `NetStandard.Library` cuando el destino es .NET Standard, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecerla en la versión necesaria.</span><span class="sxs-lookup"><span data-stu-id="5bb48-111">If you need a specific version of `NetStandard.Library` when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set it to the version you need.</span></span>
4. <span data-ttu-id="5bb48-112">No agregue referencias a `Microsoft.NETCore.App` y `NETSTandard.Library` ni las actualice de forma explícita en proyectos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5bb48-112">Don't eplicitly add or update references to either `Microsoft.NETCore.App` or `NETSTandard.Library` in .NET Framework projects.</span></span> <span data-ttu-id="5bb48-113">NuGet instala de forma automática cualquier versión de `NETStandard.Library` que necesite al usar un paquete NuGet basado en .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="5bb48-113">NuGet automatically installs any version of `NETStandard.Library` you need when using a .NET Standard-based NuGet package.</span></span>
5. <span data-ttu-id="5bb48-114">No especifique una versión para `Microsoft.AspNetCore.App` o `Microsoft.AspNetCore.All` al usar .NET Core 2.1 y posteriores, ya que el SDK de .NET Core selecciona de forma automática la versión adecuada.</span><span class="sxs-lookup"><span data-stu-id="5bb48-114">Do not specify a version for `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` when using .NET Core 2.1+, as the .NET Core SDK automatically selects the appropriate version.</span></span> <span data-ttu-id="5bb48-115">(Nota: Esto solo funciona cuando el destino es .NET Core 2.1 si el proyecto también utiliza `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="5bb48-115">(Note: This only works when targeting .NET Core 2.1 if the project also uses `Microsoft.NET.Sdk.Web`.</span></span> <span data-ttu-id="5bb48-116">Este problema se ha resuelto en el SDK de .NET Core 2.2).</span><span class="sxs-lookup"><span data-stu-id="5bb48-116">This problem was resolved in the .NET Core 2.2 SDK.)</span></span>
6. <span data-ttu-id="5bb48-117">Si quiere que desaparezca la advertencia, también puede deshabilitarla:</span><span class="sxs-lookup"><span data-stu-id="5bb48-117">If you want the warning to go away, you can also disable it:</span></span>

   ```xml
   <PackageReference Include="Microsoft.NetCore.App" Version="2.2.8" >
     <AllowExplicitVersion>true</AllowExplicitVersion>
   </PackageReference>
   ```
