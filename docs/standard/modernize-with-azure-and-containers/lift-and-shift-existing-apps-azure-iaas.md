---
title: Levantar y mover aplicaciones .NET existentes a Azure IaaS (infraestructura de nube-Ready)
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 2b987d43f476f261bfdbd1b2af6ca7f792178cf8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266629"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Levantar y mover aplicaciones .NET existentes a Azure IaaS (infraestructura de nube-Ready)

> Visión: Como primer paso, para reducir la inversión en el entorno local y el costo total de hardware y mantenimiento de red, simplemente rehospedar las aplicaciones existentes en la nube.

Antes de entrar en *cómo* para migrar las aplicaciones existentes a la infraestructura de Azure como plataforma de servicio (IaaS), es importante analizar las razones *¿por qué* desea migrar directamente a IaaS en Azure. El escenario en este nivel de madurez de modernización es básicamente empezar a usar máquinas virtuales en la nube, en lugar de usar la infraestructura local actual, continuar.

Otro aspecto a analizar es *¿por qué* desea migrar a la nube de IaaS pura en lugar de limitarse a agregar más avanzada de servicios administrados de Azure. Determinar qué casos podrían requerir IaaS en primer lugar.

Figura 2-1 se coloca en la nube infraestructura lista para las aplicaciones en los niveles de madurez de modernización:

![Posición en la nube infraestructura lista para aplicaciones](./media/image2-1.png)

> **Figura 2-1.** Posición en la nube infraestructura lista para aplicaciones

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>¿Por qué migrar las aplicaciones web .NET existentes a IaaS de Azure

Es la razón principal para migrar a la nube, incluso en un nivel de IaaS inicial alcanzar reducciones de costos. Mediante el uso de más servicios de infraestructura administrada, su organización puede reducir su inversión en mantenimiento de hardware, servidor o aprovisionamiento de máquinas virtuales e implementación y administración de la infraestructura.

Después de realizar la decisión de migrar sus aplicaciones a la nube, la razón principal por qué elegiría IaaS en lugar de las opciones más avanzadas como PaaS es simplemente que el entorno de IaaS estará más familiarizada. Mover a un entorno que es similar a la actual, el entorno local ofrece una menor curva de aprendizaje, lo que facilita el camino a la nube.

Sin embargo, tomar el camino a la nube no significa que obtendrá el máximo provecho de tener las aplicaciones que se ejecutan en la nube. Cualquier organización obtendrá las ventajas más importantes de una migración a la nube en los niveles de madurez nativas de la nube y optimizadas para la nube ya introducido.

También resulta evidente que las aplicaciones son más fáciles de modernización y rediseño en el futuro cuando ya se están ejecutando en la nube, incluso en IaaS. Ya se ha logrado la migración de datos de aplicación. Además, su organización habrá adquirido los conocimientos necesarios para trabajar en la nube y realiza el cambio para operar en un "culture en la nube".

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Cuándo realizar la migración a IaaS en lugar de a PaaS

Las secciones siguientes describen las aplicaciones optimizadas para la nube que se basan principalmente en los servicios y plataformas PaaS. Estas aplicaciones ofrecen las mayores ventajas de migrar a la nube. 

Si su objetivo es mover aplicaciones existentes a la nube, en primer lugar, identifique las aplicaciones existentes que no requieran una modificación sustancial para ejecutarse en Azure App Service. Estas aplicaciones deben ser los primeros candidatos para optimizada para la nube. 

A continuación, para las aplicaciones que aún no se puede mover a contenedores de Windows y PaaS como App Service u orquestadores como Azure Service Fabric, migrarlas máquinas virtuales sin formato simple (IaaS). 

Sin embargo, tenga en cuenta que correctamente configurar, proteger y mantener las máquinas virtuales requieren mucho más tiempo y experiencia en TI en comparación con el uso de los servicios de PaaS en Azure. Si está pensando en Azure Virtual Machines, asegúrese de tener en cuenta el esfuerzo de mantenimiento continuado necesario para aplicar revisiones, actualizar y administrar su entorno de máquina virtual. Azure Virtual Machines es IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Use Azure Migrate para analizar y migrar las aplicaciones existentes a Azure

