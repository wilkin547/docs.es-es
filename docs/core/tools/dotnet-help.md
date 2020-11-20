---
title: Comando dotnet help
description: El comando dotnet help muestra documentación en línea más detallada para el comando especificado.
ms.date: 02/14/2020
ms.openlocfilehash: d583142edabb24df972bdf9a06dbfe04688f9d97
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634473"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="6ad4c-103">Referencia de dotnet help</span><span class="sxs-lookup"><span data-stu-id="6ad4c-103">dotnet help reference</span></span>

<span data-ttu-id="6ad4c-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="6ad4c-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="6ad4c-105">Name</span><span class="sxs-lookup"><span data-stu-id="6ad4c-105">Name</span></span>

<span data-ttu-id="6ad4c-106">`dotnet help`: muestra documentación más detallada en línea para el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="6ad4c-106">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6ad4c-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6ad4c-107">Synopsis</span></span>

```dotnetcli
dotnet help <COMMAND_NAME> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="6ad4c-108">Description</span><span class="sxs-lookup"><span data-stu-id="6ad4c-108">Description</span></span>

<span data-ttu-id="6ad4c-109">El comando `dotnet help` abre la página de referencia para obtener información más detallada sobre el comando especificado en docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="6ad4c-109">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="6ad4c-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6ad4c-110">Arguments</span></span>

- **`COMMAND_NAME`**

  <span data-ttu-id="6ad4c-111">Nombre del comando de la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="6ad4c-111">Name of the .NET CLI command.</span></span> <span data-ttu-id="6ad4c-112">Para obtener una lista de los comandos de la CLI válidos, vea [Comandos de la CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="6ad4c-112">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="6ad4c-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="6ad4c-113">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="6ad4c-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6ad4c-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="6ad4c-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6ad4c-115">Examples</span></span>

- <span data-ttu-id="6ad4c-116">Se abre la página de documentación del comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="6ad4c-116">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```dotnetcli
  dotnet help new
  ```
