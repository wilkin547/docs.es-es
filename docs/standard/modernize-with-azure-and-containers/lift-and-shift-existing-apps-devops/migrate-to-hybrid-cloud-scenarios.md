---
title: "Migrar a escenarios de nube híbrida"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Migrar a escenarios de nube híbrida"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/2/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6216068786745ac4ebc00263a14b4afe247193f5
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Migrar a escenarios de nube híbrida

Algunas organizaciones y empresas no pueden migrar algunos de sus aplicaciones a nubes públicas como Microsoft Azure o cualquier otra nube pública debido a la normativa o sus propias directivas. Sin embargo, es probable que cualquier organización puede beneficiarse de tener algunos de sus aplicaciones en la nube pública y otras aplicaciones locales. Pero puede provocar un entorno mixto excesiva complejidad en los entornos debido a distintas plataformas y tecnologías que se usan en nubes públicas frente a entornos locales.

Microsoft proporciona la mejor solución de nube híbrida, uno en el que se pueden optimizar sus activos existentes en local y en la nube pública, mientras se asegura la coherencia en una nube híbrida de Azure. Puede maximizar los conocimientos y obtener un enfoque flexible y unificado para la generación de aplicaciones que se ejecutan en la nube o local, gracias a la pila de Azure (local) y Azure (nube pública).

En cuanto a seguridad, puede centralizar la administración y la seguridad a través de la nube híbrida. Puede obtener un control sobre todos los recursos, desde el centro de datos en la nube, proporcionando un inicio de sesión único a local y las aplicaciones de nube. Esto se consigue mediante la extensión de Active Directory a una nube híbrida y mediante el uso de administración de identidades.

Por último, puede distribuir y analizar los datos sin problemas, use los mismos lenguajes de consulta para los activos en la nube y locales y aplicar profunda de aprendizaje de Azure para enriquecer los datos, independientemente de su origen y análisis.

## <a name="azure-stack"></a>Pila de Azure

Pila de Azure es una plataforma de nube híbrida que le permite ofrecer servicios de Azure desde el centro de datos de su organización. Pila de Azure está diseñado para admitir nuevas opciones para las aplicaciones modernas en escenarios claves, como el borde y entornos no conectados o resolver determinados requisitos de seguridad y cumplimiento de normas.

Figura 4-13 muestra una visión general de la plataforma de nube híbrida true que ofrece Microsoft.

![Plataforma de nube híbrida de Microsoft con la pila de Azure y Azure](./media/image13.jpg)

> **Figura 4-13.** Plataforma de nube híbrida de Microsoft con la pila de Azure y Azure

Pila de Azure se ofrece en dos opciones de implementación, para satisfacer sus necesidades:

-   Sistemas integrados de pila de Azure

-   Kit de desarrollo de la pila de Azure

### <a name="azure-stack-integrated-systems"></a>Sistemas integrados de pila de Azure

Sistemas de pila integrada Azure se ofrecen a través de una asociación de asociados de Microsoft y hardware. El perfil crea una solución que ofrece innovación paced en la nube que se equilibra con simplicidad de administración. Ya que Azure pila se ofrece como un sistema integrado de hardware y software, obtendrá la cantidad correcta de flexibilidad y control, mientras todavía adopta innovación de la nube. Sistemas de pila integrada Azure varían en tamaño de 4 a 12 nodos y conjuntamente son compatibles con los socios de hardware y Microsoft. Usar sistemas de pila de Azure integrado para implementar nuevos escenarios para las cargas de trabajo de producción.

### <a name="azure-stack-development-kit"></a>Kit de desarrollo de la pila de Azure

Kit de desarrollo de pila de Microsoft Azure es una implementación de un único nodo de pila de Azure, lo que puede usar para evaluar y obtener información sobre la pila de Azure. También puede usar el Kit de desarrollo de pila de Azure como un entorno de desarrollador, donde puede desarrollar con las API y herramientas que son coherentes con Azure. Kit de desarrollo de pila de Azure no está pensado para usarse como un entorno de producción.

### <a name="additional-resources"></a>Recursos adicionales

-   **Nube híbrida de Azure**

    [https://www.microsoft.com/cloud-platform/hybrid-cloud](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   **Azure Stack**

    [https://azure.microsoft.com/overview/azure-stack/](https://azure.microsoft.com/overview/azure-stack/)

-   **Cuentas de servicio de Active Directory para los contenedores de Windows**

    [https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   **Crear un contenedor con compatibilidad con Active Directory**

    [https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   **Licencias de beneficio híbrida de Azure**

    [https://azure.microsoft.com/pricing/hybrid-use-benefit/](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
[Anterior](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Siguiente](../walkthroughs-technical-get-started-overview.md)
