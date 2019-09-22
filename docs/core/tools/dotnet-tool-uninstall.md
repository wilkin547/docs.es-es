---
title: Comando dotnet tool uninstall
description: El comando dotnet tool uninstall desinstala del equipo la herramienta global especificada de .NET Core.
ms.date: 05/29/2018
ms.openlocfilehash: 033753f44464e78b826e908e0b6cdf276da8a179
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117552"
---
# <a name="dotnet-tool-uninstall"></a><span data-ttu-id="f33f8-103">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="f33f8-103">dotnet tool uninstall</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="f33f8-104">Name</span><span class="sxs-lookup"><span data-stu-id="f33f8-104">Name</span></span>

<span data-ttu-id="f33f8-105">`dotnet tool uninstall`: desinstala la [herramienta global de .NET Core](global-tools.md) especificada del equipo.</span><span class="sxs-lookup"><span data-stu-id="f33f8-105">`dotnet tool uninstall` - Uninstalls the specified [.NET Core Global Tool](global-tools.md) from your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f33f8-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f33f8-106">Synopsis</span></span>

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a><span data-ttu-id="f33f8-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f33f8-107">Description</span></span>

<span data-ttu-id="f33f8-108">El comando `dotnet tool uninstall` permite desinstalar del equipo herramientas globales de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f33f8-108">The `dotnet tool uninstall` command provides a way for you to uninstall .NET Core Global Tools from your machine.</span></span> <span data-ttu-id="f33f8-109">Para utilizar el comando, especifique que quiere quitar una herramienta de los usuarios con la opción `--global` o especifique una ruta de acceso en la que está instalada la herramienta usando para ello la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="f33f8-109">To use the command, you either have to specify that you want to remove a user-wide tool using the `--global` option or specify a path to where the tool is installed using the `--tool-path` option.</span></span>

## <a name="arguments"></a><span data-ttu-id="f33f8-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f33f8-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="f33f8-111">Nombre o identificador del paquete de NuGet que contiene la herramienta global de .NET Core que se quiere desinstalar.</span><span class="sxs-lookup"><span data-stu-id="f33f8-111">Name/ID of the NuGet package that contains the .NET Core Global Tool to uninstall.</span></span> <span data-ttu-id="f33f8-112">Para conocer el nombre el paquete, use el comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="f33f8-112">You can find the package name using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

## <a name="options"></a><span data-ttu-id="f33f8-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="f33f8-113">Options</span></span>

`-g|--global`

<span data-ttu-id="f33f8-114">Especifica que la herramienta que se va a quitar es de una instalación en el ámbito de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f33f8-114">Specifies that the tool to be removed is from a user-wide installation.</span></span> <span data-ttu-id="f33f8-115">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="f33f8-115">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="f33f8-116">Si no especifica esta opción, debe especificar la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="f33f8-116">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="f33f8-117">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f33f8-117">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="f33f8-118">Especifica la ubicación de donde se tiene que desinstalar la herramienta global.</span><span class="sxs-lookup"><span data-stu-id="f33f8-118">Specifies the location where to uninstall the Global Tool.</span></span> <span data-ttu-id="f33f8-119">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="f33f8-119">PATH can be absolute or relative.</span></span> <span data-ttu-id="f33f8-120">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="f33f8-120">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="f33f8-121">Si no especifica esta opción, debe especificar la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="f33f8-121">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="f33f8-122">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f33f8-122">Examples</span></span>

<span data-ttu-id="f33f8-123">Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/):</span><span class="sxs-lookup"><span data-stu-id="f33f8-123">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool:</span></span>

`dotnet tool uninstall -g dotnetsay`

<span data-ttu-id="f33f8-124">Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) de una carpeta específica de Windows:</span><span class="sxs-lookup"><span data-stu-id="f33f8-124">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Windows folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

<span data-ttu-id="f33f8-125">Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) de una carpeta específica de Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="f33f8-125">Uninstalls the [dotnetsay](https://www.nuget.org/packages/dotnetsay/) Global Tool from a specific Linux/macOS folder:</span></span>

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="f33f8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f33f8-126">See also</span></span>

- [<span data-ttu-id="f33f8-127">Herramientas globales de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f33f8-127">.NET Core Global Tools</span></span>](global-tools.md)
