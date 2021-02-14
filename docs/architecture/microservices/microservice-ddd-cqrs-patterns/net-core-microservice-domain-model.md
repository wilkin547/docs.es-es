---
title: Implementación de un modelo de dominio de microservicio con .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Información sobre la implementación de un modelo de dominio orientado a un DDD.
ms.date: 02/02/2021
ms.openlocfilehash: 87d832101d95f3ab69d1a40bbdc820e1e09af5db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665281"
---
# <a name="implement-a-microservice-domain-model-with-net"></a>Implementación de un modelo de dominio de microservicio con .NET

En la sección anterior se han explicado los principios y patrones de diseño fundamentales para diseñar un modelo de dominio. Ahora es el momento de analizar las posibles formas de implementar el modelo de dominio mediante .NET (código C\# sin formato) y EF Core. El modelo de dominio solo estará formado por el código. Tiene solo los requisitos del modelo de EF Core, pero no las dependencias reales en EF. En el modelo de dominio no debe haber dependencias fuertes ni referencias a EF Core ni ningún otro ORM.

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a>Estructura del modelo de dominio en una biblioteca personalizada de .NET Standard

La organización de carpetas usada para la aplicación de referencia eShopOnContainers muestra el modelo DDD para la aplicación. Es posible que descubra que otra organización de carpetas comunica con mayor claridad las opciones de diseño elegidas para la aplicación. Como puede ver en la figura 7-10, en el modelo de dominio Ordering hay dos agregados, el agregado Order y el agregado Buyer. Cada agregado es un grupo de entidades de dominio y objetos de valor, aunque también podría tener un agregado compuesto por una sola entidad de dominio (la raíz de agregado o entidad raíz).

:::image type="complex" source="./media/net-core-microservice-domain-model/ordering-microservice-container.png" alt-text="Captura de pantalla del proyecto Ordering.Domain en el Explorador de soluciones.":::
Vista Explorador de soluciones para el proyecto Ordering.Domain, en la que se muestra la carpeta AggregatesModel que contiene las carpetas BuyerAggregate y OrderAggregate, cada una con sus clases de entidad, archivos de objeto de valor y otros elementos.
:::image-end:::

**Figura 7-10**. Estructura del modelo de dominio del microservicio Ordering de eShopOnContainers

Además, la capa de modelo de dominio incluye los contratos de repositorio (interfaces) que son los requisitos de infraestructura del modelo de dominio. Es decir, estas interfaces expresan qué repositorios y métodos debe implementar la capa de infraestructura. Es fundamental que la implementación de los repositorios se coloque fuera de la capa de modelo de dominio, en la biblioteca de capas de infraestructura, para que la capa de modelo de dominio no quede "contaminada" por la API o clases de tecnologías de infraestructura, como Entity Framework.

También puede ver una carpeta [SeedWork](https://martinfowler.com/bliki/Seedwork.html) que contiene clases base personalizadas que se pueden usar como base para las entidades de dominio y los objetos de valor, para no tener código redundante en la clase de objeto de cada dominio.

## <a name="structure-aggregates-in-a-custom-net-standard-library"></a>Estructuración de los agregados en una biblioteca personalizada de .NET Standard

Un agregado hace referencia a un clúster de objetos de dominio agrupados para aproximarse a la coherencia transaccional. Esos objetos pueden ser instancias de entidades (una de las cuales es la raíz de agregado o entidad raíz) más los objetos de valor adicionales.

La coherencia transaccional significa que se garantiza la coherencia y actualización de un agregado al final de una acción empresarial. Por ejemplo, la composición del agregado Order del modelo de dominio del microservicio Ordering de eShopOnContainers es la que se muestra en la figura 7-11.

:::image type="complex" source="./media/net-core-microservice-domain-model/vs-solution-explorer-order-aggregate.png" alt-text="Captura de pantalla de la carpeta OrderAggregate y sus clases.":::
Una vista detallada de la carpeta OrderAggregate: Address.cs es un objeto de valor, IOrderRepository es una interfaz de repositorio, Order.cs es una raíz agregada, OrderItem.cs es una entidad secundaria y OrderStatus.cs es una clase de enumeración.
:::image-end:::

**Figura 7-11**. Agregado Order en la solución de Visual Studio

Si abre cualquiera de los archivos de una carpeta de agregado, puede ver que está marcado como clase base personalizada o interfaz, como entidad u objeto de valor, tal como se ha implementado en la carpeta [SeedWork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork).

## <a name="implement-domain-entities-as-poco-classes"></a>Implementación de entidades de dominio como clases POCO

En .NET, los modelos de dominio se implementan mediante la creación de clases POCO que implementan las entidades de dominio. En el ejemplo siguiente, la clase Order se define como una entidad y también como una raíz de agregado. Dado que la clase Order deriva de la clase base Entity, puede reutilizar código común relacionado con entidades. Tenga en cuenta que estas clases base e interfaces las define el usuario en el proyecto de modelo de dominio, por lo que es el código, no el código de infraestructura de un ORM, como EF.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 5.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    private DateTime _orderDate;
    public Address Address { get; private set; }
    private int? _buyerId;

    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    private string _description;
    private int? _paymentMethodId;

    private readonly List<OrderItem> _orderItems;
    public IReadOnlyCollection<OrderItem> OrderItems => _orderItems;

    public Order(string userId, Address address, int cardTypeId, string cardNumber, string cardSecurityNumber,
            string cardHolderName, DateTime cardExpiration, int? buyerId = null, int? paymentMethodId = null)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.Submitted.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;

        // ...Additional code ...
    }

    public void AddOrderItem(int productId, string productName,
                            decimal unitPrice, decimal discount,
                            string pictureUrl, int units = 1)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...

        var orderItem = new OrderItem(productId, productName, unitPrice, discount, pictureUrl, units);

        _orderItems.Add(orderItem);

    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

Es importante tener en cuenta que se trata de una entidad de dominio implementada como clase POCO. No tiene ninguna dependencia directa con Entity Framework Core ni ningún otro marco de trabajo de infraestructura. Esta es la implementación que se debería usar en DDD: tan solo código de C# que implementa un modelo de dominio.

Además, la clase se decora con una interfaz denominada IAggregateRoot. Esa interfaz es una interfaz vacía, que a veces se denomina *interfaz de marcador*, que se usa simplemente para indicar que esta clase de entidad también es una raíz de agregado.

Una interfaz de marcador a veces se considera un anti-patrón; pero también es una manera eficaz de marcar una clase, sobre todo cuando esa interfaz podría estar evolucionando. Un atributo podría ser la otra opción para el marcador, pero es más rápido ver la clase base (Entity) junto a la interfaz IAggregate en lugar de colocar un marcador de atributo Aggregate sobre la clase. En cualquier caso, es una cuestión de preferencias.

Tener una raíz de agregado significa que la mayoría del código relacionado con la coherencia y las reglas de negocio de las entidades del agregado deben implementarse como métodos en la clase raíz de agregado Order (por ejemplo, AddOrderItem al agregar un objeto OrderItem al agregado). No debe crear ni actualizar objetos OrderItems de forma independiente ni directa; la clase AggregateRoot debe mantener el control y la coherencia de cualquier operación de actualización en sus entidades secundarias.

## <a name="encapsulate-data-in-the-domain-entities"></a>Encapsulación de datos en entidades de dominio

Un problema habitual de los modelos de entidad es que exponen propiedades de navegación de colecciones como tipos de lista públicamente accesibles. Esto permite que cualquier desarrollador colaborador manipule el contenido de estos tipos de colecciones, con lo que se pueden omitir importantes reglas de negocio relacionadas con la colección, lo que podría dejar el objeto en un estado no válido. La solución es conceder acceso de solo lectura a las colecciones relacionadas y proporcionar explícitamente métodos que definan formas para que los clientes las manipulen.

En el código anterior, observe que muchos atributos son de solo lectura o privados, y que solo pueden actualizarlos los métodos de clase, por lo que cualquier actualización tiene en cuenta las invariables de dominio de negocio de cuenta y la lógica especificada en los métodos de clase.

Por ejemplo, de acuerdo a los patrones DDD, ***no* debería hacer lo siguiente** desde ningún método de controlador de comando ni clase de capa de aplicación (de hecho debería ser imposible hacerlo):

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems collection directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

En este caso, el método Add es puramente una operación para agregar datos, con acceso directo a la colección OrderItems. Por lo tanto, la mayoría de la lógica, las reglas o las validaciones del dominio relacionadas con esa operación con las entidades secundarias se distribuirá a la capa de aplicación (controladores de comandos y controladores de Web API).

Si omite la raíz de agregado, esta no puede garantizar sus invariables, su validez ni su coherencia. Al final tendrá código espagueti o código de script transaccional.

Para seguir los patrones DDD, las entidades no deben tener establecedores públicos en ninguna propiedad de entidad. Los cambios en una entidad deben realizarse mediante métodos explícitos con lenguaje ubicuo explícito sobre el cambio que están realizando en la entidad.

Además, las colecciones de la entidad (por ejemplo, OrderItems) deben ser propiedades de solo lectura (el método AsReadOnly explicado más adelante). Debe ser capaz de actualizarla solo desde los métodos de la clase raíz de agregado o los métodos de entidad secundaria.

Como puede ver en el código de la raíz de agregado Order, todos los establecedores deben ser privados o al menos de solo lectura externamente para que cualquier operación en los datos de la entidad o sus entidades secundarias tenga que realizarse mediante métodos en la clase de entidad. Esto mantiene la coherencia de una manera controlada y orientada a objetos en lugar de implementar código de script transaccional.

El fragmento de código siguiente muestra la manera adecuada de programar la tarea de agregar un objeto OrderItem al agregado Order.

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object's business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

En este fragmento de código, la mayoría de las validaciones o la lógica relacionadas con la creación de un objeto OrderItem están bajo el control de la raíz de agregado Order, en el método AddOrderItem, especialmente las validaciones y la lógica relacionadas con otros elementos del agregado. Por ejemplo, podría obtener el mismo artículo como resultado de varias llamadas a AddOrderItem. En ese método, puede examinar los artículos y consolidar los mismos en un único objeto OrderItem con varias unidades. Además, si hay importes de descuento distintos pero el identificador de producto es el mismo, se aplicaría el mayor descuento. Este principio se aplica a cualquier otra lógica de dominio del objeto OrderItem.

Además, la nueva operación OrderItem(params) también es controlada y realizada por el método AddOrderItem de la raíz de agregado Order. Por lo tanto, la mayoría de la lógica o las validaciones relacionadas con esa operación (especialmente todo lo que afecta a la coherencia entre otras entidades secundarias) estará en una única ubicación dentro de la raíz de agregado. Ese es el fin último del patrón de raíz de agregado.

Cuando use Entity Framework Core 1.1 o posterior, una entidad DDD se puede expresar mejor porque permite [asignar a campos](/ef/core/modeling/backing-field) además de a propiedades. Esto resulta útil al proteger colecciones de entidades secundarias u objetos de valor. Con esta mejora, puede usar campos privados simples en lugar de propiedades y puede implementar cualquier actualización de la colección de campos en los métodos públicos y proporcionar acceso de solo lectura mediante el método AsReadOnly.

En DDD, interesa actualizar la entidad únicamente mediante métodos de la entidad (o el constructor) para controlar cualquier invariable y la coherencia de los datos, de modo que las propiedades solo se definan con un descriptor de acceso get. Las propiedades se basan en campos privados. A los miembros privados solo se puede acceder desde la clase. Pero hay una excepción: EF Core también debe establecer estos campos (de forma que pueda devolver el objeto con los valores adecuados).

### <a name="map-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a>Asignación de propiedades con solo los descriptores de acceso get a los campos de la tabla de base de datos

La asignación de propiedades a columnas de la tabla de base de datos no es responsabilidad del dominio, sino que forma parte de la capa de infraestructura y persistencia. Se menciona aquí simplemente para que sea consciente de las nuevas capacidades de EF Core 1.1 o posterior relacionadas con la forma de modelar entidades. En la sección de infraestructura y persistencia se explican más detalles sobre este tema.

Cuando se usa EF Core 1.0 o posterior, en DbContext es necesario asignar las propiedades definidas únicamente con captadores a los campos reales de la tabla de base de datos. Esto se hace con el método HasField de la clase PropertyBuilder.

### <a name="map-fields-without-properties"></a>Asignación de campos sin propiedades

La característica de EF Core 1.1 o posterior para asignar columnas a campos también permite no usar propiedades. En su lugar, puede simplemente asignar columnas de una tabla a campos. Un caso de uso común de esto son los campos privados de un estado interno al que no es necesario acceder desde fuera de la entidad.

Por ejemplo, en el ejemplo de código OrderAggregate anterior, hay varios campos privados, como el campo `_paymentMethodId`, sin ninguna propiedad relacionada para un establecedor ni un captador. Ese campo también podría calcularse en la lógica de negocios de Order y usarse desde los métodos de Order, pero debe conservarse además en la base de datos. Así, en EF Core (a partir de la versión 1.1) hay una forma de asignar un campo sin ninguna propiedad relacionada a una columna de la base de datos. Esto también se explica en la sección [Capa de infraestructura](ddd-oriented-microservice.md#the-infrastructure-layer) de esta guía.

### <a name="additional-resources"></a>Recursos adicionales

- **Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework (Modelado de agregados con DDD y Entity Framework).** Tenga en cuenta que esto *no* es Entity Framework Core. \
  <https://kalele.io/blog-posts/modeling-aggregates-with-ddd-and-entity-framework/>

- **Julie Lerman. Puntos de datos - Programación para un diseño guiado por el dominio: sugerencias para los desarrolladores enfocados en datos** \
  <https://docs.microsoft.com/archive/msdn-magazine/2013/august/data-points-coding-for-domain-driven-design-tips-for-data-focused-devs>

- **Udi Dahan. Cómo crear modelos de dominio totalmente encapsulados** \
  <https://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/>

> [!div class="step-by-step"]
> [Anterior](microservice-domain-model.md)
> [Siguiente](seedwork-domain-model-base-classes-interfaces.md)
