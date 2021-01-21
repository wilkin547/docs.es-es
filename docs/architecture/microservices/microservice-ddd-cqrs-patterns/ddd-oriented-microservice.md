---
title: Diseño de un microservicio orientado a un DDD
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre el diseño del microservicio Ordering orientado a DDD y sus niveles de aplicación.
ms.date: 01/13/2021
ms.openlocfilehash: 1d17f0842bb371ce65e96f33d25b2d6e94493396
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188340"
---
# <a name="design-a-ddd-oriented-microservice"></a>Diseño de un microservicio orientado a DDD

El diseño guiado por el dominio (DDD) propone un modelado basado en la realidad de negocio con relación a sus casos de uso. En el contexto de la creación de aplicaciones, DDD hace referencia a los problemas como dominios. Describe áreas con problemas independientes como contextos delimitados (cada contexto delimitado está correlacionado con un microservicio) y resalta un lenguaje común para hablar de dichos problemas. También sugiere muchos patrones y conceptos técnicos, como entidades de dominio con reglas de modelos enriquecidos (no [modelos de dominio anémico](https://martinfowler.com/bliki/AnemicDomainModel.html)), objetos de valor, agregados y raíz agregada (o entidad raíz) para admitir la implementación interna. En esta sección se explica el diseño y la implementación de estos patrones internos.

A veces, estos patrones y reglas técnicas de DDD se perciben como obstáculos con una curva de aprendizaje pronunciada a la hora de implementar opciones de DDD. Pero lo importante no son los patrones en sí, sino organizar el código para que esté en línea con los problemas del negocio y utilizar los mismos términos empresariales (lenguaje ubicuo). Además, las opciones de DDD solo deben aplicarse en el caso de implementar microservicios complejos con reglas de negocio importantes. Las responsabilidades más sencillas, como el servicio CRUD, se pueden administrar con enfoques más sencillos.

La clave está en dónde situar los límites al diseñar y definir un microservicio. Los patrones de DDD le ayudan a comprender la complejidad del dominio. En el modelo de dominio de cada contexto delimitado, debe identificar y definir las entidades, los objetos de valor y los agregados que modelan el dominio. Debe crear y perfeccionar un modelo de dominio que se encuentre dentro de un límite definido por su contexto. Y esto se hace patente en la forma de un microservicio. Los componentes situados dentro de esos límites acaban siendo sus microservicios, aunque, en algunos casos, los contextos delimitados o los microservicios pueden estar compuestos de varios servicios físicos. El DDD afecta a los límites y, por lo tanto, a los microservicios.

## <a name="keep-the-microservice-context-boundaries-relatively-small"></a>Mantener los límites de contexto del microservicio relativamente estrechos

Determinar dónde colocar los límites entre contextos delimitados equilibra dos objetivos contrapuestos. En primer lugar, le interesa crear los microservicios más pequeños posibles, aunque su principal objetivo no debe ser este, sino el de crear un límite alrededor de elementos que deban estar cohesionados. En segundo lugar, le interesa evitar comunicaciones locuaces entre microservicios. Estos objetivos pueden ser contrapuestos. Para encontrar el equilibrio entre ellos, debe descomponer el sistema en tantos microservicios pequeños como pueda hasta que los límites de la comunicación crezcan rápidamente con cada intento adicional de separar un nuevo contexto delimitado. La cohesión es clave en un único contexto delimitado.

Se parece a una [inadecuada intuición de código de cercanía](https://sourcemaking.com/refactoring/smells/inappropriate-intimacy) al implementar las clases. Si dos microservicios necesitan colaborar mucho entre sí, probablemente sean el mismo microservicio.

Otra manera de enfocarlo es observando la autonomía. Si un microservicio debe depender de otro servicio para satisfacer directamente una solicitud, no es realmente autónomo.

## <a name="layers-in-ddd-microservices"></a>Niveles en microservicios de DDD

La mayoría de aplicaciones de empresa con una significativa complejidad empresarial y técnica se definen a partir de múltiples niveles. Los niveles son un elemento lógico y no están relacionados con la implementación del servicio, sino que sirven para ayudar a los desarrolladores a administrar la complejidad del código. Los diferentes niveles (por ejemplo, el nivel de modelo de dominio frente al nivel de presentación, etc.) pueden ser de diferentes tipos, lo que exige su traducción.

Por ejemplo, una entidad se puede cargar desde la base de datos. Puede ser que se envíe parte de esa información, o un agregado de información que incluya datos adicionales de otras entidades, a la interfaz de usuario del cliente a través de una API web de REST. La cuestión es que la entidad de dominio se debe situar dentro del nivel de modelo de dominio y no puede propagarse a otras áreas a las que no pertenece, como al nivel de presentación.

Además, debe tener entidades siempre válidas (consulte la sección [Diseño de validaciones en el nivel de modelo de dominio](domain-model-layer-validations.md)) y controladas por raíces agregadas (entidades raíz). Por lo tanto, las entidades no pueden estar enlazadas a vistas de cliente, porque puede ser que algunos datos no estén validados en el nivel de la interfaz de usuario. Y ese es el propósito de ViewModel. El modelo ViewModel es un modelo de datos exclusivo para las necesidades del nivel de presentación. Las entidades de dominio no pertenecen directamente al modelo ViewModel. En cambio, debe traducir entre ViewModels y entidades de dominio, y viceversa.

Al hablar de complejidad, es importante tener un modelo de dominio controlado por raíces agregadas que garanticen que todas las invariantes y reglas relacionadas con ese grupo de entidades (agregadas) se realicen a través de un punto de entrada o puerta únicos: la raíz agregada.

En la Figura 7-5 se muestra cómo se implementa un diseño por niveles en la aplicación eShopOnContainers.

![Diagrama que muestra las capas de un microservicio de diseño controlado por dominios.](./media/ddd-oriented-microservice/domain-driven-design-microservice.png)

**Figura 7-5**. Niveles de DDD en el microservicio de ordenación en eShopOnContainers

Las tres capas en un microservicio DDD como Ordering. Cada capa es un proyecto de VS: la capa de aplicación es Ordering.API, el nivel de dominio es Ordering.Domain y el nivel de infraestructura es Ordering.Infrastructure. Le recomendamos que diseñe el sistema de modo que cada nivel se comunique solamente con otros niveles determinados. Este enfoque puede ser más fácil de aplicar si los niveles se implementan como bibliotecas de clase distintas, porque puede identificar claramente qué dependencias se establecen entre bibliotecas. Por ejemplo, el nivel de modelo de dominio no debe depender de ningún otro nivel (las clases del modelo de dominio deben ser clases de objetos CLR estándar o [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object)). Como se muestra en la figura 7-6, la biblioteca de nivel **Ordering.Domain** solo tiene dependencias en las bibliotecas de .NET o en los paquetes NuGet, pero no en otras bibliotecas personalizadas, como la biblioteca de datos o de persistencia.

![Captura de pantalla de las dependencias de Ordering.Domain.](./media/ddd-oriented-microservice/ordering-domain-dependencies.png)

**Figura 7-6**. Los niveles implementados como bibliotecas permiten controlar mejor las dependencias entre niveles

### <a name="the-domain-model-layer"></a>El nivel de modelo de dominio

En el fantástico libro de Eric Evans, [Domain Driven Design](https://domainlanguage.com/ddd/) (Diseño guiado por el dominio), se explica lo siguiente sobre el nivel de modelo de dominio y el nivel de aplicación.

**Nivel de modelo de dominio**: responsable de representar conceptos del negocio, información sobre la situación del negocio y reglas de negocios. El estado que refleja la situación empresarial está controlado y se usa aquí, aunque los detalles técnicos de su almacenaje se delegan a la infraestructura. Este nivel es el núcleo del software empresarial.

En el nivel de modelo de dominio es donde se expresa el negocio. Al implementar un nivel de modelo de dominio de microservicio en. NET, este nivel se codifica como una biblioteca de clases con las entidades de dominio que capturan datos y comportamiento (métodos con lógica).

Siguiendo los principios de [omisión de persistencia](https://deviq.com/persistence-ignorance/) y [omisión de infraestructura](https://ayende.com/blog/3137/infrastructure-ignorance), este nivel debe omitir completamente los detalles de persistencia de datos. Las tareas de persistencia deben estar realizadas por el nivel de infraestructura. Por lo tanto, este nivel no debe tener dependencias directas en la infraestructura, lo que significa que una regla de importante es que las clases de entidad del modelo de dominio deben ser [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object).

Las entidades de dominio no deben depender directamente (como derivarse de una clase base) de ningún marco de infraestructura de acceso a los datos, como Entity Framework o NHibernate. Lo ideal es que las entidades de dominio no se deriven de ningún tipo definido en ningún marco de infraestructura ni lo implementen.

Los marcos ORM más modernos, como Entity Framework Core, permiten este enfoque, de forma que las clases de modelo de dominio no se acoplan a la infraestructura. Pero no siempre se puede disponer de entidades POCO al usar marcos y bases de datos NoSQL determinados, como actores y colecciones de confianza en Azure Service Fabric.

Incluso cuando es importante seguir el principio de omisión de persistencia en el modelo de dominio, no debe ignorar los problemas de persistencia. Sigue siendo importante comprender el modelo de datos físicos y cómo se asigna a un modelo de objetos entidad. En caso contrario, puede crear diseños imposibles.

Además, esto no significa que pueda tomar un modelo diseñado para una base de datos relacional y moverla directamente a un NoSQL o a una base de datos orientada a un documento. En algunos modelos de entidad, es posible que el modelo encaje, pero normalmente no lo hace. Sigue habiendo restricciones que el modelo de entidad debe cumplir, basándose en la tecnología de almacenamiento y en la tecnología ORM.

### <a name="the-application-layer"></a>El nivel de aplicación

Si pasamos al nivel de aplicación, podemos citar de nuevo el libro de Eric Evans [Domain Driven Design](https://domainlanguage.com/ddd/) (Diseño guiado por el dominio):

**Nivel de aplicación**: define los trabajos que se supone que el software debe hacer y dirige los objetos de dominio expresivo para que resuelvan problemas. Las tareas que son responsabilidad de este nivel son significativas para la empresa o necesarias para la interacción con los niveles de aplicación de otros sistemas. Este nivel debe mantenerse estrecho. No contiene reglas de negocios ni conocimientos, sino que solo coordina tareas y delega trabajo a colaboraciones de objetos de dominio en el siguiente nivel. No tiene ningún estado que refleje la situación empresarial, pero puede tener un estado que refleje el progreso de una tarea para el usuario o el programa.

Normalmente, el nivel de aplicación de microservicios en .NET se codifica como un proyecto de ASP.NET Core Web API. El proyecto implementa la interacción del microservicio, el acceso a redes remotas y las API web externas utilizadas desde aplicaciones cliente o de interfaz de usuario. Incluye consultas si se utiliza un enfoque de CQRS, comandos aceptados por el microservicio e incluso comunicación guiada por eventos entre microservicios (eventos de integración). La ASP.NET Core Web API que representa el nivel de aplicación no puede contener reglas de negocios ni conocimientos del dominio (especialmente reglas de dominio para transacciones o actualizaciones); estos deben pertenecer a la biblioteca de clases del modelo de dominio. El nivel de aplicación solo debe coordinar tareas y no puede contener ni definir ningún estado de dominio (modelo de dominio). Delega la ejecución de reglas de negocios a las mismas clases de modelo de dominio (raíces agregadas y entidades de dominio) que, en última instancia, actualizarán los datos en esas entidades de dominio.

Básicamente, la lógica de la aplicación es el lugar en el que se implementan todos los casos de uso que dependen de un front-end determinado. Por ejemplo, la implementación relacionada con un servicio de API web.

El objetivo es que la lógica del dominio en el nivel de modelo de dominio, sus invariables, el modelo de datos y las reglas de negocios relacionadas sean totalmente independientes de los niveles de presentación y aplicación. Sobre todo, el nivel de modelo de dominio no puede depender directamente de ningún marco de infraestructura.

### <a name="the-infrastructure-layer"></a>El nivel de infraestructura

El nivel de infraestructura es la forma en que los datos que inicialmente se conservan en las entidades de dominio (en la memoria) se guardan en bases de datos o en otro almacén permanente. Un ejemplo sería usar código de Entity Framework Core para implementar las clases del patrón de repositorio que usan DBContext para conservar los datos en una base de datos relacional.

De conformidad con los principios [Omisión de persistencia](https://deviq.com/persistence-ignorance/) y [Omisión de infraestructura](https://ayende.com/blog/3137/infrastructure-ignorance) mencionados anteriormente, el nivel de infraestructura no puede "contaminar" el nivel de modelo de dominio. No puede depender demasiado de los marcos para mantener las clases de entidad de modelo de dominio apartadas de la infraestructura que utiliza para conservar datos (EF o cualquier otro marco). La biblioteca de clases de nivel de modelo de dominio solo debe tener el código de dominio, solo clases de entidad [POCO](https://en.wikipedia.org/wiki/Plain_Old_CLR_Object) que implementen la esencia del software y debe estar completamente desacoplada de tecnologías de infraestructura.

Así, los proyectos y bibliotecas de clases o niveles dependerán, en última instancia, del nivel de modelo de dominio (biblioteca) y no al revés, como se muestra en la Figura 7-7.

![Diagrama que muestra las dependencias que existen entre las capas de servicio de DDD.](./media/ddd-oriented-microservice/ddd-service-layer-dependencies.png)

**Figura 7-7**. Dependencias existentes entre niveles en DDD

Dependencias en un servicio de DDD, la capa de aplicación depende del dominio y la infraestructura, y la infraestructura depende del dominio, pero el dominio no depende de ninguna capa. Este diseño de nivel debe ser independiente para cada microservicio. Como se indicó anteriormente, puede implementar microservicios más complejos siguiendo patrones DDD, al mismo tiempo que puede implementar microservicios guiados por datos más simples (un único CRUD en un solo nivel) de una forma más sencilla.

#### <a name="additional-resources"></a>Recursos adicionales

- **DevIQ. Principio de omisión de persistencia** \
  <https://deviq.com/persistence-ignorance/>

- **Oren Eini. Omisión de infraestructura** \
  <https://ayende.com/blog/3137/infrastructure-ignorance>

- **Angel Lopez. Arquitectura por capas en un diseño controlado por dominios** \
  <https://ajlopez.wordpress.com/2008/09/12/layered-architecture-in-domain-driven-design/>

>[!div class="step-by-step"]
>[Anterior](cqrs-microservice-reads.md)
>[Siguiente](microservice-domain-model.md)
