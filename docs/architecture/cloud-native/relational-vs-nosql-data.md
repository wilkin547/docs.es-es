---
title: Soluciones relacionales y datos NoSQL
description: Obtenga información sobre datos relacionales y NoSQL en aplicaciones nativas de la nube
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 3fb3dcc3a87e278c05f3e15d261245f4d61453d1
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805810"
---
# <a name="relational-vs-nosql-data"></a>Soluciones relacionales y datos NoSQL

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Relacional y NoSQL son dos tipos de sistemas de base de datos comúnmente implementados en aplicaciones nativas de la nube. Se crean de forma diferente, almacenan datos de forma diferente y se accede a ellos de forma diferente. En esta sección, veremos ambos. Más adelante en este capítulo, veremos una tecnología de base de datos emergente llamada *NewSQL*.

Las bases de *datos relacionales* han sido una tecnología prevalente durante décadas. Son maduros, probados y ampliamente implementados. Abundan los productos, herramientas y experiencia de la base de datos de la competencia. Las bases de datos relacionales proporcionan un almacén de tablas de datos relacionadas. Estas tablas tienen un esquema fijo, usan SQL (lenguaje de consulta estructurado) para administrar datos y admiten garantías ACID.

*Las bases de datos no SQL* hacen referencia a almacenes de datos no relacionales de alto rendimiento. Destacan en sus características de facilidad de uso, escalabilidad, resiliencia y disponibilidad. En lugar de unir tablas de datos normalizados, NoSQL almacena datos no estructurados o semiestructurados, a menudo en pares clave-valor o documentos JSON. Las bases de datos no SQL normalmente no proporcionan garantías ACID más allá del ámbito de una sola partición de base de datos. Los servicios de alto volumen que requieren un tiempo de respuesta de menos de un segundo favorecen a los almacenes de datos NoSQL.

El impacto de las tecnologías [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) para sistemas nativos de la nube distribuidos no se puede exagerar. La proliferación de nuevas tecnologías de datos en este espacio ha interrumpido las soluciones que antes se basaban exclusivamente en bases de datos relacionales.

Las bases de datos NoSQL incluyen varios modelos diferentes para acceder y administrar datos, cada uno adecuado para casos de uso específicos. La Figura 5-9 presenta cuatro modelos comunes.

![Modelos de datos NoSQL](./media/types-of-nosql-datastores.png)

**Figura 5-9**: Modelos de datos para bases de datos NoSQL

| Modelo | Características |
| :-------- | :-------- |
| Tienda de documentos | Los datos y metadatos se almacenan jerárquicamente en documentos basados en JSON dentro de la base de datos. |
| Almacén de valor clave | La más simple de las bases de datos NoSQL, los datos se representan como una colección de pares clave-valor. |
| Tienda de columna ancha | Los datos relacionados se almacenan como un conjunto de pares de clave/valor anidados dentro de una sola columna. |
| Tienda de gráficos | Los datos se almacenan en una estructura de gráfico como propiedades de nodo, borde y datos. |

## <a name="the-cap-theorem"></a>El teorema de la PAC

Como una manera de entender las diferencias entre estos tipos de bases de datos, considere el teorema CAP, un conjunto de principios aplicados a los sistemas distribuidos que almacenan el estado. La Figura 5-10 muestra las tres propiedades del teorema CAP.

![Teorema CAP](./media/cap-theorem.png)

**Figura 5-10**. El teorema de la PAC

El teorema indica que los sistemas de datos distribuidos ofrecerán un equilibrio entre coherencia, disponibilidad y tolerancia de partición. Y, que cualquier base de datos sólo puede garantizar *dos* de las tres propiedades:

- *Consistencia.* Cada nodo del clúster responde con los datos más recientes, incluso si el sistema debe bloquear la solicitud hasta que se actualicen todas las réplicas. Si consulta un "sistema coherente" para un elemento que se está actualizando actualmente, esperará esa respuesta hasta que todas las réplicas se actualicen correctamente. Sin embargo, recibirá los datos más actuales.

