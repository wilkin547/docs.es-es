---
title: 'Tutorial: Instalación y uso de una herramienta global de .NET Core'
description: Aprenda a instalar y usar una herramienta de .NET como una herramienta global.
ms.date: 02/12/2020
ms.openlocfilehash: 9f8378e50fd2544eedbbaaeffb89d67800ec6880
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156743"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="15c4e-103">Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="15c4e-103">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>

<span data-ttu-id="15c4e-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="15c4e-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="15c4e-105">En este tutorial se enseña cómo instalar y usar una herramienta global.</span><span class="sxs-lookup"><span data-stu-id="15c4e-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="15c4e-106">Usará una herramienta que ha creado en el [primer tutorial de esta serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="15c4e-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="15c4e-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="15c4e-107">Prerequisites</span></span>

* <span data-ttu-id="15c4e-108">Complete el [primer tutorial de esta serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="15c4e-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="15c4e-109">Uso de la herramienta como una herramienta global</span><span class="sxs-lookup"><span data-stu-id="15c4e-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="15c4e-110">Instale la herramienta desde el paquete; para ello, ejecute el comando [dotnet tool install](dotnet-tool-install.md) en la carpeta del proyecto *microsoft.botsay*:</span><span class="sxs-lookup"><span data-stu-id="15c4e-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *microsoft.botsay* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="15c4e-111">El parámetro `--global` indica a la CLI de .NET Core que instale los archivos binarios de la herramienta en una ubicación predeterminada que se agrega automáticamente a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="15c4e-111">The `--global` parameter tells the .NET Core CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="15c4e-112">El parámetro `--add-source` indica a la CLI de .NET Core que use temporalmente el directorio *./nupkg* como una fuente de origen adicional para los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="15c4e-112">The `--add-source` parameter tells the .NET Core CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="15c4e-113">Ha asignado un nombre único al paquete para asegurarse de que solo se encontrará en el directorio *./nupkg*, no en el sitio de Nuget.org.</span><span class="sxs-lookup"><span data-stu-id="15c4e-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span>

   <span data-ttu-id="15c4e-114">En la salida se muestra el comando que se ha usado para llamar a la herramienta y la versión instalada:</span><span class="sxs-lookup"><span data-stu-id="15c4e-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="15c4e-115">Invoque la herramienta:</span><span class="sxs-lookup"><span data-stu-id="15c4e-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="15c4e-116">Si se produce un error en este comando, es posible que tenga que abrir un nuevo terminal para actualizar el valor de PATH.</span><span class="sxs-lookup"><span data-stu-id="15c4e-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="15c4e-117">Ejecute el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) para quitar la herramienta:</span><span class="sxs-lookup"><span data-stu-id="15c4e-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="15c4e-118">Uso de la herramienta como una herramienta global instalada en una ubicación personalizada</span><span class="sxs-lookup"><span data-stu-id="15c4e-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="15c4e-119">Instale la herramienta desde el paquete.</span><span class="sxs-lookup"><span data-stu-id="15c4e-119">Install the tool from the package.</span></span>

   <span data-ttu-id="15c4e-120">En Windows:</span><span class="sxs-lookup"><span data-stu-id="15c4e-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="15c4e-121">En Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="15c4e-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="15c4e-122">El parámetro `--tool-path` indica a la CLI de .NET Core que instale los archivos binarios de la herramienta en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="15c4e-122">The `--tool-path` parameter tells the .NET Core CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="15c4e-123">Si el directorio no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="15c4e-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="15c4e-124">Este directorio no se agrega automáticamente a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="15c4e-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="15c4e-125">En la salida se muestra el comando que se ha usado para llamar a la herramienta y la versión instalada:</span><span class="sxs-lookup"><span data-stu-id="15c4e-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="15c4e-126">Invoque la herramienta:</span><span class="sxs-lookup"><span data-stu-id="15c4e-126">Invoke the tool:</span></span>

   <span data-ttu-id="15c4e-127">En Windows:</span><span class="sxs-lookup"><span data-stu-id="15c4e-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="15c4e-128">En Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="15c4e-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="15c4e-129">Ejecute el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) para quitar la herramienta:</span><span class="sxs-lookup"><span data-stu-id="15c4e-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="15c4e-130">En Windows:</span><span class="sxs-lookup"><span data-stu-id="15c4e-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   <span data-ttu-id="15c4e-131">En Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="15c4e-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a><span data-ttu-id="15c4e-132">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="15c4e-132">Troubleshoot</span></span>

<span data-ttu-id="15c4e-133">Si recibe un mensaje de error al seguir el tutorial, vea [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="15c4e-133">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="15c4e-134">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="15c4e-134">Next steps</span></span>

<span data-ttu-id="15c4e-135">En este tutorial, ha instalado y usado una herramienta como una herramienta global.</span><span class="sxs-lookup"><span data-stu-id="15c4e-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="15c4e-136">Para instalar y usar la misma herramienta como una herramienta local, vaya al siguiente tutorial.</span><span class="sxs-lookup"><span data-stu-id="15c4e-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="15c4e-137">Instalación y uso de herramientas locales</span><span class="sxs-lookup"><span data-stu-id="15c4e-137">Install and use local tools</span></span>](local-tools-how-to-use.md)
