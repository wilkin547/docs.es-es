---
title: Procedimiento para instalar y configurar los componentes de activación de WFC
description: Obtenga información acerca de cómo configurar el servicio de activación de procesos de Windows (WAS) en Windows Vista para hospedar servicios WCF que no se comunican a través de HTTP.
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 84a0dcc4fed28ebd7a536bdabfcdc389be6072d8
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246888"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="052fd-103">Procedimiento para instalar y configurar los componentes de activación de WFC</span><span class="sxs-lookup"><span data-stu-id="052fd-103">How to: Install and Configure WCF Activation Components</span></span>

<span data-ttu-id="052fd-104">En este tema se describen los pasos necesarios para configurar el servicio de activación de procesos de Windows (también conocido como WAS) en Windows Vista para hospedar servicios Windows Communication Foundation (WCF) que no se comunican a través de protocolos de red HTTP.</span><span class="sxs-lookup"><span data-stu-id="052fd-104">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="052fd-105">Las siguientes secciones describen los pasos para realizar esta configuración:</span><span class="sxs-lookup"><span data-stu-id="052fd-105">The following sections outline the steps for this configuration:</span></span>

- <span data-ttu-id="052fd-106">Instale (o confirme la instalación de) los componentes de activación de WCF.</span><span class="sxs-lookup"><span data-stu-id="052fd-106">Install (or confirm the installation of) the WCF activation components.</span></span>

- <span data-ttu-id="052fd-107">Configure WAS para que admita un protocolo que no sea HTTP.</span><span class="sxs-lookup"><span data-stu-id="052fd-107">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="052fd-108">El procedimiento siguiente configura Windows Vista para la activación de TCP.</span><span class="sxs-lookup"><span data-stu-id="052fd-108">The following procedure configures Windows Vista for TCP activation.</span></span>

<span data-ttu-id="052fd-109">Después de instalar y configurar WAS, consulte [Cómo: hospedar un servicio WCF en was](how-to-host-a-wcf-service-in-was.md) para los procedimientos para crear un servicio WCF que exponga un punto de conexión que no sea http y que emplee was.</span><span class="sxs-lookup"><span data-stu-id="052fd-109">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>

## <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="052fd-110">Instalación de los componentes de activación que no son HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="052fd-110">To install the WCF non-HTTP activation components</span></span>

1. <span data-ttu-id="052fd-111">Haga clic en el botón **Inicio** y, a continuación, haga clic en **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="052fd-111">Click the **Start** button, and then click **Control Panel**.</span></span>

2. <span data-ttu-id="052fd-112">Haga clic en **Programas** y, a continuación, haga clic en **Programas y características**.</span><span class="sxs-lookup"><span data-stu-id="052fd-112">Click **Programs**, and then click **Programs and Features**.</span></span>

3. <span data-ttu-id="052fd-113">En el menú **tareas** , haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="052fd-113">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>

4. <span data-ttu-id="052fd-114">Busque el nodo WinFX, selecciónelo y, a continuación, expándalo.</span><span class="sxs-lookup"><span data-stu-id="052fd-114">Find the WinFX node, select and then expand it.</span></span>

5. <span data-ttu-id="052fd-115">Seleccione el cuadro **componentes de activación no http de WCF** y guarde la configuración.</span><span class="sxs-lookup"><span data-stu-id="052fd-115">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>

## <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="052fd-116">Configuración de WAS para admitir la activación TCP</span><span class="sxs-lookup"><span data-stu-id="052fd-116">To configure the WAS to support TCP activation</span></span>

1. <span data-ttu-id="052fd-117">Para admitir la activación del net.tcp, el sitio web predeterminado debe enlazarse primero a un puerto net.tcp.</span><span class="sxs-lookup"><span data-stu-id="052fd-117">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="052fd-118">Puede hacerlo mediante Appcmd.exe, que se instala con el conjunto de herramientas de administración de IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="052fd-118">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="052fd-119">En una ventana de símbolo de sistema para administradores, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="052fd-119">In an administrator-level Command Prompt window, run the following command.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="052fd-120">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="052fd-120">This command is a single line of text.</span></span> <span data-ttu-id="052fd-121">Este comando agrega un enlace del sitio net.tcp al sitio web predeterminado que realiza escuchas en el puerto TCP 808 con cualquier nombre de host.</span><span class="sxs-lookup"><span data-stu-id="052fd-121">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>