- *Disponibilidad.* Cada nodo devuelve una respuesta inmediata, incluso si esa respuesta no es la más reciente. Si consulta un "sistema disponible" para un elemento que se está actualizando, obtendrá la mejor respuesta posible que el servicio puede proporcionar en ese momento.

- *Tolerancia de partición.* Garantiza que el sistema siga funcionando incluso si se produce un error en un nodo de datos replicado o pierde conectividad con otros nodos de datos replicados.

Las bases de datos relacionales suelen proporcionar coherencia y disponibilidad, pero no tolerancia a particiones. Normalmente se aprovisionan en un único servidor y se escalan verticalmente agregando más recursos a la máquina.

Muchos sistemas de bases de datos relacionales admiten características de replicación integradas donde se pueden realizar copias de la base de datos principal en otras instancias de servidor secundario. Las operaciones de escritura se realizan en la instancia principal y se replican en cada una de las secundarias. Tras un error, la instancia principal puede conmutar por error a una secundaria para proporcionar alta disponibilidad. Los segundos también se pueden utilizar para distribuir operaciones de lectura. Aunque las operaciones de escritura siempre van en la réplica principal, las operaciones de lectura se pueden enrutar a cualquiera de las secundarias para reducir la carga del sistema.

Los datos también se pueden particionar horizontalmente en varios nodos, como con el [particionamiento.](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-scale-introduction) Sin embargo, el partimiento aumenta drásticamente la sobrecarga operativa al escupir datos en muchas piezas que no se pueden comunicar fácilmente. Puede ser costoso y lento administrar. Puede terminar afectando al rendimiento, las combinaciones de tablas y la integridad referencial.

Si las réplicas de datos perdieran conectividad de red en un clúster de base de datos relacional "altamente coherente", no podría escribir en la base de datos. El sistema rechazaría la operación de escritura, ya que no puede replicar ese cambio en la otra réplica de datos. Cada réplica de datos tiene que actualizarse antes de que se pueda completar la transacción.

Las bases de datos NoSQL suelen admitir alta disponibilidad y tolerancia a particiones. Se escalan horizontalmente, a menudo entre servidores de productos básicos. Este enfoque proporciona una enorme disponibilidad, tanto dentro como entre regiones geográficas, a un costo reducido. Los datos se particionan y replican en estos equipos, o nodos, lo que proporciona redundancia y tolerancia a errores. La desventaja es la consistencia. Un cambio en los datos en un nodo NoSQL puede tardar algún tiempo en propagarse a otros nodos. Normalmente, un nodo de base de datos NoSQL proporcionará una respuesta inmediata a una consulta, incluso si los datos que se presentan están obsoletos y aún no se han actualizado.

Si las réplicas de datos perdieran conectividad en un clúster de base de datos NoSQL "altamente disponible", aún podría completar una operación de escritura en la base de datos. El clúster de base de datos permitiría la operación de escritura y actualizaría cada réplica de datos a medida que esté disponible.

Este tipo de resultado se conoce como coherencia final, una característica de los sistemas de datos distribuidos donde no se admiten transacciones ACID. Es un breve retraso entre la actualización de un elemento de datos y el tiempo que se tarda en propagar esa actualización a cada uno de los nodos de réplica. En condiciones normales, el retraso suele ser corto, pero puede aumentar cuando surgen problemas. Por ejemplo, ¿qué sucedería si actualizara un elemento de producto en una base de datos NoSQL en Estados Unidos y consultara ese mismo elemento de datos desde un nodo de réplica en Europa? Recibirá la información anterior del producto hasta que el clúster actualice el nodo europeo con el cambio de producto. Al devolver inmediatamente un resultado de consulta y no esperar a que se actualicen todos los nodos de réplica, obtendrá una escala y un volumen enormes, pero con la posibilidad de presentar datos antiguos.

La alta disponibilidad y la escalabilidad masiva suelen ser más críticas para el negocio que la coherencia sólida. Los desarrolladores pueden implementar técnicas y patrones como Sagas, CQRS y mensajería asincrónica para adoptar la coherencia final.

