---
title: Azure Active Directory
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 207043507a9052c47683383a98cef6417a1a2740
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840734"
---
# <a name="azure-active-directory"></a>Azure Active Directory

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Microsoft Azure Active Directory (Azure AD) ofrece administración de identidades y acceso como servicio. Los clientes la usan para configurar y mantener a los usuarios, la información que debe almacenar sobre ellos, quién puede tener acceso a esa información, quién puede administrarla y qué aplicaciones pueden acceder a ella. AAD puede autenticar a los usuarios para las aplicaciones configuradas para usarlos, lo que proporciona una experiencia de inicio de sesión único (SSO). Puede usarse por sí mismo o estar integrado con Windows AD que se ejecuta en el entorno local.

Azure AD se crea para la nube. Es realmente una solución de identidad nativa en la nube que usa una sintaxis de Graph API y de OData basada en REST para consultas, a diferencia de Windows AD, que usa LDAP. Active Directory locales pueden sincronizar los atributos de usuario con la nube mediante servicios de sincronización de identidades, lo que permite que toda la autenticación tenga lugar en la nube mediante Azure AD. Como alternativa, la autenticación se puede configurar a través de Connect para pasar de nuevo a la Active Directory local a través de ADFS para que Windows AD lo complete de forma local.

Azure AD admite pantallas de inicio de sesión con personalización de marca de empresa, autenticación multifábrica y proxies de aplicación basados en la nube que se usan para proporcionar SSO para aplicaciones hospedadas en el entorno local. Ofrece diferentes tipos de informes de seguridad y capacidades de alerta.

## <a name="references"></a>Referencias

- [Plataforma de Microsoft Identity](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[Anterior](authentication-authorization.md)
>[Siguiente](identity-server.md)