Migración a la nube no tiene que ser difícil. Pero muchas organizaciones tienen dificultades para comenzar - para obtener una visibilidad profunda en el entorno y la estrecha interdependencias entre aplicaciones, cargas de trabajo y datos. Sin esa visibilidad, puede ser difícil de planear la ruta de acceso. Sin información detallada sobre lo que se requiere para una migración correcta, no puede tener las conversaciones derecha dentro de su organización. No sabe lo suficiente acerca de los posibles costes ventajas, o si las cargas de trabajo podrían simplemente mediante lift-and-shift o requerirían modificaciones importantes para migrar correctamente. No es de extrañar que muchas organizaciones dudan.

[Azure Migrate](https://aka.ms/azuremigrate) es un nuevo servicio que proporciona la orientación, información y los mecanismos necesarios para ayudarle a migrar a Azure. Azure Migrate ofrece:

- Detección y evaluación para las máquinas virtuales de un entorno local

- Asignación de dependencias integrada para la detección de alta confianza de aplicaciones de niveles múltiples

- Intelligent adquirir un tamaño adecuado para máquinas virtuales de Azure

- Creación de informes con las directrices para solucionar posibles problemas de compatibilidad

- Integración con el servicio de administración de base de datos de Azure para la detección de base de datos y migración

Azure Migrate le ofrece confianza de que las cargas de trabajo pueden migrar con un impacto mínimo en el negocio y ejecutarse según lo previsto en Azure. Con las herramientas adecuadas y orientación, puede lograr la máxima rentabilidad de la inversión y garantizar que el rendimiento crítico y se cumplen las necesidades de confiabilidad.

Figura 2-2 se muestra la asignación de dependencias integrada para todas las conexiones de servidor y la aplicación que realiza Azure Migrate.

![Posición en la nube infraestructura lista para aplicaciones](./media/image2-2.png)

> **Figura 2-2.** Posición en la nube infraestructura lista para aplicaciones

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Usar Azure Site Recovery para migrar las máquinas virtuales existentes a máquinas virtuales de Azure

Como parte de end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) es una herramienta que puede usar para migrar fácilmente sus aplicaciones web a las máquinas virtuales en Azure. Puede usar Site Recovery para replicar máquinas virtuales locales y servidores físicos en Azure, o para replicarlas a una ubicación secundaria en el entorno local. Incluso puede replicar una carga de trabajo que se ejecuta en una VM de Azure compatibles, en un uso local *Hyper-V* máquina virtual, en un *VMware* de máquina virtual, o en un servidor físico de Windows o Linux. Replicación en Azure elimina el costo y la complejidad de mantener un centro de datos secundaria.

También se realiza la recuperación de sitio específicamente para entornos híbridos que son parcialmente en el entorno local y en parte en Azure. Site Recovery ayuda a garantizar la continuidad empresarial manteniendo las aplicaciones que se ejecutan en máquinas virtuales locales y en los servidores físicos disponibles si un sitio deja de funcionar. Replica las cargas de trabajo que se ejecutan en máquinas virtuales y servidores físicos para que sigan estando disponibles en una ubicación secundaria si el sitio primario no está disponible. Recupera las cargas de trabajo para el sitio primario cuando ya está activo y vuelva a ejecutar.

Figura 2-3 se muestra la ejecución de varias migraciones de máquina virtual mediante Azure Site Recovery.

![Posición en la nube infraestructura lista para aplicaciones](./media/image2-3.png)

> **Figura 2-3.** Posición en la nube infraestructura lista para aplicaciones

### <a name="additional-resources"></a>Recursos adicionales

- **Hoja de datos de migración de Azure**

    [https://aka.ms/azuremigration\_datasheet](https://aka.ms/azuremigration\_datasheet)

- **Azure Migrate**

    [https://aka.ms/azuremigrate](https://aka.ms/azuremigrate)

- **Centro de migración de Azure**

    [https://azure.microsoft.com/migration/](https://azure.microsoft.com/migration/)

- **Migrar a Azure con Site Recovery**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

- **Introducción al servicio Azure Site Recovery**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-overview](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

- **Migración de máquinas virtuales de AWS a máquinas virtuales de Azure**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](migrate-your-relational-databases-to-azure.md)
