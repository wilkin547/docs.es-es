---
title: Cuándo no se debe implementar en contenedores de Windows
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Cuándo no se debe implementar en contenedores de Windows
ms.date: 04/28/2018
ms.openlocfilehash: 65e793b846b495e9a1be6db9ddfa38bbf0d49445
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638896"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Cuándo no se debe implementar en contenedores de Windows

Algunas tecnologías de Windows no se admiten los contenedores de Windows. En esos casos, deberá migrar a máquinas virtuales de los estándares, normalmente con solo Windows e IIS.

Casos que no se admite en los contenedores de Windows, a partir de mayo de 2018:

- Actualmente solo está disponible en los contenedores de Windows basada en Windows Server v1803 versión, pero no en cualquier otra versión anterior Microsoft Message Queuing (MSMQ).

  - [Foro de la solicitud de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Foro de discusión](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Coordinador de transacciones distribuidas de Microsoft (MSDTC) actualmente no se admite en los contenedores de Windows.

  - [Problema de GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office no admite actualmente los contenedores.

  - [Foro de la solicitud de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- Las aplicaciones de interfaz de usuario (aplicaciones de cliente con una interfaz de usuario visual) no son escenarios admitidos.

- Roles de infraestructura de Windows (DNS, DHCP, DC, NTP, impresión, servidor de archivos, etc. IAM) no son escenarios admitidos.

Para otros escenarios no admitidos y las solicitudes de la Comunidad, vea el foro de UserVoice para contenedores de Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Recursos adicionales

- **Las máquinas virtuales y contenedores en Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Anterior](deploy-existing-net-apps-as-windows-containers.md)
> [Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
