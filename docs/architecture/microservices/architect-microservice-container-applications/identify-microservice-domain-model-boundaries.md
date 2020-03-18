---
title: Identificación de los límites del modelo de dominio para cada microservicio
description: Explore la esencia de crear particiones de una aplicación grande en microservicios para lograr una arquitectura sólida.
ms.date: 09/20/2018
ms.openlocfilehash: 9c433066dd8e93dbb09b15e58c9c85617775723d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "71834416"
---
# <a name="identify-domain-model-boundaries-for-each-microservice"></a>Identificar los límites del modelo de dominio para cada microservicio

El objetivo al identificar los límites del modelo y el tamaño de cada microservicio no es llegar a la separación más específica posible (aunque debería intentar usar microservicios pequeños siempre que sea posible), sino que debería ser llegar a la separación más significativa basada en el conocimiento del dominio. El énfasis no está en el tamaño, sino más bien en las capacidades empresariales. Además, si se necesita una clara cohesión para un área concreta de la aplicación sobre la base de un gran número de dependencias, eso también indica la necesidad de un solo microservicio. La cohesión es una manera de identificar cómo separar o agrupar microservicios. En última instancia, al tiempo que conoce mejor el dominio, debe adaptar el tamaño de su microservicio de forma iterativa. Buscar el tamaño adecuado no es un proceso monoestable.

