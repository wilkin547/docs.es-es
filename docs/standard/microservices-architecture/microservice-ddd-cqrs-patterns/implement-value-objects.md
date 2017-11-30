---
title: Implementar objetos de valor
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementar objetos de valor
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c20bc80d2ddb864a3a0172beb211974426a278a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-value-objects"></a><span data-ttu-id="fd7f5-104">Implementar objetos de valor</span><span class="sxs-lookup"><span data-stu-id="fd7f5-104">Implementing value objects</span></span>

<span data-ttu-id="fd7f5-105">Como se describe en las secciones anteriores sobre las entidades y agregados, identidad es fundamental para las entidades.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-105">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="fd7f5-106">Sin embargo, hay muchos objetos y elementos de datos en un sistema que no requieren una identidad y realizar el seguimiento, como los objetos de valor.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-106">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="fd7f5-107">Un objeto de valor puede hacer referencia a otras entidades.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-107">A value object can reference other entities.</span></span> <span data-ttu-id="fd7f5-108">Por ejemplo, en una aplicación que genera una ruta que describe cómo obtener desde un punto a otro, esa ruta sería un objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-108">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="fd7f5-109">Sería una instantánea de los puntos en una ruta específica, pero esta ruta sugerida no tendría una identidad, aunque internamente podrían hacer referencia a entidades como ciudad, Road, etcetera.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-109">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="fd7f5-110">Figura 9-13 muestra el objeto de valor de dirección en el agregado de orden.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-110">Figure 9-13 shows the Address value object within the Order aggregate.</span></span>

![](./media/image14.png)

<span data-ttu-id="fd7f5-111">**Figura 9-13**.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-111">**Figure 9-13**.</span></span> <span data-ttu-id="fd7f5-112">Objeto de valor en el agregado de orden de direcciones</span><span class="sxs-lookup"><span data-stu-id="fd7f5-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="fd7f5-113">Como se muestra en la figura 9-13, una entidad normalmente se compone de varios atributos.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-113">As shown in Figure 9-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="fd7f5-114">Por ejemplo, orden se puede modelar como una entidad con una identidad e internamente formada por un conjunto de atributos como OrderId, OrderDate, OrderItems, etcetera. Pero la dirección, que es simplemente un valor complejo que compone de país, calle, ciudad, etc. deben modelar y se trata como un objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-114">For example, Order can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex value composed of country, street, city, etc. must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="fd7f5-115">Características importantes de los objetos de valor</span><span class="sxs-lookup"><span data-stu-id="fd7f5-115">Important characteristics of value objects</span></span>

<span data-ttu-id="fd7f5-116">Hay dos características principales para los objetos de valor:</span><span class="sxs-lookup"><span data-stu-id="fd7f5-116">There are two main characteristics for value objects:</span></span>

-   <span data-ttu-id="fd7f5-117">No tienen que no hay ninguna identidad.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-117">They have no identity.</span></span>

-   <span data-ttu-id="fd7f5-118">Únicamente son inmutables.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-118">They are immutable.</span></span>

<span data-ttu-id="fd7f5-119">La primera característica ya se ha mencionado.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="fd7f5-120">Inmutabilidad es un requisito importante.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-120">Immutability is an important requirement.</span></span> <span data-ttu-id="fd7f5-121">Los valores de un objeto de valor deben ser inmutables una vez creado el objeto.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="fd7f5-122">Por lo tanto, cuando se construye el objeto, debe proporcionar los valores necesarios, pero no debe permitir que cambie durante la duración del objeto.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="fd7f5-123">Objetos de valor permiten realizar algunos trucos para el rendimiento, gracias a su naturaleza inmutable.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="fd7f5-124">Esto es especialmente cierto en sistemas donde pueden haber miles de valor instancias de objetos, muchos de los cuales tienen los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="fd7f5-125">Su naturaleza inmutable les permite reutilizar; pueden ser objetos intercambiables, ya que sus valores son los mismos y no tienen ninguna identidad.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="fd7f5-126">Este tipo de optimización a veces puede suponer una diferencia entre el software que se ejecuta con lentitud y el software con un buen rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="fd7f5-127">Por supuesto, todos estos casos dependen el entorno de aplicación y el contexto de la implementación.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="fd7f5-128">Implementación de objeto de valor en C\#</span><span class="sxs-lookup"><span data-stu-id="fd7f5-128">Value object implementation in C\#</span></span>

