---
title: Cuándo no se debe implementar en contenedores de Windows
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Cuándo no se debe implementar en contenedores de Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 75db31a8f4599e9681c2c4156d93db5416d2ca96
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200745"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="dec36-103">Cuándo no se debe implementar en contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="dec36-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="dec36-104">Algunas tecnologías de Windows no se admiten los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="dec36-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="dec36-105">En esos casos, deberá migrar a máquinas virtuales de los estándares, normalmente con solo Windows e IIS.</span><span class="sxs-lookup"><span data-stu-id="dec36-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="dec36-106">Casos que no se admite en los contenedores de Windows, a partir de mayo de 2018:</span><span class="sxs-lookup"><span data-stu-id="dec36-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="dec36-107">Actualmente solo está disponible en los contenedores de Windows basada en Windows Server v1803 versión, pero no en cualquier otra versión anterior Microsoft Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="dec36-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="dec36-108">Foro de la solicitud de UserVoice</span><span class="sxs-lookup"><span data-stu-id="dec36-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="dec36-109">Foro de discusión</span><span class="sxs-lookup"><span data-stu-id="dec36-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="dec36-110">Coordinador de transacciones distribuidas de Microsoft (MSDTC) actualmente no se admite en los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="dec36-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="dec36-111">Problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="dec36-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="dec36-112">Microsoft Office no admite actualmente los contenedores.</span><span class="sxs-lookup"><span data-stu-id="dec36-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="dec36-113">Foro de la solicitud de UserVoice</span><span class="sxs-lookup"><span data-stu-id="dec36-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="dec36-114">Las aplicaciones de interfaz de usuario (aplicaciones de cliente con una interfaz de usuario visual) no son escenarios admitidos.</span><span class="sxs-lookup"><span data-stu-id="dec36-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="dec36-115">Roles de infraestructura de Windows (DNS, DHCP, DC, NTP, impresión, servidor de archivos, etc. IAM) no son escenarios admitidos.</span><span class="sxs-lookup"><span data-stu-id="dec36-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="dec36-116">Para otros escenarios no admitidos y las solicitudes de la Comunidad, vea el foro de UserVoice para contenedores de Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="dec36-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="dec36-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dec36-117">Additional resources</span></span>

-   **<span data-ttu-id="dec36-118">Las máquinas virtuales y contenedores en Azure</span><span class="sxs-lookup"><span data-stu-id="dec36-118">Virtual machines and containers in Azure</span></span>**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
><span data-ttu-id="dec36-119">[Anterior](deploy-existing-net-apps-as-windows-containers.md)
>[Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="dec36-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>