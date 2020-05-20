---
title: Identidad
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Identidad
ms.date: 05/13/2020
ms.openlocfilehash: 9fa48977e58e2ca5a5f3e231372a4791640a85fd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614024"
---
# <a name="identity"></a>Identidad

La mayoría de las aplicaciones de software deben tener algún conocimiento del usuario o proceso que las llama. El usuario o proceso que interactúa con una aplicación se conoce como una entidad de seguridad, y el proceso de autenticación y autorización de estas entidades de seguridad se conoce como administración de identidades, o simplemente *identidad*. Las aplicaciones sencillas pueden incluir toda la administración de identidades dentro de la aplicación, pero este enfoque no se escala bien con muchas aplicaciones y muchos tipos de entidades de seguridad. Windows admite el uso de Active Directory para proporcionar autenticación y autorización centralizadas.

<!-- (insert figure showing Windows AD auth model) -->

Aunque esta solución es efectiva en las redes corporativas, no está diseñada para que la usen los usuarios o las aplicaciones que se encuentran fuera del dominio de AD. Con el crecimiento de las aplicaciones basadas en Internet y el aumento de las aplicaciones nativas en la nube, los modelos de seguridad han evolucionado.

En el modelo de identidad nativa de la nube de hoy en día, se supone que la arquitectura está distribuida. Las aplicaciones se pueden implementar en cualquier lugar y pueden comunicarse con otras aplicaciones en cualquier lugar. Los clientes pueden comunicarse con estas aplicaciones desde cualquier lugar y, de hecho, los clientes pueden constar de cualquier combinación de plataformas y dispositivos. Las soluciones de identidad nativas de la nube aprovechan los estándares abiertos para lograr un acceso seguro a las aplicaciones desde los clientes. Estos clientes van desde usuarios humanos en equipos o teléfonos hasta otras aplicaciones hospedadas en línea, hasta decodificadores y dispositivos IOT que ejecutan cualquier plataforma de software en cualquier parte del mundo.

Las soluciones de identidad nativas en la nube modernas suelen aprovechar los tokens de acceso emitidos por un servidor o servicio de token seguro (STS) a una entidad de seguridad una vez que se determina su identidad. El token de acceso, normalmente un JSON Web Token (JWT), incluye *notificaciones* sobre la entidad de seguridad. Estas notificaciones incluirán mínimamente la identidad del usuario, pero también pueden incluir notificaciones adicionales que las aplicaciones pueden usar para determinar el nivel de acceso que se va a conceder a la entidad de seguridad.

<!-- (insert figure showing basic handshake involving a principal, an STS, and an app) -->

Normalmente, el STS solo es responsable de autenticar la entidad de seguridad. La determinación del nivel de acceso a los recursos se deja en otras partes de la aplicación.

## <a name="references"></a>Referencias

- [Plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[Anterior](azure-monitor.md)
>[Siguiente](authentication-authorization.md)