> Hoy en día, se debe tener cuidado al cumplir con las restricciones del teorema de la PAC. Ha surgido un nuevo tipo de base de datos, llamado NewSQL, que amplía el motor de base de datos relacional para admitir tanto la escalabilidad horizontal como el rendimiento escalable de los sistemas NoSQL.

## <a name="considerations-for-relational-vs-nosql-systems"></a>Consideraciones para sistemas relacionales frente a sistemas NoSQL

En función de los requisitos de datos específicos, un microservicio basado en la nube puede implementar un almacén de datos NoSQL relacional o ambos.

|  Considere un almacén de datos NoSQL cuando: | Considere una base de datos relacional cuando: |
| :-------- | :-------- |
| Tiene cargas de trabajo de gran volumen que requieren grandes escalas | Su volumen de carga de trabajo es coherente y requiere una escala de mediano a gran escala |
| Sus cargas de trabajo no requieren garantías ACID |  Se requieren garantías ACID |
| Sus datos son dinámicos y cambian con frecuencia | Sus datos son predecibles y altamente estructurados |
| Los datos se pueden expresar sin relaciones | Los datos se expresan mejor relacionalmente |  
| Necesitas escrituras rápidas y la seguridad de escritura no es crítica | La seguridad de escritura es un requisito |  
| La recuperación de datos es simple y tiende a ser plana | Trabaja con consultas e informes complejos|
| Sus datos requieren una amplia distribución geográfica | Sus usuarios están más centralizados |
| La aplicación se implementará en hardware básico, como con las nubes públicas | La aplicación se implementará en hardware grande de gama alta |
|||

En las secciones siguientes, exploraremos las opciones disponibles en la nube de Azure para almacenar y administrar los datos nativos de la nube.

## <a name="database-as-a-service"></a>Base de datos como servicio

Para empezar, puede aprovisionar una máquina virtual de Azure e instalar la base de datos de su elección para cada servicio. Aunque tendría control total sobre el entorno, le gustaría dejar de crear muchas características integradas de la plataforma en la nube. También sería responsable de administrar la máquina virtual y la base de datos para cada servicio. Este enfoque podría volverse rápidamente lento y costoso.

