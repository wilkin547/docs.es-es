---
title: Introducción e información general de .NET Core
description: .NET Core es una implementación modular y de alto rendimiento de .NET para crear aplicaciones Windows, Linux y macOS. Obtenga información sobre .NET Core para comenzar.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: f99b446bbd38b2b814c13afa13ab34cd5c9aa086
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645522"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="ead2c-104">Introducción a .NET Core</span><span class="sxs-lookup"><span data-stu-id="ead2c-104">Introduction to .NET Core</span></span>

<span data-ttu-id="ead2c-105">[.NET Core](about.md) es una plataforma de desarrollo [de código abierto](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) para uso general.</span><span class="sxs-lookup"><span data-stu-id="ead2c-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform.</span></span> <span data-ttu-id="ead2c-106">Puede crear aplicaciones de .NET Core para Windows, macOS y Linux para procesadores x64, x86, ARM32 y ARM64 mediante varios lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="ead2c-106">You can create .NET Core apps for Windows, macOS, and Linux for x64, x86, ARM32, and ARM64 processors using multiple programming languages.</span></span> <span data-ttu-id="ead2c-107">Se proporcionan marcos y API para la [nube](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), la [Interfaz de usuario de cliente](../desktop-wpf/overview/index.md) y el [aprendizaje automático](/dotnet/machine-learning/).</span><span class="sxs-lookup"><span data-stu-id="ead2c-107">Frameworks and APIs are provided for [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [client UI](../desktop-wpf/overview/index.md), and [machine learning](/dotnet/machine-learning/).</span></span>

<span data-ttu-id="ead2c-108">[Descargue el SDK de .NET Core](https://dotnet.microsoft.com/download) para probar .NET Core en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ead2c-108">[Download the .NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your machine.</span></span> <span data-ttu-id="ead2c-109">La última versión es [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span><span class="sxs-lookup"><span data-stu-id="ead2c-109">The latest version is [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

## <a name="download-net-core"></a><span data-ttu-id="ead2c-110">Descarga de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ead2c-110">Download .NET Core</span></span>

<span data-ttu-id="ead2c-111">Puede obtener .NET Core de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="ead2c-111">You can get .NET Core in the following ways:</span></span>

* [<span data-ttu-id="ead2c-112">Instaladores para Windows y macOS</span><span class="sxs-lookup"><span data-stu-id="ead2c-112">Installers for Windows and macOS</span></span>](https://dotnet.microsoft.com/download)
* [<span data-ttu-id="ead2c-113">Paquetes de Linux</span><span class="sxs-lookup"><span data-stu-id="ead2c-113">Linux packages</span></span>](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [<span data-ttu-id="ead2c-114">Contenedores de Docker</span><span class="sxs-lookup"><span data-stu-id="ead2c-114">Docker containers</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
* [<span data-ttu-id="ead2c-115">Archivos ZIP y tar</span><span class="sxs-lookup"><span data-stu-id="ead2c-115">Zips and tar balls</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [<span data-ttu-id="ead2c-116">Scripts de instalación</span><span class="sxs-lookup"><span data-stu-id="ead2c-116">Install scripts</span></span>](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [<span data-ttu-id="ead2c-117">Notas de la versión</span><span class="sxs-lookup"><span data-stu-id="ead2c-117">Release notes</span></span>](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a><span data-ttu-id="ead2c-118">Creación de la primera aplicación</span><span class="sxs-lookup"><span data-stu-id="ead2c-118">Create your first application</span></span>

<span data-ttu-id="ead2c-119">Después de instalar el SDK de .NET Core, abra un símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="ead2c-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="ead2c-120">Use los comandos siguientes para crear y ejecutar una aplicación:</span><span class="sxs-lookup"><span data-stu-id="ead2c-120">Use the following commands to create and run an application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="ead2c-121">Debería ver los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="ead2c-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="contribute"></a><span data-ttu-id="ead2c-122">Contribuir</span><span class="sxs-lookup"><span data-stu-id="ead2c-122">Contribute</span></span>

<span data-ttu-id="ead2c-123">.NET Core es una plataforma abierta.</span><span class="sxs-lookup"><span data-stu-id="ead2c-123">.NET Core is an open platform.</span></span> <span data-ttu-id="ead2c-124">Todo el mundo puede participar.</span><span class="sxs-lookup"><span data-stu-id="ead2c-124">Everyone is welcome to participate.</span></span>

* <span data-ttu-id="ead2c-125">Registre las incidencias y preguntas sobre el producto en [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span><span class="sxs-lookup"><span data-stu-id="ead2c-125">File product issues and questions at [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span></span>
* <span data-ttu-id="ead2c-126">Las contribuciones al producto se deben realizar en uno de los repositorios del proyecto, como [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn) o [aspnetcore](https://github.com/dotnet/aspnetcore).</span><span class="sxs-lookup"><span data-stu-id="ead2c-126">Product contributions should be made on one of the project repositories, such as [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn), or [aspnetcore](https://github.com/dotnet/aspnetcore).</span></span> <span data-ttu-id="ead2c-127">Para obtener más información, vea [Repositorios de .NET Core](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span><span class="sxs-lookup"><span data-stu-id="ead2c-127">For more information, see [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span></span>

## <a name="support"></a><span data-ttu-id="ead2c-128">Soporte técnico</span><span class="sxs-lookup"><span data-stu-id="ead2c-128">Support</span></span>

<span data-ttu-id="ead2c-129">.NET Core es compatible con Microsoft en Windows, macOS y Linux, y con Red Hat en Red Hat Enterprise Linux.</span><span class="sxs-lookup"><span data-stu-id="ead2c-129">.NET Core is supported by Microsoft on Windows, macOS, and Linux and by Red Hat on Red Hat Enterprise Linux.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ead2c-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ead2c-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ead2c-131">Tutoriales de .NET Core</span><span class="sxs-lookup"><span data-stu-id="ead2c-131">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="ead2c-132">Prueba de .NET Core en el explorador</span><span class="sxs-lookup"><span data-stu-id="ead2c-132">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
