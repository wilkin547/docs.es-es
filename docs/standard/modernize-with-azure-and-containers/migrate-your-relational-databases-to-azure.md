---
title: Migrar las bases de datos relacionales a azure
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | migrar las bases de datos relacionales a azure
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: fe1bf5820c2306beb380749b34d5a56964e016e4
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="migrate-your-relational-databases-to-azure"></a>Migrar las bases de datos relacionales a azure

Visión: Azure ofrece la migración de base de datos más completa.

En Azure, puede migrar los servidores de base de datos directamente a las máquinas virtuales de IaaS (elevación pura y MAYÚS), o puede migrar a base de datos de SQL Azure, para otras ventajas. La base de datos de SQL Azure ofrece instancia administrada y opciones de completa base de datos como-servicio (DBaaS). Figura 3-1 muestra la base de datos relacional varias rutas de acceso de migración disponibles en Azure.

![Rutas de migración de base de datos de Azure](./media/image3-1.png)

> **Figura 3-1.** Rutas de migración de base de datos de Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Cuándo se debe migrar a la instancia de base de datos administrada de SQL de Azure

En la mayoría de los casos, la instancia de base de datos administrada de SQL de Azure será la mejor opción para tener en cuenta al migrar los datos en Azure. Si va a migrar las bases de datos de SQL Server y necesita casi garantía de 100% que no tendrá que cambie la arquitectura de la aplicación o realizar cambios en los datos o el código de acceso de datos, elija la característica de instancia administrada de la base de datos de SQL Azure.

Instancia de administrados de la base de datos de SQL Azure es la mejor opción si tiene requisitos adicionales para la funcionalidad de nivel de instancia de SQL Server o requisitos de aislamiento más allá de las características proporcionadas en una base de datos estándar SQL de Azure (modelo de base de datos única). Esta última de ellas es la opción más orientados a PaaS, pero que no ofrece las mismas características que la de un servidor SQL tradicional. Migración podría expuesta frictions.

Por ejemplo, una organización que ha realizado fuertes inversiones en las capacidades de SQL Server de nivel de instancia se beneficiaría de la migración a la instancia administrada de SQL. Algunos ejemplos de las capacidades de SQL Server de nivel de instancia son SQL integración common language runtime (CLR), Agente SQL Server y entre bases de datos realizar consultas. Compatibilidad con estas características no está disponible en Azure SQL Database estándar (un modelo de base de datos única).

Una organización que opera en un sector altamente regulado y que necesitan mantener el aislamiento por motivos de seguridad, también puede beneficiarse de elegir el modelo de instancia administrada de SQL.

Instancia administrada en la base de datos de SQL Azure tiene las siguientes características:

- Aislamiento de seguridad a través de la red Virtual de Azure

- Compatibilidad de superficie de aplicación, con estas características:

  - Agente SQL Server y SQL Server Profiler

  - La replicación entre bases de datos de las referencias y las consultas, CLR de SQL y captura de datos modificados (CDC), Service Broker

- Cambia el tamaño de base de datos hasta 35 TB

- Migración de tiempo de inactividad mínimo, con estas características:

  - Servicio de migración de base de datos de Azure

  - Native copias de seguridad y restauración y el trasvase de registros

Con estas funcionalidades, al migrar las bases de datos de aplicación existente a base de datos de SQL Azure, el modelo de instancia administrada ofrece casi el 100% de las ventajas de Paas para SQL Server. Instancia administrada es un entorno de SQL Server donde, seguir usando las capacidades de nivel de instancia sin cambiar el diseño de aplicaciones.

Instancia administrada es probablemente la mejor opción para las empresas que actualmente está usando SQL Server, y que requieren flexibilidad en la seguridad de red en la nube. Es como tener una red privada virtual para las bases de datos SQL.

## <a name="when-to-migrate-to-azure-sql-database"></a>Cuándo se debe migrar a base de datos de SQL Azure

Como se mencionó, la base de datos de SQL de Azure estándar es un DBaaS completamente administrado y relacionales. Base de datos SQL actualmente administra millones de bases de datos de producción, en centros de 38 datos, todo el mundo. Admite una amplia gama de aplicaciones y cargas de trabajo, de la administración de los datos transaccionales sencillos, para controlar las aplicaciones de misión crítica, de uso más intensivo de datos que requieren procesamiento avanzado de datos en una escala global.

Debido a sus características completas de PaaS, mejor precios- y en última instancia menor costo-debe mover la base de datos de SQL de Azure estándar como "de forma predeterminada prefiera" Si tiene una aplicación que usa básico, estándar SQL bases de datos y ninguna característica de instancia adicional. Características de SQL Server como la integración CLR de SQL, Agente SQL Server y realizar consultas entre bases de datos no se admiten en la base de datos de SQL de Azure estándar. Estas características solo están disponibles en el modelo de instancia de base de datos administrada de SQL de Azure.

La base de datos de SQL Azure es el servicio de base de datos de nube solo inteligente que se ha diseñado para los desarrolladores de aplicaciones. También es el único servicio de base de datos en la nube que admita la ampliación sobre la marcha, sin tiempo de inactividad, que le ayudarán a distribuir aplicaciones para varios inquilinos de manera eficaz. En última instancia, base de datos de SQL Azure, queda más tiempo para innovar y acelera el tiempo de comercialización. Puede crear aplicaciones seguras y conéctese a la base de datos SQL mediante el uso de los lenguajes y plataformas que prefiera.

La base de datos de SQL Azure ofrece las siguientes ventajas:

