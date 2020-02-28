---
title: Comando dotnet tool run
description: El comando dotnet tool run invoca una herramienta local.
ms.date: 02/14/2020
ms.openlocfilehash: 05b21c0f5ea86f4b99b220f556c61bf83f464114
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543831"
---
# <a name="dotnet-tool-run"></a><span data-ttu-id="46a47-103">dotnet tool run</span><span class="sxs-lookup"><span data-stu-id="46a47-103">dotnet tool run</span></span>

<span data-ttu-id="46a47-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="46a47-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="46a47-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="46a47-105">Name</span></span>

<span data-ttu-id="46a47-106">`dotnet tool run`: invoca una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="46a47-106">`dotnet tool run` - Invokes a local tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="46a47-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="46a47-107">Synopsis</span></span>

```dotnetcli
dotnet tool run <COMMAND NAME> 
dotnet tool run <-h|--help>
```

## <a name="description"></a><span data-ttu-id="46a47-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="46a47-108">Description</span></span>

<span data-ttu-id="46a47-109">El comando `dotnet tool run` busca los archivos de manifiesto de las herramientas que se encuentran en el ámbito del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="46a47-109">The `dotnet tool run` command searches tool manifest files that are in scope for the current directory.</span></span> <span data-ttu-id="46a47-110">Cuando encuentra una referencia a la herramienta especificada, ejecuta la herramienta.</span><span class="sxs-lookup"><span data-stu-id="46a47-110">When it finds a reference to the specified tool, it runs the tool.</span></span> <span data-ttu-id="46a47-111">Para obtener más información, vea [Invocación de una herramienta local](global-tools.md#invoke-a-local-tool).</span><span class="sxs-lookup"><span data-stu-id="46a47-111">For more information, see [Invoke a local tool](global-tools.md#invoke-a-local-tool).</span></span>

## <a name="arguments"></a><span data-ttu-id="46a47-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="46a47-112">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="46a47-113">El nombre del comando de la herramienta que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="46a47-113">The command name of the tool to run.</span></span>

## <a name="options"></a><span data-ttu-id="46a47-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="46a47-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="46a47-115">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="46a47-115">Prints out a short help for the command.</span></span>

## <a name="example"></a><span data-ttu-id="46a47-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46a47-116">Example</span></span>

- **`dotnet tool run dotnetsay`**

  <span data-ttu-id="46a47-117">Ejecuta la herramienta local `dotnetsay`.</span><span class="sxs-lookup"><span data-stu-id="46a47-117">Runs the `dotnetsay` local tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="46a47-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="46a47-118">See also</span></span>

- [<span data-ttu-id="46a47-119">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="46a47-119">.NET Core tools</span></span>](global-tools.md)
