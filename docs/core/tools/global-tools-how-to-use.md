---
title: 'Tutorial: Instalación y uso de una herramienta global de .NET'
description: Aprenda a instalar y usar una herramienta de .NET como una herramienta global.
ms.topic: tutorial
ms.date: 02/12/2020
ms.openlocfilehash: 01b773516da92fb16fb0f67fc6617e0c70d17c9d
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633900"
---
# <a name="tutorial-install-and-use-a-net-global-tool-using-the-net-cli"></a><span data-ttu-id="e4e4c-103">Tutorial: Instalación y uso de una herramienta global de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="e4e4c-103">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>

<span data-ttu-id="e4e4c-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e4e4c-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="e4e4c-105">En este tutorial se enseña cómo instalar y usar una herramienta global.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="e4e4c-106">Usará una herramienta que ha creado en el [primer tutorial de esta serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="e4e4c-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e4e4c-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e4e4c-107">Prerequisites</span></span>

* <span data-ttu-id="e4e4c-108">Complete el [primer tutorial de esta serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="e4e4c-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="e4e4c-109">Uso de la herramienta como una herramienta global</span><span class="sxs-lookup"><span data-stu-id="e4e4c-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="e4e4c-110">Instale la herramienta desde el paquete; para ello, ejecute el comando [dotnet tool install](dotnet-tool-install.md) en la carpeta del proyecto *microsoft.botsay*:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *microsoft.botsay* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="e4e4c-111">El parámetro `--global` indica a la CLI de .NET que instale los archivos binarios de la herramienta en una ubicación predeterminada que se agrega de forma automática a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-111">The `--global` parameter tells the .NET CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="e4e4c-112">El parámetro `--add-source` indica a la CLI de .NET que use temporalmente el directorio *./nupkg* como una fuente de origen adicional para los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-112">The `--add-source` parameter tells the .NET CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="e4e4c-113">Ha asignado un nombre único al paquete para asegurarse de que solo se encontrará en el directorio *./nupkg*, no en el sitio de Nuget.org.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span>

   <span data-ttu-id="e4e4c-114">En la salida se muestra el comando que se ha usado para llamar a la herramienta y la versión instalada:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="e4e4c-115">Invoque la herramienta:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="e4e4c-116">Si se produce un error en este comando, es posible que tenga que abrir un nuevo terminal para actualizar el valor de PATH.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="e4e4c-117">Ejecute el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) para quitar la herramienta:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="e4e4c-118">Uso de la herramienta como una herramienta global instalada en una ubicación personalizada</span><span class="sxs-lookup"><span data-stu-id="e4e4c-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="e4e4c-119">Instale la herramienta desde el paquete.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-119">Install the tool from the package.</span></span>

   <span data-ttu-id="e4e4c-120">En Windows:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="e4e4c-121">En Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="e4e4c-122">El parámetro `--tool-path` indica a la CLI de .NET que instale los archivos binarios de la herramienta en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-122">The `--tool-path` parameter tells the .NET CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="e4e4c-123">Si el directorio no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="e4e4c-124">Este directorio no se agrega automáticamente a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="e4e4c-125">En la salida se muestra el comando que se ha usado para llamar a la herramienta y la versión instalada:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="e4e4c-126">Invoque la herramienta:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-126">Invoke the tool:</span></span>

   <span data-ttu-id="e4e4c-127">En Windows:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="e4e4c-128">En Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="e4e4c-129">Ejecute el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) para quitar la herramienta:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="e4e4c-130">En Windows:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   <span data-ttu-id="e4e4c-131">En Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="e4e4c-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a><span data-ttu-id="e4e4c-132">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="e4e4c-132">Troubleshoot</span></span>

<span data-ttu-id="e4e4c-133">Si recibe un mensaje de error al seguir el tutorial, vea [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="e4e4c-133">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="e4e4c-134">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e4e4c-134">Next steps</span></span>

<span data-ttu-id="e4e4c-135">En este tutorial, ha instalado y usado una herramienta como una herramienta global.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="e4e4c-136">Para instalar y usar la misma herramienta como una herramienta local, vaya al siguiente tutorial.</span><span class="sxs-lookup"><span data-stu-id="e4e4c-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e4e4c-137">Instalación y uso de herramientas locales</span><span class="sxs-lookup"><span data-stu-id="e4e4c-137">Install and use local tools</span></span>](local-tools-how-to-use.md)
