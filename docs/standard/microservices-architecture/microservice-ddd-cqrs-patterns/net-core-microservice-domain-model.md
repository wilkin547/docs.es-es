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
# <a name="implementing-a-microservice-domain-model-with-net-core"></a><span data-ttu-id="331a4-104">Implementar un modelo de dominio de microservicio con .NET Core</span><span class="sxs-lookup"><span data-stu-id="331a4-104">Implementing a microservice domain model with .NET Core</span></span> 

<span data-ttu-id="331a4-105">En la sección anterior, se explican los principios de diseño fundamentales y patrones de diseño de un modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="331a4-105">In the previous section, the fundamental design principles and patterns for designing a domain model were explained.</span></span> <span data-ttu-id="331a4-106">Ahora es el momento para explorar maneras posibles para implementar el modelo de dominio mediante .NET Core (sin formato C\# código) y EF Core.</span><span class="sxs-lookup"><span data-stu-id="331a4-106">Now it is time to explore possible ways to implement the domain model by using .NET Core (plain C\# code) and EF Core.</span></span> <span data-ttu-id="331a4-107">Tenga en cuenta que el modelo de dominio podría estar compuesto simplemente por el código.</span><span class="sxs-lookup"><span data-stu-id="331a4-107">Note that your domain model will be composed simply of your code.</span></span> <span data-ttu-id="331a4-108">Esto tendrá solo los requisitos principales de EF de modelo, sino dependencias no reales en EF.</span><span class="sxs-lookup"><span data-stu-id="331a4-108">It will have just the EF Core model requirements, but not real dependencies on EF.</span></span> <span data-ttu-id="331a4-109">No debe tener dependencias o referencias a EF Core o cualquier otro ORM en el modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="331a4-109">You should not have hard dependencies or references to EF Core or any other ORM in your domain model.</span></span>

## <a name="domain-model-structure-in-a-custom-net-standard-library"></a><span data-ttu-id="331a4-110">Estructura del modelo de dominio en una biblioteca de .NET estándar personalizada</span><span class="sxs-lookup"><span data-stu-id="331a4-110">Domain model structure in a custom .NET Standard library</span></span>

<span data-ttu-id="331a4-111">La organización de carpetas usada para la aplicación de referencia de eShopOnContainers muestra el modelo DDD para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="331a4-111">The folder organization used for the eShopOnContainers reference application demonstrates the DDD model for the application.</span></span> <span data-ttu-id="331a4-112">Es posible que una organización de carpetas diferente con mayor claridad comunica las opciones de diseño elegidas para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="331a4-112">You might find that a different folder organization more clearly communicates the design choices made for your application.</span></span> <span data-ttu-id="331a4-113">Como puede ver en la figura 9-10, en el modelo de dominio ordenación hay dos agregados, el agregado de orden y el agregado de comprador.</span><span class="sxs-lookup"><span data-stu-id="331a4-113">As you can see in Figure 9-10, in the ordering domain model there are two aggregates, the order aggregate and the buyer aggregate.</span></span> <span data-ttu-id="331a4-114">Cada agregado es un grupo de entidades de dominio y objetos de valor, aunque podría tener un agregado compuesto por una única entidad del dominio (la raíz agregada o entidad raíz) también.</span><span class="sxs-lookup"><span data-stu-id="331a4-114">Each aggregate is a group of domain entities and value objects, although you could have an aggregate composed of a single domain entity (the aggregate root or root entity) as well.</span></span>

![](./media/image11.png)

<span data-ttu-id="331a4-115">**Figura 9-10**.</span><span class="sxs-lookup"><span data-stu-id="331a4-115">**Figure 9-10**.</span></span> <span data-ttu-id="331a4-116">Estructura del modelo de dominio para la ordenación microservicio en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="331a4-116">Domain model structure for the ordering microservice in eShopOnContainers</span></span>

<span data-ttu-id="331a4-117">Además, el nivel de modelo de dominio incluye los contratos de repositorio (interfaces) que son los requisitos de infraestructura de su modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="331a4-117">Additionally, the domain model layer includes the repository contracts (interfaces) that are the infrastructure requirements of your domain model.</span></span> <span data-ttu-id="331a4-118">En otras palabras, estas interfaces expresan qué repositorios debe implementar el nivel de infraestructura y cómo.</span><span class="sxs-lookup"><span data-stu-id="331a4-118">In other words, these interfaces express what repositories the infrastructure layer must implement and how.</span></span> <span data-ttu-id="331a4-119">Es fundamental que la implementación de los repositorios de colocarse fuera de la capa de modelo de dominio, en la biblioteca de capa de infraestructura, por lo que el nivel de modelo de dominio no "contaminado" API o las clases de tecnologías de infraestructura, como Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="331a4-119">It is critical that the implementation of the repositories be placed outside of the domain model layer, in the infrastructure layer library, so the domain model layer is not “contaminated” by API or classes from infrastructure technologies, like Entity Framework.</span></span>

<span data-ttu-id="331a4-120">También puede ver un [SeedWork](https://martinfowler.com/bliki/Seedwork.html) objetos de carpeta que contiene las clases base personalizadas que puede usar como base para el valor de entidades de dominio y, por lo que no tiene código redundante en la clase de objeto de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="331a4-120">You can also see a [SeedWork](https://martinfowler.com/bliki/Seedwork.html) folder that contains custom base classes that you can use as a base for your domain entities and value objects, so you do not have redundant code in each domain’s object class.</span></span>

## <a name="structuring-aggregates-in-a-custom-net-standard-library"></a><span data-ttu-id="331a4-121">Estructurar los agregados en una biblioteca de .NET estándar personalizado</span><span class="sxs-lookup"><span data-stu-id="331a4-121">Structuring aggregates in a custom .NET Standard library</span></span>

<span data-ttu-id="331a4-122">Un agregado hace referencia a un clúster de objetos de dominio que se agrupan para que coincida con la coherencia transaccional.</span><span class="sxs-lookup"><span data-stu-id="331a4-122">An aggregate refers to a cluster of domain objects grouped together to match transactional consistency.</span></span> <span data-ttu-id="331a4-123">Esos objetos pueden ser instancias de entidades (uno de los cuales es la raíz agregada o entidad raíz) además de los objetos de un valor adicional.</span><span class="sxs-lookup"><span data-stu-id="331a4-123">Those objects could be instances of entities (one of which is the aggregate root or root entity) plus any additional value objects.</span></span>

<span data-ttu-id="331a4-124">Coherencia transaccional significa que un agregado está garantizado que sea coherente y al día al final de una acción empresarial.</span><span class="sxs-lookup"><span data-stu-id="331a4-124">Transactional consistency means that an aggregate is guaranteed to be consistent and up to date at the end of a business action.</span></span> <span data-ttu-id="331a4-125">Por ejemplo, el agregado de orden de la eShopOnContainers orden microservicio modelo de dominio se compone tal como se muestra en la figura 9-11.</span><span class="sxs-lookup"><span data-stu-id="331a4-125">For example, the order aggregate from the eShopOnContainers ordering microservice domain model is composed as shown in Figure 9-11.</span></span>

![](./media/image12.png)

<span data-ttu-id="331a4-126">**Figura 9-11**.</span><span class="sxs-lookup"><span data-stu-id="331a4-126">**Figure 9-11**.</span></span> <span data-ttu-id="331a4-127">El orden de agregado en la solución de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="331a4-127">The order aggregate in Visual Studio solution</span></span>

<span data-ttu-id="331a4-128">Si abre cualquiera de los archivos en una carpeta de agregado, puede ver cómo se marca como una clase base personalizada o una interfaz, como objeto de entidad o un valor, tal como se implementa en el [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) carpeta.</span><span class="sxs-lookup"><span data-stu-id="331a4-128">If you open any of the files in an aggregate folder, you can see how it is marked as either a custom base class or interface, like entity or value object, as implemented in the [Seedwork](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Services/Ordering/Ordering.Domain/SeedWork) folder.</span></span>

## <a name="implementing-domain-entities-as-poco-classes"></a><span data-ttu-id="331a4-129">Implementar las entidades de dominio como las clases</span><span class="sxs-lookup"><span data-stu-id="331a4-129">Implementing domain entities as POCO classes</span></span>

<span data-ttu-id="331a4-130">Implementar un modelo de dominio en .NET mediante la creación de las clases que implementan las entidades de dominio.</span><span class="sxs-lookup"><span data-stu-id="331a4-130">You implement a domain model in .NET by creating POCO classes that implement your domain entities.</span></span> <span data-ttu-id="331a4-131">En el ejemplo siguiente, la clase Order se define como una entidad y también como una raíz agregada.</span><span class="sxs-lookup"><span data-stu-id="331a4-131">In the following example, the Order class is defined as an entity and also as an aggregate root.</span></span> <span data-ttu-id="331a4-132">Dado que la clase Order se deriva de la clase base de la entidad, puede reutilizar el código comunes relacionadas con entidades.</span><span class="sxs-lookup"><span data-stu-id="331a4-132">Because the Order class derives from the Entity base class, it can reuse common code related to entities.</span></span> <span data-ttu-id="331a4-133">Tenga en cuenta que estas clases base e interfaces se definen por el usuario en el proyecto de modelo de dominio, por lo que es el código, no el código de infraestructura desde un ORM como EF.</span><span class="sxs-lookup"><span data-stu-id="331a4-133">Bear in mind that these base classes and interfaces are defined by you in the domain model project, so it is your code, not infrastructure code from an ORM like EF.</span></span>

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

<span data-ttu-id="331a4-134">Es importante tener en cuenta que se trata de una entidad de dominio que se implementa como una clase POCO.</span><span class="sxs-lookup"><span data-stu-id="331a4-134">It is important to note that this is a domain entity implemented as a POCO class.</span></span> <span data-ttu-id="331a4-135">No tiene ninguna dependencia directa en Entity Framework Core o cualquier otro marco de trabajo de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="331a4-135">It does not have any direct dependency on Entity Framework Core or any other infrastructure framework.</span></span> <span data-ttu-id="331a4-136">Esta implementación es como debería ser, simplemente C\# código que implementa un modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="331a4-136">This implementation is as it should be, just C\# code implementing a domain model.</span></span>

<span data-ttu-id="331a4-137">Además, la clase se decora con una interfaz denominada IAggregateRoot.</span><span class="sxs-lookup"><span data-stu-id="331a4-137">In addition, the class is decorated with an interface named IAggregateRoot.</span></span> <span data-ttu-id="331a4-138">Esa interfaz es una interfaz vacía, que se denomina a veces un *interfaz de marcador*, que se utiliza para indicar que esta clase de entidad también es una raíz agregada.</span><span class="sxs-lookup"><span data-stu-id="331a4-138">That interface is an empty interface, sometimes called a *marker interface*, that is used just to indicate that this entity class is also an aggregate root.</span></span>

<span data-ttu-id="331a4-139">Una interfaz de marcador a veces se considera como un antipatrón; Sin embargo, también es una manera limpia para marcar una clase, sobre todo cuando podría ir evolucionando esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="331a4-139">A marker interface is sometimes considered as an anti-pattern; however, it is also a clean way to mark a class, especially when that interface might be evolving.</span></span> <span data-ttu-id="331a4-140">Un atributo podría ser la otra opción para el marcador, pero es más rápido, vea la clase base (entidad) junto a la interfaz IAggregate en lugar de colocar un marcador de atributo de agregado por encima de la clase.</span><span class="sxs-lookup"><span data-stu-id="331a4-140">An attribute could be the other choice for the marker, but it is quicker to see the base class (Entity) next to the IAggregate interface instead of putting an Aggregate attribute marker above the class.</span></span> <span data-ttu-id="331a4-141">Es un metter de preferencias, en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="331a4-141">It is a metter of preferences, in any case.</span></span>

<span data-ttu-id="331a4-142">Tener un medio de raíz agregada que relacionados con la mayoría del código para mejorar la coherencia y reglas de negocios de entidades del agregado deben implementarse como métodos en la clase raíz agregada (por ejemplo, AddOrderItem al agregar un objeto OrderItem al agregado) .</span><span class="sxs-lookup"><span data-stu-id="331a4-142">Having an aggregate root means that most of the code related to consistency and business rules of the aggregate’s entities should be implemented as methods in the Order aggregate root class (for example, AddOrderItem when adding an OrderItem object to the aggregate).</span></span> <span data-ttu-id="331a4-143">No debe crear o actualizar los objetos de OrderItems independientemente o directamente; la clase AggregateRoot debe mantener control y la coherencia de cualquier operación de actualización con sus entidades secundarias.</span><span class="sxs-lookup"><span data-stu-id="331a4-143">You should not create or update OrderItems objects independently or directly; the AggregateRoot class must keep control and consistency of any update operation against its child entities.</span></span>

<span data-ttu-id="331a4-144">Por ejemplo, debería *no* realice las siguientes acciones de cualquier clase de capa de aplicación o el método de controlador de comando:</span><span class="sxs-lookup"><span data-stu-id="331a4-144">For example, you should *not* do the following from any command handler method or application layer class:</span></span>

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

<span data-ttu-id="331a4-145">En este caso, el método Add es puramente una operación para agregar datos, con acceso directo a la colección OrderItems.</span><span class="sxs-lookup"><span data-stu-id="331a4-145">In this case, the Add method is purely an operation to add data, with direct access to the OrderItems collection.</span></span> <span data-ttu-id="331a4-146">Por lo tanto, la mayoría de la lógica del dominio, reglas o validaciones relacionadas con que la operación con las entidades secundarias se distribuirán a través de la capa de aplicación (controladores de comandos y controladores de API Web).</span><span class="sxs-lookup"><span data-stu-id="331a4-146">Therefore, most of the domain logic, rules, or validations related to that operation with the child entities will be spread across the application layer (command handlers and Web API controllers).</span></span>

<span data-ttu-id="331a4-147">Si dejan alrededor de la raíz agregada, la raíz agregada no puede garantizar sus invariables, su validez o su coherencia.</span><span class="sxs-lookup"><span data-stu-id="331a4-147">If you go around the aggregate root, the aggregate root cannot guarantee its invariants, its validity, or its consistency.</span></span> <span data-ttu-id="331a4-148">Finalmente tendrá spaghetti código o script transaccional.</span><span class="sxs-lookup"><span data-stu-id="331a4-148">Eventually you will have spaghetti code or transactional script code.</span></span>

<span data-ttu-id="331a4-149">Para seguir patrones DDD, las entidades no deben tener establecedores públicos en cualquier propiedad de entidad.</span><span class="sxs-lookup"><span data-stu-id="331a4-149">To follow DDD patterns, entities must not have public setters in any entity property.</span></span> <span data-ttu-id="331a4-150">Cambios en una entidad deben determinarse mediante métodos explícitos con lenguaje ubicuo explícitas acerca del cambio que se están realizando en la entidad.</span><span class="sxs-lookup"><span data-stu-id="331a4-150">Changes in an entity should be driven by explicit methods with explicit ubiquitous language about the change they are performing in the entity.</span></span>

<span data-ttu-id="331a4-151">Además, las colecciones dentro de la entidad (por ejemplo, los artículos del pedido) deben ser propiedades de solo lectura (el método AsReadOnly explicará más adelante).</span><span class="sxs-lookup"><span data-stu-id="331a4-151">Furthermore, collections within the entity (like the order items) should be read-only properties (the AsReadOnly method explained later).</span></span> <span data-ttu-id="331a4-152">Debe ser capaz de actualizar solo desde dentro de los métodos de la clase raíz agregada o los métodos de la entidad secundaria.</span><span class="sxs-lookup"><span data-stu-id="331a4-152">You should be able to update it only from within the aggregate root class methods or the child entity methods.</span></span>

<span data-ttu-id="331a4-153">Como puede ver en el código de la raíz agregado de orden, todos los establecedores deben ser privados o al menos de solo lectura externamente, por lo que cualquier operación con los datos de la entidad o sus entidades secundarias tiene que realizarse a través de métodos en la clase de entidad.</span><span class="sxs-lookup"><span data-stu-id="331a4-153">As you can see in the code for the Order aggregate root, all setters should be private or at least read-only externally, so that any operation against the entity’s data or its child entities has to be performed through methods in the entity class.</span></span> <span data-ttu-id="331a4-154">Esto mantiene la coherencia de una manera controlada y orientada a objetos en lugar de implementar el código de la secuencia de comandos transaccional.</span><span class="sxs-lookup"><span data-stu-id="331a4-154">This maintains consistency in a controlled and object-oriented way instead of implementing transactional script code.</span></span>

<span data-ttu-id="331a4-155">El fragmento de código siguiente muestra la manera adecuada de la tarea de agregar un objeto OrderItem para el agregado de orden de código.</span><span class="sxs-lookup"><span data-stu-id="331a4-155">The following code snippet shows the proper way to code the task of adding an OrderItem object to the Order aggregate.</span></span>

```csharp
// RIGHT ACCORDING TO DDD--CODE AT THE APPLICATION LAYER OR COMMAND HANDLERS
// The code in command handlers or WebAPI controllers, related only to application stuff
// There is NO code here related to OrderItem object’s business logic
myOrder.AddOrderItem(productId, productName, pictureUrl, unitPrice, discount, units);

// The code related to OrderItem params validations or domain rules should
// be WITHIN the AddOrderItem method.

//...
```

<span data-ttu-id="331a4-156">En este fragmento de código, la mayoría de las validaciones o la lógica relacionada con la creación de un objeto OrderItem será bajo el control de la raíz agregado de orden, en el método AddOrderItem, especialmente las validaciones y lógica relacionados con otros elementos en conjunto.</span><span class="sxs-lookup"><span data-stu-id="331a4-156">In this snippet, most of the validations or logic related to the creation of an OrderItem object will be under the control of the Order aggregate root—in the AddOrderItem method—especially validations and logic related to other elements in the aggregate.</span></span> <span data-ttu-id="331a4-157">Por ejemplo, podría obtener el mismo elemento de producto como el resultado de varias llamadas a AddOrderItem.</span><span class="sxs-lookup"><span data-stu-id="331a4-157">For instance, you might get the same product item as the result of multiple calls to AddOrderItem.</span></span> <span data-ttu-id="331a4-158">En ese método, puede examinar los elementos de producto y consolidar los mismos elementos de producto en un único objeto OrderItem con varias unidades.</span><span class="sxs-lookup"><span data-stu-id="331a4-158">In that method, you could examine the product items and consolidate the same product items into a single OrderItem object with several units.</span></span> <span data-ttu-id="331a4-159">Además, si hay cantidades de descuento distinto, pero el identificador de producto es el mismo, es probable que se aplicará el mayor descuento.</span><span class="sxs-lookup"><span data-stu-id="331a4-159">Additionally, if there are different discount amounts but the product ID is the same, you would likely apply the higher discount.</span></span> <span data-ttu-id="331a4-160">Este principio se aplica a cualquier otra lógica de dominio para el objeto OrderItem.</span><span class="sxs-lookup"><span data-stu-id="331a4-160">This principle applies to any other domain logic for the OrderItem object.</span></span>

<span data-ttu-id="331a4-161">Además, la nueva operación OrderItem(params) también se controlan y realizada por el método AddOrderItem desde la raíz agregado de orden.</span><span class="sxs-lookup"><span data-stu-id="331a4-161">In addition, the new OrderItem(params) operation will also be controlled and performed by the AddOrderItem method from the Order aggregate root.</span></span> <span data-ttu-id="331a4-162">Por lo tanto, la mayoría de la lógica o validaciones relacionadas con que operación (especialmente todo lo que afecta a la coherencia entre otras entidades secundarias) estarán en un único lugar dentro de la raíz agregado.</span><span class="sxs-lookup"><span data-stu-id="331a4-162">Therefore, most of the logic or validations related to that operation (especially anything that impacts the consistency between other child entities) will be in a single place within the aggregate root.</span></span> <span data-ttu-id="331a4-163">Es el objetivo final del patrón raíz agregada.</span><span class="sxs-lookup"><span data-stu-id="331a4-163">That is the ultimate purpose of the aggregate root pattern.</span></span>

<span data-ttu-id="331a4-164">Cuando se usa Entity Framework 1.1, se puede expresar mejor una entidad DDD porque una de las nuevas características de Entity Framework Core 1.1 es que permite [asignar a campos](https://docs.microsoft.com/ef/core/modeling/backing-field) además de propiedades.</span><span class="sxs-lookup"><span data-stu-id="331a4-164">When you use Entity Framework 1.1, a DDD entity can be better expressed because one of the new features of Entity Framework Core 1.1 is that it allows [mapping to fields](https://docs.microsoft.com/ef/core/modeling/backing-field) in addition to properties.</span></span> <span data-ttu-id="331a4-165">Esto es útil cuando se protegen las colecciones de las entidades secundarias u objetos de valor.</span><span class="sxs-lookup"><span data-stu-id="331a4-165">This is useful when protecting collections of child entities or value objects.</span></span> <span data-ttu-id="331a4-166">Con esta mejora, puede usar los campos privados simples en lugar de propiedades y puede implementar las actualizaciones en la colección de campos en los métodos públicos y proporcionar acceso de solo lectura a través del método AsReadOnly.</span><span class="sxs-lookup"><span data-stu-id="331a4-166">With this enhancement, you can use simple private fields instead of properties and you can implement any update to the field collection in public methods and provide read-only access through the AsReadOnly method.</span></span>

<span data-ttu-id="331a4-167">En el DDD que desea actualizar la entidad sólo a través de métodos en la entidad (o el constructor) con el fin de controlar cualquier invariable y la coherencia de los datos, por lo que propiedades se definen únicamente con un descriptor de acceso get.</span><span class="sxs-lookup"><span data-stu-id="331a4-167">In DDD you want to update the entity only through methods in the entity (or the constructor) in order to control any invariant and the consistency of the data, so properties are defined only with a get accessor.</span></span> <span data-ttu-id="331a4-168">Las propiedades se basan en campos privados.</span><span class="sxs-lookup"><span data-stu-id="331a4-168">The properties are backed by private fields.</span></span> <span data-ttu-id="331a4-169">Los miembros privados sólo puede tener acceso desde dentro de la clase.</span><span class="sxs-lookup"><span data-stu-id="331a4-169">Private members can only be accessed from within the class.</span></span> <span data-ttu-id="331a4-170">Sin embargo, excepción de allí uno: Core EF necesita establecer estos campos también.</span><span class="sxs-lookup"><span data-stu-id="331a4-170">However, there one exception: EF Core needs to set these fields as well.</span></span>

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

### <a name="mapping-properties-with-only-get-accessors-to-the-fields-in-the-database-table"></a><span data-ttu-id="331a4-171">Obtención de propiedades de asignación con solo los descriptores de acceso a los campos en la tabla de base de datos</span><span class="sxs-lookup"><span data-stu-id="331a4-171">Mapping properties with only get accessors to the fields in the database table</span></span>

<span data-ttu-id="331a4-172">Asignar propiedades a las columnas de tabla de base de datos no es responsabilidad de un dominio, pero como parte de la capa de infraestructura y persistencia.</span><span class="sxs-lookup"><span data-stu-id="331a4-172">Mapping properties to the database table columns is not a domain responsibility, but part of the infrastructure and persistence layer.</span></span> <span data-ttu-id="331a4-173">Mencionamos esta aquí solo por lo que es consciente de las nuevas capacidades de 1.1 EF relacionados con cómo puede modelar las entidades.</span><span class="sxs-lookup"><span data-stu-id="331a4-173">We mention this here just so you are aware of the new capabilities in EF 1.1 related to how you can model entities.</span></span> <span data-ttu-id="331a4-174">Obtener más detalles sobre este tema se explican en la sección infraestructura y persistencia.</span><span class="sxs-lookup"><span data-stu-id="331a4-174">Additional details on this topic are explained in the infrastructure and persistence section.</span></span>

<span data-ttu-id="331a4-175">Cuando usas EF 1.0, dentro de DbContext debe asignar las propiedades que se definen únicamente con captadores a los campos en la tabla de base de datos reales.</span><span class="sxs-lookup"><span data-stu-id="331a4-175">When you use EF 1.0, within the DbContext you need to map the properties that are defined only with getters to the actual fields in the database table.</span></span> <span data-ttu-id="331a4-176">Esto se realiza con el método HasField de la clase PropertyBuilder.</span><span class="sxs-lookup"><span data-stu-id="331a4-176">This is done with the HasField method of the PropertyBuilder class.</span></span>

### <a name="mapping-fields-without-properties"></a><span data-ttu-id="331a4-177">Asignación de campos sin propiedades</span><span class="sxs-lookup"><span data-stu-id="331a4-177">Mapping fields without properties</span></span>

<span data-ttu-id="331a4-178">Con la nueva característica de EF Core 1.1 para asignar columnas a campos, también es posible no utilizar propiedades.</span><span class="sxs-lookup"><span data-stu-id="331a4-178">With the new feature in EF Core 1.1 to map columns to fields, it is also possible to not use properties.</span></span> <span data-ttu-id="331a4-179">En su lugar, solo puede asignar columnas de una tabla a campos.</span><span class="sxs-lookup"><span data-stu-id="331a4-179">Instead, you can just map columns from a table to fields.</span></span> <span data-ttu-id="331a4-180">Un caso de uso común para esto es campos privados de un estado interno que no es necesario tener acceso desde fuera de la entidad.</span><span class="sxs-lookup"><span data-stu-id="331a4-180">A common use case for this is private fields for an internal state that does not need to be accessed from outside the entity.</span></span>

<span data-ttu-id="331a4-181">Por ejemplo, en el ejemplo de código anterior, el \_someOrderInternalState campo no tiene ninguna propiedad relacionada de un establecedor o captador.</span><span class="sxs-lookup"><span data-stu-id="331a4-181">For example, in the preceding code example, the \_someOrderInternalState field has no related property for either a setter or getter.</span></span> <span data-ttu-id="331a4-182">Ese campo también se calculan dentro de la lógica de negocios de la orden y se usa uno de los métodos de la orden, pero debe conservarse en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="331a4-182">That field will also be calculated within the order’s business logic and used from the order’s methods, but it needs to be persisted in the database as well.</span></span> <span data-ttu-id="331a4-183">Por lo tanto, en EF 1.1 es una manera de asignar un campo sin una propiedad relacionada a una columna de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="331a4-183">So, in EF 1.1 there is a way to map a field without a related property to a column in the database.</span></span> <span data-ttu-id="331a4-184">Esto también se explica en la [nivel de infraestructura](#the-infrastructure-layer) sección de esta guía.</span><span class="sxs-lookup"><span data-stu-id="331a4-184">This is also explained in the [Infrastructure layer](#the-infrastructure-layer) section of this guide.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="331a4-185">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="331a4-185">Additional resources</span></span>

-   <span data-ttu-id="331a4-186">**Vaughn Vernon. Modelado agregados con DDD y Entity Framework.**</span><span class="sxs-lookup"><span data-stu-id="331a4-186">**Vaughn Vernon. Modeling Aggregates with DDD and Entity Framework.**</span></span> <span data-ttu-id="331a4-187">Tenga en cuenta que esto es *no* Entity Framework Core.</span><span class="sxs-lookup"><span data-stu-id="331a4-187">Note that this is *not* Entity Framework Core.</span></span>
    [<span data-ttu-id="331a4-188">*https://vaughnvernon.co/?p=879*</span><span class="sxs-lookup"><span data-stu-id="331a4-188">*https://vaughnvernon.co/?p=879*</span></span>](https://vaughnvernon.co/?p=879)

-   <span data-ttu-id="331a4-189">**Julia Lerman. Codificación de diseño basado en dominio: sugerencias para desarrolladores centradas en datos**
    [*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span><span class="sxs-lookup"><span data-stu-id="331a4-189">**Julie Lerman. Coding for Domain-Driven Design: Tips for Data-Focused Devs**
[*https://msdn.microsoft.com/en-us/magazine/dn342868.aspx*](https://msdn.microsoft.com/en-us/magazine/dn342868.aspx)</span></span>

-   <span data-ttu-id="331a4-190">**UDI Dahan. Cómo crear totalmente encapsula modelos de dominio**
    [*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span><span class="sxs-lookup"><span data-stu-id="331a4-190">**Udi Dahan. How to create fully encapsulated Domain Models**
[*http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/*](http://udidahan.com/2008/02/29/how-to-create-fully-encapsulated-domain-models/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="331a4-191">[Anterior] (microservicio-dominio-model.md) [siguiente] (seedwork-domain-model-base-classes-interfaces.md)</span><span class="sxs-lookup"><span data-stu-id="331a4-191">[Previous] (microservice-domain-model.md) [Next] (seedwork-domain-model-base-classes-interfaces.md)</span></span>