<span data-ttu-id="fd7f5-129">En cuanto a implementación, puede tener una clase base de objeto de valor que tiene métodos de utilidad básica como igualdad en función de comparación entre todos los atributos (ya que un objeto de valor no debe basarse en la identidad) y otras características fundamentales.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="fd7f5-130">En el ejemplo siguiente se muestra una clase base de objeto de valor usada en la ordenación microservicio desde eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

```csharp
public abstract class ValueObject
{
    protected static bool EqualOperator(ValueObject left, ValueObject right)
    {
        if (ReferenceEquals(left, null) ^ ReferenceEquals(right, null))
        {
            return false;
        }
        return ReferenceEquals(left, null) || left.Equals(right);
    }

    protected static bool NotEqualOperator(ValueObject left, ValueObject right)
    {
        return !(EqualOperator(left, right));
    }

    protected abstract IEnumerable<object> GetAtomicValues();

    public override bool Equals(object obj)
    {
        if (obj == null || obj.GetType() != GetType())
        {
            return false;
        }

        ValueObject other = (ValueObject)obj;
        IEnumerator<object> thisValues = GetAtomicValues().GetEnumerator();
        IEnumerator<object> otherValues = other.GetAtomicValues().GetEnumerator();
        while (thisValues.MoveNext() && otherValues.MoveNext())
        {
            if (ReferenceEquals(thisValues.Current, null) ^
                ReferenceEquals(otherValues.Current, null))
            {
                return false;
            }

            if (thisValues.Current != null &&
                !thisValues.Current.Equals(otherValues.Current))
            {
                return false;
            }
        }
        return !thisValues.MoveNext() && !otherValues.MoveNext();
    }
    // Other utilility methods
}
```

