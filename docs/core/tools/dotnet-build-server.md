---
title: Comando dotnet build-server
description: El comando dotnet build-server interactúa con los servidores que se han iniciado por una compilación.
ms.date: 04/24/2019
ms.openlocfilehash: 89d1aba104e2cb07b46766a3768eed68d85a7aa7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117764"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="15c9e-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="15c9e-103">dotnet build-server</span></span>

<span data-ttu-id="15c9e-104">**Este artículo se aplica a: ✓** SDK de .NET Core 2.1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="15c9e-104">**This article applies to: ✓** .NET Core 2.1 SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a><span data-ttu-id="15c9e-105">Name</span><span class="sxs-lookup"><span data-stu-id="15c9e-105">Name</span></span>

<span data-ttu-id="15c9e-106">`dotnet build-server`: interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="15c9e-106">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="15c9e-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="15c9e-107">Synopsis</span></span>

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="15c9e-108">Comandos</span><span class="sxs-lookup"><span data-stu-id="15c9e-108">Commands</span></span>

* **`shutdown`**

  <span data-ttu-id="15c9e-109">Cierra los servidores de la compilación que se inician desde dotnet.</span><span class="sxs-lookup"><span data-stu-id="15c9e-109">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="15c9e-110">De forma predeterminada, se cierran todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="15c9e-110">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="15c9e-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="15c9e-111">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="15c9e-112">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="15c9e-112">Prints out a short help for the command.</span></span>

* **`--msbuild`**

  <span data-ttu-id="15c9e-113">Cierra el servidor de compilación de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="15c9e-113">Shuts down the MSBuild build server.</span></span>

* **`--razor`**

  <span data-ttu-id="15c9e-114">Cierra el servidor de compilación de Razor.</span><span class="sxs-lookup"><span data-stu-id="15c9e-114">Shuts down the Razor build server.</span></span>

* **`--vbcscompiler`**

  <span data-ttu-id="15c9e-115">Cierra el servidor de compilación del compilador de VB/C#.</span><span class="sxs-lookup"><span data-stu-id="15c9e-115">Shuts down the VB/C# compiler build server.</span></span>
