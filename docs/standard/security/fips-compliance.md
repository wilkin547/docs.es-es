---
title: 'Cumplimiento de FIPS: .NET Core'
description: Explica la compatibilidad de .NET Core Estándar federal de procesamiento de información (FIPS).
ms.date: 11/20/2019
author: Rick-Anderson
ms.author: riande
ms.openlocfilehash: cf640c857e79ae811dd38d57a0e5301b7bc96572
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74205081"
---
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a><span data-ttu-id="2e5b8-103">Compatibilidad con Estándar federal de procesamiento de información de .NET Core (FIPS)</span><span class="sxs-lookup"><span data-stu-id="2e5b8-103">.NET Core Federal Information Processing Standard (FIPS) compliance</span></span>

<span data-ttu-id="2e5b8-104">La publicación Estándar federal de procesamiento de información (FIPS) 140-2 es un estándar del gobierno de EE. UU. que define los requisitos de seguridad mínimos para los módulos criptográficos en los productos de tecnología de la información, como se define en la sección 5131 de la información. Acto de reforma de administración de tecnología de 1996.</span><span class="sxs-lookup"><span data-stu-id="2e5b8-104">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="2e5b8-105">.NET Core:</span><span class="sxs-lookup"><span data-stu-id="2e5b8-105">.NET Core:</span></span>

* <span data-ttu-id="2e5b8-106">Pasa las llamadas primitivas criptográficas a través de a los módulos estándar que proporciona el sistema operativo subyacente.</span><span class="sxs-lookup"><span data-stu-id="2e5b8-106">Passes cryptographic primitives calls through to the standard modules the underlying operating system provides.</span></span>
* <span data-ttu-id="2e5b8-107">No **exige el** uso de algoritmos o tamaños de clave aprobados por FIPS en aplicaciones de .net Core.</span><span class="sxs-lookup"><span data-stu-id="2e5b8-107">Does **not** enforce the use of FIPS Approved algorithms or key sizes in .NET Core apps.</span></span>

<span data-ttu-id="2e5b8-108">El administrador del sistema es responsable de configurar la compatibilidad con FIPS para un sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2e5b8-108">The system administrator is responsible for configuring the FIPS compliance for an operating system.</span></span>

<span data-ttu-id="2e5b8-109">Si el código se escribe para un entorno compatible con FIPS, el desarrollador es responsable de garantizar que no se usen algoritmos FIPS no compatibles.</span><span class="sxs-lookup"><span data-stu-id="2e5b8-109">If code is written for a FIPS-compliant environment, the developer is responsible for ensuring that non-compliant FIPS algorithms aren't used.</span></span>

<span data-ttu-id="2e5b8-110">Para obtener más información sobre la conformidad con FIPS, consulte los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="2e5b8-110">For more information on FIPS compliance, see the following articles:</span></span>

* [<span data-ttu-id="2e5b8-111">Compatibilidad con FIPS de Windows</span><span class="sxs-lookup"><span data-stu-id="2e5b8-111">Windows FIPS Compliance</span></span>](/windows/security/threat-protection/fips-140-validation)
* [<span data-ttu-id="2e5b8-112">Configuración de Windows para la compatibilidad con FIPS</span><span class="sxs-lookup"><span data-stu-id="2e5b8-112">Configuring Windows for FIPS Compliance</span></span>](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [<span data-ttu-id="2e5b8-113">10,2. ESTÁNDAR FEDERAL DE PROCESAMIENTO DE INFORMACIÓN (FIPS)</span><span class="sxs-lookup"><span data-stu-id="2e5b8-113">10.2. FEDERAL INFORMATION PROCESSING STANDARD (FIPS)</span></span>](https://access.redhat.com/documentation/red_hat_enterprise_linux/6/html/security_guide/sect-security_guide-federal_standards_and_regulations-federal_information_processing_standard)
