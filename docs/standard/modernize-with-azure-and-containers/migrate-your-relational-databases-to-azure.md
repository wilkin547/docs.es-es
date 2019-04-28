---
title: Migrar bases de datos relacionales a azure
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | migrar bases de datos relacionales a azure
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 600c47b6b0ccaf704c8e7b638c759e990acaaacf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61812793"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Migrar bases de datos relacionales a azure

Visión: Azure ofrece la migración de base de datos más completa.

En Azure, puede migrar los servidores de base de datos directamente a máquinas virtuales de IaaS (puro levantar y mover) o puede migrar a Azure SQL Database, para obtener más ventajas. La base de datos de SQL Azure ofrece opciones de completa base de datos como-servicio (DBaaS) y de instancia administrada. Figura 3-1 se muestra la base de datos relacional varias rutas de acceso de migración disponibles en Azure.

![Rutas de migración de base de datos en Azure](./media/image3-1.png)

> **Figura 3-1.** Rutas de migración de base de datos en Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Cuándo realizar la migración a instancia administrada de Azure SQL Database

En la mayoría de los casos, la instancia administrada de Azure SQL Database será la mejor opción a tener en cuenta al migrar los datos en Azure. Si va a migrar las bases de datos de SQL Server y necesita casi 100% seguros que no es necesario rediseñar su aplicación o realizar cambios en los datos o código de acceso a datos, elija la característica de instancia administrada de Azure SQL Database.

Instancia administrada de Azure SQL Database es la mejor opción si tiene requisitos adicionales para la funcionalidad de nivel de instancia de SQL Server o los requisitos de aislamiento más allá de las características proporcionadas en Azure SQL Database (modelo de base de datos única) estándar. Este último es la elección más orientado a PaaS, pero no ofrece las mismas características que el de un servidor SQL tradicional. Migración, es posible que surja fricción.

Por ejemplo, una organización que ha realizado grandes inversiones en las capacidades de SQL Server de nivel de instancia se beneficiaría de migración a instancia administrada de SQL. Algunos ejemplos de las capacidades de SQL Server de nivel de instancia son SQL integración common language runtime (CLR), Agente SQL Server y entre bases de datos realizar consultas. Compatibilidad con estas características no está disponible en Azure SQL Database estándar (un modelo de base de datos única).

Una organización que opere en un sector extremadamente regulado, y que necesita mantener el aislamiento por motivos de seguridad, también podría beneficiarse de la elección del modelo de instancia administrada de SQL.

Instancia administrada de Azure SQL Database tiene las siguientes características:

- Aislamiento de seguridad a través de Azure Virtual Network

- Compatibilidad de superficie de aplicaciones, con estas características:

  - Agente SQL Server y SQL Server Profiler

  - La replicación entre bases de datos de las referencias y las consultas, CLR de SQL, captura de datos modificados (CDC) y Service Broker

- Tamaños de base de datos hasta 35 TB

- Migración de tiempo de inactividad mínimo, con estas características:

  - Azure Database Migration Service

  - El trasvase de registros y restauración y copia de seguridad nativa

Con estas capacidades, al migrar las bases de datos de aplicación existente a Azure SQL Database, el modelo de instancia administrada ofrece casi el 100% de las ventajas de PaaS de SQL Server. Instancia administrada es un entorno de SQL Server donde seguir usando capacidades de nivel de instancia sin cambiar el diseño de aplicaciones.

Instancia administrada es probablemente la mejor opción para las empresas que actualmente está utilizando SQL Server, y que requieren flexibilidad en su seguridad de red en la nube. Es como tener una red privada virtual para las bases de datos SQL.

## <a name="when-to-migrate-to-azure-sql-database"></a>Cuándo realizar la migración a Azure SQL Database

Como se mencionó, la base de datos de SQL de Azure estándar es un DBaaS totalmente administrado y relacionales. Actualmente, SQL Database administra millones de bases de datos de producción, en 38 centros de datos, todo el mundo. Admite una amplia gama de aplicaciones y cargas de trabajo, desde sencillos datos transaccionales, para impulsar las aplicaciones críticas con muchos más datos que requieren procesamiento avanzado de datos a escala global de administración.

Debido a sus características de PaaS completas, mejores precios- y en última instancia, reducir el costo-debe mover la base de datos de SQL de Azure estándar como la "opción de forma predeterminada" Si tiene una aplicación que usa básico, estándar SQL bases de datos y ninguna característica de instancia adicional. No se admiten las características de SQL Server, como la integración CLR de SQL, Agente SQL Server y realizar consultas entre bases de datos en la base de datos de SQL de Azure estándar. Estas características solo están disponibles en el modelo de instancia administrada de Azure SQL Database.

Azure SQL Database es el servicio de base de datos en la nube solo inteligente que se ha creado para los desarrolladores de aplicaciones. También es el único servicio de base de datos en la nube que se escala sobre la marcha, sin tiempo de inactividad, que le ayudarán a entrega eficaz de aplicaciones para varios inquilinos. En última instancia, base de datos de SQL Azure deja más tiempo para innovar y acelera el tiempo de comercialización. Puede crear aplicaciones seguras y conectarse a la base de datos SQL mediante el uso de los lenguajes y plataformas que prefiera.

