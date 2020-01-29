---
title: Comando dotnet help
description: El comando dotnet help muestra documentación en línea más detallada para el comando especificado.
ms.date: 08/08/2019
ms.openlocfilehash: 9bb4e54d2634c000707752edf53b38af43c4344e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734233"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="c9d38-103">Referencia de dotnet help</span><span class="sxs-lookup"><span data-stu-id="c9d38-103">dotnet help reference</span></span>

<span data-ttu-id="c9d38-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c9d38-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a><span data-ttu-id="c9d38-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="c9d38-105">Name</span></span>

<span data-ttu-id="c9d38-106">`dotnet help`: muestra documentación más detallada en línea para el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="c9d38-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c9d38-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c9d38-107">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="c9d38-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9d38-108">Description</span></span>

<span data-ttu-id="c9d38-109">El comando `dotnet help` abre la página de referencia para obtener información más detallada sobre el comando especificado en docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c9d38-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="c9d38-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c9d38-110">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="c9d38-111">Nombre del comando de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c9d38-111">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="c9d38-112">Para obtener una lista de los comandos de la CLI válidos, vea [Comandos de la CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="c9d38-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="c9d38-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="c9d38-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="c9d38-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c9d38-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="c9d38-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c9d38-115">Examples</span></span>

* <span data-ttu-id="c9d38-116">Se abre la página de documentación del comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="c9d38-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
