---
title: Migre sus bases de datos relacionales a Azure
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Migre sus bases de datos relacionales a Azure
ms.date: 04/28/2018
ms.openlocfilehash: 3d4f03e61144bb6a442a50916d7fd024d38ec611
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69578378"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Migre sus bases de datos relacionales a Azure

Visión: Azure ofrece la migración de bases de datos más completa.

En Azure, puede migrar los servidores de bases de datos directamente a las máquinas virtuales de IaaS (elevación y desplazamiento puros), o puede migrar a Azure SQL Database para obtener ventajas adicionales. Azure SQL Database ofrece una instancia administrada y opciones completas de base de datos como servicio (DBaaS). En la figura 3-1 se muestran las diversas rutas de acceso de migración de bases de datos relacionales disponibles en Azure.

![Rutas de migración de bases de datos en Azure](./media/image3-1.png)

> **Figura 3-1.** Rutas de migración de bases de datos en Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Cuándo migrar a Instancia administrada de Azure SQL Database

En la mayoría de los casos, Instancia administrada de Azure SQL Database será la mejor opción para tener en cuenta al migrar los datos a Azure. Si va a migrar bases de datos de SQL Server y necesita casi un 100% de seguridad que no necesitará para rediseñar la aplicación ni realizar cambios en los datos o el código de acceso a datos, elija la característica Instancia administrada de Azure SQL Database.

Instancia administrada de Azure SQL Database es la mejor opción si tiene requisitos adicionales para SQL Server funcionalidad de nivel de instancia o los requisitos de aislamiento más allá de las características proporcionadas en un Azure SQL Database estándar (modelo de base de datos única). Esta última es la opción más orientada a PaaS, pero no ofrece las mismas características que la de un servidor SQL Server tradicional. La migración podría mostrar fricción.

Por ejemplo, una organización que ha realizado inversiones profundas en las capacidades de SQL Server de nivel de instancia se beneficiaría de la migración a SQL Instancia administrada. Entre los ejemplos de funciones de SQL Server de nivel de instancia se incluyen integración de SQL Common Language Runtime (CLR), Agente SQL Server y consulta entre bases de datos. La compatibilidad con estas características no está disponible en Azure SQL Database estándar (un modelo de base de datos única).

Una organización que opere en un sector muy regulado y que necesite mantener el aislamiento por motivos de seguridad, también podría beneficiarse de elegir el modelo de Instancia administrada de SQL.

Instancia administrada en Azure SQL Database tiene las siguientes características:

- Aislamiento de seguridad a través de Azure Virtual Network

- Compatibilidad con la superficie de la aplicación, con estas características:

  - Agente SQL Server y SQL Server Profiler

  - Referencias y consultas entre bases de datos, SQL CLR, replicación, captura de datos modificados (CDC) y Service Broker

- Tamaños de base de datos de hasta 35 TB

- Migración de tiempo de inactividad mínimo, con estas características:

  - Azure Database Migration Service

  - Copias de seguridad y restauración nativas y trasvase de registros

Con estas funcionalidades, al migrar las bases de datos de aplicación existentes a Azure SQL Database, el modelo de Instancia administrada ofrece casi el 100% de las ventajas de PaaS para SQL Server. Instancia administrada es un entorno de SQL Server en el que se siguen usando capacidades de nivel de instancia sin cambiar el diseño de la aplicación.

Instancia administrada es probablemente la mejor opción para las empresas que usan actualmente SQL Server y que requieren flexibilidad en la seguridad de la red en la nube. Es como tener una red virtual privada para las bases de datos SQL.

## <a name="when-to-migrate-to-azure-sql-database"></a>Cuándo migrar a Azure SQL Database

Como se mencionó, el Azure SQL Database estándar es un DBaaS relacional totalmente administrado. Actualmente, SQL Database administra millones de bases de datos de producción, en varios centros de datos 38 en todo el mundo. Es compatible con una amplia gama de aplicaciones y cargas de trabajo, desde la administración de datos transaccionales directos hasta la mayoría de las aplicaciones críticas de gran uso de datos que requieren un procesamiento avanzado de datos a escala global.

Debido a sus características de PaaS completas, mejores precios y, en última instancia, el costo más bajo, debe pasar al Azure SQL Database estándar como su "opción predeterminada" Si tiene una aplicación que usa bases de datos SQL básicas y estándar, y no tiene características de instancia adicionales. No se admiten SQL Server características como la integración de SQL CLR, la Agente SQL Server y las consultas entre bases de datos en el Azure SQL Database estándar. Estas características solo están disponibles en el modelo de Instancia administrada de Azure SQL Database.

Azure SQL Database es el único servicio de base de datos en la nube inteligente que se ha creado para los desarrolladores de aplicaciones. También es el único servicio de base de datos en la nube que se escala sobre la marcha, sin tiempo de inactividad, para ayudarle a ofrecer aplicaciones multiinquilino de forma eficaz. En última instancia, Azure SQL Database le deja más tiempo para innovar y acelera el tiempo de comercialización. Puede crear aplicaciones seguras y conectarse a la base de datos SQL mediante los lenguajes y las plataformas que prefiera.

