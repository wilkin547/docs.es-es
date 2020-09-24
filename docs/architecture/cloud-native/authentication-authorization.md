---
title: Autenticación y autorización en aplicaciones nativas de la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Autenticación y autorización en aplicaciones nativas en la nube
ms.date: 05/13/2020
ms.openlocfilehash: bbd2df110dd7a7dc7363e9c07d87f1fa12f4e464
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161144"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>Autenticación y autorización en aplicaciones nativas en la nube

La *autenticación* es el proceso de determinar la identidad de una entidad de seguridad. La *autorización* es el acto de conceder un permiso de entidad de seguridad autenticada para realizar una acción o tener acceso a un recurso. A veces se acorta la autenticación `AuthN` y se acorta la autorización a `AuthZ` . Las aplicaciones nativas de la nube deben basarse en protocolos abiertos basados en HTTP para autenticar las entidades de seguridad, ya que tanto los clientes como las aplicaciones podrían ejecutarse en cualquier parte del mundo en cualquier plataforma o dispositivo. El único factor común es HTTP.

Muchas organizaciones todavía dependen de servicios de autenticación locales como Servicios de federación de Active Directory (AD FS) (ADFS). Aunque este enfoque ha servido tradicionalmente a las organizaciones para satisfacer las necesidades de autenticación locales, las aplicaciones nativas de la nube se benefician de los sistemas diseñados específicamente para la nube. Una reciente consulta de 2019 Reino Unido National Cyber Security Centre (NCSC) indica que "las organizaciones que usan Azure AD como su origen de autenticación principal reducirán realmente su riesgo en comparación con ADFS". Algunas de las razones que se describen en [este análisis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) incluyen:

- Acceso al conjunto completo de tecnologías de protección de credenciales de Microsoft.
- La mayoría de las organizaciones ya están confiando en Azure AD hasta cierto punto.
- El doble hash de hashes de NTLM garantiza que el riesgo no permitirá credenciales que funcionen en Active Directory local.

## <a name="references"></a>Referencias

- [Conceptos básicos sobre autenticación](/azure/active-directory/develop/authentication-scenarios)
- [Tokens de acceso y notificaciones](/azure/active-directory/develop/access-tokens)
- [Puede ser hora de deshacerse de los servicios de autenticación locales](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[Anterior](identity.md)
>[Siguiente](azure-active-directory.md)