<span data-ttu-id="fd7f5-131">Puede usar esta clase cuando implementa el objeto de valor real, al igual que con el objeto de valor de dirección que se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fd7f5-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    public Address(string street, string city, string state,
        string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a><span data-ttu-id="fd7f5-132">Ocultar la característica de identidad al usar EF Core conservar objetos de valor</span><span class="sxs-lookup"><span data-stu-id="fd7f5-132">Hiding the identity characteristic when using EF Core to persist value objects</span></span>

<span data-ttu-id="fd7f5-133">Una limitación cuando se utiliza EF principal es que en su versión actual (EF Core 1.1) no se puede utilizar [tipos complejos](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) tal como se define en EF 6.x.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-133">A limitation when using EF Core is that in its current version (EF Core 1.1) you cannot use [complex types](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) as defined in EF 6.x.</span></span> <span data-ttu-id="fd7f5-134">Por lo tanto, debe almacenar el objeto de valor como una entidad EF.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-134">Therefore, you must store your value object as an EF entity.</span></span> <span data-ttu-id="fd7f5-135">Sin embargo, puede ocultar su ID por lo que hacer claro que no es importante en el modelo que el objeto de valor forma parte de la identidad.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-135">However, you can hide its ID so you make clear that the identity is not important in the model that the value object is part of.</span></span> <span data-ttu-id="fd7f5-136">Ocultar el identificador está utilizando el identificador como una propiedad de instantáneas.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-136">You hide the ID is by using the ID as a shadow property.</span></span> <span data-ttu-id="fd7f5-137">Puesto que esa configuración para ocultar el identificador en el modelo se configura en el nivel de infraestructura, será transparente para el modelo de dominio y su implementación de infraestructura podría cambiar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-137">Since that configuration for hiding the ID in the model is set up in the infrastructure level, it will be transparent for your domain model, and its infrastructure implementation could change in the future.</span></span>

<span data-ttu-id="fd7f5-138">En eShopOnContainers, el identificador oculto sea necesario mediante la infraestructura básica de EF se implementa de la manera siguiente en el nivel de DbContext, mediante la API fluida en el proyecto de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-138">In eShopOnContainers, the hidden ID needed by EF Core infrastructure is implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span>

```csharp
// Fluent API within the OrderingContext:DbContext in the
// Ordering.Infrastructure project

void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);
    addressConfiguration.Property<int>("Id").IsRequired();
    addressConfiguration.HasKey("Id");
}
```

<span data-ttu-id="fd7f5-139">Por lo tanto, el identificador está oculta para el punto de vista de dominio modelo y en el futuro, la infraestructura de objeto de valor también puede implementarse como un tipo complejo o de otra manera.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-139">Therefore, the ID is hidden from the domain model point of view, and in the future, the value object infrastructure could also be implemented as a complex type or another way.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fd7f5-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fd7f5-140">Additional resources</span></span>

-   <span data-ttu-id="fd7f5-141">**Martin Fowler. Patrón de ValueObject**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span><span class="sxs-lookup"><span data-stu-id="fd7f5-141">**Martin Fowler. ValueObject pattern**
[*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)</span></span>

-   <span data-ttu-id="fd7f5-142">**Eric Evans. Diseño basado en dominio: Realiza para complejidad en el centro de Software.**</span><span class="sxs-lookup"><span data-stu-id="fd7f5-142">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="fd7f5-143">(Libro; incluye una explicación de los objetos de valor) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="fd7f5-143">(Book; includes a discussion of value objects) [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="fd7f5-144">**Vaughn Vernon. Implementar el diseño basado en dominio.**</span><span class="sxs-lookup"><span data-stu-id="fd7f5-144">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="fd7f5-145">(Libro; incluye una explicación de los objetos de valor) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="fd7f5-145">(Book; includes a discussion of value objects) [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="fd7f5-146">**Ocultar propiedades**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span><span class="sxs-lookup"><span data-stu-id="fd7f5-146">**Shadow Properties**
[*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)</span></span>

-   <span data-ttu-id="fd7f5-147">**Tipos complejos u objetos de valor**.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-147">**Complex types and/or value objects**.</span></span> <span data-ttu-id="fd7f5-148">Explicación en el repositorio de GitHub de núcleo de EF (pestaña de problemas) [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span><span class="sxs-lookup"><span data-stu-id="fd7f5-148">Discussion in the EF Core GitHub repo (Issues tab) [*https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)</span></span>

-   <span data-ttu-id="fd7f5-149">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="fd7f5-149">**ValueObject.cs.**</span></span> <span data-ttu-id="fd7f5-150">Clase de objeto de valor base en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-150">Base value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="fd7f5-151">*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span><span class="sxs-lookup"><span data-stu-id="fd7f5-151">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   <span data-ttu-id="fd7f5-152">**Clase de direcciones.**</span><span class="sxs-lookup"><span data-stu-id="fd7f5-152">**Address class.**</span></span> <span data-ttu-id="fd7f5-153">Clase de objeto de valor de ejemplo de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="fd7f5-153">Sample value object class in eShopOnContainers.</span></span>
    [<span data-ttu-id="fd7f5-154">*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span><span class="sxs-lookup"><span data-stu-id="fd7f5-154">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
<span data-ttu-id="fd7f5-155">[Anterior] (seedwork-domain-model-base-classes-interfaces.md) [siguiente] (enumeración-clases-over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="fd7f5-155">[Previous] (seedwork-domain-model-base-classes-interfaces.md) [Next] (enumeration-classes-over-enum-types.md)</span></span>
