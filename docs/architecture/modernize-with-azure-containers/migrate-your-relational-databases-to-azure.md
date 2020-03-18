---
title: Migración de las bases de datos relacionales a Azure
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Migración de las bases de datos relacionales a Azure
ms.date: 04/28/2018
ms.openlocfilehash: efd1548c3f74fc27450f4949d71a1c4d61907ba5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73093611"
---
# <a name="migrate-your-relational-databases-to-azure"></a>Migración de las bases de datos relacionales a Azure

Visión: Azure ofrece la migración más completa de las bases de datos.

En Azure, puede migrar los servidores de bases de datos directamente a máquinas virtuales IaaS (método lift-and-shift puro) o puede migrarlos a Azure SQL Database para obtener ventajas adicionales. Azure SQL Database ofrece instancia administrada y opciones completas de base de datos como servicio (DBaaS). En la figura 3-1 se muestran las diversas rutas disponibles en Azure para la migración de bases de datos relacionales.

![Rutas de migración de bases de datos en Azure](./media/image3-1.png)

**Figura 3-1.** Rutas de migración de bases de datos en Azure

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Cuándo migrar a Instancia administrada de Azure SQL Database

En la mayoría de los casos, Instancia administrada de Azure SQL Database será la mejor opción a tener en cuenta al migrar los datos a Azure. Si va a migrar bases de datos SQL Server y necesita estar seguro casi al 100 % de que no necesitará rediseñar la aplicación ni realizar cambios en los datos o en el código de acceso a ellos, elija la característica Instancia administrada de Azure SQL Database.

Instancia administrada de Azure SQL Database es la mejor opción si tiene requisitos adicionales de funcionalidad de nivel de instancia de SQL Server o requisitos de aislamiento que no se satisfagan con las características proporcionadas en una instancia de Azure SQL Database (modelo de base de datos única). Esta última es la opción más orientada a PaaS, pero no ofrece las mismas características que un servidor SQL Server tradicional. La migración podría presentar fricciones.

Por ejemplo, una organización que ha realizado grandes inversiones en funcionalidades de SQL Server de nivel de instancia se beneficiará de la migración a Instancia administrada de SQL. Algunos de estas funcionalidades son la integración con Common Language Runtime (CLR) de SQL, Agente SQL Server y consulta entre bases de datos. La compatibilidad con estas características no está disponible en Azure SQL Database estándar (modelo de base de datos única).

Una organización que opere en un sector muy regulado y que necesite mantener el aislamiento por motivos de seguridad también podría beneficiarse de elegir el modelo de Instancia administrada de SQL.

Instancia administrada en Azure SQL Database tiene las siguientes características:

- Aislamiento de seguridad mediante Azure Virtual Network

- Compatibilidad con la superficie de la aplicación, con estas características:

  - Agente SQL Server y SQL Server Profiler

  - Referencias y consultas entre bases de datos, SQL CLR, replicación, captura de datos modificados (CDC) y Service Broker

- Tamaños de base de datos de hasta 35 TB

- Migración con tiempo de inactividad mínimo, con estas características:

  - Azure Database Migration Service

  - Copia de seguridad y restauración nativas y trasvase de registros

Con estas funcionalidades, al migrar las bases de datos de aplicación existentes a Azure SQL Database, el modelo de Instancia administrada ofrece prácticamente el 100 % de las ventajas de PaaS para SQL Server. Instancia administrada es un entorno SQL Server en el que se siguen usando funcionalidades de nivel de instancia sin cambiar el diseño de la aplicación.

Instancia administrada es probablemente la mejor opción para las empresas que usan actualmente SQL Server y que necesitan flexibilidad en la seguridad de la red en la nube. Es como tener una red virtual privada para las bases de datos SQL.

## <a name="when-to-migrate-to-azure-sql-database"></a>Cuándo realizar la migración a Azure SQL Database

Como se ha mencionado, Azure SQL Database estándar es una base de datos como servicio relacional totalmente administrada. SQL Database administra actualmente millones de bases de datos de producción, en 38 centro de datos de todo el mundo. Admite una amplia gama de aplicaciones y cargas de trabajo, desde la administración de datos transaccionales directos hasta el control de la mayoría de aplicaciones críticas que consumen muchos datos y que necesitan el procesamiento avanzado de estos a escala global.

Debido a las características PaaS completas, el mejor precio y, en última instancia, el costo reducido, haga la transición a Azure SQL Database estándar como "opción predeterminada" si tiene una aplicación que use bases de datos SQL estándar básicas y carezca de características de instancia adicionales. Características de SQL Server como la integración de SQL CLR, Agente SQL Server y la consulta entre bases de datos no se admiten en Azure SQL Database estándar. Estas características solo están disponibles en el modelo de Instancia administrada de Azure SQL Database.

Azure SQL Database es el único servicio de base de datos en la nube inteligente que se ha creado para los desarrolladores de aplicaciones. También es el único que se escala sobre la marcha, sin tiempo de inactividad, para ayudarle a entregar aplicaciones multiinquilino de forma eficaz. A la larga, Azure SQL Database deja más tiempo a la innovación y acelera el tiempo de comercialización. Puede crear aplicaciones seguras y conectarse a la base de datos SQL mediante los lenguajes y las plataformas que prefiera.