- Inteligencia incorporada (aprendizaje automático) que aprende y se adapta a la aplicación

- Aprovisionamiento de la base de datos a petición

- Un intervalo de ofertas, para todas las cargas de trabajo

- disponibilidad del 99,99% SLA, cero mantenimiento

- Servicios de replicación geográfica y restauración para la protección de datos

- Punto de base de datos de SQL Azure en la característica de restauración a un momento

- Compatibilidad con SQL Server 2016, incluidos híbrida y migración

La base de datos de SQL de Azure estándar está más cerca de PaaS que la instancia de base de datos administrada de SQL de Azure. Prefieren la base de datos de SQL de Azure estándar porque obtendrá ventajas más de una nube administrada. Sin embargo, base de datos de SQL Azure presenta algunas diferencias claves normales y las instancias de SQL Server local. Dependiendo de los requisitos de la base de datos de la aplicación existente y los requisitos de empresa y directivas, no sería la mejor opción cuando planee la migración a la nube.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Cuándo se debe pasar el RDBMS original a una máquina virtual (IaaS)

Una de las opciones de migración es mover el original sistema de administración de bases de datos relacionales (RDBMS), entre otras, Oracle, IBM DB2, MySQL, PostgreSQL o SQL Server, un servidor similar a la que se ejecuta en una VM de Azure. Si tiene aplicaciones existentes que requieren la migración más rápida a la nube con unos cambios mínimos o ningún cambio en absoluto, una migración directa a IaaS en la nube podría ser una opción razonable. Es posible que no sea la mejor manera de aprovechar las ventajas de la de la nube, pero probablemente es la ruta de acceso inicial más rápida.

En la actualidad, Microsoft Azure admite hasta [331 servidores de base de datos diferente](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) implementados como máquinas virtuales de IaaS. Esto incluye RDBMS populares como SQL Server, Oracle, MySQL, PostgreSQL e IBM DB2 y muchas otras bases de datos NoSQL como MongoDB, Casandra, DataStax, MariaDB y Cloudera.

> [!NOTE]
> Aunque mover el RDBMS para una VM de Azure puede ser la manera más rápida para migrar los datos a la nube (porque está IaaS), este enfoque requiere una inversión importante en los equipos de TI (administradores de base de datos y los profesionales de TI). Los equipos de la empresa necesitan poder configurar y administrar la aplicación de revisiones de SQL Server, alta disponibilidad y recuperación ante desastres. Este contexto también necesita un entorno personalizado, con derechos administrativos completos.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Cuándo realizar la migración a SQL Server como una máquina virtual (IaaS)

Puede haber algunos casos donde todavía tiene que migrar a SQL Server como una máquina virtual regular. Un escenario de ejemplo es si necesita usar SQL Server Reporting Services. En la mayoría de los casos, sin embargo, la instancia administrada de Azure SQL base de datos puede proporcionar todo lo que necesita para migrar de servidores de SQL Server local, por lo que la migración a una VM de SQL Server debe ser el último recurso para probar.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Usar el servicio de migración de base de datos de Azure para migrar las bases de datos relacionales a Azure 

Puede usar el servicio de migración de base de datos de Azure para migrar bases de datos relacional como SQL Server, Oracle y MySQL en Azure, si la base de datos de destino es la base de datos de SQL Azure, instancia de base de datos administrada de SQL de Azure o SQL Server en una máquina virtual de Azure.

El flujo de trabajo automatizado, con los informes de evaluación, le guía a través de los cambios que debe realizar antes de migrar la base de datos. Cuando esté listo, el servicio migra la base de datos de origen en Azure.

Cada vez que cambie un RDBMS original, debe volver a probar. También podrían necesitar cambiar el código de asignación relacional de objetos (ORM) en la aplicación, según los resultados de las pruebas o las sentencias SQL.

Si tiene cualquier otra base de datos (por ejemplo, IBM DB2) y optar por un enfoque elevar y cambiar, puede seguir usando esas bases de datos como las máquinas virtuales de IaaS en Azure, a menos que esté dispuesto a realizar una migración de datos más compleja. Una migración de datos más compleja requerirán un esfuerzo adicional porque podría migrar a un tipo diferente de la base de datos con el nuevo esquema y las bibliotecas de programación diferentes.

Para obtener información sobre cómo migrar las bases de datos mediante el servicio de migración de base de datos de Azure, consulte [llegar a la nube más rápida con la instancia de base de datos administrada de SQL de Azure y el servicio de migración de base de datos de Azure](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Recursos adicionales

- **Elija una opción de SQL Server de la nube: base de datos de SQL de Azure (PaaS) o SQL Server en la máquina virtual de Azure (IaaS)**

    [https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas)

- **Obtener en la nube más rápida con la instancia administrada de Azure SQL DB y el servicio de migración de base de datos**

    [https://channel9.msdn.com/Events/Build/2017/P4008](https://channel9.msdn.com/Events/Build/2017/P4008)

- **Migración de base de datos de SQL Server para la base de datos de SQL en la nube**

    [https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate](https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate)

- **Azure SQL Database**

    [https://azure.microsoft.com/services/sql-database/?v=16.50](https://azure.microsoft.com/services/sql-database/?v=16.50)

- **SQL Server en máquinas virtuales**

    [https://azure.microsoft.com/services/virtual-machines/sql-server/](https://azure.microsoft.com/services/virtual-machines/sql-server/)

>[!div class="step-by-step"]
[Anterior](lift-and-shift-existing-apps-azure-iaas.md)
[Siguiente](modernize-existing-apps-to-cloud-optimized/index.md)