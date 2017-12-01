---
title: "Diseñar un microservicio orientados a DDD"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Diseñar un microservicio orientados a DDD"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: df45441089fd59d5e0e52b4bcec409adcc11fb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-ddd-oriented-microservice"></a>Diseñar un microservicio orientados a DDD

Diseño basado en dominio (DDD) encarga modelado basado en la realidad de negocio que sea relevante para los casos de uso. En el contexto de la creación de aplicaciones, DDD habla sobre los problemas como dominios. Describe áreas con problemas independientes como limitado contextos (cada contexto limitado se correlaciona con un microservicio) y resalta un lenguaje común de hablar acerca de estos problemas. También sugiere muchos conceptos técnicos y los patrones, similares a las entidades de dominio con modelos enriquecidos (no [modelo de dominio anemic](https://martinfowler.com/bliki/AnemicDomainModel.html)), valor objetos, agregados y raíz agregada (o entidad raíz), las reglas para admitir la implementación interna. Esta sección presenta el diseño e implementación de esos patrones internos.

A veces dichas DDD técnicas reglas y patrones se perciban como obstáculos que tienen una pronunciada curva de aprendizaje para implementar métodos DDD. Pero lo importante es no los patrones a sí mismos, pero el código de la organización para que se alinee a los problemas empresariales y con los mismos términos de negocio (lenguaje ubicuo). Además, deben aplicarse DDD enfoques solo si está implementando microservicios complejos con reglas de negocios importantes. Responsabilidades más sencillas, como un servicio CRUD, se pueden administrar con los enfoques más sencillos.

Dónde debe dibujar los límites de la tarea es la clave cuando diseñe y definir un microservicio. Patrones DDD le ayudan a comprender la complejidad del dominio. Para el modelo de dominio en cada contexto limitado, identificar y definir las entidades, los objetos de valor y los agregados que modelan el dominio. Crear y perfeccionar un modelo de dominio que se encuentra dentro de un límite que define el contexto. Y eso es muy explícita en forma de un microservicio. Los componentes dentro de esos límites acabar siendo su microservicios, aunque en algunos casos una continuidad del negocio o microservicios de negocios pueden estar compuesto de varios servicios físicos. DDD es acerca de los límites y por lo tanto, son microservicios.

## <a name="keep-the-microservice-context-boundaries-relatively-small"></a>Mantener los límites del contexto la microservicio relativamente pequeño

Determinar dónde colocar los límites entre contextos limitado equilibra dos objetivos de la competencia. En primer lugar, desea crear inicialmente la microservicios más pequeño posible, aunque no debe ser el controlador principal; debe crear un límite alrededor, lo que necesita cohesión. En segundo lugar, desea evitar las comunicaciones locuaces entre microservicios. Estos objetivos pueden contradecir entre sí. Se debe equilibrar por descomponer el sistema en tantos microservicios pequeños que lo haría con hasta que vea los límites de comunicación creciendo rápidamente con cada intento adicional para separar un nuevo contexto limitado. Cohesión es clave dentro de un único contexto enlazado.

Es similar a la [olor a código inapropiado intimidad](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy) al implementar las clases. Si necesitan dos microservicios mucho colaborar entre sí, probablemente deben ser el mismo microservicio.

Otra manera de enfocar todo esto es autonomía. Si un microservicio debe depende de otro servicio para una solicitud de servicio directamente, no es realmente autónomo.

## <a name="layers-in-ddd-microservices"></a>Capas en DDD microservicios

La mayoría de las aplicaciones de enterprise con significativos para el negocio y complejidad técnica se definen mediante varias capas. Las capas son un artefacto de lógico y no están relacionadas con la implementación del servicio. Existen para ayudar a los desarrolladores administrar la complejidad del código. Diferentes niveles (por ejemplo, el nivel de modelo de dominio frente a la capa de presentación, etc.) podrían tener diferentes tipos, que exige las traducciones entre dichos tipos.

Por ejemplo, una entidad se pudo cargar desde la base de datos. A continuación, parte de esa información o una agregación de información que incluye datos adicionales de otras entidades, puede enviarse a la interfaz de usuario a través de una API de REST de Web de cliente. El punto aquí es que la entidad de dominio está dentro de la capa del modelo de dominio y no se debería propagar a otras áreas que no pertenece a, al igual que en el nivel de presentación.

Además, debe tener entidades siempre válido (vea la [diseñar validaciones en el nivel de modelo de dominio](#designing-validations-in-the-domain-model-layer) sección) controla las raíces de agregado (entidades raíz). Por lo tanto, las entidades no se deberían enlazar a las vistas de cliente, porque en el nivel de interfaz de usuario algunos datos podrían no se pueden validar. Para esto es el modelo de vista. El modelo de vista es un modelo de datos exclusivamente para las necesidades de la capa de presentación. Las entidades de dominio no pertenecen directamente en el modelo de vista. En su lugar, es necesario traducir entre entidades ViewModels y el dominio y viceversa.

Cuando abordar complejidad, es importante tener un modelo de dominio que controla las raíces agregadas (entraremos en esto con más detalle más adelante) que se aseguran de que todas las invariantes y reglas relacionadas con ese grupo de entidades (agregados) se realizan a través de una única entrada punto o puerta de la raíz agregada.

Figura 9-5 se muestra cómo se implementa un diseño en capas en la aplicación eShopOnContainers.

![](./media/image6.png)

**Figura 9-5**. Capas DDD en la ordenación microservicio en eShopOnContainers

Desea diseñar el sistema para que cada nivel se comunica sólo con determinadas otras capas. Puede que sea más fácil aplicar si las capas se implementan como bibliotecas de clases diferentes, porque puede identificar claramente qué dependencias estén establecidas entre las bibliotecas. Por ejemplo, el nivel de modelo de dominio no debe tomar una dependencia en cualquier otra capa (las clases del modelo de dominio deben ser objetos CLR antiguos sin formato o [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object), clases). Como se muestra en la figura 9-6, la **Ordering.Domain** biblioteca de capa tiene dependencias sólo en las bibliotecas de .NET Core pero no en cualquier otra biblioteca personalizada (biblioteca de datos, biblioteca de persistencia, etcetera).

![](./media/image7.PNG)

**Figura 9-6**. Capas que se implementa como bibliotecas permiten un mejor control de las dependencias existentes entre capas

### <a name="the-domain-model-layer"></a>El nivel de modelo de dominio

Libro excelente de Eric Evans [dominio controlado por diseño](http://domainlanguage.com/ddd/) dice lo siguiente acerca de la capa del modelo de dominio y el nivel de aplicación.

**Nivel de modelo de dominio**: responsables para representar conceptos del negocio, información sobre la situación de negocio y reglas de negocios. Estado que refleja la situación empresarial se controla y usado aquí, aunque se delegan los detalles técnicos de almacenarla en la infraestructura. Este nivel es el núcleo de software empresarial.

El nivel de modelo de dominio es donde se expresa el negocio. Al implementar un nivel de modelo de dominio de microservicio en. NET, que se acumulan se codifica como una biblioteca de clases con las entidades de dominio que capturan datos más comportamiento (métodos con una lógica).

Después de la [omisión de persistencia](http://deviq.com/persistence-ignorance/) y [omisión de infraestructura](https://ayende.com/blog/3137/infrastructure-ignorance) principios, este nivel deben omitir completamente los detalles de persistencia de datos. El nivel de infraestructura se deberían realizar estas tareas de persistencia. Por lo tanto, este nivel no debe tener dependencias directas en la infraestructura, lo que significa que una regla de importante es que las clases de entidad del modelo de dominio deben ser [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)s.

Las entidades de dominio no deben tener ninguna dependencia directa (por ejemplo, se deriva de una clase base) con cualquier marco de trabajo de la infraestructura de acceso de datos como Entity Framework o NHibernate. Lo ideal es que, las entidades de dominio no deben derivarse de o implementar cualquier tipo definido en cualquier marco de infraestructura.

Marcos de trabajo ORM más modernos como Entity Framework Core permiten este enfoque, de forma que las clases de modelo de dominio no se acoplan a la infraestructura. Sin embargo, con entidades POCO no siempre es posible cuando se usan ciertas bases de datos NoSQL y marcos de trabajo, como actores y colecciones confiable en Azure Service Fabric.

Aunque es importante seguir el principio de omisión de persistencia para el modelo de dominio, no debe ignorar problemas de persistencia. Todavía es muy importante comprender el modelo de datos físicos y cómo se asigna a un modelo de objetos de entidad. En caso contrario, puede crear diseños imposibles.

Además, esto no significa que puede tomar un modelo diseñado para una base de datos relacional y directamente moverla a un NoSQL o bases de datos orientado en el documento. En algunos modelos de entidad, es posible que ajuste el modelo, pero normalmente no. Todavía hay restricciones que debe cumplir el modelo de entidad, basada en la tecnología de almacenamiento y la tecnología ORM.

### <a name="the-application-layer"></a>El nivel de aplicación

Mover el nivel de aplicación, que le podemos citar nuevo libro de Eric Evans [dominio controlado por diseño](http://domainlanguage.com/ddd/):

**Capa de aplicación:** define los trabajos que el software se supone que debe para hacer y dirige los objetos de dominio expresivo para resolver problemas. Las tareas de que este nivel es responsable son significativas para la empresa o es necesario para la interacción con las capas de aplicación de otros sistemas. Esta capa se mantiene fina. No contiene reglas de negocios o conocimiento, pero solo las tareas de coordenadas y los delegados funcionan para colaboraciones de objetos del dominio en el siguiente nivel hacia abajo. No tiene estado que refleja la situación empresarial, pero puede tener el estado que refleja el progreso de una tarea para el usuario o el programa.

Capa de aplicación de microservicio en .NET normalmente se codifica como un proyecto de ASP.NET Core Web API. El proyecto implementa la interacción de microservicio y acceso a redes remotas, la API Web externo que se usan desde las aplicaciones de interfaz de usuario o cliente. Incluye las consultas si utilizando un CQRS enfocar comandos aceptados por el microservicio e incluso la comunicación orientada a eventos entre microservicios (eventos de integración). La API de Web de ASP.NET Core que representa el nivel de aplicación no puede contener reglas de negocios o conocimiento del dominio (especialmente reglas de dominio para las transacciones o actualizaciones); debería pertenecer la biblioteca de clases del modelo de dominio. La coordenada solo de aplicación capa debe tareas y no debe contener o definir cualquier estado de dominio (modelo de dominio). Delega la ejecución de reglas de negocios para las clases de modelo de dominio por sí mismos (agregadas raíces y entidades de dominio), que finalmente actualizará los datos dentro de las entidades de dominio.

Básicamente, la lógica de aplicación es donde se implementan todos los casos de uso que dependen de un determinado front-end. Por ejemplo, la implementación relacionados con un servicio de API Web.

El objetivo es que la lógica del dominio en el nivel de modelo de dominio, sus invariables, el modelo de datos y reglas de negocios relacionadas debe ser totalmente independiente de las capas de presentación y aplicación. Más de todo, el nivel de modelo de dominio no debe dependen directamente en cualquier marco de infraestructura.

### <a name="the-infrastructure-layer"></a>El nivel de infraestructura

El nivel de infraestructura es cómo se guardan los datos que inicialmente se mantienen en las entidades de dominio (en memoria) en las bases de datos o en otro almacén persistente. Un ejemplo sería usar código de Entity Framework Core para implementar las clases de patrón de repositorio que usan un DBContext para conservar los datos en una base de datos relacional.

Con arreglo a la mencionada anteriormente [omisión de persistencia](http://deviq.com/persistence-ignorance/) y [infraestructura omisión](https://ayende.com/blog/3137/infrastructure-ignorance) principios, el nivel de infraestructura no deben "contaminar" el nivel de modelo de dominio. Debe mantener al independiente de clases de entidad de modelo de dominio de la infraestructura que se utiliza para conservar datos (EF o cualquier otro marco de trabajo) tomando no dependencias en marcos de trabajo. La biblioteca de clases de nivel de modelo de dominio debe tener solo el código de dominio, simplemente [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) entidad las clases que implementan la esencia del software y completamente desacoplada de tecnologías de infraestructura.

Por lo tanto, los proyectos o bibliotecas de clases y las capas deben en última instancia depender de la capa de modelo de dominio (biblioteca), y no al revés, tal como se muestra en la figura 9-7.

![](./media/image8.png)

**Figura 9-7**. Dependencias existentes entre capas DDD

Este diseño de la capa debe ser independiente para cada microservicio. Como se indicó anteriormente, puede implementar la microservicios más complejo microservicios tras patrones DDD, mientras más sencillo de implementación controlada por datos (CRUD simple en una sola capa) de una forma más sencilla.

#### <a name="additional-resources"></a>Recursos adicionales

-   **DevIQ. Principio de omisión de persistencia**
    [*http://deviq.com/persistence-ignorance/*](http://deviq.com/persistence-ignorance/)

-   **Oren Eini. Omisión de infraestructura**
    [*https://ayende.com/blog/3137/infrastructure-ignorance*](https://ayende.com/blog/3137/infrastructure-ignorance)

-   **Ángulo López. Capas de arquitectura de diseño basado en dominio**
    [*https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/*](https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/)


>[!div class="step-by-step"]
[Anterior] (cqrs-microservicio-reads.md) [siguiente] (microservicio-dominio-model.md)
