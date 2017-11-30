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
# <a name="implementing-value-objects"></a>Implementar objetos de valor

Como se describe en las secciones anteriores sobre las entidades y agregados, identidad es fundamental para las entidades. Sin embargo, hay muchos objetos y elementos de datos en un sistema que no requieren una identidad y realizar el seguimiento, como los objetos de valor.

Un objeto de valor puede hacer referencia a otras entidades. Por ejemplo, en una aplicación que genera una ruta que describe cómo obtener desde un punto a otro, esa ruta sería un objeto de valor. Sería una instantánea de los puntos en una ruta específica, pero esta ruta sugerida no tendría una identidad, aunque internamente podrían hacer referencia a entidades como ciudad, Road, etcetera.

Figura 9-13 muestra el objeto de valor de dirección en el agregado de orden.

![](./media/image14.png)

**Figura 9-13**. Objeto de valor en el agregado de orden de direcciones

Como se muestra en la figura 9-13, una entidad normalmente se compone de varios atributos. Por ejemplo, orden se puede modelar como una entidad con una identidad e internamente formada por un conjunto de atributos como OrderId, OrderDate, OrderItems, etcetera. Pero la dirección, que es simplemente un valor complejo que compone de país, calle, ciudad, etc. deben modelar y se trata como un objeto de valor.

## <a name="important-characteristics-of-value-objects"></a>Características importantes de los objetos de valor

Hay dos características principales para los objetos de valor:

-   No tienen que no hay ninguna identidad.

-   Únicamente son inmutables.

La primera característica ya se ha mencionado. Inmutabilidad es un requisito importante. Los valores de un objeto de valor deben ser inmutables una vez creado el objeto. Por lo tanto, cuando se construye el objeto, debe proporcionar los valores necesarios, pero no debe permitir que cambie durante la duración del objeto.

Objetos de valor permiten realizar algunos trucos para el rendimiento, gracias a su naturaleza inmutable. Esto es especialmente cierto en sistemas donde pueden haber miles de valor instancias de objetos, muchos de los cuales tienen los mismos valores. Su naturaleza inmutable les permite reutilizar; pueden ser objetos intercambiables, ya que sus valores son los mismos y no tienen ninguna identidad. Este tipo de optimización a veces puede suponer una diferencia entre el software que se ejecuta con lentitud y el software con un buen rendimiento. Por supuesto, todos estos casos dependen el entorno de aplicación y el contexto de la implementación.

## <a name="value-object-implementation-in-c"></a>Implementación de objeto de valor en C\#

En cuanto a implementación, puede tener una clase base de objeto de valor que tiene métodos de utilidad básica como igualdad en función de comparación entre todos los atributos (ya que un objeto de valor no debe basarse en la identidad) y otras características fundamentales. En el ejemplo siguiente se muestra una clase base de objeto de valor usada en la ordenación microservicio desde eShopOnContainers.

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

Puede usar esta clase cuando implementa el objeto de valor real, al igual que con el objeto de valor de dirección que se muestra en el ejemplo siguiente:

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

## <a name="hiding-the-identity-characteristic-when-using-ef-core-to-persist-value-objects"></a>Ocultar la característica de identidad al usar EF Core conservar objetos de valor

Una limitación cuando se utiliza EF principal es que en su versión actual (EF Core 1.1) no se puede utilizar [tipos complejos](https://docs.microsoft.com/de-de/dotnet/api/system.componentmodel.dataannotations.schema.complextypeattribute?view=netframework-4.7) tal como se define en EF 6.x. Por lo tanto, debe almacenar el objeto de valor como una entidad EF. Sin embargo, puede ocultar su ID por lo que hacer claro que no es importante en el modelo que el objeto de valor forma parte de la identidad. Ocultar el identificador está utilizando el identificador como una propiedad de instantáneas. Puesto que esa configuración para ocultar el identificador en el modelo se configura en el nivel de infraestructura, será transparente para el modelo de dominio y su implementación de infraestructura podría cambiar en el futuro.

En eShopOnContainers, el identificador oculto sea necesario mediante la infraestructura básica de EF se implementa de la manera siguiente en el nivel de DbContext, mediante la API fluida en el proyecto de infraestructura.

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

Por lo tanto, el identificador está oculta para el punto de vista de dominio modelo y en el futuro, la infraestructura de objeto de valor también puede implementarse como un tipo complejo o de otra manera.

## <a name="additional-resources"></a>Recursos adicionales

-   **Martin Fowler. Patrón de ValueObject**
    [*https://martinfowler.com/bliki/ValueObject.html*](https://martinfowler.com/bliki/ValueObject.html)

-   **Eric Evans. Diseño basado en dominio: Realiza para complejidad en el centro de Software.** (Libro; incluye una explicación de los objetos de valor) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Vaughn Vernon. Implementar el diseño basado en dominio.** (Libro; incluye una explicación de los objetos de valor) [ *https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **Ocultar propiedades**
    [*https://docs.microsoft.com/ef/core/modeling/shadow-properties*](https://docs.microsoft.com/ef/core/modeling/shadow-properties)

-   **Tipos complejos u objetos de valor**. Explicación en el repositorio de GitHub de núcleo de EF (pestaña de problemas) [ *https://github.com/aspnet/EntityFramework/issues/246*](https://github.com/aspnet/EntityFramework/issues/246)

-   **ValueObject.cs.** Clase de objeto de valor base en eShopOnContainers.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/ValueObject.cs)

-   **Clase de direcciones.** Clase de objeto de valor de ejemplo de eShopOnContainers.
    [*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/OrderAggregate/Address.cs)


>[!div class="step-by-step"]
[Anterior] (seedwork-domain-model-base-classes-interfaces.md) [siguiente] (enumeración-clases-over-enum-types.md)