[Sam Newman](https://samnewman.io/), un reconocido promotor de microservicios y autor del libro [Crear microservicios](https://samnewman.io/books/building_microservices/), resalta que los microservicios se deben diseñar de acuerdo con el patrón de contexto limitado (BC) (parte del diseño guiado por el dominio), como se ha mencionado anteriormente. A veces, un BC podría estar compuesto de varios servicios físicos, pero no viceversa.

Un modelo de dominio con entidades de dominio específicas se aplica en un BC o un microservicio concreto. Un BC delimita la aplicabilidad de un modelo de dominio y ofrece a los miembros del equipo de desarrolladores una descripción clara y compartida de qué partes deben ser cohesivas y qué partes se pueden desarrollar de manera independiente. Estos son los mismos objetivos para los microservicios.

Otra herramienta que informa sobre su elección de diseño es la [ley de Conway](https://en.wikipedia.org/wiki/Conway%27s_law), que indica que una aplicación reflejará los límites sociales de la organización que la produjo. Pero a veces sucede lo contrario: el software forma la organización de una empresa. Tal vez deba invertir la ley de Conway y establecer los límites de la forma que quiere que la empresa se organice, decantándose por la consultoría de procesos empresariales.

Para identificar los contextos limitados, puede usar un patrón DDD denominado [patrón de asignación de contexto](https://www.infoq.com/articles/ddd-contextmapping). Con la asignación de contexto, puede identificar los distintos contextos de la aplicación y sus límites. Es habitual tener un contexto y un límite diferentes para cada subsistema pequeño, por ejemplo. La asignación de contexto es una manera de definir y establecer explícitamente esos límites entre dominios. Un BC es autónomo, incluye los detalles de un único dominio, como las entidades de dominio, y define los contratos de integración con otros BC. Esto es similar a la definición de un microservicio: es autónomo, implementa cierta capacidad de dominio y debe proporcionar interfaces. Esta es la razón por la que la asignación de contexto y el patrón de contexto limitado son enfoques excelentes para identificar los límites del modelo de dominio de sus microservicios.

Al diseñar una aplicación grande, verá cómo se puede fragmentar su modelo de dominio; por ejemplo, un experto en dominios del dominio de catálogo denominará las entidades de una manera diferente en los dominios de catálogo e inventario que un experto en dominios de envío. O puede que la entidad de dominio de usuario sea diferente en tamaño y número de atributos cuando se trata de un experto de CRM que quiere almacenar todos los detalles sobre el cliente, en comparación con un experto en dominios de pedido que solo necesita datos parciales sobre el cliente. Es muy difícil eliminar la ambigüedad de todos los términos del dominio en todos los dominios relacionados con una aplicación grande. Pero lo más importante es que no debe intentar unificar los términos. En su lugar, acepte las diferencias y la riqueza que cada dominio proporciona. Si intenta tener una base de datos unificada para toda la aplicación, los intentos de establecer un vocabulario unificado serán difíciles y los resultados no sonarán bien a ninguno de los múltiples expertos en dominios. Por tanto, con los BC (implementados como microservicios) será más fácil aclarar dónde puede usar determinados términos del dominio y dónde debe dividir el sistema y crear BC adicionales con dominios diferentes.

Sabrá que obtuvo los límites y los tamaños correctos de cada BC y modelo de dominio si tiene pocas relaciones sólidas entre los modelos de dominio y normalmente no necesita combinar información de varios modelos de dominio al realizar operaciones de aplicaciones típicas.

Quizá la mejor respuesta a la pregunta de qué tamaño debe tener un modelo de dominio para cada microservicio es la siguiente: debe tener un BC autónomo, tan aislado como sea posible, que le permita trabajar sin tener que cambiar constantemente a otros contextos (otros modelos de microservicio). En la figura 4-10 puede ver cómo varios microservicios (varios BC) tienen su propio modelo y cómo se pueden definir sus entidades, según los requisitos específicos para cada uno de los dominios identificados en la aplicación.

![Diagrama que muestra entidades en varios límites del modelo.](./media/identify-microservice-domain-model-boundaries/identify-entities-microservice-model-boundries.png)

**Figura 4-10**. Identificación de las entidades y de los límites del modelo de microservicio

En la figura 4-10 se ilustra un escenario de ejemplo relacionado con un sistema de administración de conferencias en línea. La misma entidad aparece como "Users", "Buyers", "Payers" y "Customers" en función del contexto delimitado. Ha identificado varios BC que se podrían implementar como microservicios, de acuerdo con los dominios que los expertos en dominios definieron para su caso. Como puede ver, hay entidades que están presentes solo en un modelo de microservicio único, como los pagos en el microservicio de pago. Serán fáciles de implementar.

Sin embargo, también puede tener entidades que tienen una forma diferente, pero comparten la misma identidad a través de los múltiples modelos de dominio de los diversos microservicios. Por ejemplo, la entidad User se identifica en el microservicio de administración de conferencias. Ese mismo usuario, con la misma identidad, es el que se llama compradores en el microservicio de pedidos, o el que se llama pagador en el microservicio de pago e incluso el que se llama cliente en el microservicio de servicio al cliente. Esto es porque, según el [lenguaje ubicuo](https://martinfowler.com/bliki/UbiquitousLanguage.html) que cada experto en dominios use, un usuario podría tener una perspectiva distinta incluso con atributos diferentes. La entidad de usuario en el modelo de microservicio denominado Administración de conferencias podría tener la mayoría de sus atributos de datos personales. Sin embargo, puede ser que ese mismo usuario en la forma de pagador en el microservicio de pago o en la forma de cliente en el microservicio de servicio al cliente no necesite la misma lista de atributos.

Un enfoque similar se muestra en la figura 4-11.

![Diagrama que muestra cómo descomponer un modelo de datos en varios modelos de dominio.](./media/identify-microservice-domain-model-boundaries/decompose-traditional-data-models.png)

**Figura 4-11**. Descomponer los modelos de datos tradicionales en varios modelos de dominio

Al descomponer un modelo de datos tradicionales entre contextos limitados, puede tener distintas entidades que comparten la misma identidad (un comprador también es un usuario) con otros atributos en cada contexto delimitado. Puede ver cómo el usuario está presente en el modelo de microservicio de administración de conferencias como la entidad User y también está presente en la forma de la entidad Buyer en el microservicio de precios, con atributos o detalles alternativos sobre el usuario cuando es realmente un comprador. Puede ser que no todos los microservicios o BC necesiten todos los datos relacionados con una entidad User, solo parte de ellos, según el problema que se deba resolver o el contexto. Por ejemplo, en el modelo del microservicio de precios, no necesita la dirección ni el identificador del usuario, solo el identificador (como identidad) y el estado, que influirán en los descuentos al poner precio al número de puestos por comprador.

La entidad Seat tiene el mismo nombre, pero distintos atributos en cada modelo de dominio, pero Seat comparte la identidad según el mismo identificador, como sucede con User y Buyer.

Básicamente, hay un concepto compartido de un usuario que existe en varios servicios (dominios), que comparten la identidad de ese usuario. Pero, en cada modelo de dominio, podría haber detalles adicionales o diferentes sobre la entidad de usuario. Por tanto, debe haber una manera de asignar una entidad de usuario de un dominio (microservicio) a otro.

No compartir la misma entidad de usuario con el mismo número de atributos entre dominios tiene varias ventajas. Una ventaja es reducir la duplicación, por lo que los modelos de microservicio no tienen ningún dato que no necesiten. Otra ventaja es tener un microservicio maestro que posee un determinado tipo de datos por entidad para que solo ese microservicio dirija las actualizaciones y las consultas para ese tipo de datos.

>[!div class="step-by-step"]
>[Anterior](distributed-data-management.md)
>[Siguiente](direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
