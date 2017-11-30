---
title: "Diseñar un modelo de dominio de microservicio"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Diseñar un modelo de dominio de microservicio"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 455a2c5a39fb9b765b557610ab108f8c75882dbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="designing-a-microservice-domain-model"></a>Diseñar un modelo de dominio de microservicio

*Definir un modelo de dominio enriquecido para cada microservicio de negocios o contexto limitado*

El objetivo es crear un modelo de dominio coherente único para cada microservicio de negocios o contexto limitado (BC). Tenga en cuenta, sin embargo, que una continuidad del negocio o business microservicio a veces podría estar compuesto por varios servicios físicos que comparten un modelo de dominio único. El modelo de dominio debe capturar las reglas, comportamiento, lenguaje de negocios y las restricciones del único contexto limitado o microservicio de negocios que representa.

## <a name="the-domain-entity-pattern"></a>El modelo de entidad del dominio

Las entidades representan objetos del dominio y se definen principalmente por su identidad, la continuidad y la persistencia con el tiempo y no solo por los atributos que se componen de ellos. Tal y como se indica Eric Evans, "un objeto definido principalmente por su identidad se denomina una entidad." Las entidades son muy importantes en el modelo de dominio, ya que son la base para un modelo. Por lo tanto, debe identificar y diseñarlos cuidadosamente.

*Identidad de una entidad puede cruzar varios microservicios o contextos limitado.*

La misma identidad (aunque no es la misma entidad) se pueden modelar en varios contextos limitado o microservicios. Sin embargo, que no implica que la misma entidad, con los mismos atributos y lógica se implementa en varios contextos limitado. En su lugar, las entidades en cada contexto limitado limitan sus atributos y comportamientos a los requeridos en el dominio de ese contexto limitado.

Por ejemplo, la entidad de comprador podría tener la mayoría de los atributos de una persona que están definidos en la entidad de usuario en el perfil o la identidad microservicio, incluida la identidad. Pero la entidad de comprador en la ordenación microservicio podría tener menos de los atributos, porque solo determinados datos comprador está relacionado con el proceso de pedido. El contexto de cada microservicio o contexto limitado afecta a su modelo de dominio.

*Las entidades de dominio deben implementar el comportamiento además de implementar los atributos de datos*

Una entidad de dominio en DDD debe implementar la lógica del dominio o el comportamiento relacionado con los datos de entidad (es decir, el objeto al que obtuvo acceso memoria). Por ejemplo, como parte de una clase de entidad order deben tener lógica de negocios y las operaciones que se implementan como métodos para realizar tareas como agregar un elemento de pedido, la validación de datos y el cálculo total. Métodos de la entidad ocupan de las reglas de la entidad en lugar de tener esas reglas se propagan a través de la capa de aplicación e invariables.

Figura 9-8 muestra una entidad del dominio que implementa no solo los atributos de datos, pero las operaciones o métodos con lógica de dominio relacionadas.

![](./media/image9.png)

**Figura 9-8**. Ejemplo de un diseño de la entidad de dominio implementar datos más comportamiento

Por supuesto, a veces puede tener entidades que implementar ninguna lógica como parte de la clase de entidad. Esto puede ocurrir en las entidades secundarias dentro de un agregado si la entidad secundaria no tiene ninguna lógica especial porque la mayor parte de la lógica se define en la raíz agregada. Si tiene un microservicio complejo que tiene mucha lógica implementada en las clases de servicio en lugar de en las entidades de dominio, podría encontrarse en el modelo de dominio anemic, que se explica en la sección siguiente.

### <a name="rich-domain-model-versus-anemic-domain-model"></a>Modelo de dominio enriquecido frente al modelo de dominio anemic

