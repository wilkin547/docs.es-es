---
title: 'Comando dotnet build-server: CLI de .NET Core'
description: El comando dotnet build-server interactúa con los servidores que se han iniciado por una compilación.
author: mairaw
ms.author: mairaw
ms.date: 07/02/2018
ms.openlocfilehash: 1c59c85f246b79c7e2552f704db5b4f076f9b502
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404338"
---
# <a name="dotnet-build-server"></a><span data-ttu-id="43114-103">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="43114-103">dotnet build-server</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="43114-104">nombre</span><span class="sxs-lookup"><span data-stu-id="43114-104">Name</span></span>

<span data-ttu-id="43114-105">`dotnet build-server`: interactúa con servidores iniciados por una compilación.</span><span class="sxs-lookup"><span data-stu-id="43114-105">`dotnet build-server` - Interacts with servers started by a build.</span></span>

## <a name="synopsis"></a><span data-ttu-id="43114-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="43114-106">Synopsis</span></span>

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a><span data-ttu-id="43114-107">Comandos</span><span class="sxs-lookup"><span data-stu-id="43114-107">Commands</span></span>

`shutdown`

<span data-ttu-id="43114-108">Cierra los servidores de la compilación que se inician desde dotnet.</span><span class="sxs-lookup"><span data-stu-id="43114-108">Shuts down build servers that are started from dotnet.</span></span> <span data-ttu-id="43114-109">De forma predeterminada, se cierran todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="43114-109">By default, all servers are shut down.</span></span>

## <a name="options"></a><span data-ttu-id="43114-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="43114-110">Options</span></span>

`-h|--help`

<span data-ttu-id="43114-111">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="43114-111">Prints out a short help for the command.</span></span>

`--msbuild`

<span data-ttu-id="43114-112">Cierra el servidor de compilación de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="43114-112">Shuts down the MSBuild build server.</span></span>

`--razor`

<span data-ttu-id="43114-113">Cierra el servidor de compilación de Razor.</span><span class="sxs-lookup"><span data-stu-id="43114-113">Shuts down the Razor build server.</span></span>

`--vbcscompiler`

<span data-ttu-id="43114-114">Cierra el servidor de compilación del compilador de VB/C#.</span><span class="sxs-lookup"><span data-stu-id="43114-114">Shuts down the VB/C# compiler build server.</span></span>
