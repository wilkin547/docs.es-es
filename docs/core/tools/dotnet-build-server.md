---
title: Comando dotnet build-server
description: El comando dotnet build-server interactúa con los servidores que se han iniciado por una compilación.
ms.date: 12/04/2018
ms.openlocfilehash: 7f78a0cae6e3297f3084754dc56b0da4eac38caf
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169668"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="44d16-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="44d16-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="44d16-104">nombre</span><span class="sxs-lookup"><span data-stu-id="44d16-104">Name</span></span>

<span data-ttu-id="44d16-105">`dotnet build-server`: interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="44d16-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="44d16-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="44d16-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="44d16-107">Comandos</span><span class="sxs-lookup"><span data-stu-id="44d16-107">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="44d16-108">Cierra los servidores de la compilación que se inician desde dotnet.</span><span class="sxs-lookup"><span data-stu-id="44d16-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="44d16-109">De forma predeterminada, se cierran todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="44d16-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="44d16-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="44d16-110">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="44d16-111">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="44d16-111">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="44d16-112">Cierra el servidor de compilación de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="44d16-112">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="44d16-113">Cierra el servidor de compilación de Razor.</span><span class="sxs-lookup"><span data-stu-id="44d16-113">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="44d16-114">Cierra el servidor de compilación del compilador de VB/C#.</span><span class="sxs-lookup"><span data-stu-id="44d16-114">Shuts down the VB/C# compiler build server.</span></span>