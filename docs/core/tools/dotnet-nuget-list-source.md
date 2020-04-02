---
title: Comando dotnet nuget list source
description: El comando dotnet nuget list source muestra todos los orígenes existentes de los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 4d7bc3dbd3ab5eb14c1ebf592044b685d28355cd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148499"
---
# <a name="dotnet-nuget-list-source"></a><span data-ttu-id="c1b42-103">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="c1b42-103">dotnet nuget list source</span></span>

<span data-ttu-id="c1b42-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c1b42-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c1b42-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c1b42-105">Name</span></span>

<span data-ttu-id="c1b42-106">`dotnet nuget list source`: enumera todos los orígenes de NuGet configurados.</span><span class="sxs-lookup"><span data-stu-id="c1b42-106">`dotnet nuget list source` - Lists all configured NuGet sources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c1b42-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c1b42-107">Synopsis</span></span>

```dotnetcli
dotnet nuget list source [--format] [--configfile]
dotnet nuget list source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="c1b42-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1b42-108">Description</span></span>

<span data-ttu-id="c1b42-109">El comando `dotnet nuget list source` muestra todos los orígenes existentes de los archivos de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c1b42-109">The `dotnet nuget list source` command lists all existing sources from your NuGet configuration files.</span></span>

## <a name="options"></a><span data-ttu-id="c1b42-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="c1b42-110">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="c1b42-111">Archivo de configuración de NuGet.</span><span class="sxs-lookup"><span data-stu-id="c1b42-111">The NuGet configuration file.</span></span> <span data-ttu-id="c1b42-112">Si se especifica, solo se usará la configuración de este archivo.</span><span class="sxs-lookup"><span data-stu-id="c1b42-112">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="c1b42-113">Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c1b42-113">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="c1b42-114">Para más información, consulte [Configuraciones comunes de NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="c1b42-114">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`--format`**

  <span data-ttu-id="c1b42-115">Formato de la salida del comando de lista: `Detailed` (valor predeterminado) y `Short`.</span><span class="sxs-lookup"><span data-stu-id="c1b42-115">The format of the list command output: `Detailed` (the default) and `Short`.</span></span>

## <a name="examples"></a><span data-ttu-id="c1b42-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c1b42-116">Examples</span></span>

- <span data-ttu-id="c1b42-117">Enumeración de los orígenes configurados del directorio actual:</span><span class="sxs-lookup"><span data-stu-id="c1b42-117">List configured sources from the current directory:</span></span>

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a><span data-ttu-id="c1b42-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1b42-118">See also</span></span>

- [<span data-ttu-id="c1b42-119">Secciones de origen del paquete en archivos NuGet.config</span><span class="sxs-lookup"><span data-stu-id="c1b42-119">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="c1b42-120">Comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="c1b42-120">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
