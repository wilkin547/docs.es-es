---
title: Comando dotnet nuget disable source
description: El comando dotnet nuget disable source deshabilita un origen existente en los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: af37a6589cebaf0501ee5647ebadb83125d0f56e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537956"
---
# <a name="dotnet-nuget-disable-source"></a><span data-ttu-id="7d26d-103">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="7d26d-103">dotnet nuget disable source</span></span>

<span data-ttu-id="7d26d-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7d26d-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="7d26d-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="7d26d-105">Name</span></span>

<span data-ttu-id="7d26d-106">`dotnet nuget disable source`: deshabilita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7d26d-106">`dotnet nuget disable source` - Disable a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7d26d-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="7d26d-107">Synopsis</span></span>

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a><span data-ttu-id="7d26d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d26d-108">Description</span></span>

<span data-ttu-id="7d26d-109">El comando `dotnet nuget disable source` deshabilita un origen existente en los archivos de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7d26d-109">The `dotnet nuget disable source` command disables an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="7d26d-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7d26d-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="7d26d-111">Nombre del origen.</span><span class="sxs-lookup"><span data-stu-id="7d26d-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="7d26d-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="7d26d-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="7d26d-113">Archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7d26d-113">The NuGet configuration file.</span></span> <span data-ttu-id="7d26d-114">Si se especifica, solo se usará la configuración de este archivo.</span><span class="sxs-lookup"><span data-stu-id="7d26d-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="7d26d-115">Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7d26d-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="7d26d-116">Para más información, consulte [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="7d26d-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="7d26d-117">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7d26d-117">Examples</span></span>

- <span data-ttu-id="7d26d-118">Deshabilite un origen con el nombre de `mySource`:</span><span class="sxs-lookup"><span data-stu-id="7d26d-118">Disable a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="7d26d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d26d-119">See also</span></span>

- [<span data-ttu-id="7d26d-120">Secciones de origen del paquete en archivos NuGet.config</span><span class="sxs-lookup"><span data-stu-id="7d26d-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="7d26d-121">Comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="7d26d-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
