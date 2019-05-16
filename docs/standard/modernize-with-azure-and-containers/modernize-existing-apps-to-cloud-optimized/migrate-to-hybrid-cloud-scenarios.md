---
title: Migración a escenarios de nube híbrida
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Migrar a escenarios de nube híbrida
ms.date: 04/30/2018
ms.openlocfilehash: 04c618681c61f5584e641e0a4735e1261ab34fa3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643717"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a>Migración a escenarios de nube híbrida

Algunas organizaciones y empresas no pueden migrar algunos de sus aplicaciones a nubes públicas, como Microsoft Azure o cualquier otra nube pública debido a las regulaciones o sus propias directivas. Sin embargo, es probable que cualquier organización puede beneficiarse de tener algunas de sus aplicaciones en la nube pública y otras aplicaciones locales. Pero un entorno mixto puede dar lugar a una complejidad excesiva en los entornos debido a distintas plataformas y tecnologías utilizadas en las nubes públicas frente a entornos locales.

Microsoft proporciona la mejor solución de nube híbrida, uno en el que puede optimizar los recursos existentes en el entorno local y en la nube pública, mientras que garantizar la coherencia de una nube híbrida de Azure. Puede maximizar las habilidades existentes y obtener un enfoque flexible y unificado para crear aplicaciones que se pueden ejecutar en la nube o local, gracias a Azure Stack (local) y Azure (nube pública).

En cuanto a seguridad, puede centralizar la administración y seguridad en la nube híbrida. Puede obtener el control sobre todos los recursos del centro de datos a la nube, proporcionando el inicio de sesión único en el entorno local y aplicaciones en la nube. Esto se consigue mediante la extensión de Active Directory a una nube híbrida y mediante el uso de administración de identidades.

Por último, puede distribuir y analizar datos sin problemas, use los mismos lenguajes de consulta para los recursos locales y en la nube y aplicar análisis y aprendizaje profundo de Azure para enriquecer los datos, independientemente de su origen.

## <a name="azure-stack"></a>Azure Stack

Azure Stack es una plataforma de nube híbrida que le permite proporcionar servicios de Azure desde el centro de datos de su organización. Azure Stack está diseñado para admitir las nuevas opciones para las aplicaciones modernas en escenarios clave, como borde y entornos desconectados o resolver determinados requisitos de seguridad y cumplimiento.

Figura 4-13 se muestra una visión general de la plataforma de nube híbrida verdadera que ofrece Microsoft.

![Plataforma de nube híbrida de Microsoft con Azure Stack y Azure](./media/image13.jpg)

> **Figura 4-13.** Plataforma de nube híbrida de Microsoft con Azure Stack y Azure

Azure Stack se ofrece en dos opciones de implementación para satisfacer sus necesidades:

- Sistemas integrados de Azure Stack

- Kit de desarrollo de Azure Stack

### <a name="azure-stack-integrated-systems"></a>Sistemas integrados de Azure Stack

Sistemas de Azure Stack integrado se ofrecen a través de una asociación de asociados de Microsoft y de hardware. La asociación crea una solución que ofrece innovación paced en la nube que sea equilibrada con simplicidad en la administración. Dado que Azure Stack se ofrece como un sistema integrado de hardware y software, obtener la cantidad adecuada de flexibilidad y control, al seguir adoptando la innovación de la nube. Sistemas de Azure Stack integrado oscilar entre 4 a 12 nodos y son compatibles en conjunto con asociados de hardware y Microsoft. Utilice los sistemas integrados de Azure Stack para implementar nuevos escenarios para las cargas de trabajo de producción.

### <a name="azure-stack-development-kit"></a>Kit de desarrollo de Azure Stack

Kit de desarrollo de Microsoft Azure Stack es una implementación de nodo único de Azure Stack, que puede usar para evaluar y conocer Azure Stack. También puede usar el Kit de desarrollo de Azure Stack como entorno de desarrollo, donde puede desarrollar mediante las API y herramientas que son coherentes con Azure. El Kit de desarrollo de Azure Stack no está pensado para usarse como un entorno de producción.

### <a name="additional-resources"></a>Recursos adicionales

- **Nube híbrida de Azure**

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- **Azure Stack**

    <https://azure.microsoft.com/overview/azure-stack/>

- **Cuentas de servicio de Active Directory para contenedores de Windows**

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- **Crear un contenedor con compatibilidad con Active Directory**

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- **Licencias de ventaja híbrida de Azure**

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
>[Anterior](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Siguiente](../walkthroughs-technical-get-started-overview.md)
