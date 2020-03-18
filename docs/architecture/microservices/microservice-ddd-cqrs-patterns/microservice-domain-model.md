---
title: Diseño de un modelo de dominio de microservicio
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre los conceptos clave para diseñar un modelo de dominio orientado a un DDD
ms.date: 01/30/2020
ms.openlocfilehash: 628fb5c76362ec8f48367b3d69d16ea6ebd24f09
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77502332"
---
# <a name="design-a-microservice-domain-model"></a>Diseño de un modelo de dominio de microservicio

*Defina un modelo de dominio enriquecido para cada microservicio de negocios o contexto delimitado.*

El objetivo es crear un modelo de dominio coherente único para cada microservicio de negocio o contexto delimitado (BC). Pero tenga en cuenta que en ocasiones un BC o microservicio de negocio puede estar compuesto por varios servicios físicos que comparten un único modelo de dominio. El modelo de dominio debe capturar las reglas, el comportamiento, el lenguaje de negocios y las restricciones del contexto delimitado o microservicio de negocio que representa.

## <a name="the-domain-entity-pattern"></a>El modelo de entidad del dominio

Las entidades representan objetos del dominio y se definen principalmente por su identidad, continuidad y persistencia en el tiempo y no solo por los atributos que las componen. Como afirma Eric Evans, "un objeto definido principalmente por su identidad se denomina entidad". Las entidades son muy importantes en el modelo de dominio, ya que son la base para un modelo. Por tanto, debe identificarlas y diseñarlas cuidadosamente.

*La identidad de una entidad puede abarcar varios microservicios o contextos delimitados.*

La misma identidad (es decir, el mismo valor de `Id`, aunque quizás no sea la misma entidad de dominio) se puede modelar en varios contextos delimitados o microservicios. Pero eso no implica que la misma entidad, con los mismos atributos y lógica, se implemente en varios contextos delimitados. En su lugar, las entidades de cada contexto delimitado limitan sus atributos y comportamientos a los requeridos en el dominio de ese contexto delimitado.

Por ejemplo, es posible que la entidad de comprador tenga la mayoría de los atributos de una persona que estén definidos en la entidad de usuario en el microservicio de perfiles o identidades, incluida la identidad. Pero la entidad de comprador en el microservicio de pedidos podría tener menos atributos, porque solo determinados datos del comprador están relacionados con el proceso de pedido. El contexto de cada microservicio o contexto delimitado afecta a su modelo de dominio.

*Las entidades de dominio deben implementar el comportamiento además de los atributos de datos.*

Una entidad de dominio en DDD debe implementar la lógica del dominio o el comportamiento relacionado con los datos de entidad (el objeto al que se obtiene acceso en memoria). Por ejemplo, como parte de una clase de entidad de pedido debería implementar la lógica de negocios y las operaciones como métodos para tareas como agregar un elemento de pedido, la validación de datos y el cálculo total. Los métodos de la entidad se encargan de las invariables y las reglas de la entidad en lugar de tener esas reglas distribuidas por el nivel de aplicación.

En la figura 7-8 se muestra una entidad de dominio que implementa no solo los atributos de datos, sino también las operaciones o los métodos con lógica de dominio relacionada.

![Diagrama que muestra el patrón de una entidad de dominio.](./media/microservice-domain-model/domain-entity-pattern.png)

**Figura 7-8.** Ejemplo de un diseño de entidad de dominio en el que se implementan datos y comportamiento

Una entidad del modelo de dominio implementa comportamientos a través de métodos, es decir, no es un modelo "anémico". Evidentemente, en ocasiones puede tener entidades que no implementen ninguna lógica como parte de la clase de entidad. Esto puede ocurrir en entidades secundarias dentro de un agregado si la entidad secundaria no tiene ninguna lógica especial porque la mayor parte de la lógica se define en la raíz agregada. Si tiene un microservicio complejo con gran cantidad de lógica implementada en las clases de servicio en lugar de en las entidades de dominio, podría encontrarse en el modelo de dominio anémico que se explica en la sección siguiente.

