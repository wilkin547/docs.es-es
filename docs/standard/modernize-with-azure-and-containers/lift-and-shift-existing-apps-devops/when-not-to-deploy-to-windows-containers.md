---
title: Cuándo no se debe implementar en los contenedores de Windows
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cuándo no se debe implementar en los contenedores de Windows
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b8fb31a17d1f9d91fe053596685b7560a7fa1ee1
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
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

    [https://docs.microsoft.com/azure/virtual-machines/windows/containers](https://docs.microsoft.com/azure/virtual-machines/windows/containers)

>[!div class="step-by-step"]
[Anterior](deploy-existing-net-apps-as-windows-containers.md)
[Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
