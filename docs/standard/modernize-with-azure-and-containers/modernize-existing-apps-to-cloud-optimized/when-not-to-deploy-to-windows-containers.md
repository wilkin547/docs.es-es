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
# <a name="when-not-to-deploy-to-windows-containers"></a>Cuándo no se debe implementar en los contenedores de Windows

Algunas tecnologías de Windows no son compatibles con los contenedores de Windows. En esos casos, deberá migrar a las máquinas virtuales de estándares, normalmente con solo Windows e IIS.

No se admite en los contenedores de Windows, a partir de mayo de 2018 los casos: 

-   Actualmente solo está disponible en los contenedores de Windows basada en Windows Server v1803 versión, pero no en cualquier otra versión anterior Microsoft Message Queuing (MSMQ). 

    -   [Foro de solicitud de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Foro de discusión](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Coordinador de transacciones distribuidas de Microsoft (MSDTC) actualmente no se admite en los contenedores de Windows.

    -   [Problema de GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office no admite actualmente los contenedores.

    -   [Foro de solicitud de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

-   Aplicaciones de interfaz de usuario (aplicaciones de cliente con una interfaz de usuario visual) no están admitidas.

-   Roles de infraestructura de Windows (DNS, DHCP, DC, NTP, impresión, servidor de archivos, etc. IAM) no están admitidas.


Para las solicitudes de la Comunidad y otros escenarios no admitidos, vea el foro de UserVoice para contenedores de Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Recursos adicionales

-   **Máquinas virtuales y contenedores en Azure**

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Anterior](deploy-existing-net-apps-as-windows-containers.md)
[Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
