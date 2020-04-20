---
title: Comando dotnet nuget remove source
description: El comando dotnet nuget remove source quita un origen existente de los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: b259873e1885644b272136fa31414410bdfd9f27
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463488"
---
# <a name="dotnet-nuget-remove-source"></a><span data-ttu-id="5d078-103">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="5d078-103">dotnet nuget remove source</span></span>

<span data-ttu-id="5d078-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="5d078-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5d078-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="5d078-105">Name</span></span>

<span data-ttu-id="5d078-106">`dotnet nuget remove source`: quita un origen de NuGet.</span><span class="sxs-lookup"><span data-stu-id="5d078-106">`dotnet nuget remove source` - Remove a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5d078-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5d078-107">Synopsis</span></span>

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a><span data-ttu-id="5d078-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d078-108">Description</span></span>

<span data-ttu-id="5d078-109">El comando `dotnet nuget remove source` quita un origen existente de los archivos de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="5d078-109">The `dotnet nuget remove source` command removes an existing source from your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="5d078-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5d078-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="5d078-111">Nombre del origen.</span><span class="sxs-lookup"><span data-stu-id="5d078-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="5d078-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="5d078-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="5d078-113">Archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="5d078-113">The NuGet configuration file.</span></span> <span data-ttu-id="5d078-114">Si se especifica, solo se usará la configuración de este archivo.</span><span class="sxs-lookup"><span data-stu-id="5d078-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="5d078-115">Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="5d078-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="5d078-116">Para más información, consulte [Configuraciones comunes de NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="5d078-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

## <a name="examples"></a><span data-ttu-id="5d078-117">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5d078-117">Examples</span></span>

- <span data-ttu-id="5d078-118">Quite un origen con el nombre de `mySource`:</span><span class="sxs-lookup"><span data-stu-id="5d078-118">Remove a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a><span data-ttu-id="5d078-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d078-119">See also</span></span>

- [<span data-ttu-id="5d078-120">Secciones de origen del paquete en archivos NuGet.config</span><span class="sxs-lookup"><span data-stu-id="5d078-120">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="5d078-121">Comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="5d078-121">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
