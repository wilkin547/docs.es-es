---
title: Migración a escenarios de nube híbrida
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Migración a escenarios de nube híbrida
ms.date: 04/30/2018
ms.openlocfilehash: 313608c41427b3833bbc873398595ceb37bd7c7d
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373940"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Migración a escenarios de nube híbrida

Algunas organizaciones y empresas no pueden migrar algunas de sus aplicaciones a nubes públicas como Microsoft Azure o cualquier otra nube pública debido a las regulaciones o a sus propias directivas. Sin embargo, es probable que cualquier organización pueda beneficiarse de tener algunas de sus aplicaciones en la nube pública y en otras aplicaciones locales. Pero un entorno mixto puede conducir a una complejidad excesiva en entornos debido a diferentes plataformas y tecnologías que se usan en nubes públicas frente a entornos locales.

Microsoft ofrece la mejor solución de nube híbrida, una en la que puede optimizar sus recursos locales y en la nube pública, al tiempo que garantiza la coherencia en una nube híbrida de Azure. Puede maximizar los conocimientos existentes y obtener un enfoque flexible y unificado para crear aplicaciones que se puedan ejecutar en la nube o de forma local, gracias a Azure Stack (local) y a Azure (nube pública).

En cuanto a la seguridad, puede centralizar la administración y la seguridad en toda la nube híbrida. Puede obtener el control sobre todos los recursos, desde su centro de recursos a la nube, proporcionando inicio de sesión único a aplicaciones locales y en la nube. Para ello, puede extender Active Directory a una nube híbrida y mediante el uso de la administración de identidades.

Por último, puede distribuir y analizar datos sin problemas, usar los mismos lenguajes de consulta para los recursos locales y en la nube, y aplicar análisis y aprendizaje profundo en Azure para enriquecer sus datos, independientemente de su origen.

## <a name="azure-stack"></a>Azure Stack

Azure Stack es una plataforma en la nube híbrida que le permite ofrecer servicios de Azure desde el centro de recursos de su organización. Azure Stack está diseñado para admitir nuevas opciones para las aplicaciones modernas en escenarios clave, como entornos perimetrales y no conectados, o para cumplir los requisitos específicos de seguridad y cumplimiento.

En la figura 4-13 se muestra una visión general de la verdadera plataforma en la nube híbrida que ofrece Microsoft.

![Plataforma de nube híbrida de Microsoft con Azure Stack y Azure](./media/image13.jpg)

**Figura 4-13.** Plataforma de nube híbrida de Microsoft con Azure Stack y Azure

Azure Stack se ofrece en dos opciones de implementación, para satisfacer sus necesidades:

- Sistemas integrados Azure Stack

- Kit de desarrollo de Azure Stack

### <a name="azure-stack-integrated-systems"></a>Sistemas integrados Azure Stack

Azure Stack sistemas integrados se ofrecen a través de una asociación de Microsoft y de asociados de hardware. La Asociación crea una solución que ofrece innovación en el ritmo de la nube que se equilibra con simplicidad en la administración. Dado que Azure Stack se ofrece como un sistema integrado de hardware y software, obtiene la cantidad adecuada de flexibilidad y control, a la vez que sigue adoptando la innovación de la nube. Azure Stack sistemas integrados tienen un tamaño de entre 4 y 12 nodos y se admiten conjuntamente por el asociado de hardware y Microsoft. Use Azure Stack sistemas integrados para implementar nuevos escenarios para las cargas de trabajo de producción.

### <a name="azure-stack-development-kit"></a>Kit de desarrollo de Azure Stack

Microsoft Azure Stack kit de desarrollo es una implementación de un solo nodo de Azure Stack, que puede usar para evaluar y obtener información sobre Azure Stack. También puede usar Kit de desarrollo de Azure Stack como entorno de desarrollo, donde puede desarrollar con las API y las herramientas que son coherentes con Azure. Kit de desarrollo de Azure Stack no está diseñado para usarse como un entorno de producción.

### <a name="additional-resources"></a>Recursos adicionales

- **Nube híbrida de Azure**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Active Directory cuentas de servicio para contenedores de Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Creación de un contenedor con compatibilidad con Active Directory**

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- **Licencias de Ventaja híbrida de Azure**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[Anterior](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Siguiente](../walkthroughs-technical-get-started-overview.md)
