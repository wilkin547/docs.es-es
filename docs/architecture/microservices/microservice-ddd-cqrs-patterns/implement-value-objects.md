---
title: Implementar objetos de valor
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Obtenga los detalles y las opciones para implementar objetos de valor mediante las características nuevas de Entity Framework.
ms.date: 10/08/2018
ms.openlocfilehash: 70c92fe86fda20ed4e909b945b843e8e71092f09
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899774"
---
# <a name="implement-value-objects"></a><span data-ttu-id="914c1-103">Implementación de objetos de valor</span><span class="sxs-lookup"><span data-stu-id="914c1-103">Implement value objects</span></span>

<span data-ttu-id="914c1-104">Como se describe en secciones anteriores sobre las entidades y agregados, la identidad es esencial para las entidades,</span><span class="sxs-lookup"><span data-stu-id="914c1-104">As discussed in earlier sections about entities and aggregates, identity is fundamental for entities.</span></span> <span data-ttu-id="914c1-105">pero hay muchos objetos y elementos de datos en un sistema que no requieren ninguna identidad ni ningún seguimiento de identidad, como los objetos de valor.</span><span class="sxs-lookup"><span data-stu-id="914c1-105">However, there are many objects and data items in a system that do not require an identity and identity tracking, such as value objects.</span></span>

<span data-ttu-id="914c1-106">Un objeto de valor puede hacer referencia a otras entidades.</span><span class="sxs-lookup"><span data-stu-id="914c1-106">A value object can reference other entities.</span></span> <span data-ttu-id="914c1-107">Por ejemplo, en una aplicación que genera una ruta que describe cómo ir de un punto a otro, esa ruta sería un objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="914c1-107">For example, in an application that generates a route that describes how to get from one point to another, that route would be a value object.</span></span> <span data-ttu-id="914c1-108">Sería una instantánea de puntos en una ruta específica, pero esta ruta sugerida no tendría una identidad, aunque internamente podría hacer referencia a entidades como Ciudad, Carretera, etc.</span><span class="sxs-lookup"><span data-stu-id="914c1-108">It would be a snapshot of points on a specific route, but this suggested route would not have an identity, even though internally it might refer to entities like City, Road, etc.</span></span>

<span data-ttu-id="914c1-109">En la figura 7-13 se muestra el objeto de valor Address en el agregado Order.</span><span class="sxs-lookup"><span data-stu-id="914c1-109">Figure 7-13 shows the Address value object within the Order aggregate.</span></span>

![Diagrama que muestra el objeto de valor Address dentro del agregado Order.](./media/implement-value-objects/value-object-within-aggregate.png)

<span data-ttu-id="914c1-111">**Figura 7-13**.</span><span class="sxs-lookup"><span data-stu-id="914c1-111">**Figure 7-13**.</span></span> <span data-ttu-id="914c1-112">Objeto de valor Dirección en el agregado Pedido</span><span class="sxs-lookup"><span data-stu-id="914c1-112">Address value object within the Order aggregate</span></span>

<span data-ttu-id="914c1-113">Como se muestra en la figura 7-13, una entidad suele constar de varios atributos.</span><span class="sxs-lookup"><span data-stu-id="914c1-113">As shown in Figure 7-13, an entity is usually composed of multiple attributes.</span></span> <span data-ttu-id="914c1-114">Por ejemplo, la entidad `Order` se puede modelar como una entidad con una identidad y puede estar formada internamente por un conjunto de atributos, como OrderId, OrderDate, OrderItems, etc. Pero la dirección, que es un valor complejo formado por el país o región, la calle, la ciudad, etc., y que no tiene ninguna identidad en este dominio, se debe modelar y tratar como un objeto de valor.</span><span class="sxs-lookup"><span data-stu-id="914c1-114">For example, the `Order` entity can be modeled as an entity with an identity and composed internally of a set of attributes such as OrderId, OrderDate, OrderItems, etc. But the address, which is simply a complex-value composed of country/region, street, city, etc. and has no identity in this domain, must be modeled and treated as a value object.</span></span>

## <a name="important-characteristics-of-value-objects"></a><span data-ttu-id="914c1-115">Características importantes de los objetos de valor</span><span class="sxs-lookup"><span data-stu-id="914c1-115">Important characteristics of value objects</span></span>

<span data-ttu-id="914c1-116">Hay dos características principales en los objetos de valor:</span><span class="sxs-lookup"><span data-stu-id="914c1-116">There are two main characteristics for value objects:</span></span>

- <span data-ttu-id="914c1-117">No tienen ninguna identidad.</span><span class="sxs-lookup"><span data-stu-id="914c1-117">They have no identity.</span></span>