### <a name="rich-domain-model-versus-anemic-domain-model"></a>Diferencias entre el modelo de dominio y el modelo de dominio anémico

En su publicación [AnemicDomainModel](https://martinfowler.com/bliki/AnemicDomainModel.html), Martin Fowler describe un modelo de dominio anémico de esta manera:

El síntoma básico de un modelo de dominio anémico es que a primera vista parece real. Hay objetos, muchos denominados en función de los nombres del espacio de dominio, que están conectados con las relaciones enriquecidas y la estructura de los modelos de dominio reales. Lo interesante aparece cuando se examina el comportamiento y se descubre que apenas hay comportamiento en estos objetos, lo que los convierte en poco más que conjuntos de captadores y establecedores.

Por supuesto, cuando se usa un modelo de dominio anémico, esos modelos de datos se usan desde un conjunto de objetos de servicio (denominado tradicionalmente *capa de negocio*) que captura toda la lógica de negocios o de dominio. La capa de negocio se encuentra en la parte superior del modelo de datos y usa el modelo de datos al igual que los datos.

El modelo de dominio anémico es simplemente un diseño de estilo de procedimientos. Los objetos de entidad anémicos no son objetos reales, ya que carecen de comportamiento (métodos). Solo contienen propiedades de datos y, por tanto, no se trata de un diseño orientado a objetos. Al colocar todo el comportamiento en objetos de servicio (la capa de negocio), básicamente se crea [código espagueti](https://en.wikipedia.org/wiki/Spaghetti_code) o [scripts de transacción](https://martinfowler.com/eaaCatalog/transactionScript.html), y, por tanto, se pierden las ventajas que proporciona un modelo de dominio.

Pero si el microservicio o contexto delimitado es muy sencillo (un servicio CRUD), es posible que sea suficiente con el modelo de dominio anémico en forma de objetos de entidad con solo propiedades de datos y que no merezca la pena implementar modelos DDD más complejos. En ese caso, será simplemente un modelo de persistencia, porque se ha creado deliberadamente una entidad solo con datos para fines CRUD.

Por ese motivo las arquitecturas de microservicios son perfectas para un enfoque de múltiples arquitecturas según cada contexto delimitado. Por ejemplo, en eShopOnContainers, el microservicio de pedidos implementa patrones DDD, pero el microservicio de catálogo, que es un servicio CRUD simple, no lo hace.

Hay usuarios que afirman que el modelo de dominio anémico es un antipatrón. En realidad, depende de lo que se vaya a implementar. Si el microservicio que se va a crear es bastante sencillo (por ejemplo, un servicio CRUD), seguir el modelo de dominio anémico no es un antipatrón. Pero si es necesario abordar la complejidad del dominio de un microservicio que tiene muchas reglas de negocio cambiantes, es posible que el modelo de dominio anémico sea un antipatrón para ese microservicio o contexto delimitado. En ese caso, es posible que diseñarlo como un modelo enriquecido con entidades que contienen datos y comportamiento además de implementar otros patrones DDD (agregados, objetos de valor, etc.) tenga enormes ventajas para el éxito a largo plazo de este tipo de microservicio.

#### <a name="additional-resources"></a>Recursos adicionales

- **DevIQ. Entidad de dominio** \
  <https://deviq.com/entity/>

- **Martin Fowler. El modelo de dominio** \
  <https://martinfowler.com/eaaCatalog/domainModel.html>

- **Martin Fowler. El modelo de dominio anémico** \
  <https://martinfowler.com/bliki/AnemicDomainModel.html>

### <a name="the-value-object-pattern"></a>El patrón de objeto de valor

Como ha mencionado Eric Evans, "Muchos objetos no tienen identidad conceptual. Estos objetos describen ciertas características de una cosa".

Una entidad requiere una identidad, pero en un sistema hay muchos objetos que no lo hacen, como el patrón de objeto de valor. Un objeto de valor es un objeto sin identidad conceptual que describe un aspecto de dominio. Se trata de objetos de los que se crea una instancia para representar elementos de diseño que solo interesan temporalmente. Interesa lo *que* son, no *quiénes* son. Los números y las cadenas son algunos ejemplos, pero también pueden ser conceptos de nivel superior como grupos de atributos.

Es posible que algo que sea una entidad en un microservicio no lo sea en otro, porque en el segundo caso, es posible que el contexto delimitado tenga un significado diferente. Por ejemplo, una dirección en una aplicación de comercio electrónico podría no tener ninguna identidad, ya que es posible que solo represente un grupo de atributos del perfil de cliente para una persona o empresa. En este caso, la dirección se debería clasificar como un objeto de valor. Pero en una aplicación para una empresa de energía eléctrica, la dirección del cliente podría ser importante para el dominio de negocio. Por tanto, la dirección debe tener una identidad para poder vincular el sistema de facturación directamente con la dirección. En ese caso, una dirección debería clasificarse como una entidad de dominio.

Una persona con un nombre y apellido normalmente es una entidad debido a que una persona tiene identidad, incluso si el nombre y apellido coinciden con otro conjunto de valores, por ejemplo si también hacen referencia a otra persona.

Los objetos de valor son difíciles de administrar en bases de datos relacionales y ORM como Entity Framework (EF), mientras que en las bases de datos orientadas a documentos son más fáciles de implementar y usar.

EF Core 2.0 y las versiones posteriores incluyen la característica [Entidades poseídas](https://devblogs.microsoft.com/dotnet/announcing-entity-framework-core-2-0/#owned-entities-and-table-splitting), que facilita la administración de los objetos de valor, como veremos en detalle más adelante.

#### <a name="additional-resources"></a>Recursos adicionales

- **Martin Fowler. Patrón de objeto de valor** \
  <https://martinfowler.com/bliki/ValueObject.html>

- **Objeto de valor** \
  <https://deviq.com/value-object/>

- **Objetos de valor en el desarrollo controlado por pruebas** \
  [https://leanpub.com/tdd-ebook/read\#leanpub-auto-value-objects](https://leanpub.com/tdd-ebook/read#leanpub-auto-value-objects)

- **Eric Evans. Diseño orientado al dominio: abordar la complejidad en el corazón del software.** (Libro; incluye una descripción de los objetos de valor) \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

### <a name="the-aggregate-pattern"></a>El patrón de agregado

Un modelo de dominio contiene grupos de entidades de datos diferentes y procesos que pueden controlar un área importante de funcionalidad, como el cumplimiento de pedidos o el inventario. Una unidad de DDD más específica es el agregado, que describe un clúster o grupo de entidades y comportamientos que se pueden tratar como una unidad coherente.

Normalmente, un agregado se define según las transacciones que se necesitan. Un ejemplo clásico es un pedido que también contiene una lista de elementos de pedido. Normalmente, un elemento de pedido será una entidad. Pero será una entidad secundaria dentro del agregado de pedido, que también contendrá la entidad de pedido como su entidad raíz, denominada normalmente raíz agregada.

La identificación de agregados puede ser difícil. Un agregado es un grupo de objetos que deben ser coherentes entre sí, pero no se puede seleccionar simplemente un grupo de objetos y etiquetarlos como agregado. Debe empezar por un concepto de dominio y pensar en las entidades que se usan en las transacciones más comunes relacionadas con ese concepto. Esas entidades que deben ser transaccionalmente coherentes son las que constituyen un agregado. La mejor manera de identificar agregados probablemente sea pensar en las operaciones de transacción.

### <a name="the-aggregate-root-or-root-entity-pattern"></a>El modelo de raíz agregada o entidad raíz

Un agregado se compone de al menos una entidad: la raíz agregada, que también se denomina entidad raíz o entidad principal. Además, puede tener varios objetos de valor y entidades secundarias, con todas las entidades y objetos trabajando de forma conjunta para implementar las transacciones y el comportamiento necesarios.

El propósito de una raíz agregada es asegurar la coherencia del agregado; debe ser el único punto de entrada para las actualizaciones del agregado a través de métodos u operaciones en la clase de raíz agregada. Los cambios en las entidades dentro del agregado solo se deben realizar a través de la raíz agregada. Se encarga de proteger la coherencia del agregado, teniendo en cuenta todas las invariables y reglas de coherencia que es posible que tenga que cumplir en el agregado. Si cambia una entidad secundaria o un objeto de valor por separado, la raíz agregada no podrá garantizar que el agregado esté en un estado válido. Sería como una mesa con una pata coja. El propósito principal de la raíz agregada es mantener la coherencia.

En la figura 7-9 se pueden ver agregados de ejemplo como el de Comprador, que contiene una sola entidad (la raíz agregada Comprador). El agregado de pedido contiene varias entidades y un objeto de valor.

![Diagrama que compara un agregado de comprador y un agregado de pedido.](./media/microservice-domain-model/buyer-order-aggregate-pattern.png)

**Figura 7-9**. Ejemplo de agregados con una o varias entidades

Un modelo de dominio de un DDD se compone de agregados, un agregado puede tener una sola entidad o más, y también puede incluir objetos de valor. Observe que el agregado Comprador podría tener entidades secundarias adicionales, según su dominio, como ocurre en el microservicio de pedidos de la aplicación de referencia eShopOnContainers. En la figura 7-9 solo se ilustra un caso en el que el comprador tiene una única entidad, como un ejemplo de agregado que solo contiene una raíz agregada.

Con el fin de mantener la separación de agregados y límites claros entre ellos, un procedimiento recomendado en un modelo de dominio de DDD consiste en no permitir la navegación directa entre agregados y tener solo el campo de clave externa (FK), como se implementa en el [modelo de dominio de microservicio Ordering](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Order.cs) en eShopOnContainers. La entidad Order solo tiene un campo de clave externa para el comprador, pero no una propiedad de navegación de EF Core, como se muestra en el código siguiente:

```csharp
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId; //FK pointing to a different aggregate root
    public OrderStatus OrderStatus { get; private set; }
    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;
    // ... Additional code
}
```

Para identificar y trabajar con agregados se requiere investigación y experiencia. Para obtener más información, vea la lista siguiente de recursos adicionales.

#### <a name="additional-resources"></a>Recursos adicionales

- **Vaughn Vernon. Diseño eficaz de agregados - Parte I: modelado de un único agregado** (de <http://dddcommunity.org/>) \
  <http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_1.pdf>

- **Vaughn Vernon. Diseño eficaz de agregados - Parte II: hacer que los agregados funcionen de forma conjunta** (de <http://dddcommunity.org/>) \
  <http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_2.pdf>

- **Vaughn Vernon. Diseño eficaz de agregados - Parte III: obtención de datos mediante la detección** (de <http://dddcommunity.org/>) \
  <http://dddcommunity.org/wp-content/uploads/files/pdf_articles/Vernon_2011_3.pdf>

- **Sergey Grybniak. Patrones de diseño tácticos de diseño guiado por el dominio** \
  <https://www.codeproject.com/Articles/1164363/Domain-Driven-Design-Tactical-Design-Patterns-Part>

- **Chris Richardson. Desarrollo de microservicios transaccionales con agregados** \
  <https://www.infoq.com/articles/microservices-aggregates-events-cqrs-part-1-richardson>

- **DevIQ. El patrón de agregado** \
  <https://deviq.com/aggregate-pattern/>

>[!div class="step-by-step"]
>[Anterior](ddd-oriented-microservice.md)
>[Siguiente](net-core-microservice-domain-model.md)
