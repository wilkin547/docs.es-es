---
title: Seedwork (interfaces y clases base reutilizables para su modelo de dominio)
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Uso del concepto SeedWork como punto de partida para iniciar la implementación de un modelo de dominio orientado a DDD.
ms.date: 10/08/2018
ms.openlocfilehash: 545be2723ba468a5fd65f81978799328234ca113
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988315"
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork (interfaces y clases base reutilizables para su modelo de dominio)

La carpeta de soluciones contiene una carpeta *SeedWork*. Esta carpeta contiene las clases base personalizadas que puede usar como base de los objetos de valor y las entidades de dominio. Use estas clases base para no tener código redundante en la clase de objeto de cada dominio. La carpeta para estos tipos de clases se denomina *SeedWork* y no nombres parecidos como *Marco*. Se llama *SeedWork* porque la carpeta contiene solo un pequeño subconjunto de clases reutilizables que realmente no se puede considerar un marco. *Seedwork* es un término introducido por [Michael Feathers](https://www.artima.com/forums/flat.jsp?forum=106&thread=8826) y popularizado por [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html), pero esta carpeta también se puede denominar Common, SharedKernel o similar.

En la Figura 7-12 se muestran las clases que forman el seedwork del modelo de dominio en el microservicio de pedidos. Tiene algunas clases base personalizadas, como Entity, ValueObject y Enumeration, además de algunas interfaces. Estas interfaces (IRepository y IUnitOfWork) informan al nivel de infraestructura de lo que requiere implementación. Estas interfaces también se usan mediante la inserción de dependencias del nivel de aplicación.

:::image type="complex" source="./media/seedwork-domain-model-base-classes-interfaces/vs-solution-seedwork-classes.png" alt-text="Captura de pantalla de las clases contenidas en la carpeta SeedWork.":::
Contenido detallado de la carpeta SeedWork, que contiene interfaces y clases base: Entity.cs, Enumeration.cs, IAggregateRoot.cs, IRepository.cs, IUnitOfWork.cs y ValueObject.cs.
:::image-end:::

**Figura 7-12.** Un conjunto de muestra de interfaces y clases base "seedwork" del modelo de dominio

Este es el tipo de reutilización de copiar y pegar que muchos desarrolladores comparten entre proyectos, y no un marco formal. Puede tener seedworks en cualquier nivel o biblioteca. Pero si el conjunto de clases e interfaces se hace lo suficientemente grande, puede crear una sola biblioteca de clases.

## <a name="the-custom-entity-base-class"></a>La clase base de entidad personalizada

El código siguiente es un ejemplo de clase base Entity en la que puede colocar código que puede ser utilizado de la misma forma por cualquier entidad de dominio, como el id. de entidad, [operadores de igualdad](../../../csharp/language-reference/operators/equality-operators.md), una lista de eventos de dominio por entidad, etc.

```csharp
// COMPATIBLE WITH ENTITY FRAMEWORK CORE (1.1 and later)
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;
    private List<INotification> _domainEvents;
    public virtual int Id
    {
        get
        {
            return _Id;
        }
        protected set
        {
            _Id = value;
        }
    }

    public List<INotification> DomainEvents => _domainEvents;
    public void AddDomainEvent(INotification eventItem)
    {
        _domainEvents = _domainEvents ?? new List<INotification>();
        _domainEvents.Add(eventItem);
    }
    public void RemoveDomainEvent(INotification eventItem)
    {
        if (_domainEvents is null) return;
        _domainEvents.Remove(eventItem);
    }

    public bool IsTransient()
    {
        return this.Id == default(Int32);
    }

    public override bool Equals(object obj)
    {
        if (obj == null || !(obj is Entity))
            return false;
        if (Object.ReferenceEquals(this, obj))
            return true;
        if (this.GetType() != obj.GetType())
            return false;
        Entity item = (Entity)obj;
        if (item.IsTransient() || this.IsTransient())
            return false;
        else
            return item.Id == this.Id;
    }

    public override int GetHashCode()
    {
        if (!IsTransient())
        {
            if (!_requestedHashCode.HasValue)
                _requestedHashCode = this.Id.GetHashCode() ^ 31;
            // XOR for random distribution. See:
            // https://docs.microsoft.com/archive/blogs/ericlippert/guidelines-and-rules-for-gethashcode
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }
    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null));
        else
            return left.Equals(right);
    }
    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

Este código, en el que se utiliza una lista de eventos de dominio por entidad, se describirá en las secciones siguientes, al hablar de los eventos de dominio.

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Contratos de repositorio (interfaces) en el nivel de modelo de dominio

Los contratos de repositorio no son más que interfaces .NET que expresan los requisitos de contrato de los repositorios que se van a utilizar en cada agregado.

Los repositorios en sí, con el código básico de EF Core o cualquier otra dependencia de infraestructura y código (Linq, SQL, etc.), no se deben implementar en el modelo de dominio; los repositorios solo deben implementar las interfaces que defina en el modelo de dominio.

Otro patrón relacionado con esta práctica (que coloca interfaces de repositorio en el nivel de modelo de dominio) es el patrón de interfaz separada. Como [explica](https://www.martinfowler.com/eaaCatalog/separatedInterface.html) Martin Fowler, "utilice una interfaz separada para definir una interfaz en un paquete e implementarla en otro. De esta forma, un cliente que necesite la dependencia en la interfaz puede no tener en cuenta para nada la implementación".

Seguir el patrón de interfaz separada permite que el nivel de aplicación (en este caso, el proyecto API web para el microservicio) tenga una dependencia en los requisitos definidos en el modelo de dominio, pero no una dependencia directa en el nivel de infraestructura/persistencia. Además, puede usar la inserción de dependencias para aislar la implementación, que se implementa en el nivel de infraestructura/persistencia utilizando repositorios.

Por ejemplo, el siguiente ejemplo con la interfaz de IOrderRepository define las operaciones que la clase OrderRepository tendrá que implementar en el nivel de infraestructura. En la implementación actual de la aplicación, el código solo necesita agregar o actualizar los pedidos en la base de datos, puesto que las consultas se dividen siguiendo el enfoque de CQRS simplificado.

```csharp
// Defined at IOrderRepository.cs
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);

    void Update(Order order);

    Task<Order> GetAsync(int orderId);
}

// Defined at IRepository.cs (Part of the Domain Seedwork)
public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a>Recursos adicionales

- **Martin Fowler. Separated Interface** (Interfaz independiente). \
  <https://www.martinfowler.com/eaaCatalog/separatedInterface.html>

>[!div class="step-by-step"]
>[Anterior](net-core-microservice-domain-model.md)
>[Siguiente](implement-value-objects.md)
