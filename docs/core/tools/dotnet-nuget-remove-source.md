---
title: Comando dotnet nuget remove source
description: El comando dotnet nuget remove source quita un origen existente de los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b5575c31c0008d6e3e5a2e52906a076614217dd0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537901"
---
# <a name="dotnet-nuget-remove-source"></a><span data-ttu-id="46e08-103">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="46e08-103">dotnet nuget remove source</span></span>

<span data-ttu-id="46e08-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="46e08-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="46e08-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="46e08-105">Name</span></span>

<span data-ttu-id="46e08-106">`dotnet nuget remove source`: quita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="46e08-106">`dotnet nuget remove source` - Remove a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="46e08-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="46e08-107">Synopsis</span></span>

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a><span data-ttu-id="46e08-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="46e08-108">Description</span></span>

<span data-ttu-id="46e08-109">El comando `dotnet nuget remove source` quita un origen existente de los archivos de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="46e08-109">The `dotnet nuget remove source` command removes an existing source from your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="46e08-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="46e08-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="46e08-111">Nombre del origen.</span><span class="sxs-lookup"><span data-stu-id="46e08-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="46e08-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="46e08-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="46e08-113">Archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="46e08-113">The NuGet configuration file.</span></span> <span data-ttu-id="46e08-114">Si se especifica, solo se usará la configuración de este archivo.</span><span class="sxs-lookup"><span data-stu-id="46e08-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="46e08-115">Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="46e08-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="46e08-116">Para más información, consulte [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="46e08-116">For more information, see [Common NuGet Configurations](/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="46e08-117">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="46e08-117">Examples</span></span>

- <span data-ttu-id="46e08-118">Quite un origen con el nombre de `mySource`:</span><span class="sxs-lookup"><span data-stu-id="46e08-118">Remove a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="46e08-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="46e08-119">See also</span></span>

- [<span data-ttu-id="46e08-120">Secciones de origen del paquete en archivos NuGet.config</span><span class="sxs-lookup"><span data-stu-id="46e08-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="46e08-121">Comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="46e08-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