- <span data-ttu-id="914c1-118">Son inmutables.</span><span class="sxs-lookup"><span data-stu-id="914c1-118">They are immutable.</span></span>

<span data-ttu-id="914c1-119">La primera característica ya se ha mencionado.</span><span class="sxs-lookup"><span data-stu-id="914c1-119">The first characteristic was already discussed.</span></span> <span data-ttu-id="914c1-120">La inmutabilidad es un requisito importante.</span><span class="sxs-lookup"><span data-stu-id="914c1-120">Immutability is an important requirement.</span></span> <span data-ttu-id="914c1-121">Los valores de un objeto de valor deben ser inmutables una vez creado el objeto.</span><span class="sxs-lookup"><span data-stu-id="914c1-121">The values of a value object must be immutable once the object is created.</span></span> <span data-ttu-id="914c1-122">Por lo tanto, cuando se construye el objeto, debe proporcionar los valores necesarios, pero no debe permitir que cambien durante la vigencia del objeto.</span><span class="sxs-lookup"><span data-stu-id="914c1-122">Therefore, when the object is constructed, you must provide the required values, but you must not allow them to change during the object’s lifetime.</span></span>

<span data-ttu-id="914c1-123">Los objetos de valor le permiten hacer algunos trucos de rendimiento gracias a su naturaleza inmutable.</span><span class="sxs-lookup"><span data-stu-id="914c1-123">Value objects allow you to perform certain tricks for performance, thanks to their immutable nature.</span></span> <span data-ttu-id="914c1-124">Esto es así sobre todo en los sistemas en los que puede haber miles de instancias de objetos de valor, muchas de las cuales tienen los mismos valores.</span><span class="sxs-lookup"><span data-stu-id="914c1-124">This is especially true in systems where there may be thousands of value object instances, many of which have the same values.</span></span> <span data-ttu-id="914c1-125">Su naturaleza inmutable permite que se puedan reutilizar y pueden ser objetos intercambiables, ya que sus valores son los mismos y no tienen ninguna identidad.</span><span class="sxs-lookup"><span data-stu-id="914c1-125">Their immutable nature allows them to be reused; they can be interchangeable objects, since their values are the same and they have no identity.</span></span> <span data-ttu-id="914c1-126">Este tipo de optimización a veces puede suponer una diferencia entre el software que se ejecuta con lentitud y el software que tiene un buen rendimiento.</span><span class="sxs-lookup"><span data-stu-id="914c1-126">This type of optimization can sometimes make a difference between software that runs slowly and software with good performance.</span></span> <span data-ttu-id="914c1-127">Como es lógico, todos estos casos dependen el entorno de aplicación y del contexto de implementación.</span><span class="sxs-lookup"><span data-stu-id="914c1-127">Of course, all these cases depend on the application environment and deployment context.</span></span>

## <a name="value-object-implementation-in-c"></a><span data-ttu-id="914c1-128">Implementación de objetos de valor en C\#</span><span class="sxs-lookup"><span data-stu-id="914c1-128">Value object implementation in C\#</span></span>

<span data-ttu-id="914c1-129">En cuanto a la implementación, puede tener una clase base de objeto de valor que tenga métodos de utilidad básicos, como la igualdad según la comparación entre todos los atributos (ya que un objeto de valor no se debe basar en la identidad) y otras características esenciales.</span><span class="sxs-lookup"><span data-stu-id="914c1-129">In terms of implementation, you can have a value object base class that has basic utility methods like equality based on comparison between all the attributes (since a value object must not be based on identity) and other fundamental characteristics.</span></span> <span data-ttu-id="914c1-130">En el ejemplo siguiente se muestra una clase base de objeto de valor que se usa en el microservicio de ordenación de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="914c1-130">The following example shows a value object base class used in the ordering microservice from eShopOnContainers.</span></span>

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

    public override int GetHashCode()
    {
        return GetAtomicValues()
         .Select(x => x != null ? x.GetHashCode() : 0)
         .Aggregate((x, y) => x ^ y);
    }
    // Other utility methods
}
```

<span data-ttu-id="914c1-131">Puede usar esta clase al implementar el objeto de valor real, al igual que con el objeto de valor Address (Dirección) que se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="914c1-131">You can use this class when implementing your actual value object, as with the Address value object shown in the following example:</span></span>

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    private Address() { }

    public Address(string street, string city, string state, string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetAtomicValues()
    {
        // Using a yield return statement to return each element one at a time
        yield return Street;
        yield return City;
        yield return State;
        yield return Country;
        yield return ZipCode;
    }
}
```

