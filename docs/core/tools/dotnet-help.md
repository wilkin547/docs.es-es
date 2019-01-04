---
title: Comando dotnet help
description: El comando dotnet help muestra documentación en línea más detallada para el comando especificado.
ms.date: 12/04/2018
ms.openlocfilehash: 44274b698ed83bd3cdb58787f433eeb5c555bc6d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168962"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="d55e7-103">Referencia de dotnet help</span><span class="sxs-lookup"><span data-stu-id="d55e7-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="d55e7-104">nombre</span><span class="sxs-lookup"><span data-stu-id="d55e7-104">Name</span></span>

<span data-ttu-id="d55e7-105">`dotnet help`: muestra documentación más detallada en línea para el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="d55e7-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d55e7-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d55e7-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="d55e7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d55e7-107">Description</span></span>

<span data-ttu-id="d55e7-108">El comando `dotnet help` abre la página de referencia para obtener información más detallada sobre el comando especificado en docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d55e7-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="d55e7-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d55e7-109">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="d55e7-110">Nombre del comando de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d55e7-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="d55e7-111">Para obtener una lista de los comandos de la CLI válidos, vea [Comandos de la CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="d55e7-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="d55e7-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="d55e7-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="d55e7-113">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="d55e7-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="d55e7-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d55e7-114">Examples</span></span>

* <span data-ttu-id="d55e7-115">Se abre la página de documentación del comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="d55e7-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```