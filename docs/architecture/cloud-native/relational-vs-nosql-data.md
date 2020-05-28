---
title: Soluciones relacionales y datos NoSQL
description: Más información sobre los datos relacionales y NoSQL en aplicaciones nativas de la nube
author: robvet
ms.date: 05/17/2020
ms.openlocfilehash: cc47faa4fcd4468de9ddc468e488297db4289ff5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613790"
---
# <a name="relational-vs-nosql-data"></a>Soluciones relacionales y datos NoSQL

Relacional y NoSQL son dos tipos de sistemas de base de datos que se implementan normalmente en aplicaciones nativas en la nube. Se compilan de forma diferente, almacenan los datos de manera diferente y se accede a ellos de forma diferente. En esta sección, veremos ambos. Más adelante en este capítulo, veremos una tecnología de base de datos emergente denominada *NewSQL*.

*Las bases de datos relacionales* han sido una tecnología predominante para décadas. Están consolidados, probados y ampliamente implementados. Los productos de base de datos, las herramientas y la experiencia en competencia abundan. Las bases de datos relacionales proporcionan un almacén de tablas de datos relacionadas. Estas tablas tienen un esquema fijo, usan SQL (Lenguaje de consulta estructurado) para administrar datos y admiten garantías ACID.

*Las bases de datos no-SQL* hacen referencia a almacenes de datos no relacionales de alto rendimiento. Excel en sus características de facilidad de uso, escalabilidad, resistencia y disponibilidad. En lugar de combinar tablas de datos normalizados, NoSQL almacena datos no estructurados o semiestructurados, a menudo en pares clave-valor o documentos JSON. Las bases de datos no-SQL normalmente no proporcionan garantías ACID más allá del ámbito de una sola partición de base de datos. Los servicios de gran volumen que requieren un tiempo de respuesta de subsegundo favorecen los almacenes de los mismos.

No se puede sobreasignar el impacto de las tecnologías [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) para sistemas nativos en la nube distribuida. La proliferación de nuevas tecnologías de datos en este espacio ha interrumpido soluciones que, una vez confiaba exclusivamente en las bases de datos relacionales.

Las bases de datos NoSQL incluyen varios modelos diferentes para el acceso y la administración de datos, cada uno de los cuales es adecuado para casos de uso específicos. La figura 5-9 presenta cuatro modelos comunes.

![Modelos de datos NoSQL](./media/types-of-nosql-datastores.png)

**Figura 5-9**: modelos de datos para bases de datos NoSQL

| Modelo | Características |
| :-------- | :-------- |
| Almacén de documentos | Los datos y los metadatos se almacenan de forma jerárquica en documentos basados en JSON dentro de la base de datos. |
| Almacén de valores de clave | La más sencilla de las bases de datos NoSQL, los datos se representan como una colección de pares clave-valor. |
| Almacén de columnas anchas | Los datos relacionados se almacenan como un conjunto de pares de clave-valor anidados dentro de una sola columna. |
| Almacén de grafos | Los datos se almacenan en una estructura de grafos como propiedades de nodo, borde y datos. |

## <a name="the-cap-theorem"></a>Teorema CAP

Para comprender las diferencias entre estos tipos de bases de datos, tenga en cuenta el CAP teorema, un conjunto de principios aplicados a los sistemas distribuidos que almacenan el estado. En la figura 5-10 se muestran las tres propiedades del CAP teorema.

![Teorema CAP](./media/cap-theorem.png)

**Figura 5-10**. Teorema CAP

El teorema indica que los sistemas de datos distribuidos ofrecerán un equilibrio entre coherencia, disponibilidad y tolerancia de particiones. Y, que cualquier base de datos solo puede garantizar *dos* de las tres propiedades:

- *Réplica.* Cada nodo del clúster responde con los datos más recientes, incluso si el sistema debe bloquear la solicitud hasta que se actualicen todas las réplicas. Si consulta un "sistema coherente" para un elemento que se está actualizando actualmente, esperará esa respuesta hasta que todas las réplicas se actualicen correctamente. Sin embargo, recibirá los datos más actuales.

- *Disponibilidad.* Cada nodo devuelve una respuesta inmediata, incluso si esa respuesta no es los datos más recientes. Si consulta un "sistema disponible" para un elemento que se está actualizando, obtendrá la mejor respuesta posible que el servicio pueda proporcionar en ese momento.

