---
title: Implementación de aplicaciones .NET en Raspberry PI
description: Obtenga información sobre cómo implementar aplicaciones .NET en Raspberry PI.
author: camsoper
ms.author: casoper
ms.date: 11/13/2020
ms.topic: how-to
ms.prod: dotnet
ms.openlocfilehash: 4da558e2cdfc283d21f2a5497cb71dc746109614
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96594731"
---
# <a name="deploy-net-apps-to-raspberry-pi"></a><span data-ttu-id="20b4d-103">Implementación de aplicaciones .NET en Raspberry PI</span><span class="sxs-lookup"><span data-stu-id="20b4d-103">Deploy .NET apps to Raspberry Pi</span></span>

<span data-ttu-id="20b4d-104">La implementación de aplicaciones .NET en Raspberry PI es idéntica a la de cualquier otra plataforma.</span><span class="sxs-lookup"><span data-stu-id="20b4d-104">Deployment of .NET apps to Raspberry Pi is identical to that of any other platform.</span></span> <span data-ttu-id="20b4d-105">La aplicación puede ejecutarse como modo *de implementación independiente* o *dependiente del marco* .</span><span class="sxs-lookup"><span data-stu-id="20b4d-105">Your app can run as *self-contained* or *framework-dependent* deployment modes.</span></span> <span data-ttu-id="20b4d-106">Cada estrategia tiene ventajas.</span><span class="sxs-lookup"><span data-stu-id="20b4d-106">There are advantages to each strategy.</span></span> <span data-ttu-id="20b4d-107">Para obtener más información, vea [información general sobre la publicación de aplicaciones .net](../core/deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="20b4d-107">For more information, see [.NET application publishing overview](../core/deploying/index.md).</span></span>

## <a name="deploying-a-framework-dependent-app"></a><span data-ttu-id="20b4d-108">Implementación de una aplicación dependiente del marco</span><span class="sxs-lookup"><span data-stu-id="20b4d-108">Deploying a framework-dependent app</span></span>

<span data-ttu-id="20b4d-109">Para implementar la aplicación como una aplicación dependiente del marco, complete los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="20b4d-109">To deploy your app as a framework-dependent app, complete the following steps:</span></span>

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. <span data-ttu-id="20b4d-110">Instale .NET en Raspberry PI con los [scripts de dotnet-install](../core/tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="20b4d-110">Install .NET on the Raspberry Pi using the [dotnet-install scripts](../core/tools/dotnet-install-script.md).</span></span> <span data-ttu-id="20b4d-111">Complete los pasos siguientes desde un símbolo del sistema de bash en Raspberry PI (local o SSH):</span><span class="sxs-lookup"><span data-stu-id="20b4d-111">Complete the following steps from a Bash prompt on the Raspberry Pi (local or SSH):</span></span>
    1. <span data-ttu-id="20b4d-112">Ejecute el siguiente comando para instalar .NET:</span><span class="sxs-lookup"><span data-stu-id="20b4d-112">Run the following command to install .NET:</span></span>

        ```bash
        curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin
        ```

        > [!NOTE]
        > <span data-ttu-id="20b4d-113">De este modo se instala la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="20b4d-113">This installs the latest version.</span></span> <span data-ttu-id="20b4d-114">Si necesita una versión concreta, agregue `--version <VERSION>` al final, donde `<VERSION>` es la versión de compilación específica.</span><span class="sxs-lookup"><span data-stu-id="20b4d-114">If you need a specific version, add `--version <VERSION>` to the end, where `<VERSION>` is the specific build version.</span></span>

    1. <span data-ttu-id="20b4d-115">Para simplificar la resolución de la ruta de acceso, agregue una `DOTNET_ROOT` variable de entorno y agregue el directorio *. dotnet* a `$PATH` con los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="20b4d-115">To simplify path resolution, add a `DOTNET_ROOT` environment variable and add the *.dotnet* directory to `$PATH` with the following commands:</span></span>

        ```bash
        echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
        echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
        source ~/.bashrc
        ```

    1. <span data-ttu-id="20b4d-116">Compruebe la instalación de .NET con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="20b4d-116">Verify the .NET installation with the following command:</span></span>

        ```dotnetcli
        dotnet --version
        ```

        <span data-ttu-id="20b4d-117">Compruebe que la versión mostrada coincide con la versión que instaló.</span><span class="sxs-lookup"><span data-stu-id="20b4d-117">Verify the displayed version matches the version you installed.</span></span>

1. <span data-ttu-id="20b4d-118">Publique la aplicación en el equipo de desarrollo de la siguiente manera, en función del entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="20b4d-118">Publish the app on the development computer as follows, depending on development environment.</span></span>
    - <span data-ttu-id="20b4d-119">Si usa **Visual Studio**, [implemente la aplicación en una carpeta local](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="20b4d-119">If using **Visual Studio**, [deploy the app to a local folder](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span></span> <span data-ttu-id="20b4d-120">Antes de la publicación, seleccione **Editar** en el Resumen de Perfil de publicación y seleccione la pestaña **configuración** . Asegúrese de que el **modo de implementación** está establecido en tiempo *de ejecución dependiente del marco y el* de **destino** está establecido en *portable*.</span><span class="sxs-lookup"><span data-stu-id="20b4d-120">Before publishing, select **Edit** in the publish profile summary and select the **Settings** tab. Ensure that **Deployment mode** is set to *Framework-dependent* and **Target runtime** is set to *Portable*.</span></span>
    - <span data-ttu-id="20b4d-121">Si usa la **CLI de .net**, use el comando [dotnet Publish](../core/tools/dotnet-publish.md) .</span><span class="sxs-lookup"><span data-stu-id="20b4d-121">If using the **.NET CLI**, use the [dotnet publish](../core/tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="20b4d-122">No se requieren argumentos adicionales.</span><span class="sxs-lookup"><span data-stu-id="20b4d-122">No additional arguments are required.</span></span>

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. <span data-ttu-id="20b4d-123">Desde un símbolo del sistema de bash en Raspberry PI (local o SSH), ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="20b4d-123">From a Bash prompt on the Raspberry Pi (local or SSH), run the app.</span></span> <span data-ttu-id="20b4d-124">Para ello, establezca la carpeta de implementación como el directorio actual y ejecute el siguiente comando (donde *HelloWorld.dll* es el punto de entrada de la aplicación):</span><span class="sxs-lookup"><span data-stu-id="20b4d-124">To do this, set the deployment folder as the current directory and execute the following command (where *HelloWorld.dll* is the entry point of the app):</span></span>

    ```dotnetcli
    dotnet HelloWorld.dll
    ```

## <a name="deploying-a-self-contained-app"></a><span data-ttu-id="20b4d-125">Implementación de una aplicación independiente</span><span class="sxs-lookup"><span data-stu-id="20b4d-125">Deploying a self-contained app</span></span>

<span data-ttu-id="20b4d-126">Para implementar la aplicación como una aplicación independiente, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="20b4d-126">To deploy your app as a self-contained app, complete the following steps:</span></span>

1. [!INCLUDE [ensure-ssh](includes/ensure-ssh.md)]

1. <span data-ttu-id="20b4d-127">Publique la aplicación en el equipo de desarrollo de la siguiente manera, en función del entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="20b4d-127">Publish the app on the development computer as follows, depending on development environment.</span></span>
    - <span data-ttu-id="20b4d-128">Si usa **Visual Studio**, [implemente la aplicación en una carpeta local](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span><span class="sxs-lookup"><span data-stu-id="20b4d-128">If using **Visual Studio**, [deploy the app to a local folder](/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019).</span></span> <span data-ttu-id="20b4d-129">Antes de la publicación, seleccione **Editar** en el Resumen de Perfil de publicación y seleccione la pestaña **configuración** . Asegúrese de que el **modo de implementación** está establecido en *independiente y el* tiempo de ejecución de **destino** está establecido en *Linux-ARM*.</span><span class="sxs-lookup"><span data-stu-id="20b4d-129">Before publishing, select **Edit** in the publish profile summary and select the **Settings** tab. Ensure that **Deployment mode** is set to *Self-contained* and **Target runtime** is set to *linux-arm*.</span></span>
    - <span data-ttu-id="20b4d-130">Si usa la **CLI de .net**, use el comando [dotnet Publish](../core/tools/dotnet-publish.md) con el `-r linux-arm` argumento:</span><span class="sxs-lookup"><span data-stu-id="20b4d-130">If using the **.NET CLI**, use the [dotnet publish](../core/tools/dotnet-publish.md) command with the `-r linux-arm` argument:</span></span>

        ```dotnetcli
        dotnet publish -r linux-arm
        ```

1. [!INCLUDE [sftp-client](includes/sftp-client.md)]

1. <span data-ttu-id="20b4d-131">Desde un símbolo del sistema de bash en Raspberry PI (local o SSH), ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="20b4d-131">From a Bash prompt on the Raspberry Pi (local or SSH), run the app.</span></span> <span data-ttu-id="20b4d-132">Para ello, establezca el directorio actual en la ubicación de implementación y complete los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="20b4d-132">To do this, set the current directory to the deployment location and complete the following steps:</span></span>
    1. <span data-ttu-id="20b4d-133">Conceda el permiso de *ejecución* ejecutable (donde `HelloWorld` es el nombre del archivo ejecutable).</span><span class="sxs-lookup"><span data-stu-id="20b4d-133">Give the executable *execute* permission (where `HelloWorld` is the executable file name).</span></span>

        ```bash
        chmod +x HelloWorld
        ```

    1. <span data-ttu-id="20b4d-134">Ejecute el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="20b4d-134">Run the executable.</span></span>

        ```bash
        ./HelloWorld
        ```
