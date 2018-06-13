---
title: Cuándo no se debe implementar en los contenedores de Windows
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Cuándo no se debe implementar en los contenedores de Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 819f32955ff019414bef8820d17d272eddc11bf8
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957965"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="cddb7-103">Cuándo no se debe implementar en los contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="cddb7-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="cddb7-104">Algunas tecnologías de Windows no son compatibles con los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="cddb7-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="cddb7-105">En esos casos, deberá migrar a las máquinas virtuales de estándares, normalmente con solo Windows e IIS.</span><span class="sxs-lookup"><span data-stu-id="cddb7-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="cddb7-106">No se admite en los contenedores de Windows, a partir de mayo de 2018 los casos:</span><span class="sxs-lookup"><span data-stu-id="cddb7-106">Cases not supported in Windows Containers, as of May 2018:</span></span> 

-   <span data-ttu-id="cddb7-107">Actualmente solo está disponible en los contenedores de Windows basada en Windows Server v1803 versión, pero no en cualquier otra versión anterior Microsoft Message Queuing (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="cddb7-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span> 

    -   [<span data-ttu-id="cddb7-108">Foro de solicitud de UserVoice</span><span class="sxs-lookup"><span data-stu-id="cddb7-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [<span data-ttu-id="cddb7-109">Foro de discusión</span><span class="sxs-lookup"><span data-stu-id="cddb7-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   <span data-ttu-id="cddb7-110">Coordinador de transacciones distribuidas de Microsoft (MSDTC) actualmente no se admite en los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="cddb7-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

    -   [<span data-ttu-id="cddb7-111">Problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="cddb7-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   <span data-ttu-id="cddb7-112">Microsoft Office no admite actualmente los contenedores.</span><span class="sxs-lookup"><span data-stu-id="cddb7-112">Microsoft Office currently does not support containers.</span></span>

    -   [<span data-ttu-id="cddb7-113">Foro de solicitud de UserVoice</span><span class="sxs-lookup"><span data-stu-id="cddb7-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   <span data-ttu-id="cddb7-114">Aplicaciones de interfaz de usuario (aplicaciones de cliente con una interfaz de usuario visual) no están admitidas.</span><span class="sxs-lookup"><span data-stu-id="cddb7-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

-   <span data-ttu-id="cddb7-115">Roles de infraestructura de Windows (DNS, DHCP, DC, NTP, impresión, servidor de archivos, etc. IAM) no están admitidas.</span><span class="sxs-lookup"><span data-stu-id="cddb7-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>


<span data-ttu-id="cddb7-116">Para las solicitudes de la Comunidad y otros escenarios no admitidos, vea el foro de UserVoice para contenedores de Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.</span><span class="sxs-lookup"><span data-stu-id="cddb7-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="cddb7-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cddb7-117">Additional resources</span></span>

-   <span data-ttu-id="cddb7-118">**Máquinas virtuales y contenedores en Azure**</span><span class="sxs-lookup"><span data-stu-id="cddb7-118">**Virtual machines and containers in Azure**</span></span>

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
<span data-ttu-id="cddb7-119">[Anterior](deploy-existing-net-apps-as-windows-containers.md)
[Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="cddb7-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