- *Tolerancia de partición.* Garantiza que el sistema siga funcionando incluso si se produce un error en un nodo de datos replicado o se pierde la conectividad con otros nodos de datos replicados.

Las bases de datos relacionales proporcionan normalmente coherencia y disponibilidad, pero no tolerancia a particiones. Normalmente se aprovisionan en un solo servidor y se escalan verticalmente agregando más recursos a la máquina.

Muchos sistemas de bases de datos relacionales admiten características de replicación integradas en las que se pueden realizar copias de la base de datos principal en otras instancias de servidor secundario. Las operaciones de escritura se realizan en la instancia principal y se replican en cada una de las secundarias. Tras un error, la instancia principal puede conmutar por error a una secundaria para proporcionar alta disponibilidad. Las secundarias también se pueden usar para distribuir operaciones de lectura. Aunque las operaciones de escritura siempre pasan a la réplica principal, las operaciones de lectura se pueden enrutar a cualquiera de las secundarias para reducir la carga del sistema.

Los datos también se pueden particionar horizontalmente en varios nodos, como con el [particionamiento](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-scale-introduction). Sin embargo, el particionamiento aumenta drásticamente la sobrecarga operativa al spittingr los datos en muchas partes que no se pueden comunicar fácilmente. La administración puede resultar costosa y lenta. Puede acabar afectando al rendimiento, las combinaciones de tablas y la integridad referencial.

Si las réplicas de datos han perdido la conectividad de red en un clúster de base de datos relacional "muy coherente", no podrá escribir en la base de datos. El sistema rechazaría la operación de escritura porque no puede replicar ese cambio en la otra réplica de datos. Cada réplica de datos tiene que actualizarse antes de que se pueda completar la transacción.

Las bases de datos NoSQL suelen admitir alta disponibilidad y tolerancia a particiones. Se escalan horizontalmente, a menudo a través de servidores de mercancías. Este enfoque proporciona una gran disponibilidad, tanto dentro como entre regiones geográficas a un costo reducido. Divida y replique los datos entre estos equipos, o nodos, proporcionando redundancia y tolerancia a errores. El inconveniente es la coherencia. Un cambio en los datos de un nodo NoSQL puede tardar algún tiempo en propagarse a otros nodos. Normalmente, un nodo de base de datos NoSQL proporcionará una respuesta inmediata a una consulta, incluso si los datos que se presentan están obsoletos y aún no se han actualizado.

Si las réplicas de datos han perdido la conectividad en un clúster de base de datos NoSQL de "alta disponibilidad", puede realizar una operación de escritura en la base de datos. El clúster de base de datos permitiría la operación de escritura y actualizaría cada réplica de datos a medida que esté disponible.

Este tipo de resultado se conoce como coherencia eventual, una característica de los sistemas de datos distribuidos en los que no se admiten las transacciones ACID. Es un breve retraso entre la actualización de un elemento de datos y el tiempo que se tarda en propagar esa actualización a cada uno de los nodos de réplica. En condiciones normales, el retraso suele ser breve, pero puede aumentar cuando surjan problemas. Por ejemplo, ¿qué ocurriría si actualizara un elemento de producto en una base de datos NoSQL en el Estados Unidos y consultase ese mismo elemento de datos desde un nodo de réplica en Europa? Recibirá la información del producto anterior, hasta que el clúster actualice el nodo europeo con el cambio del producto. Al devolver inmediatamente el resultado de una consulta y no esperar a que se actualicen todos los nodos de réplica, se obtiene enormes volúmenes y escalado, pero con la posibilidad de presentar datos antiguos.

La alta disponibilidad y la escalabilidad masiva suelen ser más críticas para el negocio que la coherencia fuerte. Los desarrolladores pueden implementar técnicas y patrones como sagas, CQRS y mensajería asincrónica para adoptar la coherencia final.

> En la actualidad, se debe tener cuidado al conidering las restricciones de teorema CAP. Ha surgido un nuevo tipo de base de datos, denominado NewSQL, que extiende el motor de base de datos relacional para admitir la escalabilidad horizontal y el rendimiento escalable de los sistemas NoSQL.

## <a name="considerations-for-relational-vs-nosql-systems"></a>Consideraciones sobre sistemas relacionales y NoSQL

En función de los requisitos de datos específicos, un microservicio basado en la nube nativo puede implementar un almacén de datos relacional, NoSQL o ambos.