En su entrada [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Martin Fowler describe un modelo de dominio anemic de esta manera:

El síntoma de un modelo de dominio Anemic básico es que a primera vista parece lo real. Hay objetos, muchos denominado después de los nombres en el espacio de dominio y estos objetos están conectados con las relaciones enriquecidas y la estructura que tienen los modelos de dominio es true. La instrucción catch lleguen al mirar el comportamiento y tenga en cuenta que hay casi cualquier comportamiento que en estos objetos, hacerlos poco más de bolsas de captadores y establecedores.

Por supuesto, cuando se usa un modelo de dominio anemic, se utilizará los modelos de datos de un conjunto de objetos de servicio (con nombre tradicionalmente la *capa empresarial*) que captura toda la lógica de negocios o de dominio. La capa de negocio se encuentra en la parte superior del modelo de datos y utiliza el modelo de datos al igual que los datos.

El modelo de dominio anemic es simplemente un diseño de estilo de procedimientos. Objetos entidad anemic no son objetos reales, ya que carecen de comportamiento (métodos). Solo contienen propiedades de datos y, por tanto, no es diseño orientado a objetos. Al colocar todo el comportamiento de alejar en objetos de servicio (la capa de negocio) básicamente terminará con [código spaghetti](https://en.wikipedia.org/wiki/Spaghetti_code) o [secuencias de comandos de transacción](https://martinfowler.com/eaaCatalog/transactionScript.html), y, por tanto, se pierde las ventajas que un modelo de dominio proporciona.

Sin tener en cuenta, si su microservicio o contexto limitado es muy sencilla (un servicio CRUD), el modelo de dominio anemic en forma de objetos entidad con propiedades de datos simplemente podría bastar y puede que no sea la pena implementar modelos más complejos de DDD. En ese caso, será simplemente un modelo de persistencia, como ha creado deliberadamente una entidad con datos de solo para fines CRUD.

Para eso están microservicios arquitecturas son perfectas para varias arquitecturas según cada contexto limitado. Por ejemplo, en eShopOnContainers, la ordenación microservicio implementa patrones DDD, pero la microservicio de catálogo, que es un servicio CRUD simple, no lo hace.

Algunas personas, supongamos que el modelo de dominio anemic es un antipatrón. Realmente depende de lo que va a implementar. Si el microservicio que se va a crear es bastante sencillo (por ejemplo, un servicio CRUD), según el modelo de dominio anemic no es un antipatrón. Sin embargo, si necesita para abordar la complejidad del dominio de microservicio que tiene muchos cambiantes de reglas de negocios, el modelo de dominio anemic sería un antipatrón para ese microservicio o contexto limitado. En ese caso, se diseña como datos completos de un modelo con entidades que contiene los datos más comportamiento así como implementar otros patrones que DDD (agregados, objetos de valor, etc.) puede tener enormes ventajas para el éxito a largo plazo de este tipo un microservicio.

#### <a name="additional-resources"></a>Recursos adicionales

-   **DevIQ. Entidad del dominio**
    [*http://deviq.com/entity/*](http://deviq.com/entity/)

-   **Martin Fowler. El modelo de dominio**
    [*https://martinfowler.com/eaaCatalog/domainModel.html*](https://martinfowler.com/eaaCatalog/domainModel.html)

-   **Martin Fowler. El modelo de dominio Anemic**

    <https://martinfowler.com/bliki/AnemicDomainModel.HTML>

### <a name="the-value-object-pattern"></a>El patrón de objeto de valor

Tal y como se ha detectado Eric Evans, "muchos objetos no tienen identidad conceptual. Estos objetos describen ciertas características de una cosa."

Una entidad requiere una identidad, pero hay muchos objetos en un sistema que no lo hace, al igual que el modelo de objeto de valor. Un objeto de valor es un objeto con ninguna identidad conceptual que describe un aspecto de dominio. Se trata de objetos que crea una instancia para representar elementos de diseño que solo le interesan temporalmente. Le preocupa la *qué* , no son *que* son. Ejemplos incluyen números y cadenas, pero también pueden ser un nivel más alto conceptos como grupos de atributos.

Algo que es una entidad en un microservicio podría no ser una entidad en otra microservicio, porque en el segundo caso, el contexto limitado podría tener un significado diferente. Por ejemplo, una dirección en una aplicación de comercio electrónico podría no tener una identidad en absoluto, ya que solo puede representar un grupo de atributos de perfil del cliente para una persona o empresa. En este caso, la dirección debe clasificarse como un objeto de valor. Sin embargo, en una aplicación para una empresa de la utilidad de energía eléctrica, la dirección del cliente podría ser importante para el dominio de negocio. Por lo tanto, la dirección debe tener una identidad para que el sistema de facturación puede estar relacionado directamente con la dirección. En ese caso, una dirección debe clasificarse como una entidad de dominio.

Una persona con un nombre y apellido normalmente es una entidad debido a una persona que tiene identidad, incluso si el nombre y apellido coincidan con otro conjunto de valores, por ejemplo, si esos nombres también hace referencia a una persona diferente.

Objetos de valor son difíciles de administrar en bases de datos relacionales y ORM como EF, mientras que en el documento orientado a las bases de datos sean más fáciles de implementar y utilizar.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Martin Fowler. Patrón de objeto de valor**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Valor de objeto**
    [*http://deviq.com/value-object/*](http://deviq.com/value-object/)

-   **Valor de objetos en el desarrollo controlado por pruebas**
    [*https://leanpub.com/tdd-ebook/read\#leanpub-auto-objetos de valor*](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

-   **Eric Evans. Diseño basado en dominio: Realiza para complejidad en el centro de Software.** (Libro; incluye una explicación de los objetos de valor) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

### <a name="the-aggregate-pattern"></a>El patrón de agregado

Un modelo de dominio contiene grupos de entidades de datos diferentes y procesos que pueden controlar un área importante de funcionalidad, como el cumplimiento de pedido o inventario. Una unidad DDD más específica es la agregación, que describe un clúster o un grupo de entidades y comportamientos que se pueden tratar como una unidad coherente.

Normalmente definen un agregado basado en las transacciones que necesite. Un ejemplo clásico es un pedido que también contiene una lista de elementos de pedido. Normalmente, un elemento de pedido será una entidad. Pero será una entidad secundaria dentro de la agregación de orden, que también contendrá la entidad pedido como su entidad raíz, denominada normalmente una raíz agregada.

Puede ser difícil identificar agregados. Un agregado es un grupo de objetos que deben ser coherentes entre sí, pero simplemente no se puede seleccionar un grupo de objetos y etiquetarlas un agregado. Debe empezar por un concepto de dominio y pensar en las entidades que se usan en las transacciones más comunes relacionados con dicho concepto. Las entidades que deben ser transaccionalmente coherente son lo que constituye un agregado. Pensar acerca de las operaciones de transacción es probablemente la mejor manera de identificar agregados.

### <a name="the-aggregate-root-or-root-entity-pattern"></a>El modelo raíz agregada o entidad raíz

Un agregado se compone de al menos una entidad: la raíz de agregado, también se denomina entidad raíz o ientity principal. Además, puede tener varios objetos de valor, con todas las entidades y objetos trabajan juntos para implementar las transacciones y el comportamiento necesario y las entidades secundarias.

El propósito de una raíz agregada es asegurar la coherencia del agregado; debe ser el único punto de entrada para las actualizaciones al agregado a través de métodos o las operaciones de clase raíz en conjunto. Debe realizar cambios en las entidades dentro del agregado sólo a través de la raíz agregado. Es guardián de coherencia del agregado, teniendo en cuenta todas las invariantes y tendrá que cumplir en el agregado de reglas de coherencia. Si cambia un objeto de entidad o un valor de secundario por separado, la raíz agregada no puede garantizar que el agregado está en un estado válido. Sería como una tabla con una sección flexible. Coherencia de mantenimiento es el propósito principal de la raíz agregado.

En la figura 9-9, puede ver los agregados de ejemplo como comprador agregado, que contiene una sola entidad (la raíz agregada comprador). El agregado de pedido contiene varias entidades y un objeto de valor.

![](./media/image10.png)

**Figura 9-9**. Ejemplo de agregados con varias o únicas entidades

Tenga en cuenta que el agregado de comprador podría tener entidades secundarias adicionales, dependiendo de su dominio, como ocurre en la ordenación microservicio en la aplicación de referencia de eShopOnContainers. Figura 9-9 solo ilustra un caso en el que el comprador tiene una sola entidad, como un ejemplo de una función de agregado que contiene solo una raíz agregada.

Con el fin de mantener la separación de agregados y mantener límites claros entre ellos, es una buena práctica en un modelo de dominio DDD para no permitir la navegación directa entre agregados y solo con el campo de clave externa (FK), tal y como se implementa en el [ Orden de modelo de dominio de microservicio](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) en eShopOnContainers. La entidad Order solo tiene un campo de clave externa para el comprador, pero no una propiedad de navegación de EF principales, tal como se muestra en el código siguiente:

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
}
```

Identificar y trabajar con agregados requieren investigación y experiencia. Para obtener más información, vea la siguiente lista de recursos adicionales.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Vaughn Vernon. Diseño de agregado efectivo - parte I: un único agregado de modelado**
    [*https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD\_Comunidad\_REDACCIÓN\_ AGREGADOS\_parte\_pdf de 1.*](https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_1.pdf)

-   **Vaughn Vernon. Diseño de agregado efectivo - parte II: Agregados hacer que funcionan conjuntamente**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_2.pdf>*

-   **Vaughn Vernon. Diseño de agregado efectivo - parte III: Obtener una perspectiva mediante la detección de**
    *<https://vaughnvernon.co/wordpress/wp-content/uploads/2014/10/DDD_COMMUNITY_ESSAY_AGGREGATES_PART_3.pdf>*

-   **Sergey Grybniak. Patrones de diseño tácticas de DDD**
    [*https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part*](https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part)

-   **Chris Richardson. Desarrollar Microservicios transaccional con agregados**
    [*https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson*](https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson)

-   **DevIQ. El patrón agregado**
    [*http://deviq.com/aggregate-pattern/*](http://deviq.com/aggregate-pattern/)


>[!div class="step-by-step"]
[Anterior] (ddd-orientada a servicios-microservice.md) [siguiente] (net-core-microservicio-dominio-model.md)
