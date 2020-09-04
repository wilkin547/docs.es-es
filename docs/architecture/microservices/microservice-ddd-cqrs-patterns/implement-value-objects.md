---
title: Implementar objetos de valor
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Obtenga los detalles y las opciones para implementar objetos de valor mediante las características nuevas de Entity Framework.
ms.date: 08/21/2020
ms.openlocfilehash: 02eed7baaa364c62aa2df599f1d8b0e700dd215f
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811124"
---
# <a name="implement-value-objects"></a>Implementación de objetos de valor

Como se describe en secciones anteriores sobre las entidades y agregados, la identidad es esencial para las entidades, pero hay muchos objetos y elementos de datos en un sistema que no requieren ninguna identidad ni ningún seguimiento de identidad, como los objetos de valor.

Un objeto de valor puede hacer referencia a otras entidades. Por ejemplo, en una aplicación que genera una ruta que describe cómo ir de un punto a otro, esa ruta sería un objeto de valor. Sería una instantánea de puntos en una ruta específica, pero esta ruta sugerida no tendría una identidad, aunque internamente podría hacer referencia a entidades como Ciudad, Carretera, etc.

En la figura 7-13 se muestra el objeto de valor Address en el agregado Order.

![Diagrama que muestra el objeto de valor Address dentro del agregado Order.](./media/implement-value-objects/value-object-within-aggregate.png)

**Figura 7-13**. Objeto de valor Dirección en el agregado Pedido

Como se muestra en la figura 7-13, una entidad suele constar de varios atributos. Por ejemplo, la entidad `Order` se puede modelar como una entidad con una identidad y puede estar formada internamente por un conjunto de atributos, como OrderId, OrderDate, OrderItems, etc. Pero la dirección, que es un valor complejo formado por el país o región, la calle, la ciudad, etc., y que no tiene ninguna identidad en este dominio, se debe modelar y tratar como un objeto de valor.

## <a name="important-characteristics-of-value-objects"></a>Características importantes de los objetos de valor

Hay dos características principales en los objetos de valor:

- No tienen ninguna identidad.

- Son inmutables.

La primera característica ya se ha mencionado. La inmutabilidad es un requisito importante. Los valores de un objeto de valor deben ser inmutables una vez creado el objeto. Por lo tanto, cuando se construye el objeto, debe proporcionar los valores necesarios, pero no debe permitir que cambien durante la vigencia del objeto.

Los objetos de valor le permiten hacer algunos trucos de rendimiento gracias a su naturaleza inmutable. Esto es así sobre todo en los sistemas en los que puede haber miles de instancias de objetos de valor, muchas de las cuales tienen los mismos valores. Su naturaleza inmutable permite que se puedan reutilizar y pueden ser objetos intercambiables, ya que sus valores son los mismos y no tienen ninguna identidad. Este tipo de optimización a veces puede suponer una diferencia entre el software que se ejecuta con lentitud y el software que tiene un buen rendimiento. Como es lógico, todos estos casos dependen el entorno de aplicación y del contexto de implementación.

## <a name="value-object-implementation-in-c"></a>Implementación de objetos de valor en C\#

En cuanto a la implementación, puede tener una clase base de objeto de valor que tenga métodos de utilidad básicos, como la igualdad según la comparación entre todos los atributos (ya que un objeto de valor no se debe basar en la identidad) y otras características esenciales. En el ejemplo siguiente se muestra una clase base de objeto de valor que se usa en el microservicio de ordenación de eShopOnContainers.

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

    protected abstract IEnumerable<object> GetEqualityComponents();

    public override bool Equals(object obj)
    {
        if (obj == null || obj.GetType() != GetType())
        {
            return false;
        }

        var other = (ValueObject)obj;

        return this.GetEqualityComponents().SequenceEqual(other.GetEqualityComponents());
    }

    public override int GetHashCode()
    {
        return GetEqualityComponents()
            .Select(x => x != null ? x.GetHashCode() : 0)
            .Aggregate((x, y) => x ^ y);
    }
    // Other utility methods
}
```

Puede usar esta clase al implementar el objeto de valor real, al igual que con el objeto de valor Address (Dirección) que se muestra en el ejemplo siguiente:

```csharp
public class Address : ValueObject
{
    public String Street { get; private set; }
    public String City { get; private set; }
    public String State { get; private set; }
    public String Country { get; private set; }
    public String ZipCode { get; private set; }

