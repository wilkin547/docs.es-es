---
title: Levantar y mover las aplicaciones .NET existentes a Azure IaaS (infraestructura preparada para la nube)
description: Modernizar las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 458b1bd1fc9fc24ce43d0926655fe0767aabc43c
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956453"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Levantar y mover las aplicaciones .NET existentes a Azure IaaS (infraestructura preparada para la nube)

> Visión: como primer paso, para reducir su local inversión y coste total de hardware y redes de mantenimiento, simplemente hospedar las aplicaciones existentes en la nube.

Antes de entrar en *cómo* para migrar las aplicaciones existentes para la infraestructura de Azure como una plataforma de servicio (IaaS), es importante analizar las razones *¿por qué* desea migrar directamente a IaaS en Azure. El escenario en este nivel de madurez modernización es básicamente empezar a usar las máquinas virtuales en la nube, en lugar de seguir utilizando la infraestructura local actual.

Otro punto a analizar es *¿por qué* desea migrar a la nube de IaaS pura en lugar de limitarse a agregar más avanzada de servicios administrados en Azure. Determinar qué casos podrían requerir IaaS en primer lugar.

Figura 2-1 se coloca en los niveles de madurez Modernización aplicaciones de uso de infraestructura de nube:

![Posición de aplicaciones de uso de infraestructura de nube](./media/image2-1.png)

> **Figura 2-1.** Posición de aplicaciones de uso de infraestructura de nube

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>¿Por qué migrar las aplicaciones web .NET existentes a Azure IaaS

Es la razón principal para migrar a la nube, incluso en un nivel de IaaS inicial lograr la reducción de los costos. Mediante el uso de más de los servicios de infraestructura administrada, su organización puede reducir su inversión en mantenimiento de hardware, servidor o el aprovisionamiento de máquinas virtuales e implementación y administración de la infraestructura.

Después de tomar la decisión para mover las aplicaciones a la nube, la razón principal por qué es conveniente IaaS en lugar de las opciones más avanzadas como PaaS es simplemente que el entorno de IaaS será mucho más familiar. Mover a un entorno que es similar a la actual, el entorno local ofrece una curva de aprendizaje inferior, que lo hace la ruta de acceso más rápido para la nube.

Sin embargo, tomar la ruta de acceso más rápido a la nube no significa que dispondrá de los mayores beneficios de tener las aplicaciones que se ejecutan en la nube. Las ventajas más importantes de una migración a la nube en los niveles de madurez optimizada para la nube y nativo en la nube se ha introducido ya dispondrá de cualquier organización.

También ha resultado evidente de que las aplicaciones son más fáciles de modernizar y cambie la arquitectura en el futuro cuando todavía se están ejecutando en la nube, incluso en IaaS. Ya se ha logrado la migración de datos de aplicación. Además, su organización habrá obtenido destrezas necesarias para trabajar en la nube y realizan el desplazamiento hasta la operación en "cultura de nube".

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Cuándo se debe migrar a IaaS en lugar de a PaaS

Las secciones siguientes describen las aplicaciones optimizada para la nube que se basan principalmente en los servicios y plataformas de PaaS. Estas aplicaciones proporcionan las mayores ventajas de migrar a la nube. 

Si su objetivo es simplemente mover las aplicaciones existentes a la nube, en primer lugar, identificar las aplicaciones existentes que no requiere una modificación sustancial para que se ejecute en el servicio de aplicación de Azure. Estas aplicaciones deben ser los primeros candidatos para optimizada para la nube. 

A continuación, para las aplicaciones que aún no se puede mover a PaaS y contenedores de Windows como servicio de aplicaciones o orchestrators como Azure Service Fabric, migrarlas máquinas virtuales sin formato simple (IaaS). 

Sin embargo, tenga en cuenta que correctamente configurar, proteger y mantener las máquinas virtuales requieren mucho más tiempo y experiencia en TI en comparación con el uso de los servicios de PaaS de Azure. Si está pensando en máquinas virtuales de Azure, asegúrese de tener en cuenta la intervención de un mantenimiento continuado necesaria para aplicar la revisión, actualizar y administrar su entorno de máquinas virtuales. Máquinas virtuales de Azure es IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Usar migrar de Azure para analizar y migrar las aplicaciones existentes a Azure

