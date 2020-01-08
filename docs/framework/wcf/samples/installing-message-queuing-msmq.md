---
title: Instalar Message Queuing (MSMQ)
ms.date: 03/30/2017
ms.assetid: 7ddcd497-3e04-427e-bc04-3610ad98b01e
ms.openlocfilehash: e6d6a3a2e1bc0a0c936e4b8594eab836b559e5a7
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344745"
---
# <a name="installing-message-queuing-msmq"></a><span data-ttu-id="549a1-102">Instalar Message Queuing (MSMQ)</span><span class="sxs-lookup"><span data-stu-id="549a1-102">Installing Message Queuing (MSMQ)</span></span>
<span data-ttu-id="549a1-103">Los procedimientos siguientes muestran cómo instalar Message Queuing 4.0 y Message Queuing 3.0.</span><span class="sxs-lookup"><span data-stu-id="549a1-103">The following procedures show how to install Message Queuing 4.0 and Message Queuing 3.0.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="549a1-104">Message Queue Server 4,0 no está disponible en [!INCLUDE[wxp](../../../../includes/wxp-md.md)] y Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="549a1-104">Message Queuing 4.0 is not available in [!INCLUDE[wxp](../../../../includes/wxp-md.md)] and Windows Server 2003.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-server-2008-or-windows-server-2008-r2"></a><span data-ttu-id="549a1-105">Para instalar Message Queuing 4.0 en Windows Server 2008 o Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="549a1-105">To install Message Queuing 4.0 on Windows Server 2008 or Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="549a1-106">En Administrador del servidor, haga clic en **características**.</span><span class="sxs-lookup"><span data-stu-id="549a1-106">In Server Manager, click **Features**.</span></span>  
  
2. <span data-ttu-id="549a1-107">En el panel derecho, en **Resumen de características**, haga clic en **Agregar características**.</span><span class="sxs-lookup"><span data-stu-id="549a1-107">In the right-hand pane under **Features Summary**, click **Add Features**.</span></span>  
  
3. <span data-ttu-id="549a1-108">En la ventana resultante, expanda **Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="549a1-108">In the resulting window, expand **Message Queuing**.</span></span>  
  
4. <span data-ttu-id="549a1-109">Expanda **servicios de Message Queue Server**.</span><span class="sxs-lookup"><span data-stu-id="549a1-109">Expand **Message Queuing Services**.</span></span>  
  
5. <span data-ttu-id="549a1-110">Haga clic en **integración de servicios de directorio** (para equipos Unidos a un dominio) y, a continuación, haga clic en **compatibilidad con http**.</span><span class="sxs-lookup"><span data-stu-id="549a1-110">Click **Directory Services Integration** (for computers joined to a Domain), then click **HTTP Support**.</span></span>  
  
6. <span data-ttu-id="549a1-111">Haga clic en **siguiente**y, a continuación, en **instalar**.</span><span class="sxs-lookup"><span data-stu-id="549a1-111">Click **Next**,then click **Install**.</span></span>  
  
#### <a name="to-install-message-queuing-40-on-windows-7-or-windows-vista"></a><span data-ttu-id="549a1-112">Para instalar Message Queuing 4.0 en Windows 7 o Windows Vista</span><span class="sxs-lookup"><span data-stu-id="549a1-112">To install Message Queuing 4.0 on Windows 7 or Windows Vista</span></span>  
  
1. <span data-ttu-id="549a1-113">Abra el **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="549a1-113">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="549a1-114">Haga clic en **programas** y, a continuación, en **programas y características**, haga clic en **activar o desactivar las características de Windows**.</span><span class="sxs-lookup"><span data-stu-id="549a1-114">Click **Programs** and then, under **Programs and Features**, click **Turn Windows Features on and off**.</span></span>  
  
3. <span data-ttu-id="549a1-115">Expanda Microsoft Message Queue (MSMQ) Server, expanda Núcleo de Microsoft Message Queuing (MSMQ) y, a continuación, active las casillas para que se instalen las siguientes características de Message Queuing:</span><span class="sxs-lookup"><span data-stu-id="549a1-115">Expand Microsoft Message Queue (MSMQ) Server, expand Microsoft Message Queue (MSMQ) Server Core, and then select the check boxes for the following Message Queuing features to install:</span></span>  
  
    - <span data-ttu-id="549a1-116">Integración de Servicios de dominio de Active Directory MSMQ (para los equipos unidos a un dominio).</span><span class="sxs-lookup"><span data-stu-id="549a1-116">MSMQ Active Directory Domain Services Integration (for computers joined to a Domain).</span></span>  
  
    - <span data-ttu-id="549a1-117">Compatibilidad con MSMQ HTTP.</span><span class="sxs-lookup"><span data-stu-id="549a1-117">MSMQ HTTP Support.</span></span>  
  
4. <span data-ttu-id="549a1-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="549a1-118">Click **OK**.</span></span>  
  
5. <span data-ttu-id="549a1-119">Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="549a1-119">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
#### <a name="to-install-message-queuing-30-on-windows-xp-and-windows-server-2003"></a><span data-ttu-id="549a1-120">Para instalar Message Queuing 3.0 en Windows XP y Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="549a1-120">To install Message Queuing 3.0 on Windows XP and Windows Server 2003</span></span>  
  
1. <span data-ttu-id="549a1-121">Abra el **Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="549a1-121">Open **Control Panel**.</span></span>  
  
2. <span data-ttu-id="549a1-122">Haga clic en **Agregar o quitar programas** y, a continuación, haga clic en **agregar componentes de Windows**.</span><span class="sxs-lookup"><span data-stu-id="549a1-122">Click **Add Remove Programs** and then click **Add Windows Components**.</span></span>  
  
3. <span data-ttu-id="549a1-123">Seleccione Message Queue Server y haga clic en **detalles**.</span><span class="sxs-lookup"><span data-stu-id="549a1-123">Select Message Queuing and click **Details**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="549a1-124">Si está ejecutando Windows Server 2003, seleccione servidor de aplicaciones para tener acceso a Message Queue Server.</span><span class="sxs-lookup"><span data-stu-id="549a1-124">If you are running Windows Server 2003, select Application Server to access Message Queuing.</span></span>  
  
4. <span data-ttu-id="549a1-125">Asegúrese de que la opción de compatibilidad HTTP con MSMQ está seleccionada en la página de detalles.</span><span class="sxs-lookup"><span data-stu-id="549a1-125">Ensure that the option MSMQ HTTP Support is selected on the details page.</span></span>  
  
5. <span data-ttu-id="549a1-126">Haga clic en **Aceptar** para salir de la página de detalles y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="549a1-126">Click **OK** to exit the details page, and then click **Next**.</span></span> <span data-ttu-id="549a1-127">Complete la instalación.</span><span class="sxs-lookup"><span data-stu-id="549a1-127">Complete the installation.</span></span>  
  
6. <span data-ttu-id="549a1-128">Si se le pide que reinicie el equipo, haga clic en **Aceptar** para completar la instalación.</span><span class="sxs-lookup"><span data-stu-id="549a1-128">If you are prompted to restart the computer, click **OK** to complete the installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="549a1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="549a1-129">See also</span></span>

- [<span data-ttu-id="549a1-130">Instrucciones de instalación</span><span class="sxs-lookup"><span data-stu-id="549a1-130">Set-Up Instructions</span></span>](../../../../docs/framework/wcf/samples/set-up-instructions.md)