|  Considere la posibilidad de un almacén de almacenamiento NoSQL cuando: | Considere una base de datos relacional cuando: |
| :-------- | :-------- |
| Tiene cargas de trabajo de gran volumen que requieren gran escala | El volumen de la carga de trabajo es coherente y requiere una escala mediana y grande |
| Las cargas de trabajo no requieren garantías ACID |  Se requieren garantías ACID |
| Los datos son dinámicos y cambian con frecuencia | Los datos son predecibles y muy estructurados |
| Los datos se pueden expresar sin relaciones | Los datos se expresan con mayor relación |  
| Necesita escrituras rápidas y la seguridad de escritura no es crítica | La seguridad de escritura es un requisito |  
| La recuperación de datos es sencilla y tiende a ser plana | Trabaja con consultas e informes complejos|
| Los datos requieren una distribución geográfica amplia | Los usuarios están más centralizados |
| La aplicación se implementará en hardware estándar, como con nubes públicas. | La aplicación se implementará en hardware grande y de alto nivel. |

En las secciones siguientes, exploraremos las opciones disponibles en la nube de Azure para almacenar y administrar los datos nativos de la nube.

## <a name="database-as-a-service"></a>Base de datos como servicio

Para empezar, puede aprovisionar una máquina virtual de Azure e instalar la base de datos de su elección para cada servicio. Aunque tenga control total sobre el entorno, supongamos que tiene muchas características integradas de la plataforma en la nube. También podría ser responsable de administrar la máquina virtual y la base de datos para cada servicio. Este enfoque podría llevar mucho tiempo y caro.