    public Address() { }

    public Address(string street, string city, string state, string country, string zipcode)
    {
        Street = street;
        City = city;
        State = state;
        Country = country;
        ZipCode = zipcode;
    }

    protected override IEnumerable<object> GetEqualityComponents()
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

Puede ver cómo esta implementación de objeto de valor de Address no tiene ninguna identidad y, por tanto, ningún campo de identificador, ni en la clase Address ni tampoco en la clase ValueObject.

El hecho de no tener que disponer de un campo de identificador para su uso en Entity Framework (EF) no fue posible hasta EF Core 2.0, lo que ayuda a implementar mejor los objetos de valor sin identificador. Eso es precisamente la explicación de la sección siguiente.

Se podría argumentar que los objetos de valor, al ser inmutables, deben ser de solo lectura (es decir, tener propiedades get-only), y así es. Pero los objetos de valor normalmente se serializan y deserializan para recorrer colas de mensajes. Asimismo, si fueran de solo lectura, el deserializador no podría asignar los valores, por lo que simplemente se dejan como `private set`, lo cual ofrece un nivel de solo lectura suficiente para que resulte práctico.

## <a name="how-to-persist-value-objects-in-the-database-with-ef-core-20-and-later"></a>Procedimiento para conservar objetos de valor en la base de datos con EF Core 2.0 y versiones posteriores

Acaba de ver cómo definir un objeto de valor en el modelo de dominio, Pero ¿cómo puede conservarlo en la base de datos mediante Entity Framework Core, dado que suele tener como destino las entidades con identidad?

### <a name="background-and-older-approaches-using-ef-core-11"></a>Contexto y enfoques anteriores con EF Core 1.1

Como contexto, una limitación al usar EF Core 1.0 y 1.1 era que no se podían utilizar [tipos complejos](xref:System.ComponentModel.DataAnnotations.Schema.ComplexTypeAttribute) tal y como se definen en EF 6.x en .NET Framework tradicional. Por lo tanto, si se usaba EF Core 1.0 o 1.1, era necesario almacenar el objeto de valor como una entidad de EF con un campo de identificador. Luego, para que se pareciera más a un objeto de valor sin ninguna identidad, se podía ocultar su identificador para dejar claro que la identidad de un objeto de valor no es importante en el modelo de dominio. Ese identificador se podía ocultar usándolo como [propiedad reemplazada](https://docs.microsoft.com/ef/core/modeling/shadow-properties ). Puesto que esa configuración para ocultar el identificador en el modelo está establecida en el nivel de la infraestructura de EF, resultaría algo transparente para su modelo de dominio.

En la versión inicial de eShopOnContainers (.NET Core 1.1), el identificador oculto necesario para la infraestructura de EF Core estaba implementado del siguiente modo en el nivel de DbContext, usando la API fluida en el proyecto de la infraestructura. Por lo tanto, el identificador quedaba oculto desde el punto de vista del modelo de dominio, pero seguía presente en la infraestructura.

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

Pero la persistencia de ese objeto de valor en la base de datos se efectuaba como una entidad normal en otra tabla.

Con EF Core 2.0 y versiones posteriores hay nuevos y mejores métodos para conservar los objetos de valor.

## <a name="persist-value-objects-as-owned-entity-types-in-ef-core-20-and-later"></a>Conservación de objetos de valor como tipos entidad de propiedad en EF Core 2.0 y versiones posteriores

Aunque haya algunas lagunas entre el patrón de objeto de valor canónico en el DDD y el tipo de entidad de propiedad en EF Core, ahora mismo es la mejor manera de conservar objetos de valor con EF Core 2.0 y versiones posteriores. Puede consultar las limitaciones al final de esta sección.

La función del tipo de entidad de propiedad se agregó a EF Core a partir de la versión 2.0.

Un tipo de entidad de propiedad permite asignar tipos que no tienen su propia identidad definida de forma explícita en el modelo de dominio y que se usan como propiedades (como los objetos de valor) en cualquiera de las entidades. Un tipo de entidad de propiedad comparte el mismo tipo CLR con otro tipo de entidad (es decir, solo es una clase convencional). La entidad que contiene la navegación definitoria es la entidad del propietario. Al consultar al propietario, los tipos de propiedad se incluyen de forma predeterminada.

Si se examina el modelo de dominio, parece que los tipos de propiedad no tienen ninguna identidad pero, en el fondo, la tienen, aunque la propiedad de navegación del propietario forma parte de esta identidad.

La identidad de las instancias de los tipos de propiedad no es totalmente suya. Consta de tres componentes:

- La identidad del propietario

- La propiedad de navegación que los señala

- En el caso de las colecciones de tipos de propiedad, un componente independiente (compatible con EF Core 2.2 y versiones posteriores).

Por ejemplo, en el modelo de dominio Ordering de eShopOnContainers, como parte de la entidad Order, el objeto de valor Address se implementa como un tipo de entidad de propiedad dentro de la entidad del propietario, que es la entidad Order. `Address` es un tipo sin ninguna propiedad de identidad definida en el modelo de dominio. Se usa como propiedad del tipo Order para especificar la dirección de envío de un pedido en concreto.

Por convención, se crea una clave principal paralela para el tipo de propiedad y se asignará a la misma tabla que el propietario mediante la división de tabla. Esto permite usar tipos de propiedad de forma similar al modo en que se usan los tipos complejos en EF6 en el .NET Framework tradicional.

Es importante tener en cuenta que los tipos de propiedad nunca se detectan por convención en EF Core, por lo que se deben declarar explícitamente.

En eShopOnContainers, en el archivo OrderingContext.cs, dentro del método `OnModelCreating()`, se aplican varias configuraciones de infraestructura. Una de ellas está relacionada con la entidad Order.

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

En el código siguiente, la infraestructura de persistencia está definida para la entidad Order:

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

En el código anterior, el método `orderConfiguration.OwnsOne(o => o.Address)` especifica que la propiedad `Address` es una entidad de propiedad del tipo `Order`.

De forma predeterminada, las convenciones de EF Core asignan a las columnas de base de datos de las propiedades del tipo de entidad de propiedad el nombre `EntityProperty_OwnedEntityProperty`. Por lo tanto, las propiedades internas de `Address` aparecerán en la tabla `Orders` con los nombres `Address_Street` y `Address_City` (y así sucesivamente para `State`, `Country` y `ZipCode`).

Puede anexar el método fluido `Property().HasColumnName()` para cambiar el nombre de esas columnas. En el caso en que `Address` es una propiedad pública, las asignaciones serían similares a lo siguiente:

```csharp
orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.Street).HasColumnName("ShippingStreet");

orderConfiguration.OwnsOne(p => p.Address)
                            .Property(p=>p.City).HasColumnName("ShippingCity");
```

Se puede encadenar el método `OwnsOne` en una asignación fluida. En el siguiente ejemplo hipotético, `OrderDetails` posee `BillingAddress` y `ShippingAddress`, que son tipos `Address`. Luego, `OrderDetails` es propiedad del tipo `Order`.

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

### <a name="additional-details-on-owned-entity-types"></a>Más datos sobre los tipos de entidad de propiedad

- Los tipos de propiedad se definen al configurar una propiedad de navegación en un tipo determinado mediante la API fluida OwnsOne.

- La definición de un tipo de propiedad en nuestro modelo de metadatos es una composición del tipo de propietario, la propiedad de navegación y el tipo CLR del tipo de propiedad.

- La identidad (clave) de una instancia de tipo de propiedad en nuestra pila es una composición de la identidad del tipo de propietario y la definición del tipo de propiedad.

#### <a name="owned-entities-capabilities"></a>Capacidades de las entidades de propiedad

- Los tipos de propiedad pueden hacer referencia a otras entidades, ya sean de propiedad (tipos de propiedad anidados) o de no propiedad (propiedades de navegación de referencia normal a otras entidades).

- Se puede asignar el mismo tipo CLR como otros tipos de propiedad en la misma entidad de propietario mediante propiedades de navegación independientes.

- La división de tablas se configura por convención, pero puede dejar de usarla si asigna el tipo de propiedad a otra tabla mediante ToTable.

- En los tipos de propiedad se efectúa una carga diligente de forma automática; es decir, no es necesario llamar a `.Include()` en la consulta.

- A partir de EF Core 2.1 y versiones posteriores, se puede configurar con el atributo `[Owned]`.

- Puede controlar colecciones de tipos de propiedad (con la versión 2.2 y posteriores).

#### <a name="owned-entities-limitations"></a>Limitaciones de las entidades de propiedad

- No se puede crear un elemento `DbSet<T>` de un tipo de propiedad (por cuestiones de diseño).

- No se puede llamar a `ModelBuilder.Entity<T>()` en los tipos de propiedad (actualmente por cuestiones de diseño).

- No se admiten los tipos de propiedad opcionales (es decir, que aceptan valores NULL) que se asignan con el propietario en la misma tabla (es decir, mediante la división de tablas). Esto se debe a que la asignación se realiza para cada propiedad; no hay un centinela independiente para el valor complejo NULL como un todo.

- No hay compatibilidad con la asignación de herencia para los tipos de propiedad, pero se deberían poder asignar dos tipos hoja de las mismas jerarquías de herencia como otros tipos de propiedad. EF Core no deducirá que forman parte de la misma jerarquía.

#### <a name="main-differences-with-ef6s-complex-types"></a>Principales diferencias con los tipos complejos de EF6

- La división de tablas es opcional (es decir, opcionalmente se pueden asignar a una tabla independiente y seguir siendo tipos de propiedad).

- Pueden hacer referencia a otras entidades (es decir, pueden actuar como el lado dependiente en las relaciones con otros tipos que no son de propiedad).

## <a name="additional-resources"></a>Recursos adicionales

- **Martin Fowler. El patrón ValueObject** \
  <https://martinfowler.com/bliki/ValueObject.html>

- **Eric Evans. Diseño orientado al dominio: abordar la complejidad en el corazón del software.** (Libro; incluye una descripción de los objetos de valor) \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- **Vaughn Vernon. Implementing Domain-Driven Design** (Implementación del diseño guiado por el dominio). (Libro; incluye una descripción de los objetos de valor) \
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- **Tipos de entidad en propiedad** \
  <https://docs.microsoft.com/ef/core/modeling/owned-entities>

- **Propiedades reemplazadas** \
  <https://docs.microsoft.com/ef/core/modeling/shadow-properties>

- **Complex types and/or value objects** (Tipos u objetos de valor complejos). Descripción en el repositorio de GitHub de EF Core (pestaña Problemas) \
  <https://github.com/dotnet/efcore/issues/246>

- **ValueObject.cs.** Clase base de objeto de valor en eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs>

- **Clase Address.** Clase de objeto de valor de ejemplo en eShopOnContainers. \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs>

> [!div class="step-by-step"]
> [Anterior](seedwork-domain-model-base-classes-interfaces.md)
> [Siguiente](enumeration-classes-over-enum-types.md)
