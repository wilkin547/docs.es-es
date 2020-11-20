---
ms.openlocfilehash: 3932cf51b5194dba7956cd62ced3985a2e6311f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506824"
---

<!-- Note, this content is copied in ../macos.md. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="532b4-101">Como alternativa a los administradores de paquetes, puede descargar e instalar manualmente el SDK y el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="532b4-101">As an alternative to the package managers, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="532b4-102">La instalación manual se suele llevar a cabo durante las pruebas de integración continua o en distribuciones de Linux no admitidas.</span><span class="sxs-lookup"><span data-stu-id="532b4-102">Manual install is usually performed as part of continuous integration testing or on an unsupported Linux distribution.</span></span> <span data-ttu-id="532b4-103">Para un desarrollador o usuario, generalmente es mejor usar un administrador de paquetes.</span><span class="sxs-lookup"><span data-stu-id="532b4-103">For a developer or user, it's generally better to use a package manager.</span></span>

<span data-ttu-id="532b4-104">Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="532b4-104">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="532b4-105">En primer lugar, descargue una versión **binaria** del SDK o del entorno de ejecución de uno de los siguientes sitios:</span><span class="sxs-lookup"><span data-stu-id="532b4-105">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="532b4-106">✔️ [Descargas de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="532b4-106">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="532b4-107">✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="532b4-107">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="532b4-108">✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="532b4-108">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="532b4-109">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="532b4-109">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="532b4-110">A continuación, extraiga el archivo descargado y use el comando `export` para establecer las variables que se utilizan en .NET. Luego, asegúrese de que .NET esté en PATH.</span><span class="sxs-lookup"><span data-stu-id="532b4-110">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="532b4-111">Para extraer el entorno de ejecución y hacer que los comandos de la CLI de .NET estén disponibles en el terminal, en primer lugar, descargue una versión binaria de .NET.</span><span class="sxs-lookup"><span data-stu-id="532b4-111">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="532b4-112">Luego, abra un terminal y ejecute los siguientes comandos desde el directorio donde se guardó el archivo.</span><span class="sxs-lookup"><span data-stu-id="532b4-112">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="532b4-113">El nombre del archivo puede ser distinto en función de lo que haya descargado.</span><span class="sxs-lookup"><span data-stu-id="532b4-113">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="532b4-114">**Use el comando siguiente para extraer el entorno de ejecución**:</span><span class="sxs-lookup"><span data-stu-id="532b4-114">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="532b4-115">**Use el comando siguiente para extraer el SDK**:</span><span class="sxs-lookup"><span data-stu-id="532b4-115">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="532b4-116">Los comandos `export` anteriores solo hacen que los de la CLI de .NET estén disponibles para la sesión del terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="532b4-116">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="532b4-117">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="532b4-117">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="532b4-118">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="532b4-118">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="532b4-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="532b4-119">For example:</span></span>
>
> - <span data-ttu-id="532b4-120">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="532b4-120">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="532b4-121">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="532b4-121">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="532b4-122">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="532b4-122">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="532b4-123">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="532b4-123">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="532b4-124">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="532b4-124">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="532b4-125">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="532b4-125">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="532b4-126">Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="532b4-126">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>
