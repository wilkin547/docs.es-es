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
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="1ddf3-103">Autenticación y autorización en aplicaciones nativas en la nube</span><span class="sxs-lookup"><span data-stu-id="1ddf3-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="1ddf3-104">*La autenticación* es el proceso de determinar la identidad de una entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1ddf3-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="1ddf3-105">*La autorización* es el acto de conceder un permiso de entidad de seguridad autenticado para realizar una acción o tener acceso a un recurso.</span><span class="sxs-lookup"><span data-stu-id="1ddf3-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="1ddf3-106">A veces, la `AuthN` autenticación se acorta `AuthZ`y la autorización se acorta a .</span><span class="sxs-lookup"><span data-stu-id="1ddf3-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="1ddf3-107">Las aplicaciones nativas de la nube deben depender de protocolos abiertos basados en HTTP para autenticar entidades de seguridad, ya que tanto los clientes como las aplicaciones podrían ejecutarse en cualquier parte del mundo en cualquier plataforma o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ddf3-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="1ddf3-108">El único factor común es HTTP.</span><span class="sxs-lookup"><span data-stu-id="1ddf3-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="1ddf3-109">Muchas organizaciones todavía dependen de servicios de autenticación local como Servicios de federación de Active Directory (ADFS).</span><span class="sxs-lookup"><span data-stu-id="1ddf3-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="1ddf3-110">Aunque este enfoque tradicionalmente ha servido bien a las organizaciones para las necesidades de autenticación en las instalaciones, las aplicaciones nativas de la nube se benefician de sistemas diseñados específicamente para la nube.</span><span class="sxs-lookup"><span data-stu-id="1ddf3-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="1ddf3-111">Un reciente aviso del Centro Nacional de Ciberseguridad del Reino Unido (NCSC) de 2019 afirma que "las organizaciones que usan Azure AD como su fuente de autenticación principal en realidad reducirán su riesgo en comparación con ADFS".</span><span class="sxs-lookup"><span data-stu-id="1ddf3-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="1ddf3-112">Algunas razones descritas en [este análisis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) incluyen:</span><span class="sxs-lookup"><span data-stu-id="1ddf3-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="1ddf3-113">Acceso al conjunto completo de tecnologías de protección de credenciales de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1ddf3-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="1ddf3-114">La mayoría de las organizaciones ya confían en Azure AD hasta cierto punto.</span><span class="sxs-lookup"><span data-stu-id="1ddf3-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="1ddf3-115">El hash doble de hashes NTLM garantiza que el compromiso no permita las credenciales que funcionan en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="1ddf3-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="1ddf3-116">Referencias</span><span class="sxs-lookup"><span data-stu-id="1ddf3-116">References</span></span>

- [<span data-ttu-id="1ddf3-117">Conceptos básicos sobre autenticación</span><span class="sxs-lookup"><span data-stu-id="1ddf3-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="1ddf3-118">Acceder a tokens y reclamaciones</span><span class="sxs-lookup"><span data-stu-id="1ddf3-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="1ddf3-119">Puede ser el momento de abandonar sus servicios de autenticación en las instalaciones</span><span class="sxs-lookup"><span data-stu-id="1ddf3-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="1ddf3-120">[Anterior](identity.md)
>[Siguiente](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="1ddf3-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>