En su lugar, las aplicaciones nativas para la nube favorecen los servicios de datos expuestos como un [servicio (DBaaS)](https://www.stratoscale.com/blog/dbaas/what-is-database-as-a-service/). Totalmente administrado por un proveedor de la nube, estos servicios ofrecen seguridad, escalabilidad y supervisión integrados. En lugar de poseer el servicio, simplemente se usa como servicio de [respaldo](./definition.md#backing-services). El proveedor opera el recurso a escala y asume la responsabilidad del rendimiento y el mantenimiento.

Se pueden configurar en las regiones y zonas de disponibilidad de la nube para lograr alta disponibilidad. Todos admiten la capacidad Just-in-Time y un modelo de pago por uso. Azure incluye diferentes tipos de opciones de servicio de datos administrados, cada una con ventajas específicas.

En primer lugar, veremos los servicios relacionales de DBaaS disponibles en Azure. Verá que la base de datos insignia de Microsoft SQL Server está disponible junto con varias opciones de código abierto. A continuación, hablaremos sobre los servicios de datos NoSQL en Azure.

## <a name="azure-relational-databases"></a>Bases de datos relacionales de Azure

En el caso de los microservicios nativos en la nube que requieren datos relacionales, Azure ofrece cuatro ofertas de bases de datos relacionales como servicio (DBaaS), que se muestran en la figura 5-11.

![Bases de datos relacionales administradas en Azure](./media/azure-managed-databases.png)

**Figura 5-11**. Bases de datos relacionales administradas disponibles en Azure

En la ilustración anterior, tenga en cuenta que cada una de ellas se basa en una infraestructura de DBaaS común que incluye funcionalidades clave sin costo adicional.

Estas características son especialmente importantes para las organizaciones que aprovisionan un gran número de bases de datos, pero tienen recursos limitados para administrarlas.
Puede aprovisionar una base de datos de Azure en minutos seleccionando la cantidad de núcleos de procesamiento, la memoria y el almacenamiento subyacente. Puede escalar la base de datos sobre la marcha y ajustar dinámicamente los recursos con poco o ningún tiempo de inactividad.

## <a name="azure-sql-database"></a>Azure SQL Database

Los equipos de desarrollo con experiencia en Microsoft SQL Server deben considerar [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/). Es una base de datos relacional como servicio (DBaaS) totalmente administrada basada en el Motor de base de datos de Microsoft SQL Server. El servicio comparte muchas características que se encuentran en la versión local de SQL Server y ejecuta la versión estable más reciente del Motor de base de datos de SQL Server.

Para su uso con un microservicio nativo en la nube, Azure SQL Database está disponible con tres opciones de implementación:

- Una Base de datos única representa una SQL Database totalmente administrada que se ejecuta en un [servidor de Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-servers) en la nube de Azure. La base de datos se considera [*incluida*](https://docs.microsoft.com/sql/relational-databases/databases/contained-databases) ya que no tiene dependencias de configuración en el servidor de base de datos subyacente.
  
- Un [instancia administrada](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance) es una instancia totalmente administrada de la Microsoft SQL Server motor de base de datos que proporciona compatibilidad de% casi 100 con un SQL Server local. Esta opción admite bases de datos mayores, hasta 35 TB y se coloca en una [Virtual Network de Azure](https://docs.microsoft.com/azure/virtual-network/virtual-networks-overview) para un mejor aislamiento.

- [Azure SQL Database sin servidor](https://docs.microsoft.com/azure/sql-database/sql-database-serverless) es un nivel de proceso para una base de datos única que se escala automáticamente en función de la demanda de la carga de trabajo. Solo se factura por la cantidad de proceso utilizado por segundo. El servicio es adecuado para cargas de trabajo con patrones de uso intermitentes e imprevisibles, intercalados con períodos de inactividad. El nivel de proceso sin servidor también pone en pausa automáticamente las bases de datos durante períodos inactivos, de modo que solo se facturan los cargos de almacenamiento. Se reanuda automáticamente cuando se devuelve la actividad.

Además de la pila de Microsoft SQL Server tradicional, Azure también incluye versiones administradas de tres bases de datos de código abierto conocidas.

## <a name="open-source-databases-in-azure"></a>Bases de datos de código abierto en Azure

Las bases de datos relacionales de código abierto se han convertido en una opción popular para aplicaciones nativas en la nube. Muchas empresas favorecen el uso de productos comerciales de bases de datos, especialmente para ahorrar costos. Muchos equipos de desarrollo disfrutan de la flexibilidad, el desarrollo respaldado por la comunidad y el ecosistema de herramientas y extensiones. Las bases de datos de código abierto se pueden implementar en varios proveedores de nube, lo que ayuda a minimizar el problema de "bloqueo de proveedor".

Los desarrolladores pueden hospedar fácilmente cualquier base de datos de código abierto en una máquina virtual de Azure. A la vez que proporciona control total, este enfoque le lleva por el enlace para la administración, supervisión y mantenimiento de la base de datos y la máquina virtual.

Sin embargo, Microsoft continúa su compromiso de mantener Azure como una "plataforma abierta", ya que ofrece varias bases de datos populares de código abierto como servicios de DBaaS *totalmente administrados* .

### <a name="azure-database-for-mysql"></a>Azure Database for MySQL

[MySQL](https://en.wikipedia.org/wiki/MySQL)   es una base de datos relacional de código abierto y un pilar para aplicaciones basadas en la [pila de software LAMP](https://en.wikipedia.org/wiki/LAMP_(software_bundle)). Ampliamente elegido para cargas de trabajo de *lectura intensiva* , se usa en muchas organizaciones de gran tamaño, como Facebook, Twitter y YouTube. La edición Community está disponible de forma gratuita, mientras que la edición Enterprise requiere una compra de licencias. Creado originalmente en 1995, el producto fue adquirido por Sun Microsystems en 2008. Oracle adquirió Sun y MySQL en 2010.

[Azure Database for MySQL](https://azure.microsoft.com/services/mysql/) es un servicio de base de datos relacional administrado basado en el motor de servidor de MySQL de código abierto. Usa MySQL Community Edition. El servidor de Azure MySQL es el punto administrativo para el servicio. Es el mismo motor de MySQL Server que se usa para las implementaciones locales. El motor puede crear una sola base de datos por servidor o varias bases de datos por cada servidor que comparta recursos. Puede seguir administrando los datos con las mismas herramientas de código abierto sin tener que aprender nuevas habilidades ni administrar máquinas virtuales.

### <a name="azure-database-for-mariadb"></a>Azure Database for MariaDB

[MariaDB](https://mariadb.com/) El servidor es otro conocido servidor de base de datos de código abierto. Se creó como una *bifurcación* de MySQL cuando Oracle compró Sun Microsystems, que poseía MySQL. La intención era asegurarse de que MariaDB seguía siendo código abierto. Como MariaDB es una bifurcación de MySQL, los datos y las definiciones de tabla son compatibles y los protocolos, las estructuras y las API de cliente son Close-spojit.

MariaDB tiene una comunidad sólida y la usan muchas grandes empresas. Aunque Oracle sigue manteniendo, mejorando y respaldando MySQL, MariaDB Foundation administra MariaDB, lo que permite contribuciones públicas al producto y a la documentación.

[Azure Database for MariaDB](https://azure.microsoft.com/services/mariadb/) es una base de datos relacional totalmente administrada como servicio en la nube de Azure. El servicio se basa en el motor de servidor de MariaDB Community Edition. Puede administrar cargas de trabajo críticas con un rendimiento predecible y escalabilidad dinámica.

### <a name="azure-database-for-postgresql"></a>Azure Database for PostgreSQL

[PostgreSQL](https://www.postgresql.org/) es una base de datos relacional de código abierto con más de 30 años de desarrollo activo. PostgresSQL tiene una reputación sólida para la confiabilidad y la integridad de los datos. Es una característica enriquecida, compatible con SQL y se considera más eficaz que MySQL, especialmente para cargas de trabajo con consultas complejas y escrituras pesadas. Muchas grandes empresas, como Apple, Red Hat y Fujitsu, han creado productos con PostgreSQL.

[Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/) es un servicio de base de datos relacional totalmente administrado, basado en el motor de base de datos Postgres de código abierto. El servicio admite muchas plataformas de desarrollo, como C++, Java, Python, node, C \# y php. Puede migrar las bases de datos de PostgreSQL a ella mediante la herramienta [de la interfaz de la línea de comandos](https://datamigration.microsoft.com/scenario/postgresql-to-azurepostgresql?step=1) o el servicio de migración de datos de Azure.

Azure Database for PostgreSQL está disponible con dos opciones de implementación:

- La opción de implementación de [servidor único](https://docs.microsoft.com/azure/postgresql/concepts-servers) es un punto administrativo central para varias bases de datos en las que se pueden implementar muchas bases de datos. Los precios se estructuran por servidor en función de los núcleos y el almacenamiento.

- La [opción de hiperescala (citus)](https://azure.microsoft.com/blog/get-high-performance-scaling-for-your-azure-database-workloads-with-hyperscale/) está basada en la tecnología de datos citus. Permite un alto rendimiento al *escalar horizontalmente* una base de datos única en cientos de nodos para ofrecer un rendimiento y escalado rápidos. Esta opción permite al motor ajustar más datos en memoria, paralelizar las consultas en cientos de nodos y indexar los datos más rápidamente.

## <a name="nosql-data-in-azure"></a>Datos NoSQL en Azure

Cosmos DB es un servicio de base de datos NoSQL distribuido globalmente y totalmente administrado en la nube de Azure. Ha sido adoptada por muchas grandes empresas de todo el mundo, como Coca-Cola, Skype, ExxonMobil y Liberty Mutual.

Si los servicios requieren una respuesta rápida desde cualquier lugar del mundo, alta disponibilidad o escalabilidad elástica, Cosmos DB es una excelente opción. En la figura 5-12 se muestra Cosmos DB.

![Información general de Cosmos DB](./media/cosmos-db-overview.png)

**Figura 5-12**: información general de Cosmos dB

En la ilustración anterior se presentan muchas de las capacidades integradas de la nube nativas disponibles en Cosmos DB. En esta sección, examinaremos más de cerca.

### <a name="global-support"></a>Compatibilidad global

Las aplicaciones nativas en la nube a menudo tienen una audiencia global y requieren escala global.

Puede distribuir las bases de datos de Cosmos entre regiones o en todo el mundo, colocar los datos cerca de los usuarios, mejorar el tiempo de respuesta y reducir la latencia. Puede Agregar o quitar una base de datos de una región sin pausar o volver a implementar los servicios. En segundo plano, Cosmos DB replica de forma transparente los datos en cada una de las regiones configuradas.

Cosmos DB admite la agrupación en clústeres [activo/activo](https://kemptechnologies.com/white-papers/unfog-confusion-active-passive-activeactive-load-balancing/) en el nivel global, lo que permite configurar cualquiera de las regiones de la base de datos para admitir *escrituras y lecturas*.

El protocolo de [varios maestros](https://docs.microsoft.com/azure/cosmos-db/multi-master-benefits) es una característica importante de Cosmos dB que habilita la siguiente funcionalidad:

- Escalabilidad de escritura y lectura elásticas ilimitada.

- 99,999 % de disponibilidad de lectura y escritura en todo el mundo.

- Garantía de lecturas y escrituras atendidas en menos de 10 milisegundos en el percentil 99.

Con el Cosmos DB [API](https://docs.microsoft.com/azure/cosmos-db/distribute-data-globally)de hospedaje múltiple, el microservicio es consciente automáticamente de la región de Azure más cercana y envía solicitudes a él. La región más cercana se identifica mediante Cosmos DB sin ningún cambio de configuración. En caso de que una región deje de estar disponible, la característica de alojamiento múltiple enrutará automáticamente las solicitudes a la siguiente región disponible más cercana.

### <a name="multi-model-support"></a>Compatibilidad con varios modelos

Al volver a platformar aplicaciones monolíticas en una arquitectura nativa en la nube, los equipos de desarrollo a veces tienen que migrar almacenes de datos NoSQL de código abierto. Cosmos DB puede ayudarle a mantener su inversión en estos almacenes de datos NoSQL con su plataforma de datos de *varios modelos* . En la tabla siguiente se muestran las [API de compatibilidad](https://www.wikiwand.com/en/Cosmos_DB)NoSQL admitidas.

| Proveedor | Descripción  |
| :-------- | :-------- |
| API DE SQL | API propietaria que admite documentos JSON y consultas basadas en SQL |
| API de Mongo DB | Admite API de Mongo DB y documentos JSON|
| API de Gremlin | Admite Gremlin API con nodos basados en gráficos y representaciones de datos perimetrales |
| Cassandra API | Admite la API de Casandra para representaciones de datos de columnas anchas |  
| Table API  | Admite Azure Table Storage con mejoras Premium |  
| API de etcd | Habilita Cosmos DB como una memoria auxiliar para los clústeres de Azure Kubernetes Service |

Los equipos de desarrollo pueden migrar las bases de datos existentes de Mongo, Gremlin o Cassandra a Cosmos DB con cambios mínimos en los datos o en el código. En el caso de las nuevas aplicaciones, los equipos de desarrollo pueden elegir entre las opciones de código abierto o el modelo integrado de la API de SQL.

> Internamente, Cosmos almacena los datos en un formato de estructura simple formado por tipos de datos primitivos. Para cada solicitud, el motor de base de datos traduce los datos primitivos en la representación del modelo que ha seleccionado.

En la tabla anterior, tenga en cuenta la opción [TABLE API](https://docs.microsoft.com/azure/cosmos-db/table-introduction) . Esta API es una evolución de Azure Table Storage. Ambos comparten el mismo modelo de tabla subyacente, pero el Cosmos DB Table API agrega mejoras Premium que no están disponibles en la API de Azure Storage. En la tabla siguiente se contrastan las características.

|  | Azure Table Storage  | Azure Cosmos DB  |
| :-------- | :-------- |:-------- |
| Latencia | Rápido | Latencia de milisegundos de un solo dígito para lecturas y escrituras en cualquier parte del mundo |
| Throughput | Límite de 20.000 operaciones por tabla | 10 millones operaciones por tabla |
| Distribución global | Una sola región con una región de lectura secundaria única opcional | Distribuciones llave en mano a todas las regiones con conmutación automática por error |
| Indización | Solo disponible para las propiedades de clave de fila y partición | Indexación automática de todas las propiedades |
| Precios | Basado en el almacenamiento | Basado en el rendimiento |

Los microservicios que usan Azure Table Storage pueden migrar fácilmente a la Table API de Cosmos DB. No se requiere ningún cambio de código.

### <a name="tunable-consistency"></a>Coherencia ajustable

Anteriormente en la sección *relacional frente a NoSQL* , analizamos el asunto de la coherencia de los *datos*. La coherencia de los datos hace referencia a la *integridad* de los datos. Los servicios nativos de la nube con datos distribuidos se basan en la replicación y deben hacer un equilibrio fundamental entre la coherencia de lectura, la disponibilidad y la latencia.

La mayoría de las bases de datos distribuidas permiten a los desarrolladores elegir entre dos modelos de coherencia: coherencia fuerte y coherencia final. La *coherencia fuerte* es el estándar Gold de programación de datos. Garantiza que una consulta siempre devolverá los datos más actuales, incluso si el sistema debe incurrir en latencia de espera para que una actualización se replique en todas las copias de la base de datos. Aunque una base de datos configurada para la *coherencia final* devolverá los datos inmediatamente, incluso si no son la copia más reciente. La última opción permite una mayor disponibilidad, mayor escala y mayor rendimiento.

Azure Cosmos DB ofrece cinco [modelos de coherencia](https://docs.microsoft.com/azure/cosmos-db/consistency-levels) bien definidos que se muestran en la figura 5-13.

![Gráfico de coherencia Cosmos DB](./media/cosmos-consistency-level-graph.png)

**Figura 5-13**: niveles de coherencia de Cosmos dB

 Estas opciones le permiten tomar decisiones precisas e inconvenientes para la coherencia, la disponibilidad y el rendimiento de los datos. Los niveles se muestran en la tabla siguiente.

| Nivel de coherencia | Descripción  |
| :-------- | :-------- |
| Ocasional | No hay garantía de ordenación para las lecturas. Finalmente, las réplicas convergerán. |
| Prefijo constante | Las lecturas siguen siendo eventuales, pero los datos se devuelven en el orden en que se escriben. |
| Sesión | Garantiza que se pueden leer los datos escritos durante la sesión actual. Es el nivel de coherencia predeterminado. |
| De obsolescencia entrelazada | Lee las escrituras finales por el intervalo que especifique. |  
| Alta  | Se garantiza que las lecturas devuelven la última versión confirmada de un elemento. Un cliente nunca ve una lectura parcial o no confirmada. |  

En el artículo que se [encuentra detrás de la bola: Cosmos dB se han explicado los niveles de coherencia](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/), el administrador de programas de Microsoft Jeremy Likness proporciona una excelente explicación de los cinco modelos.

### <a name="partitioning"></a>Creación de particiones

Azure Cosmos DB adopta la creación automática de [particiones](https://docs.microsoft.com/azure/cosmos-db/partitioning-overview) para escalar una base de datos con el fin de satisfacer las necesidades de rendimiento de los servicios nativos de la nube.

Los datos de Cosmos DB se administran mediante la creación de bases de datos, contenedores y elementos.

Los contenedores residen en una base de datos de Cosmos DB y representan una agrupación de elementos independiente del esquema. Los elementos son los datos que se agregan al contenedor. Se representan como documentos, filas, nodos o bordes. Todos los elementos agregados a un contenedor se indexan automáticamente.

Para particionar el contenedor, los elementos se dividen en subconjuntos distintos denominados particiones lógicas. Las particiones lógicas se rellenan en función del valor de una clave de partición asociada a cada elemento de un contenedor. En la figura 5-14 se muestran dos contenedores cada uno con una partición lógica basada en un valor de clave de partición.

![Mecanismos de creación de particiones Cosmos DB](./media/cosmos-db-partitioning.png)

**Figura 5-14**: mecanismos de creación de particiones Cosmos dB

Observe en la ilustración anterior cómo cada elemento incluye una clave de partición de ' City ' o ' aeropuerto '. La clave determina la partición lógica del elemento. Los elementos con un código de ciudad se asignan al contenedor de la izquierda, y los elementos con un código de aeropuerto, al contenedor de la derecha. Al combinar el valor de la clave de partición con el valor de ID se crea el índice de un elemento, que identifica de forma única el elemento.

Internamente, Cosmos DB administra automáticamente la ubicación de las [particiones lógicas](https://docs.microsoft.com/azure/cosmos-db/partition-data) en las particiones físicas para satisfacer las necesidades de escalabilidad y rendimiento del contenedor. A medida que aumentan el rendimiento de la aplicación y los requisitos de almacenamiento, Azure Cosmos DB redistribuye las particiones lógicas en un número mayor de servidores. Las operaciones de redistribución se administran mediante Cosmos DB y se invocan sin interrupción ni tiempo de inactividad.

## <a name="newsql-databases"></a>Bases de datos de NewSQL

*NewSQL*   es una tecnología de base de datos emergente que combina la escalabilidad distribuida de NoSQL con las garantías ACID de una base de datos relacional. Las bases de datos de NewSQL son importantes para los sistemas empresariales que deben procesar grandes volúmenes de datos, en entornos distribuidos, con compatibilidad total transaccional y cumplimiento de ACID. Aunque una base de datos NoSQL puede proporcionar una escalabilidad masiva, no garantiza la coherencia de los datos. Los problemas intermitentes de los datos incoherentes pueden suponer una carga en el equipo de desarrollo. Los desarrolladores deben crear medidas de seguridad en su código de microservicio para administrar los problemas causados por datos incoherentes.

Cloud Native Computing Foundation (CNCF) incluye varios proyectos de base de datos NewSQL.

| Project | Características |
| :-------- | :-------- |
| BASE de Cockroach |Base de datos relacional compatible con ACID que se escala globalmente. Agregar un nuevo nodo a un clúster y CockroachDB se encarga de equilibrar los datos entre las instancias y las zonas geográficas. Crea, administra y distribuye réplicas para garantizar la confiabilidad. Es de código abierto y está disponible libremente.  |
| TiDB | Una base de datos de código abierto que admite cargas de trabajo de procesamiento analítico y transaccional híbridos (HTAP). Es compatible con MySQL y ofrece escalabilidad horizontal, coherencia alta y alta disponibilidad.  TiDB actúa como un servidor MySQL. Puede seguir usando las bibliotecas de cliente de MySQL existentes, sin necesidad de realizar cambios de código completos en la aplicación. |
| YugabyteDB | Una base de datos SQL distribuida de código abierto y de alto rendimiento. Admite una latencia de consulta baja, resistencia contra errores y distribución de datos global. YugabyteDB es compatible con PostgressSQL y controla las cargas de trabajo de OLTP y escalabilidad horizontal de Internet. El producto también admite NoSQL y es compatible con Cassandra. |
|Vitess | Vitess es una solución de base de datos para implementar, escalar y administrar clústeres de gran tamaño de instancias de MySQL. Puede ejecutarse en una arquitectura de nube pública o privada. Vitess combina y extiende muchas características y características de MySQL importantes, así como la compatibilidad con el particionamiento vertical y horizontal. Creado por YouTube, Vitess ha estado atendiendo todo el tráfico de base de datos de YouTube desde 2011. |

Los proyectos de código abierto de la ilustración anterior están disponibles desde Cloud Native Computing Foundation. Tres de las ofertas son productos de base de datos completos, que incluyen compatibilidad con .NET Core. El otro, Vitess, es un sistema de agrupación en clústeres de bases de datos que escala horizontalmente grandes clústeres de instancias de MySQL.

Un objetivo de diseño clave para las bases de datos de NewSQL es trabajar de forma nativa en Kubernetes, aprovechando la resistencia y la escalabilidad de la plataforma.

Las bases de datos de NewSQL están diseñadas para prosperar en entornos de nube efímera en los que las máquinas virtuales subyacentes se pueden reiniciar o volver a programar en un momento dado. Las bases de datos están diseñadas para sobrevivir a errores de nodo sin pérdida de datos ni tiempo de inactividad. Por ejemplo, CockroachDB puede sobrevivir a una pérdida de máquina al mantener tres réplicas coherentes de los datos en los nodos de un clúster.

Kubernetes usa una *construcción de servicios* para permitir a un cliente direccionar un grupo de procesos de bases de datos de NewSQL idénticos desde una única entrada DNS. Al desacoplar las instancias de base de datos de la dirección del servicio con el que está asociada, se puede escalar sin interrumpir las instancias de aplicación existentes. Si se envía una solicitud a cualquier servicio en un momento dado, siempre se producirá el mismo resultado.

En este escenario, todas las instancias de base de datos son iguales. No hay relaciones principales o secundarias. Las técnicas como el consenso de la *replicación* que se encuentra en CockroachDB permiten que cualquier nodo de base de datos controle cualquier solicitud. Si el nodo que recibe una solicitud de carga equilibrada tiene los datos que necesita localmente, responde inmediatamente. En caso contrario, el nodo se convierte en una puerta de enlace y reenvía la solicitud a los nodos adecuados para obtener la respuesta correcta. Desde la perspectiva del cliente, cada nodo de base de datos es el mismo: aparecen como una sola base de datos *lógica* con las garantías de coherencia de un sistema de un solo equipo, a pesar de tener docenas o incluso centenares de nodos que trabajan en segundo plano.

Para obtener una visión detallada de las bases de datos de NewSQLs subyacentes, consulte el artículo [Dash: cuatro Properties of Kubernetes-Native Databases](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/) .

## <a name="data-migration-to-the-cloud"></a>Migración de datos a la nube

Una de las tareas más lentas es migrar datos de una plataforma de datos a otra. El [servicio de migración de datos de Azure](https://azure.microsoft.com/services/database-migration/) puede ayudar a acelerar estos esfuerzos. Puede migrar datos de varios orígenes de base de datos externos a plataformas de datos de Azure con un tiempo de inactividad mínimo. Las plataformas de destino incluyen los siguientes servicios:

- Azure SQL Database
- Azure Database for MySQL
- Azure Database for MariaDB
- Azure Database for PostgreSQL
- CosmosDB
  
El servicio proporciona recomendaciones que le guiarán a través de los cambios necesarios para ejecutar una migración, tanto pequeña como grande.

>[!div class="step-by-step"]
>[Anterior](distributed-data.md)
>[Siguiente](azure-caching.md)
