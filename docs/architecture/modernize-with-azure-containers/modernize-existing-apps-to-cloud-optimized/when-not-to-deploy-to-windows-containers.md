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
# <a name="when-not-to-deploy-to-windows-containers"></a>Cuándo no se debe implementar en contenedores de Windows

Algunas tecnologías de Windows no son compatibles con los contenedores de Windows. En esos casos, debe migrar a las máquinas virtuales con estándares, normalmente solo con Windows e IIS.

No se admiten casos en contenedores de Windows, desde el 2018 de mayo:

- Microsoft Message Queuing (MSMQ) solo está disponible actualmente en contenedores de Windows basados en la versión v1803 de Windows Server, pero no en otras versiones anteriores.

  - [Foro de solicitud de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Foro de discusión](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Microsoft Coordinador de transacciones distribuidas (MSDTC) no se admite actualmente en contenedores de Windows.

  - [Problema de GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Actualmente, Microsoft Office no admite contenedores.

  - [Foro de solicitud de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- No se admiten las aplicaciones de interfaz de usuario (aplicaciones cliente con una interfaz de usuario visual).

- No se admiten los roles de infraestructura de Windows (DNS, DHCP, DC, NTP, impresión, servidor de archivos, IAM, etc.).

Para ver escenarios y solicitudes adicionales no admitidos de la comunidad, vea el foro de UserVoice para contenedores <https://windowsserver.uservoice.com/forums/304624-containers>de Windows:.

### <a name="additional-resources"></a>Recursos adicionales

- **Máquinas virtuales y contenedores en Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Anterior](deploy-existing-net-apps-as-windows-containers.md)
> [Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
