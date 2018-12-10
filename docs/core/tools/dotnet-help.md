---
title: 'Comando dotnet help: CLI de .NET Core'
description: El comando dotnet help muestra documentación en línea más detallada para el comando especificado.
ms.date: 12/04/2018
ms.openlocfilehash: 60d1cc706ca5c78fa3be877bd679888181213e88
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152180"
---
# <a name="dotnet-help-reference"></a><span data-ttu-id="b0b4e-103">Referencia de dotnet help</span><span class="sxs-lookup"><span data-stu-id="b0b4e-103">dotnet help reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a><span data-ttu-id="b0b4e-104">nombre</span><span class="sxs-lookup"><span data-stu-id="b0b4e-104">Name</span></span>

<span data-ttu-id="b0b4e-105">`dotnet help`: muestra documentación más detallada en línea para el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="b0b4e-105">`dotnet help` - Shows more detailed documentation online for the specified command.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b0b4e-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="b0b4e-106">Synopsis</span></span>

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="b0b4e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0b4e-107">Description</span></span>

<span data-ttu-id="b0b4e-108">El comando `dotnet help` abre la página de referencia para obtener información más detallada sobre el comando especificado en docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b0b4e-108">The `dotnet help` command opens up the reference page for more detailed information about the specified command at docs.microsoft.com.</span></span>

## <a name="arguments"></a><span data-ttu-id="b0b4e-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b0b4e-109">Arguments</span></span>

* **`COMMAND_NAME`**

  <span data-ttu-id="b0b4e-110">Nombre del comando de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b0b4e-110">Name of the .NET Core CLI command.</span></span> <span data-ttu-id="b0b4e-111">Para obtener una lista de los comandos de la CLI válidos, vea [Comandos de la CLI](index.md#cli-commands).</span><span class="sxs-lookup"><span data-stu-id="b0b4e-111">For a list of the valid CLI commands, see [CLI commands](index.md#cli-commands).</span></span>

## <a name="options"></a><span data-ttu-id="b0b4e-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="b0b4e-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="b0b4e-113">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="b0b4e-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b0b4e-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b0b4e-114">Examples</span></span>

* <span data-ttu-id="b0b4e-115">Se abre la página de documentación del comando [dotnet new](dotnet-new.md):</span><span class="sxs-lookup"><span data-stu-id="b0b4e-115">Opens the documentation page for the [dotnet new](dotnet-new.md) command:</span></span>

  ```console
  dotnet help new
  ```