Azure SQL Database ofrece las siguientes ventajas:

- Inteligencia integrada (machine learning) que aprende y se adapta a su aplicación

- Aprovisionamiento de la base de datos a petición

- Un intervalo de ofertas para todas las cargas de trabajo

- SLA de disponibilidad del 99,99%, sin mantenimiento

- Servicios de replicación y restauración geográfica para la protección de datos

- Azure SQL Database característica de restauración a un momento dado

- Compatibilidad con SQL Server 2016, incluido el híbrido y la migración

El Azure SQL Database estándar está más cerca de PaaS que Instancia administrada de Azure SQL Database. Prefiera el Azure SQL Database estándar porque obtendrá más ventajas de una nube administrada. Sin embargo, Azure SQL Database tiene algunas diferencias clave de las instancias de SQL Server normales y locales. En función de los requisitos de base de datos de la aplicación existente y de sus requisitos y directivas de la empresa, es posible que no sea la mejor opción cuando Planee la migración a la nube.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Cuándo trasladar el RDBMS original a una máquina virtual (IaaS)

Una de las opciones de migración consiste en trasladar el sistema de administración de bases de datos relacionales (RDBMS) original, como Oracle, IBM DB2, MySQL, PostgreSQL o SQL Server, a un servidor similar que se ejecuta en una máquina virtual de Azure. Si tiene aplicaciones existentes que requieren la migración más rápida a la nube con cambios mínimos o ningún cambio, una migración directa a IaaS en la nube puede ser una opción equitativa. Es posible que no sea la mejor manera de aprovechar todas las ventajas de la nube, pero probablemente es la ruta de acceso inicial más rápida.

Actualmente, Microsoft Azure admite hasta [331 servidores de bases de datos diferentes](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) implementados como máquinas virtuales IaaS. Entre ellas se incluyen RDBMS populares, como SQL Server, Oracle, MySQL, PostgreSQL e IBM DB2, y muchas otras bases de datos NoSQL, como MongoDB, Cassandra, DataStax, MariaDB y Cloudera.

> [!NOTE]
> Aunque el traslado de RDBMS a una máquina virtual de Azure puede ser la manera más rápida de migrar los datos a la nube (porque es IaaS), este enfoque requiere una inversión significativa en los equipos de ti (administradores de bases de datos y profesionales de TI). Los equipos empresariales deben tener la capacidad de configurar y administrar la alta disponibilidad, la recuperación ante desastres y la revisión para SQL Server. Este contexto también necesita un entorno personalizado, con derechos administrativos completos.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Cuándo migrar a SQL Server como una máquina virtual (IaaS)

Puede haber algunos casos en los que todavía tenga que migrar a SQL Server como una máquina virtual normal. Un escenario de ejemplo es si necesita usar SQL Server Reporting Services. Sin embargo, en la mayoría de los casos, Instancia administrada de Azure SQL Database puede proporcionar todo lo que necesita para migrar desde servidores SQL Server locales, por lo que la migración a una máquina virtual SQL Server debe ser el último recurso para probarlo.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Usar Azure Database Migration Service para migrar las bases de datos relacionales a Azure 

Puede usar Azure Database Migration Service para migrar bases de datos relacionales como SQL Server, Oracle y MySQL a Azure, independientemente de si la base de datos de destino se Azure SQL Database, Instancia administrada de Azure SQL Database o SQL Server en una máquina virtual de Azure.

El flujo de trabajo automatizado, con informes de evaluación, le guía a través de los cambios que debe realizar antes de migrar la base de datos. Cuando esté listo, el servicio migrará la base de datos de origen a Azure.

Siempre que cambie un RDBMS original, es posible que tenga que reprobarlo. También es posible que necesite cambiar el código de la asignación relacional de objetos (ORM) o oraciones de SQL en la aplicación, en función de los resultados de las pruebas.

Si tiene alguna otra base de datos (por ejemplo, IBM DB2) y opta por un enfoque de elevación y desplazamiento, puede que quiera seguir usando esas bases de datos como máquinas virtuales IaaS en Azure, a menos que esté dispuesto a realizar una migración de datos más compleja. Una migración de datos más compleja requerirá un esfuerzo adicional, ya que se va a migrar a un tipo de base de datos diferente con el nuevo esquema y las distintas bibliotecas de programación.

Para obtener información sobre cómo migrar bases de datos mediante Azure Database Migration Service, consulte [obtención de la nube más rápido con instancia administrada de Azure SQL Database y Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Recursos adicionales

- **Elija una opción de SQL Server en la nube: Azure SQL Database (PaaS) o SQL Server en máquinas virtuales de Azure (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Obtenga acceso a la nube más rápido con Azure SQL Database Instancia administrada y Database Migration Service**

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
