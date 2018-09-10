---
title: Creación de un paquete de NuGet con herramientas multiplataforma
description: Obtenga información sobre cómo crear un paquete NuGet con el comando "dotnet pack".
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 6be94c2e2cef443f69b2d6df7c2d490cb1fb629d
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205067"
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="a4d68-103">Cómo crear un paquete de NuGet con herramientas multiplataforma</span><span class="sxs-lookup"><span data-stu-id="a4d68-103">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="a4d68-104">A continuación se muestran ejemplos de línea de comandos mediante Unix.</span><span class="sxs-lookup"><span data-stu-id="a4d68-104">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="a4d68-105">El comando `dotnet pack`, tal como se muestra aquí, funciona del mismo modo en Windows.</span><span class="sxs-lookup"><span data-stu-id="a4d68-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="a4d68-106">Para .NET Core 1.0, está previsto que las bibliotecas se distribuyan como paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4d68-106">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="a4d68-107">De hecho, es así como se distribuyen y consumen todas las bibliotecas estándar .NET.</span><span class="sxs-lookup"><span data-stu-id="a4d68-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="a4d68-108">Esto se hace más fácil con el comando `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="a4d68-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="a4d68-109">Imagine que acaba de escribir una nueva biblioteca sorprendente que quiere distribuir a través de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4d68-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="a4d68-110">Puede crear un paquete de NuGet con herramientas multiplataforma para hacer exactamente eso.</span><span class="sxs-lookup"><span data-stu-id="a4d68-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="a4d68-111">En el ejemplo siguiente, hay una biblioteca denominada **SuperAwesomeLibrary** con destino a `netstandard1.0`.</span><span class="sxs-lookup"><span data-stu-id="a4d68-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="a4d68-112">Si tiene dependencias transitivas; es decir, un proyecto que depende de otro, deberá asegurarse de restaurar los paquetes para toda la solución con el comando `dotnet restore` antes de crear un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4d68-112">If you have transitive dependencies; that is, a project which depends on another project, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="a4d68-113">Si no lo hace, el comando `dotnet pack` no funcionará correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4d68-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


<span data-ttu-id="a4d68-114">Después de asegurarse de que se restauran los paquetes, puede ir hasta el directorio donde reside una biblioteca:</span><span class="sxs-lookup"><span data-stu-id="a4d68-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="a4d68-115">Luego, es solo cuestión de un comando desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="a4d68-115">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="a4d68-116">Su carpeta `/bin/Debug` tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a4d68-116">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="a4d68-117">Tenga en cuenta que esto producirá un paquete que se puede depurar.</span><span class="sxs-lookup"><span data-stu-id="a4d68-117">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="a4d68-118">Si quiere compilar un paquete de NuGet con archivos binarios de versión comercial, todo lo que tiene que hacer es agregar el modificador `-c`/`--configuration` y usar `release` como argumento.</span><span class="sxs-lookup"><span data-stu-id="a4d68-118">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="a4d68-119">Su `/bin` carpeta tendrá ahora una `release` carpeta que contiene el paquete de NuGet con archivos binarios de versión:</span><span class="sxs-lookup"><span data-stu-id="a4d68-119">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="a4d68-120">Y ahora tiene los archivos necesarios para publicar un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4d68-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="a4d68-121">`dotnet pack`No confunda `dotnet publish` con</span><span class="sxs-lookup"><span data-stu-id="a4d68-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="a4d68-122">Es importante tener en cuenta que en ningún momento participa el comando `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="a4d68-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="a4d68-123">El comando `dotnet publish` es para la implementación de aplicaciones con todas sus dependencias en el mismo paquete, no para generar un paquete de NuGet para distribuir y consumir a través de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a4d68-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>