2. <span data-ttu-id="052fd-122">Aunque todas las aplicaciones dentro de un sitio comparten un enlace net. tcp común, cada aplicación puede habilitar la compatibilidad net. tcp individualmente.</span><span class="sxs-lookup"><span data-stu-id="052fd-122">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="052fd-123">Para habilitar net.tcp para la aplicación, ejecute el siguiente comando desde un símbolo del sistema del nivel del administrador:</span><span class="sxs-lookup"><span data-stu-id="052fd-123">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > <span data-ttu-id="052fd-124">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="052fd-124">This command is a single line of text.</span></span> <span data-ttu-id="052fd-125">Este comando permite \<*WCF Application*> tener acceso a la aplicación/mediante `http://localhost/<WCF Application>` y `net.tcp://localhost/<WCF Application>` .</span><span class="sxs-lookup"><span data-stu-id="052fd-125">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>

     <span data-ttu-id="052fd-126">Elimine el enlace del sitio de net.tcp que ha agregado para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="052fd-126">Remove the net.tcp site binding you added for this sample.</span></span>

     <span data-ttu-id="052fd-127">Para su comodidad, los dos pasos siguientes se implementan en un archivo de información llamado RemoveNetTcpSiteBinding.cmd localizado en el directorio de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="052fd-127">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="052fd-128">Quite el net.tcp de la lista de protocolos habilitados ejecutando el comando siguiente en una ventana de símbolo del sistema del nivel del administrador:</span><span class="sxs-lookup"><span data-stu-id="052fd-128">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="052fd-129">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="052fd-129">This command is a single line of text.</span></span>

    2. <span data-ttu-id="052fd-130">Quite el enlace del sitio net.tcp ejecutando el siguiente comando desde una ventana de símbolo del sistema elevado:</span><span class="sxs-lookup"><span data-stu-id="052fd-130">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="052fd-131">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="052fd-131">This command is a single line of text.</span></span>

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="052fd-132">Quitar el net.tcp de la lista de protocolos habilitados</span><span class="sxs-lookup"><span data-stu-id="052fd-132">To remove net.tcp from the list of enabled protocols</span></span>

1. <span data-ttu-id="052fd-133">Para quitar el net.tcp de la lista de protocolos habilitados, ejecute el siguiente comando en una ventana de símbolo del sistema del nivel del administrador:</span><span class="sxs-lookup"><span data-stu-id="052fd-133">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > <span data-ttu-id="052fd-134">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="052fd-134">This command is a single line of text.</span></span>

## <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="052fd-135">Quitar el enlace de sitio de net.tcp</span><span class="sxs-lookup"><span data-stu-id="052fd-135">To remove the net.tcp site binding</span></span>

1. <span data-ttu-id="052fd-136">Para quitar el enlace del sitio net.tcp ejecute el siguiente comando desde una ventana de símbolo del sistema en el nivel de administrador:</span><span class="sxs-lookup"><span data-stu-id="052fd-136">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="052fd-137">Este comando es una sola línea de texto.</span><span class="sxs-lookup"><span data-stu-id="052fd-137">This command is a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="052fd-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="052fd-138">See also</span></span>

- [<span data-ttu-id="052fd-139">Activación TCP</span><span class="sxs-lookup"><span data-stu-id="052fd-139">TCP Activation</span></span>](../samples/tcp-activation.md)
- [<span data-ttu-id="052fd-140">Activación MSMQ</span><span class="sxs-lookup"><span data-stu-id="052fd-140">MSMQ Activation</span></span>](../samples/msmq-activation.md)
- [<span data-ttu-id="052fd-141">Activación NamedPipe</span><span class="sxs-lookup"><span data-stu-id="052fd-141">NamedPipe Activation</span></span>](../samples/namedpipe-activation.md)
- <span data-ttu-id="052fd-142">[Características de hospedaje de Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="052fd-142">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
