---
title: Instalar Message Queuing (MSMQ)
description: Obtenga información acerca de cómo instalar Message Queue Server 4,0 y Message Queue Server 3,0 para usarlos con los ejemplos de WFC como parte de un procedimiento de instalación único.
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: bf33a5cd899bf2d7ef4947c51ac1723c8eb80c29
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281877"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="7c932-103">Instalar Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="7c932-103">Installing Message Queuing (MSMQ)</span></span>

<span data-ttu-id="7c932-104">Los procedimientos siguientes muestran cómo instalar Message Queuing 4.0 y Message Queuing 3.0.</span><span class="sxs-lookup"><span data-stu-id="7c932-104">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c932-105">Message Queue Server 4,0 no está disponible en Windows XP y Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="7c932-105">Message Queuing 4.0 is not available in Windows XP and Windows Server 2003.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="7c932-106">Para instalar Message Queuing 4.0 en Windows Server 2008 o Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7c932-106">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="7c932-107">En Administrador del servidor, haga clic en **características**.</span><span class="sxs-lookup"><span data-stu-id="7c932-107">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="7c932-108">En el panel derecho, en **Resumen de características**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="7c932-108">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="7c932-109">En la ventana resultante, expanda **Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="7c932-109">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="7c932-110">Expanda **servicios de Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="7c932-110">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="7c932-111">Haga clic en **integración de servicios de directorio** (para equipos Unidos a un dominio) y, a continuación, haga clic en **compatibilidad con http**.</span><span class="sxs-lookup"><span data-stu-id="7c932-111">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="7c932-112">Haga clic en **siguiente** y, a continuación, en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="7c932-112">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="7c932-113">Para instalar Message Queuing 4.0 en Windows 7 o Windows Vista</span><span class="sxs-lookup"><span data-stu-id="7c932-113">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="7c932-114">Abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="7c932-114">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="7c932-115">Haga clic en **programas** y, a continuación, en **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="7c932-115">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="7c932-116">Expanda Microsoft Message Queuing (MSMQ), expanda Núcleo de Microsoft Message Queuing (MSMQ) y, a continuación, active las casillas para que se instalen las siguientes características de Message Queuing:</span><span class="sxs-lookup"><span data-stu-id="7c932-116">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="7c932-117">Integración de Servicios de dominio de Active Directory MSMQ (para los equipos unidos a un dominio).</span><span class="sxs-lookup"><span data-stu-id="7c932-117">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="7c932-118">Compatibilidad con MSMQ HTTP.</span><span class="sxs-lookup"><span data-stu-id="7c932-118">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="7c932-119">Haga clic en **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c932-119">Click **OK**.</span></span>  
  
5. <span data-ttu-id="7c932-120">Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="7c932-120">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="7c932-121">Para instalar Message Queuing 3.0 en Windows XP y Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="7c932-121">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="7c932-122">Abra el **Panel de control**.</span><span class="sxs-lookup"><span data-stu-id="7c932-122">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="7c932-123">Haga clic en **Agregar o quitar programas** y, a continuación, haga clic en **agregar componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="7c932-123">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="7c932-124">Seleccione Message Queue Server y haga clic en **detalles**.</span><span class="sxs-lookup"><span data-stu-id="7c932-124">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7c932-125">Si está ejecutando Windows Server 2003, seleccione servidor de aplicaciones para tener acceso a Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="7c932-125">If you are running Windows Server 2003, select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="7c932-126">Asegúrese de que la opción de compatibilidad HTTP con MSMQ está seleccionada en la página de detalles.</span><span class="sxs-lookup"><span data-stu-id="7c932-126">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="7c932-127">Haga clic en **Aceptar** para salir de la página de detalles y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7c932-127">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="7c932-128">Finalice la instalación.</span><span class="sxs-lookup"><span data-stu-id="7c932-128">Complete the installation.</span></span>  
  
6. <span data-ttu-id="7c932-129">Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="7c932-129">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c932-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c932-130">See also</span></span>

- [<span data-ttu-id="7c932-131">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="7c932-131">Set-Up Instructions</span></span>](set-up-instructions.md)
