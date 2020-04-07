---
title: Autenticación y autorización en aplicaciones nativas de la nube
description: Arquitectura de aplicaciones nativas de .NET en la nube para Azure Autenticación y autorización en aplicaciones nativas en la nube
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805542"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>Autenticación y autorización en aplicaciones nativas en la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

*La autenticación* es el proceso de determinar la identidad de una entidad de seguridad. *La autorización* es el acto de conceder un permiso de entidad de seguridad autenticado para realizar una acción o tener acceso a un recurso. A veces, la `AuthN` autenticación se acorta `AuthZ`y la autorización se acorta a . Las aplicaciones nativas de la nube deben depender de protocolos abiertos basados en HTTP para autenticar entidades de seguridad, ya que tanto los clientes como las aplicaciones podrían ejecutarse en cualquier parte del mundo en cualquier plataforma o dispositivo. El único factor común es HTTP.

Muchas organizaciones todavía dependen de servicios de autenticación local como Servicios de federación de Active Directory (ADFS). Aunque este enfoque tradicionalmente ha servido bien a las organizaciones para las necesidades de autenticación en las instalaciones, las aplicaciones nativas de la nube se benefician de sistemas diseñados específicamente para la nube. Un reciente aviso del Centro Nacional de Ciberseguridad del Reino Unido (NCSC) de 2019 afirma que "las organizaciones que usan Azure AD como su fuente de autenticación principal en realidad reducirán su riesgo en comparación con ADFS". Algunas razones descritas en [este análisis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) incluyen:

- Acceso al conjunto completo de tecnologías de protección de credenciales de Microsoft.
- La mayoría de las organizaciones ya confían en Azure AD hasta cierto punto.
- El hash doble de hashes NTLM garantiza que el compromiso no permita las credenciales que funcionan en Active Directory local.

## <a name="references"></a>Referencias

- [Conceptos básicos sobre autenticación](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [Acceder a tokens y reclamaciones](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [Puede ser el momento de abandonar sus servicios de autenticación en las instalaciones](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[Anterior](identity.md)
>[Siguiente](azure-active-directory.md)
