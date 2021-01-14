---
title: Cuándo no se debe implementar en contenedores de Windows
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Cuándo no se debe implementar en contenedores Windows
ms.date: 12/21/2020
ms.openlocfilehash: 4eea24ab8deb3719c778b45b3ddc1309277a3f50
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025178"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Cuándo no se debe implementar en contenedores de Windows

Algunas tecnologías de Windows no son compatibles con los contenedores Windows. En esos casos, debe migrar a las máquinas virtuales estándar, normalmente solo con Windows e IIS.

No se admiten casos en contenedores Windows desde mayo de 2018:

- Microsoft Message Queuing (MSMQ) actualmente solo está disponible en contenedores Windows basados en Windows Server versión v1803, pero no en otras versiones anteriores.

  - [Foro de solicitudes de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Foro de debate](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- El Coordinador de transacciones distribuidas de Microsoft (MSDTC) no se admite actualmente en contenedores Windows.

  - [Problema de GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Actualmente, Microsoft Office no admite contenedores.

  - [Foro de solicitudes de UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- No se admiten escenarios de aplicaciones con interfaz de usuario (aplicaciones cliente con una interfaz de usuario visual).

- No se admiten los roles de infraestructura de Windows (DNS, DHCP, DC, NTP, impresión, servidor de archivos, IAM, etc.).

Para ver otras solicitudes y escenarios no admitidos de la comunidad, consulte el foro de UserVoice para contenedores de Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Recursos adicionales

- **Máquinas virtuales y contenedores de Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Anterior](deploy-existing-net-apps-as-windows-containers.md)
> [Siguiente](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
