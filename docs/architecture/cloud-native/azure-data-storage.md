---
title: Almacenamiento de datos en Azure
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Almacenamiento de datos en Azure
ms.date: 06/30/2019
ms.openlocfilehash: 5ba05f53faf65334f6269af8ae2c54d81e6b0779
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337467"
---
# <a name="data-storage-in-azure"></a>Almacenamiento de datos en Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Como hemos visto en este libro, la nube está cambiando la forma en que se diseñan, implementan y administran las aplicaciones. Al pasar a la nube, una pregunta crítica es ¿cómo se mueven los datos? Afortunadamente, la nube de Azure ofrece muchas opciones.

Podría simplemente aprovisionar una máquina virtual de Azure e instalar la base de datos de su elección. Esto se conoce como [infraestructura como servicio (IaaS)](https://www.techopedia.com/definition/141/infrastructure-as-a-service-iaas). Este enfoque simplifica el traslado de una base de datos local a la nube, tal cual, pero cambia la carga de administrar la máquina virtual y la base de datos.

En su lugar, una base de datos totalmente administrada [como servicio (DBaaS)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/) es una opción mejor. Obtiene muchas características integradas mientras Microsoft administra el hospedaje, el mantenimiento y las licencias. Azure incluye diferentes tipos de opciones de almacenamiento de datos totalmente administradas, cada una con ventajas específicas. Todos admiten la capacidad Just-in-Time y un modelo de pago por uso.

A continuación, veremos las opciones de DBaaS disponibles en Azure. Verá cómo Microsoft continúa teniendo el compromiso de mantener Azure una "plataforma abierta", que ofrece soporte administrado para muchas bases de datos relacionales y NoSQL de código abierto, y realiza contribuciones clave a las diversas bases de código abierto como miembro activo.

## <a name="azure-sql-database"></a>Se aplica a: Base de datos SQL de Azure

[Azure SQL Database](https://docs.microsoft.com/azure/sql-database/) es una base de datos como servicio (DBaaS) relacional de uso general y enriquecida de características basada en la Motor de base de datos de Microsoft SQL Server. Está totalmente administrado por Microsoft y es una base de datos en la nube de alto rendimiento, confiable y segura. El servicio comparte muchas de las características que se encuentran en la versión local de SQL Server.

Puede aprovisionar un servidor de SQL Database y una base de datos en minutos. Cuando la demanda de la aplicación crece de unos pocos clientes a millones, Azure SQL Database escala sobre la marcha con un tiempo de inactividad mínimo. Puede Agregar o quitar recursos de forma dinámica, como la potencia de la CPU, la memoria, el rendimiento de e/s y el almacenamiento asignado a las bases de datos.

En la figura 5-12 se muestran las opciones de implementación para Azure SQL Database.

![Opciones de implementación de SQL de Azure](./media/azure-sql-database-deployment-options.png)

**Figura 5-12**. Opciones de implementación de SQL de Azure

Tenga en cuenta las alternativas de la ilustración anterior al implementar un SQL Database:

-  una [base de datos única](https://docs.microsoft.com/azure/sql-database/sql-database-single-database) con su propio conjunto de recursos administrados por un [servidor de SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-servers). Una base de datos única es similar a una [base de datos independiente](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) en una implementación de SQL Server local.

- Un [Grupo elástico](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-pool) en el que una colección de bases de datos SQL comparte un único servidor de SQL Database a un precio establecido. Las bases de datos únicas pueden moverse dentro y fuera de un grupo elástico según sea necesario para optimizar el rendimiento del precio de un grupo de bases de datos.

- Un [instancia administrada](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) en el que es una colección de bases de datos de usuario y de sistema que proporciona una compatibilidad de casi-100% con un SQL Server local. Esta opción admite bases de datos mayores, hasta 35 TB y se coloca en una [Virtual Network de Azure](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) para un mejor aislamiento.

Azure SQL Database es una [plataforma como servicio (PaaS)](https://docs.microsoft.com/azure/sql-database/sql-database-paas) totalmente administrada motor de base de datos que controla la actualización, la revisión, las copias de seguridad y la supervisión sin intervención del usuario. Siempre ejecuta la versión estable más reciente de la SQL Server Motor de base de datos y del sistema operativo revisado y garantiza una disponibilidad del 99,99%. Una característica de [replicación geográfica activa](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication)permite crear bases de datos secundarias legibles en el mismo centro de datos de Azure o en otro. En caso de error, se puede iniciar una conmutación por error a una base de datos secundaria. En ese momento, las demás secundarias se vinculan automáticamente a la nueva principal. Se admiten hasta cuatro réplicas secundarias en la misma región o en regiones diferentes, y estas secundarias también se pueden usar para consultas de acceso de solo lectura.

Azure SQL Database incluye características [integradas de supervisión y optimización inteligente](https://docs.microsoft.com/azure/sql-database/sql-database-monitoring-tuning-index) que pueden ayudarle a maximizar el rendimiento y reducir los costos operativos. Por ejemplo, la característica de [ajuste automático](https://docs.microsoft.com/azure/sql-database/sql-database-automatic-tuning) proporciona un ajuste del rendimiento continuo basado en la inteligencia artificial y el aprendizaje automático. El servicio aprende de las cargas de trabajo en ejecución y puede aplicar recomendaciones de optimización. Cuanto más tiempo se ejecute un Azure SQL Database con el ajuste automático habilitado, mejor se llevará a cabo.

[Azure SQL Database sin servidor](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) (disponible para la versión preliminar en el momento de escribir este libro) es un nivel de proceso para las bases de datos únicas que se escalan automáticamente en función de la demanda de la carga de trabajo y se factura la cantidad de proceso utilizado por segundo. El nivel de proceso sin servidor también pone en pausa automáticamente las bases de datos durante períodos inactivos, de modo que solo se facturan los cargos de almacenamiento. Se reanuda automáticamente cuando se devuelve la actividad.

Por último, hay el nuevo Azure SQL Database plan de tarifa de [hiperescala](https://azure.microsoft.com/services/sql-database/) . Está basado en una arquitectura de almacenamiento altamente escalable y permite que la base de datos crezca según sea necesario, lo que elimina la necesidad de aprovisionar previamente los recursos de almacenamiento. Puede escalar los recursos de proceso y almacenamiento de forma independiente, lo que proporciona la flexibilidad de optimizar el rendimiento de cada carga de trabajo. Azure SQL Database hiperescala está optimizado para el procesamiento de [OLTP](https://en.wikipedia.org/wiki/Online_transaction_processing) y cargas de trabajo de análisis de alto rendimiento con almacenamiento de hasta 100 TB.  Con las cargas de trabajo con un uso intensivo de lectura, el escalado horizontal proporciona una ampliación rápida mediante el aprovisionamiento de réplicas de lectura adicionales según sea necesario para descargar las cargas de trabajo de lectura.

Además de la pila de Microsoft SQL Server tradicional, Azure también incluye versiones administradas de varias bases de datos populares de código abierto.

## <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) es una [base de datos relacional](https://en.wikipedia.org/wiki/Relational_database_management_system) [de código abierto](https://en.wikipedia.org/wiki/Open-source_software). Es un componente de la [pila de software LAMP](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) y lo usan muchas organizaciones de gran tamaño, como Facebook, Twitter y YouTube. La edición Community está disponible de forma gratuita y Enterprise Edition requiere una compra de licencias. Creado originalmente en 1995, el producto fue adquirido por Sun Microsystems en 2008, adquirido por Oracle en 2010.

[Azure Database for MySQL](https://azure.microsoft.com/services/mysql/) es un servicio de base de datos relacional listo para la empresa y totalmente administrado basado en el motor de servidor MySQL de código abierto. Con la implementación de MySQL Community Edition, se incluyen las siguientes funcionalidades de PaaS sin costo adicional:

- [Alta disponibilidad](https://docs.microsoft.com/azure/mysql/concepts-high-availability)integrada.

- Rendimiento predecible, con [precios de pago por](https://docs.microsoft.com/azure/mysql/concepts-pricing-tiers)uso inclusivos.

- [Escale](https://docs.microsoft.com/azure/mysql/concepts-high-availability) según sea necesario en cuestión de segundos.

- Protección de información confidencial en reposo y en movimiento.

- [Copias de seguridad automáticas](https://docs.microsoft.com/azure/mysql/concepts-backup) y restauración a un momento [dado](https://docs.microsoft.com/azure/mysql/concepts-backup) durante un máximo de 35 días.

- Seguridad y cumplimiento de nivel empresarial.

Estas características de PaaS integradas son importantes para las organizaciones que tienen cientos de bases de datos "tácticas" (no estratégicas) en sus centros de datos, pero no tienen los recursos necesarios para realizar revisiones, copias de seguridad, seguridad y supervisión del rendimiento.

Además, el [servicio de migración de datos de Azure](https://azure.microsoft.com/services/database-migration/) puede migrar datos de varios orígenes de base de datos a plataformas de datos de Azure con un tiempo de inactividad mínimo. El servicio genera informes de evaluación y proporciona recomendaciones que le guiarán a través de los cambios necesarios para realizar una migración, tanto pequeños como grandes.

El [servidor de Azure MySQL](https://docs.microsoft.com/azure/mysql/concepts-servers) administrado es el punto administrativo central para el servicio. Es el mismo motor de MySQL Server que se usa para las implementaciones locales. Con él, puede crear una sola base de datos por servidor para consumir todos los recursos o crear varias bases de datos por servidor para compartir recursos. Su equipo puede seguir desarrollando aplicaciones con las herramientas y la plataforma de código abierto que prefiera sin tener que aprender nuevas habilidades o administrar máquinas virtuales e infraestructura.

## <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[MariaDB](https://mariadb.com/) El servidor es otro conocido servidor de base de datos de código abierto. Fue creado como una bifurcación de MySQL por los desarrolladores originales de MySQL en el momento en que Oracle compró a Sun Microsystems que poseía MySQL. La intención era asegurarse de que MariaDB seguía siendo código abierto.

Dado que MariaDB es una [bifurcación de MySQL](https://blog.panoply.io/a-comparative-vmariadb-vs-mysql), los datos y las definiciones de tabla son compatibles y los protocolos, las estructuras y las API de cliente son Close-spojit. Los conectores de datos de MySQL funcionarán MariaDB sin modificarlos.

MariaDB tiene un alto nivel de seguridad y es utilizado por muchas grandes empresas. A pesar de que Oracle sigue manteniendo, mejorando y respaldando MySQL, MariaDB se administra mediante MariaDB Foundation, lo que permite las contribuciones públicas al producto y la documentación.

[Azure Database for MariaDB](https://azure.microsoft.com/services/mariadb/) es una base de datos totalmente administrada como servicio en la nube de Azure. Se basa en el motor de servidor de [MariaDB Community Edition](https://mariadb.org/download/) . Puede administrar cargas de trabajo críticas con un rendimiento predecible y escalabilidad dinámica. De forma similar a las otras plataformas de Azure Database, incluye muchas capacidades de plataforma como servicio sin costo adicional:

- [Alta disponibilidad](https://docs.microsoft.com/azure/mariadb/concepts-high-availability)integrada.

- Rendimiento predecible, con [precios de pago por](https://docs.microsoft.com/azure/mariadb/concepts-pricing-tiers)uso inclusivos.

- [Escalado](https://docs.microsoft.com/azure/mariadb/concepts-high-availability) según sea necesario en cuestión de segundos.

- Protección segura de datos confidenciales en reposo y en movimiento.

- [Copias de seguridad automáticas](https://docs.microsoft.com/azure/mariadb/concepts-backup) y restauración a un momento [dado](https://docs.microsoft.com/azure/mariadb/concepts-backup) durante un máximo de 35 días.

- Seguridad y cumplimiento de nivel empresarial.

## <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/) es otra conocida base de datos relacional de código abierto con más de 30 años de desarrollo activo. Es un sistema de administración de bases de datos relacional de objetos y de uso general. Su licencia se considera "liberal" y el producto es gratuito para su uso, modificación y distribución en cualquier forma. Muchas grandes empresas, como Apple, Red Hat y Fujitsu, han creado productos con PostgreSQL.

[Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/) es un servicio de base de datos relacional totalmente administrado, basado en el motor de base de datos Postgres de código abierto. Puede administrar cargas de trabajo críticas con rendimiento predecible, seguridad, alta disponibilidad y escalabilidad dinámica. Admite varios marcos y lenguajes de código abierto, como C++, Java, Python, node, C\#y php. Permite la [migración](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) de bases de datos de PostgreSQL a través de una interfaz de línea de comandos o el [servicio de migración de datos de Azure](https://azure.microsoft.com/services/database-migration/).

El servicio incluye [inteligencia integrada](https://docs.microsoft.com/azure/postgresql/concepts-monitoring) que estudia los patrones únicos de la base de datos y proporciona recomendaciones e información personalizada para ayudarle a maximizar el rendimiento de la base de datos de PostgreSQL. La [protección contra amenazas avanzada](https://docs.microsoft.com/azure/postgresql/concepts-data-access-and-security-threat-protection) supervisa la base de datos alrededor del reloj y detecta posibles actividades malintencionadas, alertando sobre la detección para que pueda intervenir de inmediato.

Azure Database for PostgreSQL está disponible como dos opciones de implementación: servidor único y hiperescala (citus), disponible para la versión preliminar en el momento de redactar este libro.

- La opción de implementación de [servidor único](https://docs.microsoft.com/azure/postgresql/concepts-servers) es un punto administrativo central para varias bases de datos. Es el mismo motor de servidor de PostgreSQL disponible para las implementaciones locales. Con él, puede crear una sola base de datos por servidor para consumir todos los recursos o crear varias bases de datos para compartir los recursos. Los precios se estructuran por servidor en función de los núcleos y el almacenamiento.

- La [opción de hiperescala (citus)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) está basada en la tecnología de de [datos de citus](https://www.citusdata.com/) . Permite el escalado de alto rendimiento al escalar horizontalmente una base de datos única en cientos de nodos para ofrecer un rendimiento y una escala increíblemente rápidos. Esta opción permite al motor ajustar más datos en memoria, paralelizar las consultas en cientos de nodos y indexar los datos más rápidamente. La característica de hiperescala es compatible con las últimas innovaciones, versiones y herramientas para PostgreSQL, de modo que pueda aprovechar su experiencia existente de PostgreSQL.

## <a name="cosmos-db"></a>Cosmos DB

Azure Cosmos DB es un servicio de base de datos NoSQL totalmente administrado y distribuido globalmente diseñado para proporcionar baja latencia, escalabilidad elástica, coherencia de datos administrados y alta disponibilidad. En Resumen, si su aplicación necesita un tiempo de respuesta rápido garantizado en cualquier parte del mundo, si es necesario estar siempre en línea y necesita escalabilidad ilimitada y sin límites de rendimiento y almacenamiento, Cosmos DB es una excelente opción. En la figura 5-13 se muestra una introducción de alto nivel de Cosmos DB.

![Información general de Cosmos DB](./media/cosmos-db-overview.png)

**Figura 5-13**: información general de Cosmos dB

Tenga en cuenta que en la figura 5-13 cómo Cosmos DB es un servicio de base de datos sólido y muy versátil con muchas capacidades integradas de la nube nativas. En esta sección, examinaremos más de cerca.

### <a name="global-support"></a>Soporte global

Puede distribuir globalmente las bases de datos de Cosmos en todas las regiones de Azure de todo el mundo, colocar los datos cerca de los usuarios, mejorar el tiempo de respuesta y reducir la latencia. Puede Agregar o quitar una base de datos de una región sin pausar o volver a implementar la aplicación. En segundo plano, Cosmos DB replica de forma transparente los datos en todas las regiones configuradas.

Cosmos DB admite la agrupación en clústeres [activo/activo](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) en el nivel global, lo que permite configurar una o todas las regiones de la base de datos para admitir escrituras y lecturas.

La característica de protocolo de [varios maestros](https://docs.microsoft.com/azure/cosmos-db/how-to-multi-master) de Cosmos dB habilita la siguiente funcionalidad:

- Escalabilidad de escritura y lectura elásticas ilimitada.

- 99,999 % de disponibilidad de lectura y escritura en todo el mundo.

- Garantía de lecturas y escrituras atendidas en menos de 10 milisegundos en el percentil 99.

Internamente, Cosmos DB controla la replicación de datos entre regiones con garantías de nivel de coherencia y acuerdos de nivel de servicio con respaldo financiero.

Con las API de hospedaje [múltiple](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)Cosmos dB, la aplicación puede tener en cuenta automáticamente la región de Azure más cercana y enviarle solicitudes. La región más cercana se identifica mediante Cosmos DB sin ningún cambio de configuración. En caso de que una región deje de estar disponible, Cosmos DB admita la conmutación automática por error y la característica de hospedaje múltiple redirigirá automáticamente la solicitud a la siguiente región disponible más cercana.

### <a name="multi-model-support"></a>Compatibilidad con varios modelos

Cosmos DB es una *plataforma de datos de varios modelos* que permite interactuar con los datos mediante una serie de modelos NoSQL compatibles, incluidos documentos, pares de clave-valor, representaciones de columnas y de gráficos. Internamente, los datos se almacenan en un formato de [estructura](https://docs.microsoft.com/dotnet/csharp/programming-guide/classes-and-structs/using-structs) simple formado por tipos de datos primitivos, como cadenas, valores booleanos y números. Para cada solicitud, el motor de base de datos traduce los datos en la representación del modelo que ha seleccionado. Puede elegir entre una API de propiedad Cosmos DB basada en SQL o cualquiera de las [API de compatibilidad](https://www.wikiwand.com/en/Cosmos_DB) que se muestran en la figura 5-14.

![Proveedores de Cosmos DB](./media/cosmos-db-providers.png)

**Figura 5-14**: proveedores de Cosmos dB

Tenga en cuenta en la figura 5-14 cómo Cosmos DB admite [TABLE Storage](https://azure.microsoft.com/services/storage/tables/). Tanto Cosmos DB como [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) comparten el mismo modelo de tabla subyacente y exponen muchas de las mismas operaciones de tabla. Sin embargo, el [TABLE API de Cosmos dB](https://docs.microsoft.com/azure/cosmos-db/table-introduction) proporciona muchas mejoras Premium que no están disponibles en la API de Azure Storage. Estas características se contrastan en la figura 5-15.

![Azure Table API](./media/azure-table-api.png)

**Figura 5-15**: Azure Table API

Las aplicaciones escritas para Azure Table Storage pueden migrar a Azure Cosmos DB mediante el Table API sin necesidad de realizar cambios en el código.

En los escenarios de aplicaciones de [Brownfield](https://en.wikipedia.org/wiki/Brownfield_(software_development)) , los equipos de desarrollo pueden migrar las bases de datos Mongo, Gremlin o Cassandra existentes a Cosmos dB con cambios mínimos en el código de aplicación o los datos existentes. En escenarios de [Virgen](https://en.wikipedia.org/wiki/Greenfield_project) , los equipos de desarrollo pueden elegir el modelo de datos que mejor se adapte a sus requisitos y preferencias, incluidas las opciones de código abierto totalmente compatibles con las plataformas MongoDB, Cassandra y Gremlin.

### <a name="consistency-models"></a>Modelos de coherencia

Anteriormente en la sección *relacional frente a NoSQL* , analizamos el asunto de la coherencia de los *datos*, que es un término que hace referencia a la integridad de los datos. Las bases de datos distribuidas que se basan en la replicación para alta disponibilidad, latencia baja o ambas, deben hacer un equilibrio fundamental entre la coherencia de lectura, la disponibilidad y la latencia.

La mayoría de las bases de datos distribuidas permiten a los desarrolladores elegir entre dos modelos de coherencia: [coherencia fuerte](https://en.wikipedia.org/wiki/Strong_consistency) y [coherencia final](https://en.wikipedia.org/wiki/Eventual_consistency). La *coherencia fuerte* es el estándar Gold de programación de datos. Garantiza que el resultado de una consulta siempre devolverá los datos más actuales, incluso si el sistema debe incurrir en latencia en espera para que una actualización se replique en todas las copias de la base de datos. Por otro lado, un sistema configurado para la *coherencia final* devolverá los datos inmediatamente, incluso si esos datos no son la copia más reciente. Esta opción permite una mayor disponibilidad, mayor escala y mayor rendimiento.

Azure Cosmos DB ofrece un espectro de [cinco modelos de coherencia bien definidos](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) que se muestran en la figura 5-16. Estas opciones permiten tomar decisiones precisas e inconvenientes pormenorizados con respecto a la disponibilidad y el rendimiento en función de las necesidades de la aplicación. Estos modelos están bien definidos, intuitivos y respaldados por los contratos de nivel de servicio (SLA).

![Niveles de coherencia Cosmos DB](./media/cosmos-db-consistency-levels.png)

**Figura 5-16**: niveles de coherencia de Cosmos dB

### <a name="partitioning"></a>Particionamiento

Azure Cosmos DB usa la creación automática de [particiones](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) para escalar la base de datos para satisfacer las necesidades de rendimiento de la aplicación.

Los datos de Cosmos DB se administran mediante la creación de bases de datos [, contenedores y elementos](https://docs.microsoft.com/azure/cosmos-db/databases-containers-items), tal como se muestra en la figura 5-17.

![Entidades Cosmos DB](./media/cosmos-db-entities.png)

**Figura 5-17**: jerarquía de entidades de Cosmos dB

Tenga en cuenta que en la figura 5-17 se empieza por crear una base de datos de Cosmos DB dentro de una cuenta de base de datos. Esa base de datos se convierte en la unidad de administración de un conjunto de contenedores. Un contenedor es una agrupación independiente del esquema de elementos que se pueden expresar como una colección, una tabla o un grafo, en función del proveedor de API seleccionado (descrito en la sección anterior). Los elementos son los datos que se agregan al contenedor y se representan como documentos, filas, nodos o bordes. De forma predeterminada, todos los elementos que agregue a un contenedor se indexan automáticamente sin requerir ningún índice explícito ni administración de esquema.

Para particionar el contenedor, los elementos se dividen en subconjuntos distintos denominados [particiones lógicas](https://docs.microsoft.com/azure/cosmos-db/partition-data). Las particiones lógicas se crean en función del valor de una clave de partición asociada a cada elemento de un contenedor. En la figura 5-18 se muestra cómo todos los elementos de una partición lógica tienen el mismo valor de clave de partición.

![Mecanismos de creación de particiones Cosmos DB](./media/cosmos-db-partitioning.png)

**Figura 5-18**: mecanismos de creación de particiones Cosmos dB

Observe en la figura 5-18 cómo cada elemento incluye una clave de partición de ' City ' o ' aeropuerto '. Esta clave de partición determina la partición lógica del elemento. Cada código de ciudad se asigna a una partición lógica en el contenedor en el lado izquierdo y a los que tienen un código de aeropuerto en el contenedor de la derecha. Al combinar el valor de la clave de partición con el valor de identificador de un elemento, se crea el índice del elemento, que identifica de forma única el elemento.

Internamente, Cosmos DB administra automáticamente la ubicación de las [particiones lógicas](https://docs.microsoft.com/azure/cosmos-db/partition-data) en las [particiones físicas](https://docs.microsoft.com/azure/cosmos-db/partition-data) para satisfacer de forma eficaz las necesidades de escalabilidad y rendimiento del contenedor. A medida que aumentan los requisitos de rendimiento y almacenamiento de una aplicación, Azure Cosmos DB mueve las particiones lógicas para redistribuir la carga a través de un número mayor de servidores. Estas operaciones de redistribución se administran mediante Cosmos DB y se realizan sin interrupción ni tiempo de inactividad.

## <a name="azure-redis-cache"></a>Caché en Redis de Azure

Las ventajas del almacenamiento en caché para mejorar el rendimiento y la escalabilidad son perfectamente comprensibles.

En el caso de una aplicación nativa en la nube, una ubicación común para agregar almacenamiento en caché se encuentra dentro de la puerta de enlace de API. La puerta de enlace sirve como front-end para todas las solicitudes entrantes. Al agregar el almacenamiento en caché, puede aumentar el rendimiento y la capacidad de respuesta devolviendo los datos en caché y evitando los recorridos de ida y vuelta a una base de datos local o a un servicio de nivel inferior. En la figura 5-19 se muestra una arquitectura de almacenamiento en caché para una aplicación nativa en la nube.

![Almacenamiento en caché en una aplicación nativa en la nube](./media/caching-in-a-cloud-native-app.png)

**Figura 5-19**: almacenamiento en caché en una aplicación nativa en la nube

Un patrón común de almacenamiento en caché es el [patrón de reserva](https://docs.microsoft.com/azure/architecture/patterns/cache-aside). En el caso de una solicitud entrante, primero se consulta la respuesta en la memoria caché, que se muestra en el paso #1 de la figura 5-19. Si se encuentra, los datos se devuelven inmediatamente. Si los datos no existen en la memoria caché (lo que se conoce como un error de [caché](https://www.techopedia.com/definition/6308/cache-miss)), se recuperan de la base de datos local o del servicio de bajada (paso #2), se escriben en la memoria caché para solicitudes futuras (paso #3) y se devuelven al autor de la llamada. Se debe tener cuidado de expulsar periódicamente los datos almacenados en caché para que el sistema siga siendo coherente y preciso.

Además, tenga en cuenta que en la figura 5-19 el modo en que la memoria caché no se implementa localmente dentro de los límites del servicio, sino que se utiliza como un servicio de respaldo basado en la nube, como se describe en el capítulo 1.

[Azure Redis cache](https://azure.microsoft.com/services/cache/) es un servicio de agente de mensajería y almacenamiento en caché de datos. Proporciona acceso de alto rendimiento y baja latencia a los datos de las aplicaciones. Está totalmente administrado por Microsoft, hospedado en Azure y accesible para cualquier aplicación dentro o fuera de Azure.

Internamente, la caché de Azure para Redis está respaldada por el [servidor de Redis](https://redis.io/) de código abierto y admite de forma nativa estructuras de datos como [cadenas](https://redis.io/topics/data-types#strings), [valores hash](https://redis.io/topics/data-types#hashes), [listas](https://redis.io/topics/data-types#sets), [conjuntos](https://redis.io/topics/data-types#sets)y [conjuntos ordenados](https://redis.io/topics/data-types#sorted-sets). Si su aplicación usa Redis, funcionará tal cual con la memoria caché de Azure para Redis.

La caché de Azure para Redis también se puede usar como una memoria caché de datos en memoria, una base de datos no relacional distribuida y un agente de mensajes. Está disponible en tres planes de tarifa diferentes. El nivel Premium incluye muchas características de nivel empresarial, como la agrupación en clústeres, la persistencia de datos, la replicación geográfica y el aislamiento y la seguridad de la red virtual.

>[!div class="step-by-step"]
>[Anterior](data-patterns.md)
>[Siguiente](resiliency.md)
