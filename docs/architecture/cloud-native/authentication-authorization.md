---
title: Autenticación y autorización en aplicaciones nativas de la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Autenticación y autorización en aplicaciones nativas en la nube
ms.date: 06/30/2019
ms.openlocfilehash: a397175e98c2e8103d2a8c372c81fcca65f19b11
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840752"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="bb3f1-103">Autenticación y autorización en aplicaciones nativas en la nube</span><span class="sxs-lookup"><span data-stu-id="bb3f1-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="bb3f1-104">La *autenticación* es el proceso de determinar la identidad de una entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="bb3f1-105">La *autorización* es el acto de conceder un permiso de entidad de seguridad autenticada para realizar una acción o tener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="bb3f1-106">A veces se acorta la autenticación a `AuthN` y se acorta la autorización a `AuthZ`.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="bb3f1-107">Las aplicaciones nativas de la nube deben basarse en protocolos abiertos basados en HTTP para autenticar las entidades de seguridad, ya que tanto los clientes como las aplicaciones podrían ejecutarse en cualquier parte del mundo en cualquier plataforma o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="bb3f1-108">El único factor común es HTTP.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="bb3f1-109">Muchas organizaciones todavía dependen de servicios de autenticación locales como Servicios de federación de Active Directory (AD FS) (ADFS).</span><span class="sxs-lookup"><span data-stu-id="bb3f1-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="bb3f1-110">Aunque este enfoque ha servido tradicionalmente a las organizaciones para satisfacer las necesidades de autenticación locales, las aplicaciones nativas de la nube se benefician de los sistemas diseñados específicamente para la nube.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="bb3f1-111">Una reciente consulta de 2019 Reino Unido National Cyber Security Centre (NCSC) indica que "las organizaciones que usan Azure AD como su origen de autenticación principal reducirán realmente su riesgo en comparación con ADFS".</span><span class="sxs-lookup"><span data-stu-id="bb3f1-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="bb3f1-112">Algunas de las razones que se describen en [este análisis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) incluyen:</span><span class="sxs-lookup"><span data-stu-id="bb3f1-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="bb3f1-113">Acceso al conjunto completo de tecnologías de protección de credenciales de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="bb3f1-114">La mayoría de las organizaciones ya están confiando en Azure AD hasta cierto punto.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="bb3f1-115">El doble hash de hashes de NTLM garantiza que el riesgo no permitirá credenciales que funcionen en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="bb3f1-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="bb3f1-116">Referencias</span><span class="sxs-lookup"><span data-stu-id="bb3f1-116">References</span></span>

- [<span data-ttu-id="bb3f1-117">Aspectos básicos de la autenticación</span><span class="sxs-lookup"><span data-stu-id="bb3f1-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="bb3f1-118">Tokens de acceso y notificaciones</span><span class="sxs-lookup"><span data-stu-id="bb3f1-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="bb3f1-119">Puede ser hora de deshacerse de los servicios de autenticación locales</span><span class="sxs-lookup"><span data-stu-id="bb3f1-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="bb3f1-120">[Anterior](identity.md)
>[Siguiente](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="bb3f1-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
