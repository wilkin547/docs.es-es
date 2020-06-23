---
ms.openlocfilehash: e7d35045892c62f759aad5067962ac5c15a9fb8b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602703"
---

<span data-ttu-id="f4285-101">Tanto el SDK de .NET Core como .NET Core Runtime se pueden instalar manualmente una vez que se han descargado.</span><span class="sxs-lookup"><span data-stu-id="f4285-101">Both .NET Core SDK and .NET Core Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="f4285-102">Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f4285-102">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="f4285-103">En primer lugar, descargue una versión binaria del SDK o del entorno de ejecución de uno de los siguientes sitios:</span><span class="sxs-lookup"><span data-stu-id="f4285-103">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="f4285-104">✔️ [Descargas de la versión preliminar de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="f4285-104">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="f4285-105">✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="f4285-105">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="f4285-106">❌ [Descargas de .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span><span class="sxs-lookup"><span data-stu-id="f4285-106">❌ [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span></span>
- <span data-ttu-id="f4285-107">❌ [Descargas de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2)</span><span class="sxs-lookup"><span data-stu-id="f4285-107">❌ [.NET Core 2.2 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.2)</span></span>
- <span data-ttu-id="f4285-108">✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="f4285-108">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>

<span data-ttu-id="f4285-109">A continuación, extraiga el archivo descargado y use el comando `export` para establecer las variables que se utilizan en .NET Core. Luego, asegúrese de que .NET Core esté en PATH.</span><span class="sxs-lookup"><span data-stu-id="f4285-109">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="f4285-110">Para extraer el entorno de ejecución y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar, descargue una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f4285-110">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="f4285-111">Luego, abra un terminal y ejecute los siguientes comandos desde el directorio donde se guardó el archivo.</span><span class="sxs-lookup"><span data-stu-id="f4285-111">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="f4285-112">Los comandos `export` anteriores solo hacen que los comandos de la CLI de .NET Core estén disponibles para la sesión de terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="f4285-112">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="f4285-113">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="f4285-113">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="f4285-114">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="f4285-114">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="f4285-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f4285-115">For example:</span></span>
>
> - <span data-ttu-id="f4285-116">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="f4285-116">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="f4285-117">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="f4285-117">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="f4285-118">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="f4285-118">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="f4285-119">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="f4285-119">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="f4285-120">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="f4285-120">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="f4285-121">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="f4285-121">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="f4285-122">Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4285-122">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>
