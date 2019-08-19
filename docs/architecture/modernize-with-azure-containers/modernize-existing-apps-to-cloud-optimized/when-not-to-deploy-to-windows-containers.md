---
title: Cuándo no se debe implementar en contenedores de Windows
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Cuándo no implementar en contenedores de Windows
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577958"
---
# <a name="when-not-to-deploy-to-windows-containers"></a><span data-ttu-id="ba4f8-103">Cuándo no se debe implementar en contenedores de Windows</span><span class="sxs-lookup"><span data-stu-id="ba4f8-103">When not to deploy to Windows Containers</span></span>

<span data-ttu-id="ba4f8-104">Algunas tecnologías de Windows no son compatibles con los contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="ba4f8-104">Some Windows technologies are not supported by Windows Containers.</span></span> <span data-ttu-id="ba4f8-105">En esos casos, debe migrar a las máquinas virtuales con estándares, normalmente solo con Windows e IIS.</span><span class="sxs-lookup"><span data-stu-id="ba4f8-105">In those cases, you still need to migrate to standards VMs, usually with just Windows and IIS.</span></span>

<span data-ttu-id="ba4f8-106">No se admiten casos en contenedores de Windows, desde el 2018 de mayo:</span><span class="sxs-lookup"><span data-stu-id="ba4f8-106">Cases not supported in Windows Containers, as of May 2018:</span></span>

- <span data-ttu-id="ba4f8-107">Microsoft Message Queuing (MSMQ) solo está disponible actualmente en contenedores de Windows basados en la versión v1803 de Windows Server, pero no en otras versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="ba4f8-107">Microsoft Message Queuing (MSMQ) currently is only available in Windows Containers based on Windows Server v1803 release, but not in any other prior releases.</span></span>

  - [<span data-ttu-id="ba4f8-108">Foro de solicitud de UserVoice</span><span class="sxs-lookup"><span data-stu-id="ba4f8-108">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [<span data-ttu-id="ba4f8-109">Foro de discusión</span><span class="sxs-lookup"><span data-stu-id="ba4f8-109">Discussion forum</span></span>](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- <span data-ttu-id="ba4f8-110">Microsoft Coordinador de transacciones distribuidas (MSDTC) no se admite actualmente en contenedores de Windows.</span><span class="sxs-lookup"><span data-stu-id="ba4f8-110">Microsoft Distributed Transaction Coordinator (MSDTC) currently is not supported in Windows Containers.</span></span>

  - [<span data-ttu-id="ba4f8-111">Problema de GitHub</span><span class="sxs-lookup"><span data-stu-id="ba4f8-111">GitHub issue</span></span>](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- <span data-ttu-id="ba4f8-112">Actualmente, Microsoft Office no admite contenedores.</span><span class="sxs-lookup"><span data-stu-id="ba4f8-112">Microsoft Office currently does not support containers.</span></span>

  - [<span data-ttu-id="ba4f8-113">Foro de solicitud de UserVoice</span><span class="sxs-lookup"><span data-stu-id="ba4f8-113">UserVoice request forum</span></span>](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- <span data-ttu-id="ba4f8-114">No se admiten las aplicaciones de interfaz de usuario (aplicaciones cliente con una interfaz de usuario visual).</span><span class="sxs-lookup"><span data-stu-id="ba4f8-114">UI apps (client apps with a visual user interface) are not supported scenarios.</span></span>

- <span data-ttu-id="ba4f8-115">No se admiten los roles de infraestructura de Windows (DNS, DHCP, DC, NTP, impresión, servidor de archivos, IAM, etc.).</span><span class="sxs-lookup"><span data-stu-id="ba4f8-115">Windows infrastructure roles (DNS, DHCP, DC, NTP, PRINT, File server, IAM etc.) are not supported scenarios.</span></span>

<span data-ttu-id="ba4f8-116">Para ver escenarios y solicitudes adicionales no admitidos de la comunidad, vea el foro de UserVoice para contenedores <https://windowsserver.uservoice.com/forums/304624-containers>de Windows:.</span><span class="sxs-lookup"><span data-stu-id="ba4f8-116">For additional not-supported scenarios and requests from the community, see the UserVoice forum for Windows Containers: <https://windowsserver.uservoice.com/forums/304624-containers>.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="ba4f8-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ba4f8-117">Additional resources</span></span>

- <span data-ttu-id="ba4f8-118">**Máquinas virtuales y contenedores en Azure**</span><span class="sxs-lookup"><span data-stu-id="ba4f8-118">**Virtual machines and containers in Azure**</span></span>

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> <span data-ttu-id="ba4f8-119">[Anterior](deploy-existing-net-apps-as-windows-containers.md)
> [Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span><span class="sxs-lookup"><span data-stu-id="ba4f8-119">[Previous](deploy-existing-net-apps-as-windows-containers.md)
[Next](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)</span></span>
