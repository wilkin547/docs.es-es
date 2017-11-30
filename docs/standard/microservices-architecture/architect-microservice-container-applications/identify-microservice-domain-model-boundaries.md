---
title: "Identificación de los límites del modelo de dominio para cada microservicio"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Identificación de los límites del modelo de dominio para cada microservicio"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6fef11e5718706701abb29149c4c4a23ba39bde0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="identify-domain-model-boundaries-for-each-microservice"></a>Identificar los límites del modelo de dominio para cada microservicio

El objetivo al identificar a los límites del modelo y el tamaño de cada microservicio es no llegar a la separación más específico posible, aunque debe tienden hacia microservicios pequeño si es posible. En su lugar, el objetivo debe ser llegar a la separación más significativa basada en el conocimiento del dominio. El énfasis no está en el tamaño, sino más bien en las capacidades de negocio. Además, si hay desactive cohesión necesarios para un área concreta de la aplicación en función de un gran número de dependencias, indique la necesidad de una sola microservicio, demasiado. Cohesión es una manera de identificar cómo separar o microservicios juntos de grupo. En última instancia, mientras que obtener más información sobre el dominio, debe adaptar el tamaño de su microservicio forma iterativa. Buscar el tamaño adecuado no es un proceso Monoestable.

[SAM Newman](http://samnewman.io/), activa un promotor reconocido de microservicios y el autor de la libreta de [Microservicios Building](http://samnewman.io/books/building_microservices/), resalta los que debe diseñar su microservicios basado en el patrón de contexto limitado (BC) (parte de controlada por el dominio diseño), como se mencionó anteriormente. A veces, una BC podría estar compuesta de varios servicios físicos, pero no viceversa.

Se aplica un modelo de dominio con entidades de dominio específico en una BC concreta o microservicio. Una BC delimita la aplicabilidad de un modelo de dominio y miembros del equipo de desarrolladores proporciona una descripción clara y compartida de cuál debe ser coherente y lo que puede desarrollar de manera independiente. Estos son los mismos objetivos para microservicios.

Otra herramienta que le informa de su elección de diseño es [la ley de Conway](https://en.wikipedia.org/wiki/Conway%27s_law), que indica que una aplicación reflejará los límites de la organización que lo generó sociales. Pero a veces sucede lo contrario, la organización de una empresa está formada por el software. Tendrá que invertir la ley de Conway y generar los límites de la forma que desee de la empresa para organizarse, descubriendo consultoría para procesos empresariales.

Con el fin de identificar los contextos enlazados, un patrón DDD que puede usarse para esto es el [patrón de asignación de contexto](https://www.infoq.com/articles/ddd-contextmapping). Con la asignación de contexto, identifique los distintos contextos de la aplicación y sus límites. Es habitual tener un contexto diferente y el límite para cada subsistema pequeño, por ejemplo. La asignación de contexto es una manera de definir y establecer explícita esos límites entre dominios. Una continuidad del negocio es autónomo e incluye los detalles de un único dominio, los detalles como las entidades de dominio y define los contratos de integración con otros BCs. Esto es similar a la definición de un microservicio: es autónomo, que implementa la funcionalidad de dominio concreta y deben proporcionar interfaces. Esta es la razón por la asignación de contexto y el patrón de contexto limitado excelentes enfoques para identificar los límites de modelo de dominio de su microservicios.

Al diseñar una aplicación grande, verá cómo se puede fragmentar su modelo de dominio, un experto de dominio del dominio de catálogo denominará entidades diferente en los dominios de catálogo y de inventario a un dominio de envío experto, por ejemplo. O bien, puede variar en tamaño y número de atributos de la entidad de dominio de usuario cuando se trabaja con un experto de CRM que desea almacenar todos los detalles sobre el cliente que para un ordenación experto de dominio que solo necesita parte de los datos sobre el cliente. Es muy difícil eliminar la ambigüedad de todos los términos del dominio en todos los dominios relacionados con una aplicación grande. Pero lo más importante es que no debe intentar unificar los términos; en su lugar, aceptan las diferencias y riqueza proporcionada por cada dominio. Si intentas tener una base de datos unificada para toda la aplicación, intentos en un vocabulario unificado serán difícil y no suenan hacia la derecha para cualquiera de los varios expertos de dominio. Por lo tanto, BCs (implementados como microservicios) le ayudará a aclarar donde se pueden utilizar ciertos valores del dominio y dónde debe dividir el sistema y crear BCs adicionales con dominios diferentes.

Sabrá que obtuvo los límites de la derecha y tamaños de cada BC y modelo de dominio si tiene algunas relaciones sólidas entre los modelos de dominio, y lo hace normalmente no tenga que combinar información de varios modelos de dominio al realizar la aplicación típica operaciones.

Quizás la mejor respuesta a la pregunta de qué tamaño debe ser un modelo de dominio para cada microservicio es el siguiente: debe tener una BC autónomo, como aislado como sea posible, que le permite trabajar sin necesidad de cambiar constantemente a otros contextos (otros modelos de microservicio). En la figura 4-10 puede ver cómo varios microservicios (varios BCs) cada tienen su propio modelo y cómo se pueden definir sus entidades, dependiendo de los requisitos específicos para cada uno de los dominios identificados en la aplicación.

![](./media/image10.png)

**Figura 4-10**. Identificar las entidades y los límites de modelo de microservicio

Figura 4-10 se ilustra un escenario de ejemplo relacionados con un sistema de administración de conferencias en línea. Ha identificado BCs varios que se pueda implementar como microservicios, basadas en los dominios que expertos de dominio definidos. Como puede ver, hay entidades que están presentes solo en un modelo de microservicio único, como los pagos en el microservicio de pago. Serán fáciles de implementar.

Sin embargo, también puede tener entidades que tienen una forma diferente pero comparten la misma identidad a través de varios modelos de dominio de la microservicios varios. Por ejemplo, la entidad de usuario se identifica en la administración de conferencias de microservicio. Ese mismo usuario, con la misma identidad, es el uno con el nombre de los compradores en el orden de microservicio, o el nombre pagador en la microservicio de pago e incluso el un cliente con nombre en el servicio al cliente microservicio. Esto es porque, dependiendo de la [lenguaje ubicuo](https://martinfowler.com/bliki/UbiquitousLanguage.html) que está usando cada experto de dominio, un usuario podría tener una perspectiva distinta incluso con atributos diferentes. La entidad de usuario en el modelo de microservicio denominado Administración de conferencias podría tener la mayoría de sus atributos de datos personales. Sin embargo, ese mismo usuario en la forma de pagador en el pago de microservicio o en la forma de cliente en el servicio al cliente de microservicio que no tenga la misma lista de atributos.

Un enfoque similar se muestra en la figura 4-11.

![](./media/image11.png)

**Figura 4-11**. Descomponer los modelos de datos tradicional en varios modelos de dominio

Puede ver cómo el usuario está presente en el modelo de microservicio de administración de conferencias como la entidad de usuario y también está presente en el formulario de la entidad de comprador en microservicio de precios, con atributos alternativos o detalles sobre el usuario cuando es realmente un comprador. Cada microservicio o BC que no tenga todos los datos relacionados con una entidad de usuario, solo parte del mismo, según el problema al resolver o en el contexto. Por ejemplo, en el modelo de precios microservicio, no necesita la dirección o el identificador del usuario, solo el identificador (como identidad) y el estado, que tendrá un impacto en descuentos cuando precios al número de puestos por comprador.

La entidad de seguridad tiene el mismo nombre pero con distintos atributos de cada modelo de dominio. Sin embargo, puesto comparte identidad según el mismo identificador, como sucede con el usuario y el comprador.

Básicamente, hay un concepto compartido de un usuario que existe en varios servicios (dominios), que comparten la identidad del usuario. Pero, en cada modelo de dominio podría ser adicionales o diferentes detalles acerca de la entidad de usuario. Por lo tanto, debe ser un método para asignar una entidad de usuario de un dominio (microservicio) a otro.

Hay varias ventajas a no compartir la misma entidad de usuario con el mismo número de atributos entre dominios. Una ventaja es reducir la duplicación, por lo que los modelos de microservicio no tienen ningún dato que no necesitan. Otra ventaja es tener un microservicio maestro que pertenece un determinado tipo de datos por la entidad para que las actualizaciones y las consultas para ese tipo de datos controlan sólo esa microservicio.


>[!div class="step-by-step"]
[Anterior] (distributed-datos-management.md) [siguiente] (direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