En su lugar, las aplicaciones nativas de la nube favorecen los servicios de datos expuestos como base de [datos como servicio (DBaaS).](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/) Estos servicios, totalmente administrados por un proveedor de nube, proporcionan seguridad, escalabilidad y supervisión integradas. En lugar de poseer el servicio, simplemente lo consume como un servicio de [respaldo.](./definition.md#backing-services) El proveedor opera el recurso a escala y asume la responsabilidad de rendimiento y mantenimiento.

Se pueden configurar en zonas y regiones de disponibilidad en la nube para lograr una alta disponibilidad. Todos ellos admiten la capacidad Just-In-Time y un modelo de pago por uso. Azure ofrece diferentes tipos de opciones de servicio de datos administrados, cada una con ventajas específicas.

Primero examinaremos los servicios DBaaS relacionales disponibles en Azure. Verá que la base de datos de SQL Server insignia de Microsoft está disponible junto con varias opciones de código abierto. A continuación, hablaremos sobre los servicios de datos NoSQL en Azure.

## <a name="azure-relational-databases"></a>Bases de datos relacionales de Azure

Para los microservicios nativos de la nube que requieren datos relacionales, Azure ofrece cuatro ofertas de bases de datos relacionales administradas como servicio (DBaaS), que se muestran en la figura 5-11.

![Bases de datos relacionales administradas en Azure](./media/azure-managed-databases.png)

**Figura 5-11**. Bases de datos relacionales administradas disponibles en Azure

En la figura anterior, observe cómo cada uno se asienta sobre una infraestructura DBaaS común que cuenta con capacidades clave sin costo adicional.

Estas características son especialmente importantes para las organizaciones que aprovisionan un gran número de bases de datos, pero tienen recursos limitados para administrarlas.
Puede aprovisionar una base de datos de Azure en cuestión de minutos seleccionando la cantidad de núcleos de procesamiento, memoria y almacenamiento subyacente. Puede escalar la base de datos sobre la marcha y ajustar dinámicamente los recursos con poco o ningún tiempo de inactividad.

## <a name="azure-sql-database"></a>Azure SQL Database

Los equipos de desarrollo con experiencia en Microsoft SQL Server deben tener en cuenta [Azure SQL Database.](https://docs.microsoft.com/azure/sql-database/) Es una base de datos relacional como servicio (DBaaS) totalmente administrada basada en el Motor de base de datos de Microsoft SQL ServerSQL Server Database Engine. El servicio comparte muchas características que se encuentran en la versión local de SQL Server y ejecuta la versión estable más reciente del Motor de base de datos de SQL ServerSQL Server Database Engine.

Para su uso con un microservicio nativo de la nube, Azure SQL Database está disponible con tres opciones de implementación:

- Una base de datos única representa una base de datos SQL totalmente administrada que se ejecuta en un servidor de [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-servers) en la nube de Azure. La base de datos se considera [*contenida,*](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) ya que no tiene dependencias de configuración en el servidor de base de datos subyacente.
  
- Una [instancia administrada](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) es una instancia totalmente administrada del Motor de base de datos de Microsoft SQL Serverqueserver que proporciona casi el 100 % de compatibilidad con un servidor SQL Server local. Esta opción admite bases de datos más grandes, de hasta 35 TB y se coloca en una red virtual de [Azure](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) para un mejor aislamiento.

- [Azure SQL Database serverless](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) es un nivel de proceso para una sola base de datos que se escala automáticamente en función de la demanda de carga de trabajo. Solo factura la cantidad de proceso utilizado por segundo. El servicio es adecuado para cargas de trabajo con patrones de uso intermitentes e impredecibles, intercalados con períodos de inactividad. El nivel de proceso sin servidor también pausa automáticamente las bases de datos durante los períodos inactivos para que solo se facturen los cargos de almacenamiento. Se reanuda automáticamente cuando vuelve la actividad.

Más allá de la pila tradicional de Microsoft SQL Server, Azure también incluye versiones administradas de tres bases de datos de código abierto populares.

## <a name="open-source-databases-in-azure"></a>Bases de datos de código abierto en Azure

Las bases de datos relacionales de código abierto se han convertido en una opción popular para las aplicaciones nativas de la nube. Muchas empresas les favorecen los productos de bases de datos comerciales, especialmente para ahorrar costos. Muchos equipos de desarrollo disfrutan de su flexibilidad, desarrollo respaldado por la comunidad y ecosistema de herramientas y extensiones. Las bases de datos de código abierto se pueden implementar en varios proveedores de nube, lo que ayuda a minimizar la preocupación del "bloqueo de proveedores".

Los desarrolladores pueden hospedar fácilmente cualquier base de datos de código abierto en una máquina virtual de Azure. Al tiempo que proporciona control total, este enfoque le coloca en el gancho para la administración, supervisión y mantenimiento de la base de datos y la máquina virtual.

Sin embargo, Microsoft continúa su compromiso de mantener Azure como una "plataforma abierta" ofreciendo varias bases de datos de código abierto populares como servicios DBaaS *totalmente administrados.*

### <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL) es una base de datos relacional de código abierto y un pilar para aplicaciones basadas en la pila de [software LAMP.](https://en.wikipedia.org/wiki/LAMP_(software_bundle)) Ampliamente elegido para cargas de trabajo pesadas de *lectura,* es utilizado por muchas organizaciones grandes, incluyendo Facebook, Twitter y YouTube. La edición de la comunidad está disponible de forma gratuita, mientras que la edición enterprise requiere una compra de licencia. Originalmente creado en 1995, el producto fue comprado por Sun Microsystems en 2008. Oracle adquirió Sun y MySQL en 2010.

[Azure Database for MySQL](https://azure.microsoft.com/services/mysql/) es un servicio de base de datos relacional administrado basado en el motor de servidor MySQL de código abierto. Utiliza la edición MySQL Community. El servidor MySQL de Azure es el punto administrativo del servicio. Es el mismo motor de servidor MySQL utilizado para las implementaciones locales. El motor puede crear una sola base de datos por servidor o varias bases de datos por servidor que comparten recursos. Puede seguir administrando datos con las mismas herramientas de código abierto sin tener que aprender nuevas habilidades o administrar máquinas virtuales.

### <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[MariaDB](https://mariadb.com/) El servidor es otro servidor de base de datos de código abierto popular. Fue creado como una *bifurcación* de MySQL cuando Oracle compró Sun Microsystems, que era propietario de MySQL. La intención era garantizar que MariaDB siguiera siendo de código abierto. Como MariaDB es una bifurcación de MySQL, los datos y las definiciones de tabla son compatibles, y los protocolos de cliente, estructuras y API, son estrechas.

MariaDB tiene una comunidad fuerte y es utilizado por muchas grandes empresas. Mientras Oracle continúa manteniendo, mejorando y dando soporte a MySQL, la fundación MariaDB administra MariaDB, lo que permite contribuciones públicas al producto y la documentación.

[Azure Database for MariaDB](https://azure.microsoft.com/services/mariadb/) es una base de datos relacional totalmente administrada como servicio en la nube de Azure. El servicio se basa en el motor de servidor de edición de la comunidad MariaDB. Puede manejar cargas de trabajo de misión crítica con un rendimiento predecible y escalabilidad dinámica.

### <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/) es una base de datos relacional de código abierto con más de 30 años de desarrollo activo. PostgresSQL tiene una sólida reputación de fiabilidad e integridad de datos. Es rico en características, compatible con SQL y se considera más performant que MySQL, especialmente para cargas de trabajo con consultas complejas y escrituras pesadas. Muchas grandes empresas, como Apple, Red Hat y Fujitsu, han creado productos con PostgreSQL.

[Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/) es un servicio de base de datos relacional totalmente administrado, basado en el motor de base de datos Postgres de código abierto. El servicio es compatible con muchas plataformas de desarrollo, incluyendo\#C++, Java, Python, Node, C y PHP. Puede migrar bases de datos PostgreSQL a ella mediante la herramienta de [interfaz de línea de comandos](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) o Azure Data Migration Service.

Azure Database for PostgreSQL está disponible con dos opciones de implementación:

- La opción de implementación de [servidor único](https://docs.microsoft.com/azure/postgresql/concepts-servers) es un punto administrativo central para varias bases de datos en las que puede implementar muchas bases de datos. Los precios se estructuran por servidor en función de los núcleos y el almacenamiento.

- La [opción Hyperscale (Citus)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) funciona con la tecnología Citus Data. Permite un alto rendimiento mediante el *escalado horizontal* de una sola base de datos en cientos de nodos para ofrecer un rendimiento y una escala rápidos. Esta opción permite que el motor se ajuste a más datos en la memoria, paralelizar las consultas en cientos de nodos e indexar datos más rápido.

## <a name="nosql-data-in-azure"></a>Datos NoSQL en Azure

Cosmos DB es un servicio de base de datos NoSQL totalmente administrado y distribuido globalmente en la nube de Azure. Ha sido adoptado por muchas grandes empresas en todo el mundo, incluyendo Coca-Cola, Skype, ExxonMobil y Liberty Mutual.

Si sus servicios requieren una respuesta rápida desde cualquier parte del mundo, alta disponibilidad o escalabilidad elástica, Cosmos DB es una excelente opción. La figura 5-12 muestra Cosmos DB.

![Descripción general de Cosmos DB](./media/cosmos-db-overview.png)

**Figura 5-12**: Visión general de Cosmos DB

La figura anterior presenta muchas de las capacidades nativas de la nube integradas disponibles en Cosmos DB. En esta sección, vamos a echar un vistazo más de cerca a ellos.

### <a name="global-support"></a>Compatibilidad global

Las aplicaciones nativas de la nube a menudo tienen una audiencia global y requieren escala global.

Puede distribuir bases de datos de Cosmos entre regiones o en todo el mundo, colocando datos cerca de los usuarios, mejorando el tiempo de respuesta y reduciendo la latencia. Puede agregar o quitar una base de datos de una región sin pausar o volver a implementar los servicios. En segundo plano, Cosmos DB replica de forma transparente los datos en cada una de las regiones configuradas.

Cosmos DB admite la agrupación en clústeres [activa/activa](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) a nivel global, lo que le permite configurar cualquiera de las regiones de base de datos para admitir *escrituras y lecturas.*

El protocolo [Multi-Master](https://docs.microsoft.com/azure/cosmos-db/multi-master-benefits) es una característica importante de Cosmos DB que habilita la siguiente funcionalidad:

- Escalabilidad de escritura y lectura elásticas ilimitada.

- 99,999 % de disponibilidad de lectura y escritura en todo el mundo.

- Garantía de lecturas y escrituras atendidas en menos de 10 milisegundos en el percentil 99.

Con las [API de hospedaje](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)múltiple de Cosmos DB, el microservicio conoce automáticamente la región de Azure más cercana y le envía solicitudes. Cosmos DB identifica la región más cercana sin ningún cambio de configuración. Si una región deja de estar disponible, la función Multi-Homing enrutará automáticamente las solicitudes a la siguiente región disponible más cercana.

### <a name="multi-model-support"></a>Soporte multimodelo

Al replatformar aplicaciones monolíticas a una arquitectura nativa de la nube, los equipos de desarrollo a veces tienen que migrar almacenes de datos NoSQL de código abierto. Cosmos DB puede ayudarle a conservar su inversión en estos almacenes de datos NoSQL con su plataforma de datos *multimodelo.* En la figura 5-13 se muestran las API de [compatibilidad](https://www.wikiwand.com/en/Cosmos_DB)noSQL admitidas.

![Proveedores de Cosmos DB](./media/cosmos-db-providers.png)

**Figura 5-13**: Proveedores de Cosmos DB

Los equipos de desarrollo pueden migrar las bases de datos Mongo, Gremlin o Cassandra existentes a Cosmos DB con cambios mínimos en los datos o el código. Para las nuevas aplicaciones, los equipos de desarrollo pueden elegir entre las opciones de código abierto o el modelo de API de SQL integrado.

> Internamente, Cosmos almacena los datos en un formato de estructura simple compuesto por tipos de datos primitivos. Para cada solicitud, el motor de base de datos convierte los datos primitivos en la representación del modelo que ha seleccionado.

En la figura anterior, 5-13, tenga en cuenta la opción [Table API.](https://docs.microsoft.com/azure/cosmos-db/table-introduction) Esta API es una evolución de Azure Table Storage. Ambos comparten el mismo modelo de tabla subyacente, pero Table API de Cosmos DB agrega mejoras premium que no están disponibles en la API de Azure Storage. Estas características se contrastan en la Figura 5-4.

![Azure Table API](media/azure-table-api.png)

**Figura 5-14:** Proveedores de API de tabla de Azure

Los microservicios que consumen Azure Table Storage pueden migrar fácilmente a Table API de Cosmos DB. No se requiere ningún cambio de código.

### <a name="tunable-consistency"></a>Consistencia ajustable

Anteriormente, en la sección *Relacional frente a NoSQL,* analizamos el tema de la coherencia de los *datos.* La coherencia de los datos se refiere a la *integridad* de los datos. Los servicios nativos de la nube con datos distribuidos dependen de la replicación y deben hacer un equilibrio fundamental entre la coherencia de lectura, la disponibilidad y la latencia.

La mayoría de las bases de datos distribuidas permiten a los desarrolladores elegir entre dos modelos de coherencia: coherencia sólida y coherencia final. *La consistencia fuerte* es el estándar de oro de la programación de datos. Garantiza que una consulta siempre devolverá los datos más actuales, incluso si el sistema debe incurrir en latencia a la espera de que una actualización se replique en todas las copias de la base de datos. Mientras que una base de datos configurada para *la coherencia final* devolverá datos inmediatamente, incluso si esos datos no son la copia más reciente. Esta última opción permite una mayor disponibilidad, mayor escala y mayor rendimiento.

Azure Cosmos DB ofrece cinco modelos de [coherencia](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) bien definidos que se muestran en la Figura 5-15.

![Gráfico de coherencia de Cosmos DB](./media/cosmos-consistency-level-graph.png)

**Figura 5-15**: Niveles de coherencia de Cosmos DB

 Estas opciones le permiten realizar opciones precisas y compensaciones granulares por la coherencia, la disponibilidad y el rendimiento de los datos. La Figura 5-16 describe cada nivel.

![Niveles de coherencia de Cosmos DB](./media/cosmos-db-consistency-levels.png)

**Figura 5-16**: Descripción del nivel de coherencia de Cosmos DB

En el artículo [Getting Behind the 9-Ball: Cosmos DB Consistency Levels Explained](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/), el defensor del desarrollador de Microsoft Cloud, Jeremy Likeness, proporciona una excelente explicación de los cinco modelos.

### <a name="partitioning"></a>Creación de particiones

Azure Cosmos DB adopta la [partición](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) automática para escalar una base de datos para satisfacer las necesidades de rendimiento de los servicios nativos de la nube.

Puede administrar datos en datos de Cosmos DB mediante la creación de bases de datos, contenedores y elementos.

Los contenedores se viven en una base de datos de Cosmos DB y representan una agrupación independiente del esquema de elementos. Los elementos son los datos que se agregan al contenedor. Se representan como documentos, filas, nodos o bordes. Todos los elementos agregados a un contenedor se indizan automáticamente.

Para particionar el contenedor, los elementos se dividen en subconjuntos distintos denominados particiones lógicas. Las particiones lógicas se rellenan en función del valor de una clave de partición asociada a cada elemento de un contenedor. La figura 5-18 muestra dos contenedores cada uno con una partición lógica basada en un valor de clave de partición.

![Mecánica de partición de Cosmos DB](./media/cosmos-db-partitioning.png)

**Figura 5-18**: Mecánica de partición de Cosmos DB

Observe en la figura anterior cómo cada elemento incluye una clave de partición de 'ciudad' o 'aeropuerto'. La clave determina la partición lógica del elemento. Los artículos con un código de ciudad se asignan al contenedor de la izquierda y a los artículos con un código de aeropuerto, al contenedor de la derecha. La combinación del valor de clave de partición con el valor ID crea el índice de un elemento, que identifica de forma única el elemento.

Internamente, Cosmos DB administra automáticamente la ubicación de [particiones lógicas](https://docs.microsoft.com/azure/cosmos-db/partition-data) en particiones físicas para satisfacer las necesidades de escalabilidad y rendimiento del contenedor. A medida que aumentan los requisitos de almacenamiento y rendimiento de las aplicaciones, Azure Cosmos DB redistribuye las particiones lógicas en un mayor número de servidores. Cosmos DB administra las operaciones de redistribución y las invoca sin interrupción ni tiempo de inactividad.

## <a name="newsql-databases"></a>Bases de datos NewSQL

*NewSQL* es una tecnología de base de datos emergente que combina la escalabilidad distribuida de NoSQL con las garantías ACID de una base de datos relacional. Las bases de datos NewSQL son importantes para los sistemas empresariales que deben procesar grandes volúmenes de datos, en entornos distribuidos, con soporte transaccional completo y cumplimiento ACID. Aunque una base de datos NoSQL puede proporcionar escalabilidad masiva, no garantiza la coherencia de los datos. Los problemas intermitentes de los datos incoherentes pueden suponer una carga para el equipo de desarrollo. Los desarrolladores deben construir protecciones en su código de microservicio para administrar los problemas causados por datos incoherentes.

Cloud Native Computing Foundation (CNCF) cuenta con varios proyectos de bases de datos NewSQL.

| proyecto | Características |
| :-------- | :-------- |
| Cucaracha DB |Una base de datos relacional compatible con ACID que se escala globalmente. Agregue un nuevo nodo a un clúster y CockroachDB se encargue de equilibrar los datos entre instancias y geografías. Crea, administra y distribuye réplicas para garantizar la confiabilidad. Es de código abierto y está disponible de forma gratuita.  |
| TiDB | Una base de datos de código abierto que admite cargas de trabajo de procesamiento transaccional y analítico (HTAP) híbridos. Es compatible con MySQL y cuenta con escalabilidad horizontal, consistencia fuerte y alta disponibilidad.  TiDB actúa como un servidor MySQL. Puede seguir utilizando bibliotecas de cliente MySQL existentes, sin necesidad de realizar cambios de código extensos en la aplicación. |
| YugabyteDB | Una base de datos SQL distribuida de código abierto, de alto rendimiento. Admite baja latencia de consultas, resistencia frente a errores y distribución global de datos. YugabyteDB es compatible con PostgressSQL y gestiona cargas de trabajo RDBMS y OLTP de escalabilidad horizontal. El producto también es compatible con NoSQL y es compatible con Cassandra. |
|Vitess | Vitess es una solución de base de datos para implementar, escalar y administrar grandes clústeres de instancias MySQL. Se puede ejecutar en una arquitectura de nube pública o privada. Combina y amplía muchas características importantes de MySQL y cuenta con soporte de particionamiento vertical y horizontal. Originado por YouTube, Vitess ha estado sirviendo todo el tráfico de la base de datos de YouTube desde 2011. |

Los proyectos de código abierto de la figura anterior están disponibles en Cloud Native Computing Foundation. Tres de las ofertas son productos de base de datos completos, que incluyen compatibilidad con .NET Core. El otro, Vitess, es un sistema de agrupación en clústeres de bases de datos que escala horizontalmente grandes clústeres de instancias MySQL.

Un objetivo de diseño clave para las bases de datos NewSQL es trabajar de forma nativa en Kubernetes, aprovechando la resistencia y escalabilidad de la plataforma.

Las bases de datos NewSQL están diseñadas para prosperar en entornos de nube efímeros donde las máquinas virtuales subyacentes se pueden reiniciar o reprogramar en cualquier momento. Las bases de datos están diseñadas para sobrevivir a errores de nodo sin pérdida de datos ni tiempo de inactividad. CockroachDB, por ejemplo, es capaz de sobrevivir a una pérdida de máquina manteniendo tres réplicas coherentes de cualquier dato en los nodos de un clúster.

Kubernetes utiliza una *construcción Services* para permitir que un cliente dirija un grupo de procesos de bases de datos NewSQL idénticos desde una sola entrada DNS. Al desacoplar las instancias de base de datos de la dirección del servicio con el que está asociado, podemos escalar sin interrumpir las instancias de aplicación existentes. Enviar una solicitud a cualquier servicio en un momento dado siempre producirá el mismo resultado.

En este escenario, todas las instancias de base de datos son iguales. No hay relaciones primarias o secundarias. Técnicas como la *replicación de consenso* que se encuentra en CockroachDB permiten que cualquier nodo de base de datos controle cualquier solicitud. Si el nodo que recibe una solicitud con equilibrio de carga tiene los datos que necesita localmente, responde inmediatamente. Si no es así, el nodo se convierte en una puerta de enlace y reenvía la solicitud a los nodos adecuados para obtener la respuesta correcta. Desde la perspectiva del cliente, cada nodo de base de datos es el mismo: aparecen como una sola base de datos *lógica* con las garantías de coherencia de un sistema de un solo equipo, a pesar de tener docenas o incluso cientos de nodos que están trabajando en segundo plano.

Para obtener una visión detallada de la mecánica detrás de las bases de datos NewSQL, consulte el artículo [DASH: Four Properties of Kubernetes-Native Databases.](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

## <a name="data-migration-to-the-cloud"></a>Migración de datos a la nube

Una de las tareas que consumen más tiempo es migrar datos de una plataforma de datos a otra. [Azure Data Migration Service](https://azure.microsoft.com/services/database-migration/) puede ayudar a acelerar estos esfuerzos. Puede migrar datos de varios orígenes de base de datos externos a plataformas de Azure Data con un tiempo de inactividad mínimo. Las plataformas de destino incluyen los siguientes servicios:

- Azure SQL Database
- Azure Database for MySQL
- Azure Database for MariaDB
- Azure Database for PostgreSQL
- CosmosDB
  
El servicio proporciona recomendaciones para guiarle a través de los cambios necesarios para ejecutar una migración, tanto pequeña como grande.

>[!div class="step-by-step"]
>[Anterior](database-per-microservice.md)
>[Siguiente](azure-caching.md)
