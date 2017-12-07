---
title: "Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8"
description: Aprenda a instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8.
author: rlander
ms.author: mairaw
ms.date: 11/27/2017
ms.topic: article
ms.prod: .net-framework
ms.openlocfilehash: 51c412733b76777a78c4a739ce9b077acc86f069
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="1ba2b-103">Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8</span><span class="sxs-lookup"><span data-stu-id="1ba2b-103">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="1ba2b-104">Para ejecutar una aplicación en Windows 10, Windows 8.1 y Windows 8, es posible que necesite .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-104">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="1ba2b-105">También puede usar estas instrucciones para versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-105">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="1ba2b-106">Instalar .NET Framework 3.5 a petición</span><span class="sxs-lookup"><span data-stu-id="1ba2b-106">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="1ba2b-107">Si intenta ejecutar una aplicación que requiere .NET Framework 3.5, es posible que vea el siguiente cuadro de diálogo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-107">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="1ba2b-108">Elija **Instalar esta característica** para habilitar .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-108">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="1ba2b-109">Esta opción requiere una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-109">This option requires an Internet connection.</span></span>

![Cuadro de diálogo de instalación de .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="1ba2b-111">Habilitar .NET Framework 3.5 en el Panel de control</span><span class="sxs-lookup"><span data-stu-id="1ba2b-111">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="1ba2b-112">Puede habilitar .NET Framework 3.5 mediante el Panel de control de Windows.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-112">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="1ba2b-113">Esta opción requiere una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-113">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="1ba2b-114">Presione la tecla Windows ![logotipo de Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) del teclado, escriba "Características de Windows" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-114">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="1ba2b-115">Aparecerá el cuadro de diálogo **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-115">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="1ba2b-116">Active la casilla **.NET Framework 3.5 (incluye .NET 2.0 y 3.0)**, seleccione **Aceptar** y reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-116">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Instalación de .NET con el Panel de control](./media/dotnet-control-panel.png)

   <span data-ttu-id="1ba2b-118">No necesita seleccionar los elementos secundarios para la **activación HTTP de Windows Communication Foundation (WCF)** y la **activación no HTTP de Windows Communication Foundation (WCF)**, a menos que sea un desarrollador o administrador de servidores que requiera esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-118">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a><span data-ttu-id="1ba2b-119">Solución de problemas de instalación de .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="1ba2b-119">Troubleshoot the installation of the .NET Framework 3.5</span></span>

<span data-ttu-id="1ba2b-120">Durante la instalación es posible que encuentre el error 0x800f0906, 0x800f0907, 0x800f081f, o 0x800F0922. En ese caso, consulte [Error de instalación de .NET Framework 3.5: 0x800F0906, 0x800F081F, 0x800F0907](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) para ver cómo solucionar estos problemas.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-120">During installation, you may encounter error 0x800f0906, 0x800f0907, 0x800f081f, or 0x800F0922, in which case refer to [.NET Framework 3.5 installation error: 0x800f0906, 0x800f0907, or 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09) to see how to resolve these issues.</span></span>

<span data-ttu-id="1ba2b-121">Si alguno de los métodos tratados en el artículo anterior no da resultados, o si no tiene conexión a Internet, es necesario usar el medio de instalación de Windows.</span><span class="sxs-lookup"><span data-stu-id="1ba2b-121">If any of the methods discussed in the previous article fail or if you don't have an Internet connection, it's necessary to use your Windows installation media.</span></span> <span data-ttu-id="1ba2b-122">Para obtener más información, consulte [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](https://technet.microsoft.com/library/Dn482069.aspx) (Implementación de .NET Framework 3.5 mediante Administración y mantenimiento de imágenes de implementación).</span><span class="sxs-lookup"><span data-stu-id="1ba2b-122">For more information, see [Deploy .NET Framework 3.5 by using Deployment Image Servicing and Management (DISM)](https://technet.microsoft.com/library/Dn482069.aspx).</span></span> <span data-ttu-id="1ba2b-123">Si no tiene los medios para realizar la instalación, vea [Crear medios de instalación de Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span><span class="sxs-lookup"><span data-stu-id="1ba2b-123">If you don't have the installation media, see [Create installation media for Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).</span></span>