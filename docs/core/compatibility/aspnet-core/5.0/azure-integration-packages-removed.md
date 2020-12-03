---
title: 'Cambio importante: Azure: los paquetes de integración de Azure con Microsoft como prefijo se han quitado'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Azure: los paquetes de integración de Azure con Microsoft como prefijo se han quitado'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: b9f685b8c9fdcd73044f78840f2732809a0de710
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760256"
---
# <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a><span data-ttu-id="35be0-103">Azure: los paquetes de integración de Azure con Microsoft como prefijo se han quitado</span><span class="sxs-lookup"><span data-stu-id="35be0-103">Azure: Microsoft-prefixed Azure integration packages removed</span></span>

<span data-ttu-id="35be0-104">Los siguientes paquetes `Microsoft.*` que proporcionan la integración entre ASP.NET Core y SDK de Azure no se incluyen en ASP.NET Core 5.0:</span><span class="sxs-lookup"><span data-stu-id="35be0-104">The following `Microsoft.*` packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:</span></span>

* <span data-ttu-id="35be0-105">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), que integra [Azure Key Vault](/azure/key-vault/) en el [sistema de configuración](/aspnet/core/fundamentals/configuration/).</span><span class="sxs-lookup"><span data-stu-id="35be0-105">[Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), which integrates [Azure Key Vault](/azure/key-vault/) into the [Configuration system](/aspnet/core/fundamentals/configuration/).</span></span>
* <span data-ttu-id="35be0-106">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), que integra Azure Key Vault en el [sistema de protección de datos de ASP.NET Core](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="35be0-106">[Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), which integrates Azure Key Vault into the [ASP.NET Core Data Protection system](/aspnet/core/security/data-protection/introduction).</span></span>
* <span data-ttu-id="35be0-107">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), que integra [Azure Blob Storage](/azure/storage/blobs/) en el sistema de protección de datos de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="35be0-107">[Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), which integrates [Azure Blob Storage](/azure/storage/blobs/) into the ASP.NET Core Data Protection system.</span></span>

<span data-ttu-id="35be0-108">Para obtener información sobre esta incidencia, consulte [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span><span class="sxs-lookup"><span data-stu-id="35be0-108">For discussion on this issue, see [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="35be0-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="35be0-109">Version introduced</span></span>

<span data-ttu-id="35be0-110">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="35be0-110">5.0 Preview 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="35be0-111">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="35be0-111">Old behavior</span></span>

<span data-ttu-id="35be0-112">Los paquetes `Microsoft.*` integraban servicios de Azure con las API de protección de datos y configuración.</span><span class="sxs-lookup"><span data-stu-id="35be0-112">The `Microsoft.*` packages integrated Azure services with the Configuration and Data Protection APIs.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="35be0-113">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="35be0-113">New behavior</span></span>

<span data-ttu-id="35be0-114">Los nuevos paquetes `Azure.*` integran servicios de Azure con las API de protección de datos y configuración.</span><span class="sxs-lookup"><span data-stu-id="35be0-114">New `Azure.*` packages integrate Azure services with the Configuration and Data Protection APIs.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="35be0-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="35be0-115">Reason for change</span></span>

<span data-ttu-id="35be0-116">El cambio se realizó porque los paquetes `Microsoft.*`:</span><span class="sxs-lookup"><span data-stu-id="35be0-116">The change was made because the `Microsoft.*` packages were:</span></span>

* <span data-ttu-id="35be0-117">Estaban usando versiones obsoletas del SDK de Azure.</span><span class="sxs-lookup"><span data-stu-id="35be0-117">Using outdated versions of the Azure SDK.</span></span> <span data-ttu-id="35be0-118">Las actualizaciones sencillas no eran posibles porque las nuevas versiones del SDK de Azure incluían cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="35be0-118">Simple updates weren't possible because the new versions of the Azure SDK included breaking changes.</span></span>
* <span data-ttu-id="35be0-119">Estaban vinculados a la programación de versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="35be0-119">Tied to the .NET Core release schedule.</span></span> <span data-ttu-id="35be0-120">La transferencia de la propiedad de los paquetes al equipo del SDK de Azure habilita las actualizaciones de paquetes a medida que se actualiza el SDK de Azure.</span><span class="sxs-lookup"><span data-stu-id="35be0-120">Transferring ownership of the packages to the Azure SDK team enables package updates as the Azure SDK is updated.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="35be0-121">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="35be0-121">Recommended action</span></span>

<span data-ttu-id="35be0-122">En ASP.NET Core 2.1 o proyectos posteriores, reemplace el `Microsoft.*` anterior por los nuevos paquetes `Azure.*`.</span><span class="sxs-lookup"><span data-stu-id="35be0-122">In ASP.NET Core 2.1 or later projects, replace the old `Microsoft.*` with the new `Azure.*` packages.</span></span>

| <span data-ttu-id="35be0-123">Antiguo</span><span class="sxs-lookup"><span data-stu-id="35be0-123">Old</span></span> | <span data-ttu-id="35be0-124">Nuevo</span><span class="sxs-lookup"><span data-stu-id="35be0-124">New</span></span> |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [<span data-ttu-id="35be0-125">Azure.Extensions.AspNetCore.DataProtection.Keys</span><span class="sxs-lookup"><span data-stu-id="35be0-125">Azure.Extensions.AspNetCore.DataProtection.Keys</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [<span data-ttu-id="35be0-126">Azure.Extensions.AspNetCore.DataProtection.Blobs</span><span class="sxs-lookup"><span data-stu-id="35be0-126">Azure.Extensions.AspNetCore.DataProtection.Blobs</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [<span data-ttu-id="35be0-127">Azure.Extensions.AspNetCore.Configuration.Secrets</span><span class="sxs-lookup"><span data-stu-id="35be0-127">Azure.Extensions.AspNetCore.Configuration.Secrets</span></span>](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.Configuration.Secrets) |

<span data-ttu-id="35be0-128">Los nuevos paquetes usan una nueva versión del SDK de Azure que incluye cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="35be0-128">The new packages use a new version of the Azure SDK that includes breaking changes.</span></span> <span data-ttu-id="35be0-129">Los patrones de uso general no se modifican.</span><span class="sxs-lookup"><span data-stu-id="35be0-129">The general usage patterns are unchanged.</span></span> <span data-ttu-id="35be0-130">Algunas sobrecargas y opciones pueden diferir para adaptarse a los cambios en las API del SDK de Azure subyacentes.</span><span class="sxs-lookup"><span data-stu-id="35be0-130">Some overloads and options may differ to adapt to changes in the underlying Azure SDK APIs.</span></span>

<span data-ttu-id="35be0-131">Los paquetes anteriores:</span><span class="sxs-lookup"><span data-stu-id="35be0-131">The old packages will:</span></span>

* <span data-ttu-id="35be0-132">Serán compatibles con el equipo de ASP.NET Core durante la vigencia de .NET Core 2.1 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="35be0-132">Be supported by the ASP.NET Core team for the lifetime of .NET Core 2.1 and 3.1.</span></span>
* <span data-ttu-id="35be0-133">No se incluirán en .NET 5.</span><span class="sxs-lookup"><span data-stu-id="35be0-133">Not be included in .NET 5.</span></span>

<span data-ttu-id="35be0-134">Al actualizar su proyecto a .NET 5, realice la transición a los paquetes `Azure.*` para mantener la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="35be0-134">When upgrading your project to .NET 5, transition to the `Azure.*` packages to maintain support.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="35be0-135">API afectadas</span><span class="sxs-lookup"><span data-stu-id="35be0-135">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->
