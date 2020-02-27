---
title: 'Cumplimiento de FIPS: .NET Core'
description: Explica la compatibilidad de .NET Core Estándar federal de procesamiento de información (FIPS).
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: 84d6edc6975af0484bb67999ad5891eaf4db057d
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77626963"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="94c77-103">Compatibilidad con Estándar federal de procesamiento de información de .NET Core (FIPS)</span><span class="sxs-lookup"><span data-stu-id="94c77-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="94c77-104">La publicación Estándar federal de procesamiento de información (FIPS) 140-2 es un estándar del gobierno de EE. UU. que define los requisitos de seguridad mínimos para los módulos criptográficos en los productos de tecnología de la información, como se define en la sección 5131 de la información. Acto de reforma de administración de tecnología de 1996.</span><span class="sxs-lookup"><span data-stu-id="94c77-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="94c77-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="94c77-105">.NET Core:</span></span>

* <span data-ttu-id="94c77-106">Pasa las llamadas primitivas criptográficas a través de a los módulos estándar que proporciona el sistema operativo subyacente.</span><span class="sxs-lookup"><span data-stu-id="94c77-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="94c77-107">No **exige el** uso de algoritmos o tamaños de clave aprobados por FIPS en aplicaciones de .net Core.</span><span class="sxs-lookup"><span data-stu-id="94c77-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="94c77-108">El administrador del sistema es responsable de configurar la compatibilidad con FIPS para un sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="94c77-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="94c77-109">Si el código se escribe para un entorno compatible con FIPS, el desarrollador es responsable de garantizar que no se usen algoritmos FIPS no compatibles.</span><span class="sxs-lookup"><span data-stu-id="94c77-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="94c77-110">Para obtener más información sobre la conformidad con FIPS, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="94c77-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="94c77-111">Compatibilidad con FIPS de Windows</span><span class="sxs-lookup"><span data-stu-id="94c77-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="94c77-112">Configuración de Windows para la compatibilidad con FIPS</span><span class="sxs-lookup"><span data-stu-id="94c77-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="94c77-113">Capítulo 8. Normas y regulaciones federales Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="94c77-113">Chapter 8. Federal Standards and Regulations Red Hat Enterprise Linux 7</span></span>](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/chap-federal_standards_and_regulations)
