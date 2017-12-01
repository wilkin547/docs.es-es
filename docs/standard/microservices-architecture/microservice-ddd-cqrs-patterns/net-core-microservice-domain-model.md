---
title: Implementar un modelo de dominio de microservicio con .NET Core
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementar un modelo de dominio de microservicio con .NET Core
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 26c480a82ad7bb806734decebdfbe5b4a07998e6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-a-microservice-domain-model-with-net-core"></a>Implementar un modelo de dominio de microservicio con .NET Core 

En la sección anterior, se explican los principios de diseño fundamentales y patrones de diseño de un modelo de dominio. Ahora es el momento para explorar maneras posibles para implementar el modelo de dominio mediante .NET Core (sin formato C\# código) y EF Core. Tenga en cuenta que el modelo de dominio podría estar compuesto simplemente por el código. Esto tendrá solo los requisitos principales de EF de modelo, sino dependencias no reales en EF. No debe tener dependencias o referencias a EF Core o cualquier otro ORM en el modelo de dominio.

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a>Estructura del modelo de dominio en una biblioteca de .NET estándar personalizada

La organización de carpetas usada para la aplicación de referencia de eShopOnContainers muestra el modelo DDD para la aplicación. Es posible que una organización de carpetas diferente con mayor claridad comunica las opciones de diseño elegidas para la aplicación. Como puede ver en la figura 9-10, en el modelo de dominio ordenación hay dos agregados, el agregado de orden y el agregado de comprador. Cada agregado es un grupo de entidades de dominio y objetos de valor, aunque podría tener un agregado compuesto por una única entidad del dominio (la raíz agregada o entidad raíz) también.

![](./media/image11.png)

**Figura 9-10**. Estructura del modelo de dominio para la ordenación microservicio en eShopOnContainers

Además, el nivel de modelo de dominio incluye los contratos de repositorio (interfaces) que son los requisitos de infraestructura de su modelo de dominio. En otras palabras, estas interfaces expresan qué repositorios debe implementar el nivel de infraestructura y cómo. Es fundamental que la implementación de los repositorios de colocarse fuera de la capa de modelo de dominio, en la biblioteca de capa de infraestructura, por lo que el nivel de modelo de dominio no "contaminado" API o las clases de tecnologías de infraestructura, como Entity Framework.

También puede ver un [SeedWork](https://martinfowler.com/bliki/Seedwork.html) objetos de carpeta que contiene las clases base personalizadas que puede usar como base para el valor de entidades de dominio y, por lo que no tiene código redundante en la clase de objeto de cada dominio.

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a>Estructurar los agregados en una biblioteca de .NET estándar personalizado

Un agregado hace referencia a un clúster de objetos de dominio que se agrupan para que coincida con la coherencia transaccional. Esos objetos pueden ser instancias de entidades (uno de los cuales es la raíz agregada o entidad raíz) además de los objetos de un valor adicional.

Coherencia transaccional significa que un agregado está garantizado que sea coherente y al día al final de una acción empresarial. Por ejemplo, el agregado de orden de la eShopOnContainers orden microservicio modelo de dominio se compone tal como se muestra en la figura 9-11.

![](./media/image12.png)

**Figura 9-11**. El orden de agregado en la solución de Visual Studio

Si abre cualquiera de los archivos en una carpeta de agregado, puede ver cómo se marca como una clase base personalizada o una interfaz, como objeto de entidad o un valor, tal como se implementa en el [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) carpeta.

## <a name="implementing-domain-entities-as-poco-classes"></a>Implementar las entidades de dominio como las clases

Implementar un modelo de dominio en .NET mediante la creación de las clases que implementan las entidades de dominio. En el ejemplo siguiente, la clase Order se define como una entidad y también como una raíz agregada. Dado que la clase Order se deriva de la clase base de la entidad, puede reutilizar el código comunes relacionadas con entidades. Tenga en cuenta que estas clases base e interfaces se definen por el usuario en el proyecto de modelo de dominio, por lo que es el código, no el código de infraestructura desde un ORM como EF.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE 1.0
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    public int BuyerId { get; private set; }
    public DateTime OrderDate { get; private set; }
    public int StatusId { get; private set; }
    public ICollection<OrderItem> OrderItems { get; private set; }
    public Address ShippingAddress { get; private set; }
    public int PaymentId { get; private set; }
    protected Order() { } //Design constraint needed only by EF Core
    public Order(int buyerId, int paymentId)
    {
        BuyerId = buyerId;
        PaymentId = paymentId;
        StatusId = OrderStatus.InProcess.Id;
        OrderDate = DateTime.UtcNow;
        OrderItems = new List<OrderItem>();
    }

    public void AddOrderItem(productName,
        pictureUrl,
        unitPrice,
        discount,
        units)
    {
        //...
        // Domain rules/logic for adding the OrderItem to the order
        // ...
        OrderItem item = new OrderItem(this.Id, ProductId, productName,
            pictureUrl, unitPrice, discount, units);
  
        OrderItems.Add(item);
    }
    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

Es importante tener en cuenta que se trata de una entidad de dominio que se implementa como una clase POCO. No tiene ninguna dependencia directa en Entity Framework Core o cualquier otro marco de trabajo de infraestructura. Esta implementación es como debería ser, simplemente C\# código que implementa un modelo de dominio.

Además, la clase se decora con una interfaz denominada IAggregateRoot. Esa interfaz es una interfaz vacía, que se denomina a veces un *interfaz de marcador*, que se utiliza para indicar que esta clase de entidad también es una raíz agregada.

Una interfaz de marcador a veces se considera como un antipatrón; Sin embargo, también es una manera limpia para marcar una clase, sobre todo cuando podría ir evolucionando esa interfaz. Un atributo podría ser la otra opción para el marcador, pero es más rápido, vea la clase base (entidad) junto a la interfaz IAggregate en lugar de colocar un marcador de atributo de agregado por encima de la clase. Es un metter de preferencias, en cualquier caso.

Tener un medio de raíz agregada que relacionados con la mayoría del código para mejorar la coherencia y reglas de negocios de entidades del agregado deben implementarse como métodos en la clase raíz agregada (por ejemplo, AddOrderItem al agregar un objeto OrderItem al agregado) . No debe crear o actualizar los objetos de OrderItems independientemente o directamente; la clase AggregateRoot debe mantener control y la coherencia de cualquier operación de actualización con sus entidades secundarias.

Por ejemplo, debería *no* realice las siguientes acciones de cualquier clase de capa de aplicación o el método de controlador de comando:

```csharp
// WRONG ACCORDING TO DDD PATTERNS – CODE AT THE APPLICATION LAYER OR
// COMMAND HANDLERS
// Code in command handler methods or Web API controllers
//... (WRONG) Some code with business logic out of the domain classes ...
OrderItem myNewOrderItem = new OrderItem(orderId, productId, productName,
    pictureUrl, unitPrice, discount, units);

//... (WRONG) Accessing the OrderItems colletion directly from the application layer // or command handlers
myOrder.OrderItems.Add(myNewOrderItem);
//...
```

En este caso, el método Add es puramente una operación para agregar datos, con acceso directo a la colección OrderItems. Por lo tanto, la mayoría de la lógica del dominio, reglas o validaciones relacionadas con que la operación con las entidades secundarias se distribuirán a través de la capa de aplicación (controladores de comandos y controladores de API Web).

Si dejan alrededor de la raíz agregada, la raíz agregada no puede garantizar sus invariables, su validez o su coherencia. Finalmente tendrá spaghetti código o script transaccional.

Para seguir patrones DDD, las entidades no deben tener establecedores públicos en cualquier propiedad de entidad. Cambios en una entidad deben determinarse mediante métodos explícitos con lenguaje ubicuo explícitas acerca del cambio que se están realizando en la entidad.

Además, las colecciones dentro de la entidad (por ejemplo, los artículos del pedido) deben ser propiedades de solo lectura (el método AsReadOnly explicará más adelante). Debe ser capaz de actualizar solo desde dentro de los métodos de la clase raíz agregada o los métodos de la entidad secundaria.

Como puede ver en el código de la raíz agregado de orden, todos los establecedores deben ser privados o al menos de solo lectura externamente, por lo que cualquier operación con los datos de la entidad o sus entidades secundarias tiene que realizarse a través de métodos en la clase de entidad. Esto mantiene la coherencia de una manera controlada y orientada a objetos en lugar de implementar el código de la secuencia de comandos transaccional.

El fragmento de código siguiente muestra la manera adecuada de la tarea de agregar un objeto OrderItem para el agregado de orden de código.

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

En este fragmento de código, la mayoría de las validaciones o la lógica relacionada con la creación de un objeto OrderItem será bajo el control de la raíz agregado de orden, en el método AddOrderItem, especialmente las validaciones y lógica relacionados con otros elementos en conjunto. Por ejemplo, podría obtener el mismo elemento de producto como el resultado de varias llamadas a AddOrderItem. En ese método, puede examinar los elementos de producto y consolidar los mismos elementos de producto en un único objeto OrderItem con varias unidades. Además, si hay cantidades de descuento distinto, pero el identificador de producto es el mismo, es probable que se aplicará el mayor descuento. Este principio se aplica a cualquier otra lógica de dominio para el objeto OrderItem.

Además, la nueva operación OrderItem(params) también se controlan y realizada por el método AddOrderItem desde la raíz agregado de orden. Por lo tanto, la mayoría de la lógica o validaciones relacionadas con que operación (especialmente todo lo que afecta a la coherencia entre otras entidades secundarias) estarán en un único lugar dentro de la raíz agregado. Es el objetivo final del patrón raíz agregada.

Cuando se usa Entity Framework 1.1, se puede expresar mejor una entidad DDD porque una de las nuevas características de Entity Framework Core 1.1 es que permite [asignar a campos](https://docs.microsoft.com/ef/core/modeling/backing-field) además de propiedades. Esto es útil cuando se protegen las colecciones de las entidades secundarias u objetos de valor. Con esta mejora, puede usar los campos privados simples en lugar de propiedades y puede implementar las actualizaciones en la colección de campos en los métodos públicos y proporcionar acceso de solo lectura a través del método AsReadOnly.

En el DDD que desea actualizar la entidad sólo a través de métodos en la entidad (o el constructor) con el fin de controlar cualquier invariable y la coherencia de los datos, por lo que propiedades se definen únicamente con un descriptor de acceso get. Las propiedades se basan en campos privados. Los miembros privados sólo puede tener acceso desde dentro de la clase. Sin embargo, excepción de allí uno: Core EF necesita establecer estos campos también.

```csharp
// ENTITY FRAMEWORK CORE 1.1 OR LATER
// Entity is a custom base class with the ID
public class Order : Entity, IAggregateRoot
{
    // DDD Patterns comment
    // Using private fields, allowed since EF Core 1.1, is a much better
    // encapsulation aligned with DDD aggregates and domain entities (instead of
    // properties and property collections)
    private bool _someOrderInternalState;
    private DateTime _orderDate;
    public Address Address { get; private set; }
    public Buyer Buyer { get; private set; }
    private int _buyerId;
    public OrderStatus OrderStatus { get; private set; }
    private int _orderStatusId;

    // DDD patterns comment
    // Using a private collection field is better for DDD aggregate encapsulation.
    // OrderItem objects cannot be added from outside the aggregate root
    // directly to the collection, but only through the
    // OrderAggrergateRoot.AddOrderItem method, which includes behavior.
    private readonly List<OrderItem> _orderItems;
    public IEnumerable<OrderItem> OrderItems => _orderItems.AsReadOnly();
    // Using List<>.AsReadOnly()
    // This will create a read-only wrapper around the private list so it is
    // protected against external updates. It's much cheaper than .ToList(),
    // because it will not have to copy all items in a new collection.
    // (Just one heap alloc for the wrapper instance)
    // https://msdn.microsoft.com/en-us/library/e78dcd75(v=vs.110).aspx
    public PaymentMethod PaymentMethod { get; private set; }
    private int _paymentMethodId;

    protected Order() { }

    public Order(int buyerId, int paymentMethodId, Address address)
    {
        _orderItems = new List<OrderItem>();
        _buyerId = buyerId;
        _paymentMethodId = paymentMethodId;
        _orderStatusId = OrderStatus.InProcess.Id;
        _orderDate = DateTime.UtcNow;
        Address = address;
    }

    // DDD patterns comment
    // The Order aggregate root method AddOrderitem() should be the only way
    // to add items to the Order object, so that any behavior (discounts, etc.)
    // and validations are controlled by the aggregate root in order to
    // maintain consistency within the whole aggregate.
    public void AddOrderItem(int productId, string productName, decimal unitPrice,
        decimal discount, string pictureUrl, int units = 1)
    {
        // ...
        // Domain rules/logic here for adding OrderItem objects to the order
        // ...
        OrderItem item = new OrderItem(this.Id, productId, productName,
            pictureUrl, unitPrice, discount, units);
        OrderItems.Add(item);
    }

    // ...
    // Additional methods with domain rules/logic related to the Order aggregate
    // ...
}
```

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a>Obtención de propiedades de asignación con solo los descriptores de acceso a los campos en la tabla de base de datos

Asignar propiedades a las columnas de tabla de base de datos no es responsabilidad de un dominio, pero como parte de la capa de infraestructura y persistencia. Mencionamos esta aquí solo por lo que es consciente de las nuevas capacidades de 1.1 EF relacionados con cómo puede modelar las entidades. Obtener más detalles sobre este tema se explican en la sección infraestructura y persistencia.

Cuando usas EF 1.0, dentro de DbContext debe asignar las propiedades que se definen únicamente con captadores a los campos en la tabla de base de datos reales. Esto se realiza con el método HasField de la clase PropertyBuilder.

### <a name="mapping-fields-without-properties"></a>Asignación de campos sin propiedades

Con la nueva característica de EF Core 1.1 para asignar columnas a campos, también es posible no utilizar propiedades. En su lugar, solo puede asignar columnas de una tabla a campos. Un caso de uso común para esto es campos privados de un estado interno que no es necesario tener acceso desde fuera de la entidad.

Por ejemplo, en el ejemplo de código anterior, el \_someOrderInternalState campo no tiene ninguna propiedad relacionada de un establecedor o captador. Ese campo también se calculan dentro de la lógica de negocios de la orden y se usa uno de los métodos de la orden, pero debe conservarse en la base de datos. Por lo tanto, en EF 1.1 es una manera de asignar un campo sin una propiedad relacionada a una columna de la base de datos. Esto también se explica en la [nivel de infraestructura](#the-infrastructure-layer) sección de esta guía.

### <a name="additional-resources"></a>Recursos adicionales

-   **Vaughn Vernon. Modelado agregados con DDD y Entity Framework.** Tenga en cuenta que esto es *no* Entity Framework Core.
    [*https://vaughnvernon.co/?p=879*](https://vaughnvernon.co/?p=879)

-   **Julia Lerman. Codificación de diseño basado en dominio: sugerencias para desarrolladores centradas en datos**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)

-   **UDI Dahan. Cómo crear totalmente encapsula modelos de dominio**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)


>[!div class="step-by-step"]
[Anterior] (microservicio-dominio-model.md) [siguiente] (seedwork-domain-model-base-classes-interfaces.md)
