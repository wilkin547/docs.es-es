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
# <a name="seedwork-reusable-base-classes-and-interfaces-for-your-domain-model"></a><span data-ttu-id="a2ffe-104">Seedwork (reutilizables clases base e interfaces para el modelo de dominio)</span><span class="sxs-lookup"><span data-stu-id="a2ffe-104">Seedwork (reusable base classes and interfaces for your domain model)</span></span>

<span data-ttu-id="a2ffe-105">La carpeta de soluciones contiene un *SeedWork* carpeta.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-105">The solution folder contains a *SeedWork* folder.</span></span> <span data-ttu-id="a2ffe-106">El *SeedWork* carpeta contiene las clases base personalizadas que puede usar como una base de los objetos de valor y las entidades de dominio de.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-106">The *SeedWork* folder contains custom base classes that you can use as a base for your domain entities and value objects.</span></span> <span data-ttu-id="a2ffe-107">Use estas clases base para que no tengan código redundante en la clase de objeto de cada dominio.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-107">Use these base classes so you do not have redundant code in each domain’s object class.</span></span> <span data-ttu-id="a2ffe-108">La carpeta para estos tipos de clases se denomina *SeedWork* y no algo como *Framework*.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-108">The folder for these types of classes is called *SeedWork* and not something like *Framework*.</span></span> <span data-ttu-id="a2ffe-109">Se llama *SeedWork* porque la carpeta contiene solo un pequeño subconjunto de clases reutilizables que realmente no se puede considerar un marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-109">It's called *SeedWork* because the folder contains just a small subset of reusable classes which cannot really be considered a framework.</span></span> <span data-ttu-id="a2ffe-110">*Seedwork* un término introducido por [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) y popularizó [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) pero también el nombre podría esa carpeta común, SharedKernel, o similares.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-110">*Seedwork* is a term introduced by [Michael Feathers](http://www.artima.com/forums/flat.jsp?forum=106&thread=8826) and popularized by [Martin Fowler](https://martinfowler.com/bliki/Seedwork.html) but you could also name that folder Common, SharedKernel, or similar.</span></span>

<span data-ttu-id="a2ffe-111">Figura 9-12 se muestran las clases que forman el seedwork del modelo de dominio en la ordenación microservicio.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-111">Figure 9-12 shows the classes that form the seedwork of the domain model in the ordering microservice.</span></span> <span data-ttu-id="a2ffe-112">Tiene algunas clases base personalizadas como la entidad, ValueObject y enumeración más algunas interfaces.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-112">It has a few custom base classes like Entity, ValueObject, and Enumeration, plus a few interfaces.</span></span> <span data-ttu-id="a2ffe-113">Estas interfaces (IRepository y IUnitOfWork) informar a la capa de infraestructura sobre lo que necesita para implementarse.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-113">These interfaces (IRepository and IUnitOfWork) inform the infrastructure layer about what needs to be implemented.</span></span> <span data-ttu-id="a2ffe-114">Estas interfaces también se usan a través de la inyección de dependencia de la capa de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-114">Those interfaces are also used through Dependency Injection from the application layer.</span></span>

![](./media/image13.PNG)

<span data-ttu-id="a2ffe-115">**Figura 9-12**.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-115">**Figure 9-12**.</span></span> <span data-ttu-id="a2ffe-116">Un ejemplo de conjunto de interfaces y clases base "seedwork" del modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="a2ffe-116">A sample set of domain model “seedwork" base classes and interfaces</span></span>

<span data-ttu-id="a2ffe-117">Este es el tipo de la reutilización de copiar y pegar que muchos desarrolladores se comparten entre proyectos, no un marco formal.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-117">This is the type of copy and paste reuse that many developers share between projects, not a formal framework.</span></span> <span data-ttu-id="a2ffe-118">Puede tener seedworks en cualquier capa o biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-118">You can have seedworks in any layer or library.</span></span> <span data-ttu-id="a2ffe-119">Sin embargo, si el conjunto de clases e interfaces obtiene lo suficientemente grande, puede crear una sola biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-119">However, if the set of classes and interfaces gets big enough, you might want to create a single class library.</span></span>

## <a name="the-custom-entity-base-class"></a><span data-ttu-id="a2ffe-120">La clase base de entidad personalizada</span><span class="sxs-lookup"><span data-stu-id="a2ffe-120">The custom Entity base class</span></span>

<span data-ttu-id="a2ffe-121">El código siguiente es un ejemplo de una clase base de la entidad que puede colocar el código que se puede usar la misma forma por cualquier entidad del dominio, como el Id. de entidad, [operadores de igualdad](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx), etcetera.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-121">The following code is an example of an Entity base class where you can place code that can be used the same way by any domain entity, such as the entity ID, [equality operators](https://msdn.microsoft.com/en-us/library/c35t2ffz.aspx), etc.</span></span>

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

## <a name="repository-contracts-interfaces-in-the-domain-model-layer"></a><span data-ttu-id="a2ffe-122">Contratos de repositorio (interfaces) en el nivel de modelo de dominio</span><span class="sxs-lookup"><span data-stu-id="a2ffe-122">Repository contracts (interfaces) in the domain model layer</span></span>

<span data-ttu-id="a2ffe-123">Repositorio contratos son simplemente interfaces de .NET que expresan los requisitos de contrato de los repositorios de que se usará para cada agregado.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-123">Repository contracts are simply .NET interfaces that express the contract requirements of the repositories to be used for each aggregate.</span></span> <span data-ttu-id="a2ffe-124">Los repositorios de por sí mismos, con el código básico de EF o cualquier otro código y las dependencias de infraestructura no deben implementarse en el modelo de dominio; los repositorios sólo deben implementar las interfaces que definen.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-124">The repositories themselves, with EF Core code or any other infrastructure dependencies and code, must not be implemented within the domain model; the repositories should only implement the interfaces you define.</span></span>

<span data-ttu-id="a2ffe-125">Un patrón relacionados con esta práctica (colocación de las interfaces de repositorio en el nivel de modelo de dominio) es el patrón de interfaz separados.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-125">A pattern related to this practice (placing the repository interfaces in the domain model layer) is the Separated Interface pattern.</span></span> <span data-ttu-id="a2ffe-126">Como [explica](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) Martin Fowler, "Use separados interfaz para definir una interfaz en una paquete pero implementarla en otro.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-126">As [explained](http://www.martinfowler.com/eaaCatalog/separatedInterface.html) by Martin Fowler, “Use Separated Interface to define an interface in one package but implement it in another.</span></span> <span data-ttu-id="a2ffe-127">De esta forma un cliente que necesita la dependencia a la interfaz puede ser completamente sin tener en cuenta la implementación."</span><span class="sxs-lookup"><span data-stu-id="a2ffe-127">This way a client that needs the dependency to the interface can be completely unaware of the implementation.”</span></span>

<span data-ttu-id="a2ffe-128">Seguir el patrón de interfaz separados permite que la capa de aplicación (en este caso, el proyecto de Web API para el microservicio) tiene una dependencia en los requisitos definidos en el modelo de dominio, pero no una dependencia directa para la persistencia de infraestructura capa.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-128">Following the Separated Interface pattern enables the application layer (in this case, the Web API project for the microservice) to have a dependency on the requirements defined in the domain model, but not a direct dependency to the infrastructure/persistence layer.</span></span> <span data-ttu-id="a2ffe-129">Además, puede usar inserción de dependencias para aislar la implementación, que se implementa en la infraestructura / repositorios utilizando la capa de persistencia.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-129">In addition, you can use Dependency Injection to isolate the implementation, which is implemented in the infrastructure/ persistence layer using repositories.</span></span>

<span data-ttu-id="a2ffe-130">Por ejemplo, el siguiente ejemplo con la interfaz de IOrderRepository define las operaciones que la clase OrderRepository tendrá que implementar en el nivel de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-130">For example, the following example with the IOrderRepository interface defines what operations the OrderRepository class will need to implement at the infrastructure layer.</span></span> <span data-ttu-id="a2ffe-131">En la implementación actual de la aplicación, el código solo necesita agregar el pedido a la base de datos, puesto que las consultas son siguientes de división que no se implementa el enfoque CQS y actualiza los pedidos.</span><span class="sxs-lookup"><span data-stu-id="a2ffe-131">In the current implementation of the application, the code just needs to add the order to the database, since queries are split following the CQS approach, and updates to orders are not implemented.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="a2ffe-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a2ffe-132">Additional resources</span></span>

-   <span data-ttu-id="a2ffe-133">**Martin Fowler. Interfaz separada. ** 
     [ *http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span><span class="sxs-lookup"><span data-stu-id="a2ffe-133">**Martin Fowler. Separated Interface.**
[*http://www.martinfowler.com/eaaCatalog/separatedInterface.html*](http://www.martinfowler.com/eaaCatalog/separatedInterface.html%20)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="a2ffe-134">[Anterior] (net-core-microservicio-dominio-model.md) [siguiente] (implemente-valor-objects.md)</span><span class="sxs-lookup"><span data-stu-id="a2ffe-134">[Previous] (net-core-microservice-domain-model.md) [Next] (implement-value-objects.md)</span></span>
