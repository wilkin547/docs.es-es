---
title: Creación de un paquete NuGet con herramientas de la interfaz de la línea de comandos (CLI) de .NET Core
description: Obtenga información sobre cómo crear un paquete NuGet con el comando "dotnet pack".
author: cartermp
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.custom: seodec18
ms.openlocfilehash: 2d876f921d079972e2a638788195aa69a2423c49
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771944"
---
# <a name="how-to-create-a-nuget-package-with-net-core-command-line-interface-cli-tools"></a><span data-ttu-id="62ecc-103">Cómo crear un paquete NuGet con herramientas de la interfaz de la línea de comandos (CLI) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="62ecc-103">How to create a NuGet package with .NET Core command-line interface (CLI) tools</span></span>

> [!NOTE]
> <span data-ttu-id="62ecc-104">A continuación se muestran ejemplos de línea de comandos mediante Unix.</span><span class="sxs-lookup"><span data-stu-id="62ecc-104">The following shows command-line samples using Unix.</span></span> <span data-ttu-id="62ecc-105">El comando `dotnet pack`, tal como se muestra aquí, funciona del mismo modo en Windows.</span><span class="sxs-lookup"><span data-stu-id="62ecc-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="62ecc-106">Está previsto que las bibliotecas .NET Standard y .NET Core se distribuyan como paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="62ecc-106">.NET Standard and .NET Core libraries are expected to be distributed as NuGet packages.</span></span> <span data-ttu-id="62ecc-107">De hecho, es así como se distribuyen y consumen todas las bibliotecas estándar .NET.</span><span class="sxs-lookup"><span data-stu-id="62ecc-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span> <span data-ttu-id="62ecc-108">Esto se hace más fácil con el comando `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="62ecc-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="62ecc-109">Imagine que acaba de escribir una nueva biblioteca sorprendente que quiere distribuir a través de NuGet.</span><span class="sxs-lookup"><span data-stu-id="62ecc-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span> <span data-ttu-id="62ecc-110">Puede crear un paquete de NuGet con herramientas multiplataforma para hacer exactamente eso.</span><span class="sxs-lookup"><span data-stu-id="62ecc-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span> <span data-ttu-id="62ecc-111">En el ejemplo siguiente, hay una biblioteca denominada **SuperAwesomeLibrary** con destino a `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="62ecc-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="62ecc-112">Si tiene dependencias transitivas; es decir, un proyecto que depende de otro paquete, deberá asegurarse de restaurar los paquetes para toda la solución con el comando `dotnet restore` antes de crear un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="62ecc-112">If you have transitive dependencies; that is, a project which depends on another package, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span> <span data-ttu-id="62ecc-113">Si no lo hace, el comando `dotnet pack` no funcionará correctamente.</span><span class="sxs-lookup"><span data-stu-id="62ecc-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="62ecc-114">Después de asegurarse de que se restauran los paquetes, puede ir hasta el directorio donde reside una biblioteca:</span><span class="sxs-lookup"><span data-stu-id="62ecc-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

```console
cd src/SuperAwesomeLibrary
```

<span data-ttu-id="62ecc-115">Luego, es solo cuestión de un comando desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="62ecc-115">Then it's just a single command from the command line:</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="62ecc-116">La carpeta */bin/Debug* tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="62ecc-116">Your */bin/Debug* folder will now look like this:</span></span>

```console
$ ls bin/Debug
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="62ecc-117">Tenga en cuenta que esto producirá un paquete que se puede depurar.</span><span class="sxs-lookup"><span data-stu-id="62ecc-117">Note that this will produce a package which is capable of being debugged.</span></span> <span data-ttu-id="62ecc-118">Si quiere compilar un paquete NuGet con archivos binarios de versión comercial, todo lo que tiene que hacer es agregar el modificador `--configuration` (o`-c`) y usar `release` como argumento.</span><span class="sxs-lookup"><span data-stu-id="62ecc-118">If you want to build a NuGet package with release binaries, all you need to do is add the `--configuration` (or `-c`) switch and use `release` as the argument.</span></span>

```dotnetcli
dotnet pack --configuration release
```

<span data-ttu-id="62ecc-119">La carpeta */bin* tendrá ahora una carpeta *versión* que contiene el paquete NuGet con archivos binarios de versión:</span><span class="sxs-lookup"><span data-stu-id="62ecc-119">Your */bin* folder will now have a *release* folder containing your NuGet package with release binaries:</span></span>

```console
$ ls bin/release
netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="62ecc-120">Y ahora tiene los archivos necesarios para publicar un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="62ecc-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="62ecc-121">`dotnet pack`No confunda `dotnet publish` con</span><span class="sxs-lookup"><span data-stu-id="62ecc-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="62ecc-122">Es importante tener en cuenta que en ningún momento participa el comando `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="62ecc-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span> <span data-ttu-id="62ecc-123">El comando `dotnet publish` se destina a la implementación de aplicaciones con todas sus dependencias en el mismo conjunto, no a la generación de un paquete NuGet que se distribuya y consuma a través de NuGet.</span><span class="sxs-lookup"><span data-stu-id="62ecc-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -- not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>

## <a name="see-also"></a><span data-ttu-id="62ecc-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="62ecc-124">See also</span></span>

- [<span data-ttu-id="62ecc-125">Inicio rápido: Creación y publicación de un paquete</span><span class="sxs-lookup"><span data-stu-id="62ecc-125">Quickstart: Create and publish a package</span></span>](/nuget/quickstart/create-and-publish-a-package-using-the-dotnet-cli)
