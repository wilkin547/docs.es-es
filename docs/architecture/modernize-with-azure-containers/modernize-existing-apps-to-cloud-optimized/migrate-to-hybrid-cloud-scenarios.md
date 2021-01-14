---
title: Migración a escenarios de nube híbrida
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Migración a escenarios de nube híbrida
ms.date: 12/21/2020
ms.openlocfilehash: d5bf7f08381f3718061742b37c73604d8e57f1e2
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025230"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Migración a escenarios de nube híbrida

Algunas organizaciones y empresas no pueden migrar algunas de sus aplicaciones a nubes públicas, como Microsoft Azure u otras nubes públicas, debido a las regulaciones o a sus propias directivas. Sin embargo, es probable que cualquier organización pueda beneficiarse de tener algunas de sus aplicaciones en la nube pública y otras aplicaciones locales. Pero un entorno mixto puede generar una complejidad excesiva en los entornos debido a las plataformas y tecnologías diferentes que se usan en las nubes públicas y los entornos locales.

Microsoft ofrece la mejor solución de nube híbrida, una en la que puede optimizar los recursos que tiene en el entorno local y en la nube pública y, al mismo tiempo, garantizar la coherencia en una nube híbrida de Azure. Puede maximizar las aptitudes existentes y obtener un enfoque flexible y unificado para crear aplicaciones que se puedan ejecutar en la nube o en el entorno local, gracias a Azure Stack (local) y a Azure (nube pública).

En cuanto a la seguridad, puede centralizar la administración y la seguridad de toda la nube híbrida. Puede tener el control de todos los recursos, desde su centro de datos a la nube, y proporcionar un inicio de sesión único a las aplicaciones locales y en la nube. Para conseguir esta funcionalidad, puede extender Active Directory a una nube híbrida y usar la administración de identidades.

Por último, puede distribuir y analizar datos sin problemas, usar los mismos lenguajes de consulta para los recursos locales y en la nube, y aplicar análisis y aprendizaje profundo en Azure para enriquecer sus datos, independientemente de su origen.

## <a name="azure-stack"></a>Azure Stack

Azure Stack es una plataforma en la nube híbrida que permite proporcionar servicios de Azure desde el centro de datos de la organización. Azure Stack está diseñado para posibilitar nuevas opciones para las aplicaciones modernas en escenarios clave, como los entornos perimetrales y los entornos desconectados, así como para resolver determinados requisitos de seguridad y de cumplimiento.

En la figura 4-13 se muestra una visión general de la verdadera plataforma de nube híbrida que ofrece Microsoft.

![Diagrama de la plataforma de nube híbrida de Microsoft con Azure Stack y Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

**Figura 4-13.** Plataforma de nube híbrida de Microsoft con Azure Stack y Azure

Azure Stack se ofrece en dos opciones de implementación para satisfacer sus necesidades.

- Sistemas integrados de Azure Stack

- Kit de desarrollo de Azure Stack

### <a name="azure-stack-integrated-systems"></a>Sistemas integrados de Azure Stack

Los sistemas integrados de Azure Stack los ofrecen conjuntamente Microsoft y sus asociados de hardware. Esta asociación crea una solución que ofrece innovación al ritmo de la nube, equilibrada con la simplicidad de la administración. Dado que Azure Stack se ofrece como un sistema integrado de hardware y software, obtiene la cantidad adecuada de flexibilidad y control, a la vez que sigue adoptando la innovación de la nube. El tamaño de los sistemas integrados de Azure Stack va de los 4 a los 12 nodos y tiene un soporte técnico conjunto que ofrecen un asociado de hardware y Microsoft. Use los sistemas integrados de Azure Stack para implementar nuevos escenarios para las cargas de trabajo de producción.

### <a name="azure-stack-development-kit"></a>Kit de desarrollo de Azure Stack

El Kit de desarrollo de Microsoft Azure Stack es una implementación de un solo nodo de Azure Stack, que puede usar para evaluar y obtener información sobre Azure Stack. También puede usar el Kit de desarrollo de Azure Stack como entorno de desarrollo, donde puede desarrollar con API y herramientas coherentes con Azure. El Kit de desarrollo de Azure Stack no está diseñado para usarse como un entorno de producción.

### <a name="additional-resources"></a>Recursos adicionales

- **Nube híbrida de Azure**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Cuentas de servicio de Active Directory para contenedores Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Creación de un contenedor con compatibilidad con Active Directory**

    <https://docs.microsoft.com/archive/blogs/containerstuff/create-a-container-with-active-directory-support>

- **Licencias para la Ventaja híbrida de Azure**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[Anterior](life-cycle-ci-cd-pipelines-devops-tools.md)
>[Siguiente](../walkthroughs-technical-get-started-overview.md)