Azure SQL Database ofrece las siguientes ventajas:

- Inteligencia integrada (aprendizaje automático) que aprende y se adapta a la aplicación

- Aprovisionamiento de la base de datos y a petición

- Una gama de ofertas para todas las cargas de trabajo

- disponibilidad del 99,99% SLA, un mantenimiento prácticamente inexistente

- Servicios de replicación geográfica y restauración para la protección de datos

- Punto de base de datos de SQL Azure en función de restauración a un momento

- Compatibilidad con SQL Server 2016, incluido híbridas y migración

La base de datos de SQL de Azure estándar está más cerca de PaaS que instancia administrada de Azure SQL Database. Prefiere la base de datos de SQL de Azure estándar porque obtendrá más beneficios de una nube administrada. Sin embargo, Azure SQL Database presenta algunas diferencias claves normales locales y en instancias de SQL Server. Según los requisitos de base de datos de la aplicación existente y los requisitos de enterprise y las directivas, no sería la mejor opción cuando planee su migración a la nube.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Cuando se mueve el RDBMS original a una máquina virtual (IaaS)

Una de las opciones de migración es mover el original sistema de administración de bases de datos relacionales (RDBMS), como Oracle, IBM DB2, MySQL, PostgreSQL o SQL Server, a un servidor similar a la que se está ejecutando en una máquina virtual de Azure. Si tiene aplicaciones existentes que requieren la migración más rápida a la nube con unos cambios mínimos o ningún cambio en absoluto, una migración directa a IaaS en la nube podría ser una opción razonable. Podría no ser la mejor manera de aprovechar las ventajas de la de la nube, pero probablemente es la ruta de acceso inicial más rápido.

Actualmente, Microsoft Azure admite hasta [331 servidores de base de datos diferente](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) implementados como máquinas virtuales de IaaS. Estas incluyen RDBMS populares, como SQL Server, Oracle, MySQL, PostgreSQL e IBM DB2 y muchas otras bases de datos NoSQL como MongoDB, Cassandra, DataStax, Cloudera y MariaDB.

> [!NOTE]
> Aunque mover el RDBMS para una máquina virtual de Azure podría ser la manera más rápida de migrar los datos a la nube (porque es IaaS), este enfoque requiere una inversión importante en los equipos de TI (los administradores de base de datos y los profesionales de TI). Los equipos empresariales deben ser capaz de configurar y administrar alta disponibilidad, recuperación ante desastres y aplicación de revisiones para SQL Server. Este contexto también necesita un entorno personalizado con derechos administrativos completos.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Cuándo realizar la migración a SQL Server como una máquina virtual (IaaS)

Puede haber algunos casos donde todavía tiene que migrar a SQL Server como una máquina virtual normal. Un escenario de ejemplo es si necesita usar SQL Server Reporting Services. En la mayoría de los casos, sin embargo, la instancia administrada de Azure SQL Database puede proporcionar todo lo que necesita para migrar de servidores de SQL Server local, por lo que la migración a una máquina virtual de SQL Server debe ser el último recurso para probar.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Use Azure Database Migration Service para migrar las bases de datos relacionales a Azure 

Puede usar Azure Database Migration Service para migrar bases de datos relacionales como SQL Server, Oracle y MySQL a Azure, si la base de datos de destino es Azure SQL Database, instancia administrada de Azure SQL Database o SQL Server en una máquina virtual de Azure.

El flujo de trabajo automatizado, con los informes de evaluación, le guiará por los cambios que debe realizar antes de migrar la base de datos. Cuando esté listo, el servicio migra la base de datos de origen a Azure.

Cada vez que cambie un RDBMS original, es posible que deba volver a probar. También es posible que deba cambiar el código de asignación relacional de objetos (ORM) en la aplicación, dependiendo de los resultados de pruebas o frases SQL.

Si tiene cualquier otra base de datos (por ejemplo, IBM DB2) y opta por un enfoque de migración mediante lift- and -shift, es posible que desee continuar usando esas bases de datos como las máquinas virtuales de IaaS en Azure, a menos que esté dispuesto a realizar una migración de datos más compleja. Una migración más compleja de datos requiere un esfuerzo adicional ya que se desea migrar a un tipo diferente de la base de datos con el nuevo esquema y bibliotecas de programación diferentes.

Para obtener información sobre cómo migrar las bases de datos mediante el uso de Azure Database Migration Service, consulte [llegar a la nube más rápida con la instancia administrada de Azure SQL Database y Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Recursos adicionales

- **Elija una opción de SQL Server de la nube: Azure SQL Database (PaaS) o SQL Server en máquinas virtuales de Azure (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Llegar a la nube más rápida con la instancia administrada de Azure SQL DB y Database Migration Service**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **Migración de una base de datos de SQL Server a una instancia de SQL Database en la nube**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Azure SQL Database**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **SQL Server en máquinas virtuales**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [Anterior](lift-and-shift-existing-apps-azure-iaas.md)
> [Siguiente](modernize-existing-apps-to-cloud-optimized/index.md)
