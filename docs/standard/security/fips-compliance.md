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
# <a name="net-core-federal-information-processing-standard-fips-compliance"></a>Compatibilidad con Estándar federal de procesamiento de información de .NET Core (FIPS)

La publicación Estándar federal de procesamiento de información (FIPS) 140-2 es un estándar del gobierno de EE. UU. que define los requisitos de seguridad mínimos para los módulos criptográficos en los productos de tecnología de la información, como se define en la sección 5131 de la información. Acto de reforma de administración de tecnología de 1996.

.NET Core:

* Pasa las llamadas primitivas criptográficas a través de a los módulos estándar que proporciona el sistema operativo subyacente.
* No **exige el** uso de algoritmos o tamaños de clave aprobados por FIPS en aplicaciones de .net Core.

El administrador del sistema es responsable de configurar la compatibilidad con FIPS para un sistema operativo.

Si el código se escribe para un entorno compatible con FIPS, el desarrollador es responsable de garantizar que no se usen algoritmos FIPS no compatibles.

Para obtener más información sobre la conformidad con FIPS, consulte los siguientes artículos:

* [Compatibilidad con FIPS de Windows](/windows/security/threat-protection/fips-140-validation)
* [Configuración de Windows para la compatibilidad con FIPS](/windows/security/threat-protection/security-policy-settings/system-cryptography-use-fips-compliant-algorithms-for-encryption-hashing-and-signing)
* [Capítulo 8. Normas y regulaciones federales Red Hat Enterprise Linux 7](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/chap-federal_standards_and_regulations)
