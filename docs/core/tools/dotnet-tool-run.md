---
title: Comando dotnet tool run
description: El comando dotnet tool run invoca una herramienta local.
ms.date: 02/14/2020
ms.openlocfilehash: 116ecb61748a0ca70ed385b279b11b939748f4a8
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634160"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="9fea3-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="9fea3-103">dotnet tool run</span></span>

<span data-ttu-id="9fea3-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9fea3-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9fea3-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="9fea3-105">Name</span></span>

<span data-ttu-id="9fea3-106">`dotnet tool run`: invoca una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="9fea3-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9fea3-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9fea3-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run -h|--help
```

## <a name="description"></a><span data-ttu-id="9fea3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fea3-108">Description</span></span>

<span data-ttu-id="9fea3-109">El comando `dotnet tool run` busca los archivos de manifiesto de las herramientas que se encuentran en el ámbito del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9fea3-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="9fea3-110">Cuando encuentra una referencia a la herramienta especificada, ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="9fea3-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="9fea3-111">Para obtener más información, vea [Invocación de una herramienta local](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="9fea3-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="9fea3-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9fea3-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="9fea3-113">El nombre del comando de la herramienta que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9fea3-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="9fea3-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="9fea3-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="9fea3-115">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="9fea3-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="9fea3-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fea3-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="9fea3-117">Ejecuta la herramienta local `dotnetsay`.</span><span class="sxs-lookup"><span data-stu-id="9fea3-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fea3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fea3-118">See also</span></span>

- [<span data-ttu-id="9fea3-119">Herramientas de .NET</span><span class="sxs-lookup"><span data-stu-id="9fea3-119">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="9fea3-120">Tutorial: Instalación y uso de una herramienta local de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="9fea3-120">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
