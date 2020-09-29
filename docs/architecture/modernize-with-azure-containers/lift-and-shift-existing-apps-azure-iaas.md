---
title: Migración mediante lift-and-shift de aplicaciones de .NET existentes a la IaaS de Azure (listas para la infraestructura en la nube)
description: Modernización de aplicaciones de .NET existentes con Azure Cloud y contenedores Windows
ms.date: 04/28/2018
ms.openlocfilehash: d610222aa6649c1b28e198c074794dd316f895ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172175"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a>Migración mediante lift-and-shift de aplicaciones de .NET existentes a la IaaS de Azure (listas para la infraestructura en la nube)

> Visión: El primer paso para reducir la inversión local y el costo total del mantenimiento del hardware y la red es volver a hospedar las aplicaciones existentes en la nube.

Antes de entrar en *cómo* migrar las aplicaciones existentes a la plataforma de infraestructura como servicio (IaaS) de Azure, es importante analizar los motivos *por los que* desea migrar directamente a la IaaS de Azure. El escenario en este nivel de madurez de modernización consiste básicamente en empezar a usar máquinas virtuales en la nube en lugar de seguir usando la infraestructura local actual.

Otro punto para analizar es *por qué* podría querer hacer una migración tal cual a la nube de IaaS en lugar de agregar servicios administrados más avanzados en Azure. Determine en qué casos podría ser necesaria la IaaS en primer lugar.

La figura 2-1 coloca las aplicaciones preparadas para la infraestructura en la nube en los niveles de madurez de modernización:

![Posicionamiento de las aplicaciones listas para la infraestructura en la nube](./media/image2-1.png)

**Figura 2-1.** Posicionamiento de las aplicaciones listas para la infraestructura en la nube

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>Por qué migrar las aplicaciones web de .NET existentes a la IaaS de Azure

La razón principal para migrar a la nube, incluso en un nivel inicial de IaaS, es lograr una reducción de los costos. Mediante el uso de servicios de infraestructura más administrados, su organización puede reducir la inversión en mantenimiento de hardware, aprovisionamiento e implementación de servidores o máquinas virtuales, y administración de la infraestructura.

Después de tomar la decisión de trasladar sus aplicaciones a la nube, el motivo principal por el que podría elegir IaaS en lugar de opciones más avanzadas, como PaaS, es simplemente que el entorno de IaaS le resultará más familiar. El cambio a un entorno similar al entorno local actual ofrece una curva de aprendizaje más baja, lo que la convierte en la ruta más rápida a la nube.

Sin embargo, tomar la ruta de acceso más rápida a la nube no significa sacar el máximo partido de la ejecución de aplicaciones en la nube. Cualquier organización obtendrá las ventajas más importantes de una migración en la nube en los niveles de madurez de los modelos optimizado para la nube y nativo de la nube.

También ha quedado claro que es más fácil modernizar y rediseñar las aplicaciones en el futuro cuando ya se están ejecutando en la nube, incluso en IaaS. Ya se ha logrado la migración de datos de aplicación. Además, su organización habrá obtenido las aptitudes necesarias para trabajar en la nube y cambiar la mentalidad a una "cultura de la nube".

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>Cuándo se debe migrar a IaaS en lugar de a PaaS

En las secciones siguientes se describen las aplicaciones optimizadas para la nube que se basan principalmente en plataformas y servicios de PaaS. Estas aplicaciones ofrecen el máximo beneficio de la migración a la nube.

Si su objetivo es simplemente trasladar las aplicaciones existentes a la nube, identifique primero las aplicaciones que no requieren una modificación sustancial para ejecutarse en Azure App Service. Estas aplicaciones deben ser las primeras candidatas para el modelo optimizado para la nube.

Después, migre a máquinas virtuales simples (IaaS) las aplicaciones que todavía no se pueden trasladar a contenedores Windows y PaaS, como App Service u orquestadores como Azure Kubernetes Service.

Sin embargo, tenga en cuenta que la configuración, la protección y el mantenimiento correctos de las máquinas virtuales requieren mucho más tiempo y conocimientos de TI en comparación con el uso de servicios de PaaS en Azure. Si está considerando la opción de Azure Virtual Machines, tenga en cuenta el esfuerzo constante de mantenimiento requerido para aplicar revisiones al entorno de la máquina virtual, así como para actualizarlo y administrarlo. Azure Virtual Machines es IaaS.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Uso de Azure Migrate para analizar y migrar las aplicaciones existentes a Azure

