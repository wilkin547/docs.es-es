---
title: Seedwork (reutilizables clases base e interfaces para el modelo de dominio)
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Seedwork (reutilizables clases base e interfaces para el modelo de dominio)
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 17602d94ea167997389a77f0d2358326258a8219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a>Seedwork (reutilizables clases base e interfaces para el modelo de dominio)

La carpeta de soluciones contiene un *SeedWork* carpeta. El *SeedWork* carpeta contiene las clases base personalizadas que puede usar como una base de los objetos de valor y las entidades de dominio de. Use estas clases base para que no tengan código redundante en la clase de objeto de cada dominio. La carpeta para estos tipos de clases se denomina *SeedWork* y no algo como *Framework*. Se llama *SeedWork* porque la carpeta contiene solo un pequeño subconjunto de clases reutilizables que realmente no se puede considerar un marco de trabajo. *Seedwork* un término introducido por [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) y popularizó [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) pero también el nombre podría esa carpeta común, SharedKernel, o similares.

Figura 9-12 se muestran las clases que forman el seedwork del modelo de dominio en la ordenación microservicio. Tiene algunas clases base personalizadas como la entidad, ValueObject y enumeración más algunas interfaces. Estas interfaces (IRepository y IUnitOfWork) informar a la capa de infraestructura sobre lo que necesita para implementarse. Estas interfaces también se usan a través de la inyección de dependencia de la capa de aplicación.

![](./media/image13.PNG)

**Figura 9-12**. Un ejemplo de conjunto de interfaces y clases base "seedwork" del modelo de dominio

Este es el tipo de la reutilización de copiar y pegar que muchos desarrolladores se comparten entre proyectos, no un marco formal. Puede tener seedworks en cualquier capa o biblioteca. Sin embargo, si el conjunto de clases e interfaces obtiene lo suficientemente grande, puede crear una sola biblioteca de clases.

## <a name="the-custom-entity-base-class"></a>La clase base de entidad personalizada

El código siguiente es un ejemplo de una clase base de la entidad que puede colocar el código que se puede usar la misma forma por cualquier entidad del dominio, como el Id. de entidad, [operadores de igualdad](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx), etcetera.

```csharp
// ENTITY FRAMEWORK CORE 1.1
public abstract class Entity
{
    int? _requestedHashCode;
    int _Id;

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
                _requestedHashCode = this.Id.GetHashCode() \^ 31;
            // XOR for random distribution. See:
            // http://blogs.msdn.com/b/ericlippert/archive/2011/02/28/guidelines-and-rules-for-gethashcode.aspx
            return _requestedHashCode.Value;
        }
        else
            return base.GetHashCode();
    }

    public static bool operator ==(Entity left, Entity right)
    {
        if (Object.Equals(left, null))
            return (Object.Equals(right, null)) ? true : false;
        else
            return left.Equals(right);
    }

    public static bool operator !=(Entity left, Entity right)
    {
        return !(left == right);
    }
}
```

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a>Contratos de repositorio (interfaces) en el nivel de modelo de dominio

Repositorio contratos son simplemente interfaces de .NET que expresan los requisitos de contrato de los repositorios de que se usará para cada agregado. Los repositorios de por sí mismos, con el código básico de EF o cualquier otro código y las dependencias de infraestructura no deben implementarse en el modelo de dominio; los repositorios sólo deben implementar las interfaces que definen.

Un patrón relacionados con esta práctica (colocación de las interfaces de repositorio en el nivel de modelo de dominio) es el patrón de interfaz separados. Como [explica](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) Martin Fowler, "Use separados interfaz para definir una interfaz en una paquete pero implementarla en otro. De esta forma un cliente que necesita la dependencia a la interfaz puede ser completamente sin tener en cuenta la implementación."

Seguir el patrón de interfaz separados permite que la capa de aplicación (en este caso, el proyecto de Web API para el microservicio) tiene una dependencia en los requisitos definidos en el modelo de dominio, pero no una dependencia directa para la persistencia de infraestructura capa. Además, puede usar inserción de dependencias para aislar la implementación, que se implementa en la infraestructura / repositorios utilizando la capa de persistencia.

Por ejemplo, el siguiente ejemplo con la interfaz de IOrderRepository define las operaciones que la clase OrderRepository tendrá que implementar en el nivel de infraestructura. En la implementación actual de la aplicación, el código solo necesita agregar el pedido a la base de datos, puesto que las consultas son siguientes de división que no se implementa el enfoque CQS y actualiza los pedidos.

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
}

public interface IRepository<T> where T : IAggregateRoot
{
    IUnitOfWork UnitOfWork { get; }
}
```

## <a name="additional-resources"></a>Recursos adicionales

-   **Martin Fowler. Interfaz separada. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)


>[!div class="step-by-step"]
[Anterior] (net-core-microservicio-dominio-model.md) [siguiente] (implemente-valor-objects.md)
