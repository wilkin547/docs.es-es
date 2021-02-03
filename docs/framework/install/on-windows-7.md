---
title: Instalación de .NET Framework en Windows 7 SP1
description: Aprenda a instalar .NET Framework en Windows 7 SP1.
ms.date: 04/18/2019
ms.openlocfilehash: 900b38110626a93f37829045a8676ea87101d7e9
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899092"
---
# <a name="install-the-net-framework-on-windows-7-sp1-and-windows-server-2008-r2"></a><span data-ttu-id="97f18-103">Instalación de .NET Framework en Windows 7 SP1 y Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="97f18-103">Install the .NET Framework on Windows 7 SP1 and Windows Server 2008 R2</span></span>

<span data-ttu-id="97f18-104">.NET Framework se requiere para ejecutar muchas aplicaciones en Windows.</span><span class="sxs-lookup"><span data-stu-id="97f18-104">The .NET Framework is required to run many applications on Windows.</span></span> <span data-ttu-id="97f18-105">Puede usar las instrucciones siguientes para instalarlo.</span><span class="sxs-lookup"><span data-stu-id="97f18-105">You can use the following instructions to install it.</span></span> <span data-ttu-id="97f18-106">Es posible que haya llegado a esta página tras haber intentado ejecutar una aplicación y ver el cuadro de diálogo siguiente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="97f18-106">You may have arrived on this page after trying to run an application and seeing the following dialog on your machine.</span></span>

![No se pudo iniciar esta aplicación.](./media/this-application-could-not-be-started.png)

<span data-ttu-id="97f18-108">Estas instrucciones ayudan a instalar las versiones necesarias de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="97f18-108">These instructions will help you install the .NET Framework versions you need.</span></span> <span data-ttu-id="97f18-109">[.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) es la última versión.</span><span class="sxs-lookup"><span data-stu-id="97f18-109">The [.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) is the latest version.</span></span> <span data-ttu-id="97f18-110">Es compatible con Windows 7 SP1 y Windows Server 2008 R2, y está incluida en la [Actualización de mayo de 2019 de Windows 10](https://support.microsoft.com/help/4028685/windows-10-get-the-update).</span><span class="sxs-lookup"><span data-stu-id="97f18-110">It is supported on Windows 7 SP1 and Windows Server 2008 R2 and is included with [Windows 10 May 2019 Update](https://support.microsoft.com/help/4028685/windows-10-get-the-update).</span></span>

## <a name="net-framework-48"></a><span data-ttu-id="97f18-111">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="97f18-111">.NET Framework 4.8</span></span>

> [!div class="button"]
> [<span data-ttu-id="97f18-112">Descarga de .NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="97f18-112">Download .NET Framework 4.8</span></span>](https://dotnet.microsoft.com/download/dotnet-framework/net48)

<span data-ttu-id="97f18-113">[.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) se puede usar para ejecutar aplicaciones creadas para .NET Framework 4.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="97f18-113">The [.NET Framework 4.8](https://github.com/Microsoft/dotnet/tree/master/releases/net48) can be used to run applications built for .NET Framework 4.0 or later.</span></span>

### <a name="offline-installer"></a><span data-ttu-id="97f18-114">instalador sin conexión</span><span class="sxs-lookup"><span data-stu-id="97f18-114">Offline installer</span></span>

<span data-ttu-id="97f18-115">Al realizar una instalación sin conexión para .NET Framework en Windows 7, primero deberá asegurarse de que se ha instalado en la máquina de destino la versión más reciente de [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm).</span><span class="sxs-lookup"><span data-stu-id="97f18-115">When doing an offline install for .NET Framework on Windows 7, you'll first need to make sure that the latest [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm) has been installed on the target machine.</span></span>

<span data-ttu-id="97f18-116">La herramienta _certmgr.exe_ puede automatizar la instalación de un certificado y se obtiene de Visual Studio o Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="97f18-116">The _certmgr.exe_ tool can automate installing a certificate and is obtained from Visual Studio or the Windows SDK.</span></span> <span data-ttu-id="97f18-117">El siguiente comando se usa para instalar el certificado antes de ejecutar el instalador de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="97f18-117">The following command is used to install the certificate before running the .NET Framework installer:</span></span>

```console
certmgr.exe /add MicRooCerAut2011_2011_03_22.crt /s /r localMachine root
```

## <a name="net-framework-35"></a><span data-ttu-id="97f18-118">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="97f18-118">.NET Framework 3.5</span></span>

<span data-ttu-id="97f18-119">[.NET Framework 3.5](https://dotnet.microsoft.com/download/dotnet-framework/net35-sp1) está incluido en Windows 7.</span><span class="sxs-lookup"><span data-stu-id="97f18-119">The [.NET Framework 3.5](https://dotnet.microsoft.com/download/dotnet-framework/net35-sp1) is included with Windows 7.</span></span>

<span data-ttu-id="97f18-120">.NET Framework 3.5 es compatible con aplicaciones desarrolladas para .NET Framework de 1.0 a 3.5.</span><span class="sxs-lookup"><span data-stu-id="97f18-120">The .NET Framework 3.5 supports apps built for .NET Framework 1.0 through 3.5.</span></span>

## <a name="help"></a><span data-ttu-id="97f18-121">Ayuda</span><span class="sxs-lookup"><span data-stu-id="97f18-121">Help</span></span>

<span data-ttu-id="97f18-122">Si no puede instalar la versión correcta de .NET Framework, puede [ponerse en contacto con Microsoft para obtener ayuda](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help).</span><span class="sxs-lookup"><span data-stu-id="97f18-122">You can [contact Microsoft for help](mailto:dotnet-install-help@service.microsoft.com?subject=Install-Help) if you cannot get the correct version of the .NET Framework installed.</span></span>

## <a name="see-also"></a><span data-ttu-id="97f18-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="97f18-123">See also</span></span>

- [<span data-ttu-id="97f18-124">Descarga de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="97f18-124">Download the .NET Framework</span></span>](https://dotnet.microsoft.com/download)
- [<span data-ttu-id="97f18-125">Solución de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="97f18-125">Troubleshoot blocked .NET Framework installations and uninstallations</span></span>](troubleshoot-blocked-installations-and-uninstallations.md)
- [<span data-ttu-id="97f18-126">Instalación de .NET Framework para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="97f18-126">Install the .NET Framework for developers</span></span>](guide-for-developers.md)