La migración a la nube no tiene que resultar difícil. Sin embargo, a muchas organizaciones les cuesta obtener una visibilidad detallada del entorno y las estrechas interdependencias entre las aplicaciones, las cargas de trabajo y los datos. Sin esa visibilidad, planear la ruta puede ser difícil. Si no se tiene información detallada sobre lo que se necesita para que la migración sea correcta, no se pueden mantener las conversaciones correctas dentro de la organización. No sabe lo suficiente sobre las posibles ventajas para los costos o si las cargas de trabajo se pueden migrar mediante lift-and-shift o se necesita una reelaboración importante para que la migración sea correcta. Indudablemente muchas organizaciones tienen dudas.

[Azure Migrate](https://aka.ms/azuremigrate) es un nuevo servicio que proporciona las instrucciones, la información y los mecanismos necesarios para ayudarle a migrar a Azure. Azure Migrate proporciona:

- Detección y evaluación de máquinas virtuales locales

- Asignación de dependencias integrada para una detección confiable de aplicaciones de multinivel

- Ajuste inteligente del tamaño de las máquinas virtuales de Azure

- Informes de compatibilidad con directrices para corregir posibles problemas

- Integración con el servicio Azure Database Management para la detección y migración de bases de datos

Con Azure Migrate, tiene la seguridad de que las cargas de trabajo se pueden migrar con un impacto mínimo para el negocio y que se ejecutarán según lo previsto en Azure. Con las herramientas y las instrucciones adecuadas, logrará el máximo rendimiento de la inversión a la vez que garantiza que se cumplan las necesidades críticas de rendimiento y confiabilidad.

En la figura 2-2 se muestra la asignación de dependencias integrada para todas las conexiones de servidor y aplicación realizadas por Azure Migrate.

![Posicionamiento de las aplicaciones listas para la infraestructura en la nube](./media/image2-2.png)

**Figura 2-2.** Posicionamiento de las aplicaciones listas para la infraestructura en la nube

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Uso de Azure Site Recovery para migrar las máquinas virtuales existentes a máquinas virtuales de Azure

Como parte de la solución integral [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](/azure/site-recovery/site-recovery-overview) es una herramienta que se puede usar para migrar fácilmente las aplicaciones web a máquinas virtuales de Azure. Puede usar Site Recovery para replicar máquinas virtuales locales y servidores físicos en Azure, o para replicarlos en una ubicación local secundaria. Incluso puede replicar una carga de trabajo que se ejecuta en una máquina virtual de Azure compatible, en una máquina virtual de *Hyper-V* local, en una máquina virtual de *VMware* o en un servidor físico Windows o Linux. Si se replican en Azure, se elimina el costo y la complejidad de mantener un centro de datos secundario.

Site Recovery también es adecuado para entornos híbridos que tienen una parte en el entorno local y otra parte en Azure. Site Recovery ayuda a garantizar la continuidad empresarial, ya que mantiene las aplicaciones en funcionamiento tanto en las máquinas virtuales como en los servidores físicos locales disponibles si un sitio deja de funcionar. Replica las cargas de trabajo que se ejecutan en máquinas virtuales y servidores físicos para que estén disponibles en una ubicación secundaria si el sitio principal no está disponible. Recupera las cargas de trabajo en el sitio principal cuando vuelva a estar en funcionamiento.

En la figura 2-3 se muestra la ejecución de varias migraciones de máquinas virtuales mediante Azure Site Recovery.

![Posicionamiento de las aplicaciones listas para la infraestructura en la nube](./media/image2-3.png)

**Figura 2-3.** Posicionamiento de las aplicaciones listas para la infraestructura en la nube

### <a name="additional-resources"></a>Recursos adicionales

- **Hoja de datos de Azure Migrate**

    <https://aka.ms/azuremigration\_datasheet>

- **Azure Migrate**

    <https://aka.ms/azuremigrate>

- **Azure Migration Center**

    <https://azure.microsoft.com/migration/>

- **Migración a Azure con Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- **Introducción al servicio Azure Site Recovery**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- **Migración de máquinas virtuales de AWS a máquinas virtuales de Azure**

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](migrate-your-relational-databases-to-azure.md) <!-- Next Chapter -->
