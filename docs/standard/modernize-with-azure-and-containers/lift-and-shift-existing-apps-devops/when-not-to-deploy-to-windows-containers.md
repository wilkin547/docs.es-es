---
title: "Cuándo no se debe implementar en los contenedores de Windows"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cuándo no se debe implementar en los contenedores de Windows"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 538cb518cd169f42b3e8b7324ca108a1d366137a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Cuándo no se debe implementar en los contenedores de Windows

Algunas tecnologías de Windows no son compatibles con los contenedores de Windows. En esos casos, deberá migrar a las máquinas virtuales de estándares, normalmente con solo Windows e IIS.

No se admite en los contenedores de Windows, a partir de mediados de 2017 los casos:

-   Microsoft Message Queuing (MSMQ) actualmente no se admite en los contenedores de Windows.

    -   [Foro de solicitud de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

    -   [Foro de discusión](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

-   Coordinador de transacciones distribuidas de Microsoft (MSDTC) actualmente no se admite en los contenedores de Windows

    -   [Problema de GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

-   Microsoft Office no admite actualmente los contenedores

    -   [Foro de solicitud de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

Para las solicitudes de la Comunidad y otros escenarios no admitidos, vea el foro de UserVoice para contenedores de Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Recursos adicionales

-   **Máquinas virtuales y contenedores en Azure**

    [https://docs.Microsoft.com/Azure/Virtual-Machines/Windows/Containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Anterior](deploy-existing-net-apps-as-windows-containers.md)
[Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
