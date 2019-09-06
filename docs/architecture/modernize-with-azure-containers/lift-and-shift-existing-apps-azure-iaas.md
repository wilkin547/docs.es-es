---
title: Elevación y desplazamiento de las aplicaciones .NET existentes a IaaS de Azure (lista para la infraestructura de la nube)
description: Modernice las aplicaciones .NET existentes con los contenedores de Windows y la nube de Azure.
ms.date: 04/28/2018
ms.openlocfilehash: ae181784e7de5f66b34d2dc38c6e9ec2e004a0c3
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373983"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Elevación y desplazamiento de las aplicaciones .NET existentes a IaaS de Azure (lista para la infraestructura de la nube)

> Visión: Como primer paso, para reducir la inversión local y el costo total del mantenimiento del hardware y de la red, solo tiene que volver a hospedar las aplicaciones existentes en la nube.

Antes de empezar *a* migrar las aplicaciones existentes a la plataforma de infraestructura como servicio (IaaS) de Azure, es importante analizar las razones *por* las que desea migrar directamente a IaaS en Azure. El escenario de este nivel de madurez de modernización básicamente es empezar a usar las máquinas virtuales en la nube, en lugar de seguir usando la infraestructura local actual.

Otro punto para analizar es el *motivo por* el que podría querer migrar a la nube de IaaS pura en lugar de agregar simplemente servicios administrados más avanzados en Azure. Determine qué casos pueden requerir IaaS en primer lugar.

La figura 2-1 coloca las aplicaciones preparadas para la infraestructura de nube en los niveles de madurez de modernización:

![Posicionamiento de aplicaciones listas para la infraestructura de nube](./media/image2-1.png)

**Figura 2-1.** Posicionamiento de aplicaciones listas para la infraestructura de nube

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Por qué migrar aplicaciones Web .NET existentes a IaaS de Azure

La razón principal para migrar a la nube, incluso en el nivel inicial de IaaS, es lograr reducciones de costos. Mediante el uso de servicios de infraestructura más administrados, su organización puede reducir su inversión en el mantenimiento de hardware, el aprovisionamiento e implementación de servidores o máquinas virtuales y la administración de la infraestructura.

Después de tomar la decisión de trasladar sus aplicaciones a la nube, el motivo principal por el que podría elegir IaaS en lugar de opciones más avanzadas, como PaaS, es simplemente que el entorno de IaaS le resulte más familiar. El cambio a un entorno similar al entorno local actual ofrece una curva de aprendizaje más baja, lo que lo convierte en la ruta más rápida a la nube.

Sin embargo, si se toma la ruta de acceso más rápida a la nube no significa que se saque el máximo partido de hacer que las aplicaciones se ejecuten en la nube. Cualquier organización obtendrá las ventajas más importantes de una migración en la nube en los niveles de madurez de la nube y los que ya se han optimizado para la nube.

También ha resultado evidente que las aplicaciones son más fáciles de modernizar y rediseñar en el futuro cuando ya se están ejecutando en la nube, incluso en IaaS. Ya se ha logrado la migración de datos de aplicación. Además, su organización habrá obtenido los conocimientos necesarios para trabajar en la nube y realizar el cambio de funcionamiento en una "referencia cultural de la nube".

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Cuándo migrar a IaaS en lugar de a PaaS

En las secciones siguientes se describen las aplicaciones optimizadas para la nube que se basan principalmente en plataformas y servicios PaaS. Estas aplicaciones ofrecen el máximo beneficio de la migración a la nube. 

Si su objetivo es simplemente trasladar las aplicaciones existentes a la nube, identifique primero las aplicaciones existentes que no requieren la modificación sustancial para que se ejecuten en Azure App Service. Estas aplicaciones deben ser las primeras candidatas para la optimización para la nube. 

A continuación, en el caso de las aplicaciones que todavía no se pueden trasladar a contenedores de Windows y PaaS, como App Service o orquestadores como Azure Kubernetes Service, migre los a las máquinas virtuales sencillas simples (IaaS). 