<span data-ttu-id="914c1-132">Puede ver cómo esta implementación de objeto de valor de Address no tiene ninguna identidad y, por tanto, ningún campo de identificador, ni en la clase Address ni tampoco en la clase ValueObject.</span><span class="sxs-lookup"><span data-stu-id="914c1-132">You can see how this value object implementation of Address has no identity and therefore, no ID field, neither at the Address class not even at the ValueObject class.</span></span>

<span data-ttu-id="914c1-133">Hasta EF Core 2.0 no fue posible no tener ningún campo de identificador en una clase que se fuera a usar en Entity Framework, lo que ayuda a implementar mejor los objetos de valor sin identificador.</span><span class="sxs-lookup"><span data-stu-id="914c1-133">Having no ID field in a class to be used by Entity Framework was not possible until EF Core 2.0, which greatly helps to implement better value objects with no ID.</span></span> <span data-ttu-id="914c1-134">Eso es precisamente la explicación de la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="914c1-134">That is precisely the explanation of the next section.</span></span>

<span data-ttu-id="914c1-135">Se podría argumentar que los objetos de valor, al ser inmutables, deben ser de solo lectura (es decir, propiedades get-only), y realmente es cierto.</span><span class="sxs-lookup"><span data-stu-id="914c1-135">It could be argued that value objects, being immutable, should be read-only (i.e. get-only properties), and that’s indeed true.</span></span> <span data-ttu-id="914c1-136">Pero los objetos de valor normalmente se serializan y deserializan para recorrer colas de mensajes. Asimismo, si fueran de solo lectura, el deserializador no podría asignar los valores, por lo que simplemente se dejan como un conjunto privado, lo cual ofrece un nivel de solo lectura suficiente para que resulte práctico.</span><span class="sxs-lookup"><span data-stu-id="914c1-136">However, value objects are usually serialized and deserialized to go through message queues, and being read-only stops the deserializer from assigning values, so we just leave them as private set which is read-only enough to be practical.</span></span>

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20"></a><span data-ttu-id="914c1-137">Cómo conservar los objetos de valor en la base de datos con EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="914c1-137">How to persist value objects in the database with EF Core 2.0</span></span>

<span data-ttu-id="914c1-138">Acaba de ver cómo definir un objeto de valor en el modelo de dominio,</span><span class="sxs-lookup"><span data-stu-id="914c1-138">You just saw how to define a value object in your domain model.</span></span> <span data-ttu-id="914c1-139">pero ¿cómo puede conservarlo en la base de datos mediante Entity Framework (EF) Core, que suele tener como destino las entidades con identidad?</span><span class="sxs-lookup"><span data-stu-id="914c1-139">But, how can you actually persist it into the database through Entity Framework (EF) Core which usually targets entities with identity?</span></span>

### <a name="background-and-older-approaches-using-ef-core-11"></a><span data-ttu-id="914c1-140">Contexto y enfoques anteriores con EF Core 1.1</span><span class="sxs-lookup"><span data-stu-id="914c1-140">Background and older approaches using EF Core 1.1</span></span>

