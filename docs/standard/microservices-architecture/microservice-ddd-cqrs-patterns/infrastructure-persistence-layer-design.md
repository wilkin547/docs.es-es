---
title: "Diseñar la capa de persistencia de infraestructura"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Diseñar la capa de persistencia de infraestructura"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ce0f1d608eed909a7707f3c580afc5253f3eef06
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-infrastructure-persistence-layer"></a>Diseñar la capa de persistencia de infraestructura

Componentes de persistencia de datos proporcionan acceso a los datos que se hospeda dentro de los límites de un microservicio (es decir, base de datos de microservicio). Contienen la implementación real de los componentes como repositorios y [unidad de trabajo](http://martinfowler.com/eaaCatalog/unitOfWork.html) clases, como DBContexts de EF personalizado.

## <a name="the-repository-pattern"></a>El modelo de repositorio

Los repositorios son clases o componentes que encapsulan la lógica necesaria para tener acceso a orígenes de datos. Centralización de datos acceso a funcionalidad común, lo que proporciona un mejor mantenimiento y el desacoplamiento la infraestructura o la tecnología que se usa para tener acceso a las bases de datos de la capa de modelo de dominio. Si usas un ORM como Entity Framework, se simplifica el código que debe implementarse, gracias a LINQ y establecimiento inflexible de tipos. Esto le permite centrarse en la lógica de persistencia de datos en lugar de datos acceso mecánica.

El modelo de repositorio es una manera de trabajar con un origen de datos bien documentada. En la libreta de [patrones de arquitectura de aplicación empresarial](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/), Martin Fowler describe un repositorio como sigue:

Un repositorio realiza las tareas de intermediario entre los niveles de modelo de dominio y la asignación de datos, que actúa de forma similar a un conjunto de objetos de dominio en la memoria. Objetos de cliente mediante declaración generan consultas y envían a los repositorios de respuestas. Conceptualmente, un repositorio encapsula un conjunto de objetos almacenados en la base de datos y las operaciones que se pueden realizar en ellos, proporcionan una manera de que esté cerca de la capa de persistencia. Repositorios, además, admiten la finalidad de asignación o separar con claridad y en una dirección, la dependencia entre el dominio de trabajo y la asignación de datos.

### <a name="define-one-repository-per-aggregate"></a>Definir un repositorio por agregado

Para cada raíz aggregate o aggregate, debe crear una clase de repositorio. En un microservicio basándose en patrones de diseño basado en dominio, el único canal que se debe usar para actualizar la base de datos debe ser los repositorios. Esto es porque tienen una relación uno a uno con la raíz de agregado, que controla el agregado invariables y coherencia transaccional. Es correcto consultar la base de datos a través de otros canales (tal y como se pueden realizar después de un enfoque CQRS), dado que las consultas no cambian el estado de la base de datos. Sin embargo, el área transaccional, las actualizaciones, siempre debe controlarse mediante los repositorios y las agregados raíces.

Básicamente, un repositorio permite rellenar los datos en la memoria que procede de la base de datos en forma de las entidades de dominio. Una vez que las entidades se encuentran en la memoria, se pueden cambiar y, a continuación, se conserva en la base de datos a través de las transacciones.

Como se indicó anteriormente, si está utilizando el modelo de arquitectura de CQS/CQRS, las consultas iniciales se realizará por consultas del lado fuera del modelo de dominio, realizadas por instrucciones SQL simples con Dapper. Este enfoque es mucho más flexible que los repositorios, ya que puede consultar y combinar las tablas necesita, y estas consultas no están limitadas por las reglas de los agregados. Esos datos irá a la aplicación de cliente o de capa de presentación.

Si el usuario hace cambios, los datos se actualicen procederán de la capa de presentación o de aplicación de cliente a la capa de aplicación (por ejemplo, un servicio de API Web). Cuando reciba un comando (con datos) en un controlador de comandos, utilice repositorios para obtener los datos que desea actualizar desde la base de datos. Actualizar en la memoria con la información que se pasa con los comandos y, a continuación, agrega o actualiza los datos (entidades de dominio) en la base de datos a través de una transacción.

Lo debemos destacamos nuevo que un solo repositorio debe definirse para cada raíz agregada, como se muestra en la figura 9-17. Para lograr el objetivo de la raíz agregada para mantener la coherencia transaccional entre todos los objetos dentro del agregado, nunca se debe crear un repositorio para cada tabla en la base de datos.

![](./media/image18.png)

**Figura 9-17**. La relación entre tablas de base de datos, agregados y repositorios

### <a name="enforcing-one-aggregate-root-per-repository"></a>Aplicar una raíz agregada por repositorio

Puede ser útil para implementar el diseño de repositorio de tal manera que aplica la regla que solo las raíces agregadas deben tener repositorios. Puede crear un tipo de almacén genérico o base que restringe al tipo de entidades que funciona con para asegurarse de que tienen la interfaz de marcador IAggregateRoot.

Por lo tanto, cada clase de repositorio que se implementan en el nivel de infraestructura implementa su propio contrato o interfaz, como se muestra en el código siguiente:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
```

Cada interfaz del repositorio específico implementa la interfaz genérica de IRepository:

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

Sin embargo, una mejor manera para que el código de aplicar la convención de que un único agregado debe estar relacionados con cada repositorio sería implementar un tipo de almacén genérico por lo que es explícita que está usando un repositorio para tener como destino un agregado concreto. Esto puede hacer fácilmente mediante la implementación de ese genérico en la interfaz base IRepository, como se muestra en el código siguiente:

```csharp
  public interface IRepository<T> where T : IAggregateRoot
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a>El modelo de repositorio facilita probar la lógica de aplicación

El modelo de repositorio permite fácilmente probar la aplicación en pruebas unitarias. Recuerde que las pruebas unitarias prueba solo su código, no en la infraestructura, por lo que las abstracciones de repositorio que sea más fácil alcanzar ese objetivo.

Como se indicó en una sección anterior, se recomienda que defina y coloque las interfaces de repositorio en el nivel de modelo de dominio por lo que no dependen de la capa de aplicación (por ejemplo, su microservicio API Web) directamente en el nivel de infraestructura que tiene implementa las clases de repositorio real. Al hacerlo y usar inserción de dependencias en los controladores de la API de Web, puede implementar repositorios ficticios que devuelven datos falsos en lugar de datos de la base de datos. Que el enfoque desacoplado le permite crear y las pruebas unitarias de ejecución pueden probar simplemente la lógica de la aplicación sin necesidad de conectividad a la base de datos.

Las conexiones a bases de datos pueden realizarse y, más importante aún, ejecutan centenares de pruebas en una base de datos está dañada por dos motivos. En primer lugar, puede tardar mucho tiempo debido al gran número de pruebas. En segundo lugar, los registros de base de datos pueden cambiar y afectar a los resultados de las pruebas, por lo que podrían no ser coherentes. Pruebas con la base de datos no son una unidad de prueba sino una integración de pruebas. Debería tener muchas pruebas unitarias con rapidez, pero menos integración comprueba en las bases de datos.

En cuanto a la separación de intereses para las pruebas unitarias, la lógica funciona en entidades de dominio en la memoria. Se supone que la clase de repositorio ha entregado los. Una vez que la lógica de modifica las entidades de dominio, se supone que la clase del repositorio los almacenará correctamente. La cuestión importante aquí es crear pruebas unitarias para el modelo de dominio y su lógica de dominio. Las raíces agregadas son los límites de coherencia principal en DDD.

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a>La diferencia entre el modelo de repositorio y el patrón DAL (clase) de acceso a datos heredado

Un objeto de acceso a datos directamente realiza operaciones de acceso y persistencia de datos en almacenamiento. Marcas de repositorio que los datos con las operaciones que desea realizar en la memoria de una unidad de objeto de trabajo (como en EF al usar DbContext), pero estas actualizaciones no se realizará inmediatamente.

Una unidad de trabajo se conoce como una sola transacción que implica varias Insertar, actualizar o eliminar operaciones. En otras palabras, significa que para una acción de usuario específico (por ejemplo, el registro en un sitio Web), el de insert, update y delete transacciones se administran en una sola transacción. Esto es más eficaz que el control de varias transacciones de base de datos de una manera chattier.

Estos varias operaciones de persistencia se realizará más adelante en una sola acción cuando el código de la capa de aplicación los comandos. La decisión sobre cómo aplicar los cambios en memoria para el almacenamiento real de la base de datos normalmente se basa en el [patrón de la unidad de trabajo](http://martinfowler.com/eaaCatalog/unitOfWork.html). En EF, se implementa el patrón de la unidad de trabajo como DBContext.

En muchos casos, este patrón o una forma de aplicar las operaciones en el almacenamiento puede aumentar el rendimiento de la aplicación y reducir la posibilidad de incoherencias. Además, reduce transacciones de bloqueo en las tablas de base de datos, ya que todas las operaciones previstas se confirmará como parte de una transacción. Esto es más eficaz en comparación con la ejecución de muchas operaciones aisladas en la base de datos. Por lo tanto, la ORM seleccionado podrán realizar optimizar la ejecución en la base de datos mediante la agrupación de varias acciones de actualización en la misma transacción, en lugar de varias ejecuciones de transacciones pequeñas e independientes.

### <a name="repositories-should-not-be-mandatory"></a>Repositorios no deberían ser obligatorios

Los repositorios personalizados son útiles para los motivos citados anteriormente, y es el enfoque para la ordenación microservicio en eShopOnContainers. Sin embargo, no es un patrón esencial para implementar en un diseño DDD o incluso en general desarrollo en. NET.

Por ejemplo, Jimmy Bogard, al proporcionar información directa sobre esta guía, dice lo siguiente:

Esto probablemente estará mis comentarios más importantes. Realmente no estoy un ventilador de repositorios, principalmente porque ocultan los detalles importantes del mecanismo de persistencia subyacente. Su ¿por qué ir para MediatR para los comandos, demasiado. Puedo usar toda la funcionalidad de la capa de persistencia e insertar ese comportamiento de dominio en las raíces agregadas. Normalmente no desea simular mi repositorios: sigue siendo necesario tener que la integración de prueba con la acción real. Vaya CQRS significaba que realmente no teníamos una necesidad de repositorios más.

Se encontraron repositorios útil, pero sabemos que no son críticos para el DDD, en la forma en que el patrón de agregado y el modelo de dominio enriquecido son. Por lo tanto, utilice el modelo de repositorio o no, como ver quepa.

#### <a name="additional-resources"></a>Recursos adicionales

##### <a name="the-repository-pattern"></a>El modelo de repositorio

-   **Edward Hieatt y Rob me. Modelo de repositorio. ** 
     [ *http://martinfowler.com/eaaCatalog/repository.html*](http://martinfowler.com/eaaCatalog/repository.html)

-   **El modelo de repositorio**
    [*https://msdn.microsoft.com/en-us/library/ff649690.aspx*](https://msdn.microsoft.com/en-us/library/ff649690.aspx)

-   **Modelo de repositorio: Una persistencia abstracción de datos**
    [*http://deviq.com/repository-pattern/*](http://deviq.com/repository-pattern/)

-   **Eric Evans. Diseño basado en dominio: Realiza para complejidad en el centro de Software.** (Libro; incluye una explicación sobre el modelo de repositorio) [ *https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

##### <a name="unit-of-work-pattern"></a>Unidad de patrón de trabajo

-   **Martin Fowler. Unidad de patrón de trabajo. ** 
     [ *http://martinfowler.com/eaaCatalog/unitOfWork.html*](http://martinfowler.com/eaaCatalog/unitOfWork.html)

<!-- -->

-   **Implementar el repositorio y una unidad de patrones de trabajo en una aplicación de ASP.NET MVC**
    [*https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/ Implementing-the-Repository-and-Unit-of-Work-Patterns-in-an-ASP-NET-MVC-Application*](https://www.asp.net/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application)


>[!div class="step-by-step"]
[Anterior] (dominio-eventos-diseño-implementation.md) [siguiente] (infrastructure-persistence-layer-implemenation-entity-framework-core.md)