Sin embargo, tenga en cuenta que la configuración, la protección y el mantenimiento correctos de las máquinas virtuales requiere mucho más tiempo y experiencia de TI en comparación con el uso de servicios de PaaS en Azure. Si está pensando en Azure Virtual Machines, asegúrese de tener en cuenta el esfuerzo de mantenimiento continuo necesario para aplicar revisiones, actualizar y administrar su entorno de máquinas virtuales. Azure Virtual Machines es IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Usar Azure Migrate para analizar y migrar las aplicaciones existentes a Azure

No es necesario migrar a la nube. Pero muchas organizaciones luchan por empezar a obtener visibilidad profunda en el entorno y las estrechas interdependencias entre las aplicaciones, las cargas de trabajo y los datos. Sin esa visibilidad, puede ser difícil planear la ruta de acceso hacia delante. Sin información detallada sobre lo que se necesita para una migración correcta, no puede tener las conversaciones correctas dentro de la organización. No sabe lo suficiente sobre las ventajas potenciales de los costos o si las cargas de trabajo solo podrían levantarse y cambiarse o requeriría un retrabajo significativo para migrar correctamente. No dude en muchas organizaciones.

[Azure Migrate](https://aka.ms/azuremigrate) es un nuevo servicio que proporciona instrucciones, información y mecanismos necesarios para ayudarle a migrar a Azure. Azure Migrate proporciona:

- Detección y evaluación de máquinas virtuales locales

- Asignación de dependencias integrada para la detección de alta confianza de aplicaciones de niveles múltiples

- Ajuste del tamaño de forma inteligente a Azure virtual machines

- Informes de compatibilidad con directrices para corregir posibles problemas

- Integración con el servicio Azure Database Management para la detección y migración de bases de datos

Azure Migrate le da la seguridad de que las cargas de trabajo se pueden migrar con un impacto mínimo en el negocio y ejecutarse según lo previsto en Azure. Con las herramientas y las instrucciones adecuadas, puede lograr el máximo rendimiento de la inversión a la vez que garantiza que se cumplan las necesidades críticas de rendimiento y confiabilidad.

En la figura 2-2 se muestra la asignación de dependencias integrada para todas las conexiones de servidor y aplicación realizadas por Azure Migrate.

![Posicionamiento de aplicaciones listas para la infraestructura de nube](./media/image2-2.png)

**Figura 2-2.** Posicionamiento de aplicaciones listas para la infraestructura de nube

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Uso de Azure Site Recovery para migrar las máquinas virtuales existentes a máquinas virtuales de Azure

Como parte de la [Azure Migrate](https://aka.ms/azuremigrate)de un extremo a otro, [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) es una herramienta que puede usar para migrar fácilmente las aplicaciones web a las máquinas virtuales de Azure. Puede usar Site Recovery para replicar máquinas virtuales locales y servidores físicos en Azure, o para replicarlos en una ubicación local secundaria. Incluso puede replicar una carga de trabajo que se ejecuta en una máquina virtual de Azure compatible, en una máquina virtual de *Hyper-V* local, en una máquina virtual de *VMware* o en un servidor físico de Windows o Linux. La replicación en Azure elimina el costo y la complejidad del mantenimiento de un centro de datos secundario.

Site Recovery también se crea específicamente para entornos híbridos que se encuentran en parte de forma local y en parte en Azure. Site Recovery ayuda a garantizar la continuidad empresarial manteniendo las aplicaciones que se ejecutan en máquinas virtuales y servidores físicos locales disponibles si un sitio deja de funcionar. Replica las cargas de trabajo que se ejecutan en máquinas virtuales y servidores físicos para que sigan estando disponibles en una ubicación secundaria si el sitio primario no está disponible. Recupera las cargas de trabajo en el sitio principal cuando está funcionando de nuevo.

En la figura 2-3 se muestra la ejecución de varias migraciones de máquinas virtuales mediante Azure Site Recovery.

![Posicionamiento de aplicaciones listas para la infraestructura de nube](./media/image2-3.png)

**Figura 2-3.** Posicionamiento de aplicaciones listas para la infraestructura de nube

### <a name="additional-resources"></a>Recursos adicionales

- **Azure Migrate hoja de comentarios**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Azure Migration Center**

    <https://azure.microsoft.com/migration/>

- **Migre a Azure con Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Información general del servicio Azure Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **Migración de máquinas virtuales en AWS a máquinas virtuales de Azure**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](migrate-your-relational-databases-to-azure.md) <!-- Next Chapter -->
