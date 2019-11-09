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
# <a name="azure-active-directory"></a><span data-ttu-id="5459b-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5459b-103">Azure Active Directory</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="5459b-104">Microsoft Azure Active Directory (Azure AD) ofrece administración de identidades y acceso como servicio.</span><span class="sxs-lookup"><span data-stu-id="5459b-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="5459b-105">Los clientes la usan para configurar y mantener a los usuarios, la información que debe almacenar sobre ellos, quién puede tener acceso a esa información, quién puede administrarla y qué aplicaciones pueden acceder a ella.</span><span class="sxs-lookup"><span data-stu-id="5459b-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="5459b-106">AAD puede autenticar a los usuarios para las aplicaciones configuradas para usarlos, lo que proporciona una experiencia de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="5459b-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="5459b-107">Puede usarse por sí mismo o estar integrado con Windows AD que se ejecuta en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="5459b-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="5459b-108">Azure AD se crea para la nube.</span><span class="sxs-lookup"><span data-stu-id="5459b-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="5459b-109">Es realmente una solución de identidad nativa en la nube que usa una sintaxis de Graph API y de OData basada en REST para consultas, a diferencia de Windows AD, que usa LDAP.</span><span class="sxs-lookup"><span data-stu-id="5459b-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="5459b-110">Active Directory locales pueden sincronizar los atributos de usuario con la nube mediante servicios de sincronización de identidades, lo que permite que toda la autenticación tenga lugar en la nube mediante Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5459b-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="5459b-111">Como alternativa, la autenticación se puede configurar a través de Connect para pasar de nuevo a la Active Directory local a través de ADFS para que Windows AD lo complete de forma local.</span><span class="sxs-lookup"><span data-stu-id="5459b-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="5459b-112">Azure AD admite pantallas de inicio de sesión con personalización de marca de empresa, autenticación multifábrica y proxies de aplicación basados en la nube que se usan para proporcionar SSO para aplicaciones hospedadas en el entorno local.</span><span class="sxs-lookup"><span data-stu-id="5459b-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="5459b-113">Ofrece diferentes tipos de informes de seguridad y capacidades de alerta.</span><span class="sxs-lookup"><span data-stu-id="5459b-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="5459b-114">Referencias</span><span class="sxs-lookup"><span data-stu-id="5459b-114">References</span></span>

- [<span data-ttu-id="5459b-115">Plataforma de Microsoft Identity</span><span class="sxs-lookup"><span data-stu-id="5459b-115">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="5459b-116">[Anterior](authentication-authorization.md)
>[Siguiente](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="5459b-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>
