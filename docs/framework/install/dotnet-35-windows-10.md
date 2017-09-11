---
title: "Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8"
description: Aprenda a instalar .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8.
author: rlander
ms.author: mairaw
keywords: .NET Framework, Instalar
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.translationtype: HT
ms.sourcegitcommit: 21c6a1485f3d0c38bde065d6ecc7b07d5e424c1d
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.contentlocale: es-es
ms.lasthandoff: 08/05/2017

---

# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a><span data-ttu-id="67aff-104">Instalación de .NET Framework 3.5 en Windows 10, Windows 8.1 y Windows 8</span><span class="sxs-lookup"><span data-stu-id="67aff-104">Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8</span></span>

<span data-ttu-id="67aff-105">Para ejecutar una aplicación en Windows 10, Windows 8.1 y Windows 8, es posible que necesite .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="67aff-105">You may need the .NET Framework 3.5 to run an app on Windows 10, Windows 8.1, and Windows 8.</span></span> <span data-ttu-id="67aff-106">También puede usar estas instrucciones para versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="67aff-106">You can also use these instructions for earlier Windows versions.</span></span>

## <a name="install-the-net-framework-35-on-demand"></a><span data-ttu-id="67aff-107">Instalar .NET Framework 3.5 a petición</span><span class="sxs-lookup"><span data-stu-id="67aff-107">Install the .NET Framework 3.5 on Demand</span></span>

<span data-ttu-id="67aff-108">Si intenta ejecutar una aplicación que requiere .NET Framework 3.5, es posible que vea el siguiente cuadro de diálogo de configuración.</span><span class="sxs-lookup"><span data-stu-id="67aff-108">You may see the following configuration dialog if you try to run an app that requires the .NET Framework 3.5.</span></span> <span data-ttu-id="67aff-109">Elija **Instalar esta característica** para habilitar .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="67aff-109">Choose **Install this feature** to enable the .NET Framework 3.5.</span></span> <span data-ttu-id="67aff-110">Esta opción requiere una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="67aff-110">This option requires an Internet connection.</span></span>

![Cuadro de diálogo de instalación de .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a><span data-ttu-id="67aff-112">Habilitar .NET Framework 3.5 en el Panel de control</span><span class="sxs-lookup"><span data-stu-id="67aff-112">Enable the .NET Framework 3.5 in Control Panel</span></span>

<span data-ttu-id="67aff-113">Puede habilitar .NET Framework 3.5 mediante el Panel de control de Windows.</span><span class="sxs-lookup"><span data-stu-id="67aff-113">You can enable the .NET Framework 3.5 through the Windows Control Panel.</span></span> <span data-ttu-id="67aff-114">Esta opción requiere una conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="67aff-114">This option requires an Internet connection.</span></span>

1. <span data-ttu-id="67aff-115">Presione la tecla Windows ![logotipo de Windows](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) del teclado, escriba "Características de Windows" y presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="67aff-115">Press the Windows key Windows ![Windows logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) on your keyboard, type "Windows Features", and press Enter.</span></span> <span data-ttu-id="67aff-116">Aparecerá el cuadro de diálogo **Activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="67aff-116">The **Turn Windows features on or off** dialog box appears.</span></span>

2. <span data-ttu-id="67aff-117">Active la casilla **.NET Framework 3.5 (incluye .NET 2.0 y 3.0)**, seleccione **Aceptar** y reinicie el equipo si se le solicita.</span><span class="sxs-lookup"><span data-stu-id="67aff-117">Select the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box, select **OK**, and reboot your computer if prompted.</span></span>

   ![Instalación de .NET con el Panel de control](./media/dotnet-control-panel.png)

   <span data-ttu-id="67aff-119">No necesita seleccionar los elementos secundarios para la **activación HTTP de Windows Communication Foundation (WCF)** y la **activación no HTTP de Windows Communication Foundation (WCF)**, a menos que sea un desarrollador o administrador de servidores que requiera esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="67aff-119">You don't need to select the child items for **Windows Communication Foundation (WCF) HTTP Activation** and **Windows Communication Foundation (WCF) Non-HTTP Activation** unless you're a developer or server administrator who requires this functionality.</span></span>