Azure SQL Database ofrece las siguientes ventajas:

- Inteligencia integrada (aprendizaje automático) que aprende y se adapta a la aplicación

- Aprovisionamiento de bases de datos a petición

- Gama de ofertas, para todas las cargas de trabajo

- SLA de disponibilidad del 99,99 %, sin mantenimiento

- Servicios de replicación y restauración geográfica para la protección de datos

- Característica de restauración de una base de datos de Azure SQL a un momento dado

- Compatibilidad con SQL Server 2016, que incluye funcionalidad híbrida y migración

Azure SQL Database estándar está más cerca de PaaS que de Instancia administrada de Azure SQL Database. Preferirá Azure SQL Database estándar porque obtendrá más ventajas de una nube administrada. Sin embargo, Azure SQL Database presenta algunas diferencias importantes con respecto a las instancias de SQL Server normales y locales. En función de los requisitos de base de datos de la aplicación existentes y de sus requisitos y directivas empresariales, puede que no sea la mejor opción cuando planee la migración a la nube.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>Cuándo mover el RDBMS original a una máquina virtual (IaaS)

Una de las opciones de migración consiste en mover el sistema de administración de bases de datos relacionales (RDBMS) original, como Oracle, IBM DB2, MySQL, PostgreSQL o SQL Server, a un servidor similar que se ejecuta en una máquina virtual de Azure. Si tiene aplicaciones existentes que deben migrarse más rápido a la nube con cambios mínimos o ningún cambio, la migración directa a IaaS en la nube puede ser una opción razonable. Puede que no sea la mejor manera de aprovechar todas las ventajas de la nube, pero sí la ruta de acceso inicial más rápida.

Actualmente, Microsoft Azure admite hasta [331 servidores de bases de datos diferentes](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) implementados como máquinas virtuales IaaS. Entre ellos se incluyen RDBMS populares, como SQL Server, Oracle, MySQL, PostgreSQL e IBM DB2, y muchas otras bases de datos NoSQL, como MongoDB, Cassandra, DataStax, MariaDB y Cloudera.

> [!NOTE]
> Aunque mover el RDBMS a una máquina virtual de Azure puede ser la manera más rápida de migrar los datos a la nube (puesto que es un enfoque IaaS), esta estrategia requiere una inversión importante en los equipos de TI (administradores de bases de datos y profesionales de TI). Los equipos empresariales deben tener la capacidad de configurar y administrar la alta disponibilidad, la recuperación ante desastres y la aplicación de revisiones para SQL Server. Este contexto necesita un entorno personalizado con derechos administrativos completos.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>Cuándo migrar a SQL Server como máquina virtual (IaaS)

Puede haber casos en los que todavía tenga que migrar a SQL Server como una máquina virtual normal. Este sería el caso si necesitara usar SQL Server Reporting Services. Sin embargo, la mayoría de las veces, Instancia administrada de Azure SQL Database puede proporcionar todo lo que necesita para migrar desde servidores SQL Server locales, por lo que la migración a una máquina virtual SQL Server debe ser el último recurso.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>Uso de Azure Database Migration Service para migrar las bases de datos relacionales a Azure

Puede usar Azure Database Migration Service para migrar bases de datos relacionales como SQL Server, Oracle y MySQL a Azure, independientemente de si la base de datos de destino es Azure SQL Database, Instancia administrada de Azure SQL Database o SQL Server en una máquina virtual de Azure.

El flujo de trabajo automatizado, con informes de evaluación, le guía en los cambios que debe realizar antes de migrar la base de datos. Cuando esté listo, el servicio migrará la base de datos de origen a Azure.

Siempre que cambie un RDBMS original, es posible que tenga que volver a probarlo. También, puede que tenga que cambiar las instrucciones SQL o el código de asignación relacional de objetos (ORM) de la aplicación, según los resultados de las pruebas.

Si tiene alguna otra base de datos (por ejemplo, IBM DB2) y opta por el enfoque lift-and-shift, puede que quiera seguir usando esas bases de datos como máquinas virtuales IaaS en Azure, a menos que esté dispuesto a realizar una migración de datos más compleja. Una migración así requerirá un esfuerzo adicional, ya que se hará a un tipo de base de datos diferente con un nuevo esquema y bibliotecas de programación diferentes.

Para saber cómo migrar bases de datos mediante Azure Database Migration Service, consulte [Acceso más rápido a la nube con Instancia administrada de Azure SQL Database y Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).

## <a name="additional-resources"></a>Recursos adicionales

- **Elección de una opción de SQL Server en la nube: Azure SQL Database (PaaS) o SQL Server en máquinas virtuales de Azure (IaaS)**

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- **Acceso más rápido a la nube con Instancia administrada de Azure SQL Database y Database Migration Service**

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- **Migración de una base de datos de SQL Server a una instancia de SQL Database en la nube**

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- **Azure SQL Database**

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- **SQL Server en máquinas virtuales**

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> [Anterior](lift-and-shift-existing-apps-azure-iaas.md)
> [Siguiente](modernize-existing-apps-to-cloud-optimized/index.md) <!-- Next Chapter -->