Migración a la nube no tiene que ser difícil. Aunque muchas organizaciones tienen dificultades para empezar a trabajar: para obtener una profunda visibilidad en el entorno y la estrecha interdependencias entre las aplicaciones, las cargas de trabajo y los datos. Sin esa visibilidad, puede ser difícil planear la ruta de acceso. Sin información detallada sobre lo que se necesita para una migración correcta, no puede tener el derecho conversaciones dentro de su organización. No sabe lo suficiente acerca de los posibles costes ventajas, o si las cargas de trabajo podrían simplemente elevación-y-MAYÚS o requerirían modificaciones importantes para migrar correctamente. No es de extrañar que muchas organizaciones dudan.

[Migrar Azure](https://aka.ms/azuremigrate) es un nuevo servicio que proporciona la orientación, visión y los mecanismos necesarios para ayudarle a migrar a Azure. Migrar de Azure proporciona:

- Detección y evaluación de las máquinas virtuales locales

- Asignación de dependencia integradas para la detección de confianza alta de aplicaciones de varios niveles

- Inteligente adquirir un tamaño adecuado para máquinas virtuales de Azure

- Informes con instrucciones para aplicar posibles problemas de compatibilidad

- Integración con el servicio de administración de base de datos de Azure para la detección de base de datos y migración

Migrar de Azure proporciona la confianza que las cargas de trabajo pueden migrar con un impacto mínimo en la empresa y se ejecutan según lo esperado en Azure. Con las herramientas adecuadas e instrucciones, puede lograr el máximo rendimiento de la inversión mientras se asegura de que el rendimiento crítico y se cumplen las necesidades de confiabilidad.

Figura 2-2 se muestra la asignación de dependencia integrados para todas las conexiones de servidor y la aplicación realizadas la migración de Azure.

![Posición de aplicaciones de uso de infraestructura de nube](./media/image2-2.png)

> **Figura 2-2.** Posición de aplicaciones de uso de infraestructura de nube

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Usar Azure Site Recovery para migrar las máquinas virtuales existentes a máquinas virtuales de Azure

Como parte de end-to-end [Azure migrar](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) es una herramienta que puede usar para migrar fácilmente las aplicaciones web a las máquinas virtuales en Azure. Puede usar Site Recovery para replicar máquinas virtuales locales y servidores físicos en Azure, o para replicarlas a una ubicación local secundario. Incluso puede replicar una carga de trabajo que se ejecuta en una VM de Azure compatible, en una implementación local *Hyper-V* VM, en un *VMware* máquina virtual, o en un servidor físico de Windows o Linux. La replicación a Azure elimina el costo y la complejidad que supone mantener un centro de datos secundaria.

También se realiza la recuperación de sitio específicamente para entornos híbridos que son parte local y en parte en Azure. Site Recovery le ayuda a garantizar la continuidad empresarial manteniendo las aplicaciones que se ejecutan en máquinas virtuales y físicos servidores locales disponibles si un sitio deja de funcionar. Replica las cargas de trabajo que se ejecutan en máquinas virtuales y servidores físicos para que sigan estando disponibles en una ubicación secundaria si el sitio primario no está disponible. Recupera las cargas de trabajo para el sitio primario cuando está en funcionamiento y vuelva a ejecutar.

Figura 2-3 muestra la ejecución de varias migraciones de máquinas virtuales mediante el uso de Azure Site Recovery.

![Posición de aplicaciones de uso de infraestructura de nube](./media/image2-3.png)

> **Figura 2-3.** Posición de aplicaciones de uso de infraestructura de nube

### <a name="additional-resources"></a>Recursos adicionales

- **Hoja de datos de migración de Azure**

    [https://aka.ms/azuremigration\_Hoja de datos](https://aka.ms/azuremigration\_datasheet)

- **Migrar de Azure**

    [http://azuremigrationcenter.com/](http://azuremigrationcenter.com/)

- **Migrar a Azure con Site Recovery**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

- **Introducción al servicio Azure Site Recovery**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-overview](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

- **Migrar máquinas virtuales en AWS para máquinas virtuales de Azure**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
[Anterior](index.md)
[Siguiente](migrate-your-relational-databases-to-azure.md)