<span data-ttu-id="914c1-141">Como contexto, una limitación al usar EF Core 1.0 y 1.1 era que no se podían utilizar [tipos complejos](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) tal y como se definen en EF 6.x en .NET Framework tradicional.</span><span class="sxs-lookup"><span data-stu-id="914c1-141">As background, a limitation when using EF Core 1.0 and 1.1 was that you could not use [complex types](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) as defined in EF 6.x in the traditional .NET Framework.</span></span> <span data-ttu-id="914c1-142">Por lo tanto, si se usaba EF Core 1.0 o 1.1, era necesario almacenar el objeto de valor como una entidad de EF con un campo de identificador.</span><span class="sxs-lookup"><span data-stu-id="914c1-142">Therefore, if using EF Core 1.0 or 1.1, you needed to store your value object as an EF entity with an ID field.</span></span> <span data-ttu-id="914c1-143">Luego, para que se pareciera más a un objeto de valor sin ninguna identidad, se podía ocultar su identificador para dejar claro que la identidad de un objeto de valor no es importante en el modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="914c1-143">Then, so it looked more like a value object with no identity, you could hide its ID so you make clear that the identity of a value object is not important in the domain model.</span></span> <span data-ttu-id="914c1-144">Ese identificador se podía ocultar usándolo como [propiedad reemplazada](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span><span class="sxs-lookup"><span data-stu-id="914c1-144">You could hide that ID by using the ID as a [shadow property](https://docs.microsoft.com/ef/core/modeling/shadow-properties ).</span></span> <span data-ttu-id="914c1-145">Puesto que esa configuración para ocultar el identificador en el modelo está establecida en el nivel de la infraestructura de EF, resultaría algo transparente para su modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="914c1-145">Since that configuration for hiding the ID in the model is set up in the EF infrastructure level, it would be kind of transparent for your domain model.</span></span>

<span data-ttu-id="914c1-146">En la versión inicial de eShopOnContainers (.NET Core 1.1), el identificador oculto necesario para la infraestructura de EF Core estaba implementado del siguiente modo en el nivel de DbContext, usando la API fluida en el proyecto de la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="914c1-146">In the initial version of eShopOnContainers (.NET Core 1.1), the hidden ID needed by EF Core infrastructure was implemented in the following way in the DbContext level, using Fluent API at the infrastructure project.</span></span> <span data-ttu-id="914c1-147">Por lo tanto, el identificador quedaba oculto desde el punto de vista del modelo de dominio, pero seguía presente en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="914c1-147">Therefore, the ID was hidden from the domain model point of view, but still present in the infrastructure.</span></span>

```csharp
// Old approach with EF Core 1.1
// Fluent API within the OrderingContext:DbContext in the Infrastructure project
void ConfigureAddress(EntityTypeBuilder<Address> addressConfiguration)
{
    addressConfiguration.ToTable("address", DEFAULT_SCHEMA);

    addressConfiguration.Property<int>("Id")  // Id is a shadow property
        .IsRequired();
    addressConfiguration.HasKey("Id");   // Id is a shadow property
}
```

<span data-ttu-id="914c1-148">Pero la persistencia de ese objeto de valor en la base de datos se efectuaba como una entidad normal en otra tabla.</span><span class="sxs-lookup"><span data-stu-id="914c1-148">However, the persistence of that value object into the database was performed like a regular entity in a different table.</span></span>

<span data-ttu-id="914c1-149">Con EF Core 2.0 hay nuevos y mejores métodos para conservar los objetos de valor.</span><span class="sxs-lookup"><span data-stu-id="914c1-149">With EF Core 2.0, there are new and better ways to persist value objects.</span></span>

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20"></a><span data-ttu-id="914c1-150">Conservar objetos de valor como tipos entidad de propiedad en EF Core 2.0</span><span class="sxs-lookup"><span data-stu-id="914c1-150">Persist value objects as owned entity types in EF Core 2.0</span></span>

<span data-ttu-id="914c1-151">Aunque haya algunas lagunas entre el patrón de objeto de valor canónico en el DDD y el tipo de entidad de propiedad en EF Core, ahora mismo es la mejor manera de conservar objetos de valor con EF Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="914c1-151">Even with some gaps between the canonical value object pattern in DDD and the owned entity type in EF Core, it's currently the best way to persist value objects with EF Core 2.0.</span></span> <span data-ttu-id="914c1-152">Puede consultar las limitaciones al final de esta sección.</span><span class="sxs-lookup"><span data-stu-id="914c1-152">You can see limitations at the end of this section.</span></span>

<span data-ttu-id="914c1-153">La función del tipo de entidad de propiedad se agregó a EF Core a partir de la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="914c1-153">The owned entity type feature was added to EF Core since version 2.0.</span></span>

<span data-ttu-id="914c1-154">Un tipo de entidad de propiedad permite asignar tipos que no tienen su propia identidad definida de forma explícita en el modelo de dominio y que se usan como propiedades (como los objetos de valor) en cualquiera de las entidades.</span><span class="sxs-lookup"><span data-stu-id="914c1-154">An owned entity type allows you to map types that do not have their own identity explicitly defined in the domain model and are used as properties, such as a value object, within any of your entities.</span></span> <span data-ttu-id="914c1-155">Un tipo de entidad de propiedad comparte el mismo tipo CLR con otro tipo de entidad (es decir, solo es una clase convencional).</span><span class="sxs-lookup"><span data-stu-id="914c1-155">An owned entity type shares the same CLR type with another entity type (that is, it’s just a regular class).</span></span> <span data-ttu-id="914c1-156">La entidad que contiene la navegación definitoria es la entidad del propietario.</span><span class="sxs-lookup"><span data-stu-id="914c1-156">The entity containing the defining navigation is the owner entity.</span></span> <span data-ttu-id="914c1-157">Al consultar al propietario, los tipos de propiedad se incluyen de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="914c1-157">When querying the owner, the owned types are included by default.</span></span>

<span data-ttu-id="914c1-158">Si se examina el modelo de dominio, parece que los tipos de propiedad no tienen ninguna identidad</span><span class="sxs-lookup"><span data-stu-id="914c1-158">Just by looking at the domain model, an owned type looks like it doesn’t have any identity.</span></span> <span data-ttu-id="914c1-159">pero, en el fondo, los tipos de propiedad tienen identidad, aunque la propiedad de navegación del propietario forma parte de esta identidad.</span><span class="sxs-lookup"><span data-stu-id="914c1-159">However, under the covers, owned types do have identity, but the owner navigation property is part of this identity.</span></span>

<span data-ttu-id="914c1-160">La identidad de las instancias de los tipos de propiedad no es totalmente suya.</span><span class="sxs-lookup"><span data-stu-id="914c1-160">The identity of instances of owned types is not completely their own.</span></span> <span data-ttu-id="914c1-161">Consta de tres componentes:</span><span class="sxs-lookup"><span data-stu-id="914c1-161">It consists of three components:</span></span>

- <span data-ttu-id="914c1-162">La identidad del propietario</span><span class="sxs-lookup"><span data-stu-id="914c1-162">The identity of the owner</span></span>

- <span data-ttu-id="914c1-163">La propiedad de navegación que los señala</span><span class="sxs-lookup"><span data-stu-id="914c1-163">The navigation property pointing to them</span></span>

- <span data-ttu-id="914c1-164">En el caso de las colecciones de tipos de propiedad, un componente independiente (todavía no se admite en EF Core 2.0, se hará en la versión 2.2).</span><span class="sxs-lookup"><span data-stu-id="914c1-164">In the case of collections of owned types, an independent component (not yet supported in EF Core 2.0, coming up on 2.2).</span></span>

<span data-ttu-id="914c1-165">Por ejemplo, en el modelo de dominio Ordering de eShopOnContainers, como parte de la entidad Order, el objeto de valor Address se implementa como un tipo de entidad de propiedad dentro de la entidad del propietario, que es la entidad Order.</span><span class="sxs-lookup"><span data-stu-id="914c1-165">For example, in the Ordering domain model at eShopOnContainers, as part of the Order entity, the Address value object is implemented as an owned entity type within the owner entity, which is the Order entity.</span></span> <span data-ttu-id="914c1-166">Address es un tipo sin ninguna propiedad de identidad definida en el modelo de dominio.</span><span class="sxs-lookup"><span data-stu-id="914c1-166">Address is a type with no identity property defined in the domain model.</span></span> <span data-ttu-id="914c1-167">Se usa como propiedad del tipo Order para especificar la dirección de envío de un pedido en concreto.</span><span class="sxs-lookup"><span data-stu-id="914c1-167">It is used as a property of the Order type to specify the shipping address for a particular order.</span></span>

<span data-ttu-id="914c1-168">Por convención, se crea una clave principal paralela para el tipo de propiedad y se asignará a la misma tabla que el propietario mediante la división de tabla.</span><span class="sxs-lookup"><span data-stu-id="914c1-168">By convention, a shadow primary key is created for the owned type and it will be mapped to the same table as the owner by using table splitting.</span></span> <span data-ttu-id="914c1-169">Esto permite usar tipos de propiedad de forma similar al modo en que se usan los tipos complejos en EF6 en el .NET Framework tradicional.</span><span class="sxs-lookup"><span data-stu-id="914c1-169">This allows to use owned types similarly to how complex types are used in EF6 in the traditional .NET Framework.</span></span>

<span data-ttu-id="914c1-170">Es importante tener en cuenta que los tipos de propiedad nunca se detectan por convención en EF Core, por lo que se deben declarar explícitamente.</span><span class="sxs-lookup"><span data-stu-id="914c1-170">It is important to note that owned types are never discovered by convention in EF Core, so you have to declare them explicitly.</span></span>

<span data-ttu-id="914c1-171">En eShopOnContainers, en OrderingContext.cs, dentro del método OnModelCreating(), se aplican varias configuraciones de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="914c1-171">In eShopOnContainers, at the OrderingContext.cs, within the OnModelCreating() method, there are multiple infrastructure configuration being applied.</span></span> <span data-ttu-id="914c1-172">Una de ellas está relacionada con la entidad Order.</span><span class="sxs-lookup"><span data-stu-id="914c1-172">One of them is related to the Order entity.</span></span>

```csharp
// Part of the OrderingContext.cs class at the Ordering.Infrastructure project
//
protected override void OnModelCreating(ModelBuilder modelBuilder)
{
    modelBuilder.ApplyConfiguration(new ClientRequestEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new PaymentMethodEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderEntityTypeConfiguration());
    modelBuilder.ApplyConfiguration(new OrderItemEntityTypeConfiguration());
    //...Additional type configurations
}
```

<span data-ttu-id="914c1-173">En el código siguiente, la infraestructura de persistencia está definida para la entidad Order:</span><span class="sxs-lookup"><span data-stu-id="914c1-173">In the following code, the persistence infrastructure is defined for the Order entity:</span></span>

```csharp
// Part of the OrderEntityTypeConfiguration.cs class
//
public void Configure(EntityTypeBuilder<Order> orderConfiguration)
{
    orderConfiguration.ToTable("orders", OrderingContext.DEFAULT_SCHEMA);
    orderConfiguration.HasKey(o => o.Id);
    orderConfiguration.Ignore(b => b.DomainEvents);
    orderConfiguration.Property(o => o.Id)
        .ForSqlServerUseSequenceHiLo("orderseq", OrderingContext.DEFAULT_SCHEMA);

    //Address value object persisted as owned entity in EF Core 2.0
    orderConfiguration.OwnsOne(o => o.Address);

    orderConfiguration.Property<DateTime>("OrderDate").IsRequired();

    //...Additional validations, constraints and code...
    //...
}
```

<span data-ttu-id="914c1-174">En el código anterior, el método `orderConfiguration.OwnsOne(o => o.Address)` especifica que la propiedad `Address` es una entidad de propiedad del tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="914c1-174">In the previous code, the `orderConfiguration.OwnsOne(o => o.Address)` method specifies that the `Address` property is an owned entity of the `Order` type.</span></span>

<span data-ttu-id="914c1-175">De forma predeterminada, las convenciones de EF Core asignan a las columnas de base de datos de las propiedades del tipo de entidad de propiedad el nombre `EntityProperty_OwnedEntityProperty`.</span><span class="sxs-lookup"><span data-stu-id="914c1-175">By default, EF Core conventions name the database columns for the properties of the owned entity type as `EntityProperty_OwnedEntityProperty`.</span></span> <span data-ttu-id="914c1-176">Por lo tanto, las propiedades internas de `Address` aparecerán en la tabla `Orders` con los nombres `Address_Street` y `Address_City` (y así sucesivamente para `State`, `Country` y `ZipCode`).</span><span class="sxs-lookup"><span data-stu-id="914c1-176">Therefore, the internal properties of `Address` will appear in the `Orders` table with the names `Address_Street`, `Address_City` (and so on for `State`, `Country` and `ZipCode`).</span></span>

<span data-ttu-id="914c1-177">Puede anexar el método fluido `Property().HasColumnName()` para cambiar el nombre de esas columnas.</span><span class="sxs-lookup"><span data-stu-id="914c1-177">You can append the `Property().HasColumnName()` fluent method to rename those columns.</span></span> <span data-ttu-id="914c1-178">En el caso en que `Address` es una propiedad pública, las asignaciones serían similares a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="914c1-178">In the case where `Address` is a public property, the mappings would be like the following:</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

<span data-ttu-id="914c1-179">Se puede encadenar el método `OwnsOne` en una asignación fluida.</span><span class="sxs-lookup"><span data-stu-id="914c1-179">It is possible to chain the `OwnsOne` method in a fluent mapping.</span></span> <span data-ttu-id="914c1-180">En el siguiente ejemplo hipotético, `OrderDetails` posee `BillingAddress` y `ShippingAddress`, que son tipos `Address`.</span><span class="sxs-lookup"><span data-stu-id="914c1-180">In the following hypothetical example, `OrderDetails` owns `BillingAddress` and `ShippingAddress`, which are both `Address` types.</span></span> <span data-ttu-id="914c1-181">Luego, `OrderDetails` es propiedad del tipo `Order`.</span><span class="sxs-lookup"><span data-stu-id="914c1-181">Then `OrderDetails` is owned by the `Order` type.</span></span>

```csharp
orderConfiguration.OwnsOne(p => p.OrderDetails, cb =>
    {
        cb.OwnsOne(c => c.BillingAddress);
        cb.OwnsOne(c => c.ShippingAddress);
    });
//...
//...
public class Order
{
    public int Id { get; set; }
    public OrderDetails OrderDetails { get; set; }
}

public class OrderDetails
{
    public Address BillingAddress { get; set; }
    public Address ShippingAddress { get; set; }
}

public class Address
{
    public string Street { get; set; }
    public string City { get; set; }
}
```

### <a name="additional-details-on-owned-entity-types"></a><span data-ttu-id="914c1-182">Más datos sobre los tipos de entidad de propiedad</span><span class="sxs-lookup"><span data-stu-id="914c1-182">Additional details on owned entity types</span></span>

- <span data-ttu-id="914c1-183">Los tipos de propiedad se definen al configurar una propiedad de navegación en un tipo determinado mediante la API fluida OwnsOne.</span><span class="sxs-lookup"><span data-stu-id="914c1-183">Owned types are defined when you configure a navigation property to a particular type using the OwnsOne fluent API.</span></span>

- <span data-ttu-id="914c1-184">La definición de un tipo de propiedad en nuestro modelo de metadatos es una composición del tipo de propietario, la propiedad de navegación y el tipo CLR del tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="914c1-184">The definition of an owned type in our metadata model is a composite of: the owner type, the navigation property, and the CLR type of the owned type.</span></span>

- <span data-ttu-id="914c1-185">La identidad (clave) de una instancia de tipo de propiedad en nuestra pila es una composición de la identidad del tipo de propietario y la definición del tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="914c1-185">The identity (key) of an owned type instance in our stack is a composite of the identity of the owner type and the definition of the owned type.</span></span>

#### <a name="owned-entities-capabilities"></a><span data-ttu-id="914c1-186">Capacidades de las entidades de propiedad:</span><span class="sxs-lookup"><span data-stu-id="914c1-186">Owned entities capabilities:</span></span>

- <span data-ttu-id="914c1-187">Los tipos de propiedad pueden hacer referencia a otras entidades, ya sean de propiedad (tipos de propiedad anidados) o de no propiedad (propiedades de navegación de referencia normal a otras entidades).</span><span class="sxs-lookup"><span data-stu-id="914c1-187">Owned types can reference other entities, either owned (nested owned types) or non-owned (regular reference navigation properties to other entities).</span></span>

- <span data-ttu-id="914c1-188">Se puede asignar el mismo tipo CLR como otros tipos de propiedad en la misma entidad de propietario mediante propiedades de navegación independientes.</span><span class="sxs-lookup"><span data-stu-id="914c1-188">You can map the same CLR type as different owned types in the same owner entity through separate navigation properties.</span></span>

- <span data-ttu-id="914c1-189">La división de tablas se configura por convención, pero puede dejar de usarla si asigna el tipo de propiedad a otra tabla mediante ToTable.</span><span class="sxs-lookup"><span data-stu-id="914c1-189">Table splitting is setup by convention, but you can opt out by mapping the owned type to a different table using ToTable.</span></span>

- <span data-ttu-id="914c1-190">En los tipos de propiedad se efectúa una carga diligente de forma automática; es decir, no es necesario llamar a Include() en la consulta.</span><span class="sxs-lookup"><span data-stu-id="914c1-190">Eager loading is performed automatically on owned types, i.e. no need to call Include() on the query.</span></span>

- <span data-ttu-id="914c1-191">Desde EF Core 2.1, se puede configurar con el atributo \[Owned\].</span><span class="sxs-lookup"><span data-stu-id="914c1-191">Can be configured with attribute \[Owned\], as of EF Core 2.1</span></span>

#### <a name="owned-entities-limitations"></a><span data-ttu-id="914c1-192">Limitaciones de las entidades de propiedad:</span><span class="sxs-lookup"><span data-stu-id="914c1-192">Owned entities limitations:</span></span>

- <span data-ttu-id="914c1-193">No se puede crear un DbSet\<T\> de un tipo de propiedad (por diseño).</span><span class="sxs-lookup"><span data-stu-id="914c1-193">You cannot create a DbSet\<T\> of an owned type (by design).</span></span>

- <span data-ttu-id="914c1-194">No se puede llamar a ModelBuilder.Entity\<T\>() en los tipos de propiedad (actualmente por cuestiones de diseño).</span><span class="sxs-lookup"><span data-stu-id="914c1-194">You cannot call ModelBuilder.Entity\<T\>() on owned types (currently by design).</span></span>

- <span data-ttu-id="914c1-195">Todavía no hay colecciones de tipos de propiedad (en EF Core 2.1, pero se admitirán en la versión 2.2).</span><span class="sxs-lookup"><span data-stu-id="914c1-195">No collections of owned types yet (as of EF Core 2.1, but they will be supported in 2.2).</span></span>

- <span data-ttu-id="914c1-196">No se admiten los tipos de propiedad opcionales (es decir, que aceptan valores NULL) que se asignan con el propietario en la misma tabla (es decir, mediante la división de tablas).</span><span class="sxs-lookup"><span data-stu-id="914c1-196">No support for optional (that is, nullable) owned types that are mapped with the owner in the same table (i.e. using table splitting).</span></span> <span data-ttu-id="914c1-197">Esto se debe a que la asignación se realiza para cada propiedad; no hay un centinela independiente para el valor complejo NULL como un todo.</span><span class="sxs-lookup"><span data-stu-id="914c1-197">This is because mapping is done for each property, we don't have a separate sentinel for the null complex value a as whole.</span></span>

- <span data-ttu-id="914c1-198">No hay compatibilidad con la asignación de herencia para los tipos de propiedad, pero se deberían poder asignar dos tipos de hoja de las mismas jerarquías de herencia como otros tipos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="914c1-198">No inheritance mapping support for owned types, but you should be able to map two leaf types of the same inheritance hierarchies as different owned types.</span></span> <span data-ttu-id="914c1-199">EF Core no deducirá que forman parte de la misma jerarquía.</span><span class="sxs-lookup"><span data-stu-id="914c1-199">EF Core will not reason about the fact that they are part of the same hierarchy.</span></span>

#### <a name="main-differences-with-ef6s-complex-types"></a><span data-ttu-id="914c1-200">Principales diferencias con los tipos complejos de EF6</span><span class="sxs-lookup"><span data-stu-id="914c1-200">Main differences with EF6's complex types</span></span>

- <span data-ttu-id="914c1-201">La división de tablas es opcional (es decir, opcionalmente se pueden asignar a una tabla independiente y seguir siendo tipos de propiedad).</span><span class="sxs-lookup"><span data-stu-id="914c1-201">Table splitting is optional, i.e. they can optionally be mapped to a separate table and still be owned types.</span></span>

- <span data-ttu-id="914c1-202">Pueden hacer referencia a otras entidades (es decir, pueden actuar como el lado dependiente en las relaciones con otros tipos que no son de propiedad).</span><span class="sxs-lookup"><span data-stu-id="914c1-202">They can reference other entities (i.e. they can act as the dependent side on relationships to other non-owned types).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="914c1-203">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="914c1-203">Additional resources</span></span>

- <span data-ttu-id="914c1-204">**Martin Fowler. El patrón ValueObject** </span><span class="sxs-lookup"><span data-stu-id="914c1-204">**Martin Fowler. ValueObject pattern** </span></span>\
  <https://martinfowler.com/bliki/ValueObject.html>

- <span data-ttu-id="914c1-205">**Eric Evans. Diseño orientado al dominio: abordar la complejidad en el corazón del software.**</span><span class="sxs-lookup"><span data-stu-id="914c1-205">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software.**</span></span> <span data-ttu-id="914c1-206">(Libro; incluye una descripción de los objetos de valor) </span><span class="sxs-lookup"><span data-stu-id="914c1-206">(Book; includes a discussion of value objects) </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="914c1-207">**Vaughn Vernon. Implementing Domain-Driven Design** (Implementación del diseño guiado por el dominio).</span><span class="sxs-lookup"><span data-stu-id="914c1-207">**Vaughn Vernon. Implementing Domain-Driven Design.**</span></span> <span data-ttu-id="914c1-208">(Libro; incluye una descripción de los objetos de valor) </span><span class="sxs-lookup"><span data-stu-id="914c1-208">(Book; includes a discussion of value objects) </span></span>\
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="914c1-209">**Propiedades reemplazadas** </span><span class="sxs-lookup"><span data-stu-id="914c1-209">**Shadow Properties** </span></span>\
  [https://docs.microsoft.com/ef/core/modeling/shadow-properties](/ef/core/modeling/shadow-properties)

- <span data-ttu-id="914c1-210">**Complex types and/or value objects** (Tipos u objetos de valor complejos).</span><span class="sxs-lookup"><span data-stu-id="914c1-210">**Complex types and/or value objects**.</span></span> <span data-ttu-id="914c1-211">Descripción en el repositorio de GitHub de EF Core (pestaña Problemas) </span><span class="sxs-lookup"><span data-stu-id="914c1-211">Discussion in the EF Core GitHub repo (Issues tab) </span></span>\
  <https://github.com/dotnet/efcore/issues/246>

- <span data-ttu-id="914c1-212">**ValueObject.cs.**</span><span class="sxs-lookup"><span data-stu-id="914c1-212">**ValueObject.cs.**</span></span> <span data-ttu-id="914c1-213">Clase base de objeto de valor en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="914c1-213">Base value object class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs>

- <span data-ttu-id="914c1-214">**Clase Address.**</span><span class="sxs-lookup"><span data-stu-id="914c1-214">**Address class.**</span></span> <span data-ttu-id="914c1-215">Clase de objeto de valor de ejemplo en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="914c1-215">Sample value object class in eShopOnContainers.</span></span> \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs>

> [!div class="step-by-step"]
> <span data-ttu-id="914c1-216">[Anterior](seedwork-domain-model-base-classes-interfaces.md)
> [Siguiente](enumeration-classes-over-enum-types.md)</span><span class="sxs-lookup"><span data-stu-id="914c1-216">[Previous](seedwork-domain-model-base-classes-interfaces.md)
[Next](enumeration-classes-over-enum-types.md)</span></span>
