---
title: Diseño de la capa de persistencia de infraestructura
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Información sobre el modelo de repositorio en el diseño de la capa de persistencia de infraestructura.
ms.date: 10/08/2018
ms.openlocfilehash: 1b2665e81ade60affa84563121c04bca08537f07
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988484"
---
# <a name="design-the-infrastructure-persistence-layer"></a>Diseño del nivel de persistencia de infraestructura

Los componentes de persistencia de datos proporcionan acceso a los datos que se hospedan dentro de los límites de un microservicio (es decir, la base de datos de un microservicio). Contienen la implementación real de componentes como repositorios y clases de [unidad de trabajo](https://martinfowler.com/eaaCatalog/unitOfWork.html), como los objetos <xref:Microsoft.EntityFrameworkCore.DbContext> de Entity Framework (EF). DbContext de EF implementa ambos, el repositorio y los patrones de unidad de trabajo.

## <a name="the-repository-pattern"></a>El modelo de repositorio

Los repositorios son clases o componentes que encapsulan la lógica necesaria para tener acceso a orígenes de datos. Centralizan la funcionalidad de acceso a datos comunes, lo que proporciona un mejor mantenimiento y el desacoplamiento de la infraestructura o tecnología que se usa para acceder a bases de datos desde el nivel de modelo de dominio. Si se usa un asignador relacional de objetos (ORM) como Entity Framework, se simplifica el código que se debe implementar, gracias a LINQ y al establecimiento inflexible de tipos. Esto permite centrarse en la lógica de persistencia de datos en lugar del establecimiento del acceso a los datos.

El modelo de repositorio es una manera bien documentada de trabajar con un origen de datos. En el libro [Patterns of Enterprise Application Architecture](https://www.amazon.com/Patterns-Enterprise-Application-Architecture-Martin/dp/0321127420/) (Patrones de arquitectura de aplicaciones empresariales), Martin Fowler describe un repositorio de esta forma:

> Un repositorio realiza las tareas de un intermediario entre los niveles de modelo de dominio y asignación de datos, actuando de forma similar a un conjunto de objetos de dominio en memoria. Los objetos de cliente generan consultas mediante declaraciones y las envían a los repositorios para obtener las respuestas. Conceptualmente, un repositorio encapsula un conjunto de objetos almacenados en la base de datos y las operaciones que se pueden realizar en ellos, proporcionando una manera de que esté más cerca de la capa de persistencia. Además, los repositorios admiten la finalidad de separar, con claridad y en una dirección, la dependencia entre el dominio de trabajo y la asignación de datos.

### <a name="define-one-repository-per-aggregate"></a>Definir un repositorio por agregado

Para cada agregado o raíz agregada, se debe crear una clase de repositorio. En un microservicio basado en patrones de diseño controlado por dominios (DDD), el único canal que se debe usar para actualizar la base de datos deben ser los repositorios. Esto se debe a que tienen una relación uno a uno con la raíz agregada, que controla los elementos invariables del agregado y la coherencia transaccional. Es correcto consultar la base de datos a través de otros canales (como con un enfoque CQRS), dado que las consultas no cambian el estado de la base de datos. Pero el área transaccional (es decir, las actualizaciones) siempre se debe controlar mediante los repositorios y las raíces agregadas.

Básicamente, un repositorio permite rellenar los datos en memoria que proceden de la base de datos en forma de entidades de dominio. Una vez que las entidades se encuentran en memoria, se pueden cambiar y después volver a conservar en la base de datos a través de transacciones.

Como se indicó anteriormente, si se usa el modelo de arquitectura de CQS/CQRS, las consultas iniciales se realizan por medio de consultas paralelas fuera del modelo de dominio, ejecutadas por instrucciones SQL simples mediante Dapper. Este enfoque es mucho más flexible que los repositorios, ya que se pueden consultar y combinar las tablas que se necesitan, y estas consultas no están limitadas por las reglas de los agregados. Esos datos van a la capa de presentación o a la aplicación cliente.

Si el usuario realiza cambios, los datos que se van a actualizar proceden de la aplicación cliente o la capa de presentación al nivel de la aplicación (por ejemplo, un servicio de API web). Cuando se recibe un comando en un controlador de comandos, se usan repositorios para obtener los datos que se quieren actualizar desde la base de datos. Se actualiza en memoria con los datos que se pasa con los comandos y después se agregan o actualizan los datos (entidades de dominio) en la base de datos a través de una transacción.

Es importante destacar de nuevo que solo se debe definir un repositorio para cada raíz agregada, como se muestra en la figura 7-17. Para lograr el objetivo de la raíz agregada de mantener la coherencia transaccional entre todos los objetos del agregado, nunca se debe crear un repositorio para cada tabla de la base de datos.

![Diagrama que muestra las relaciones de dominio y otra infraestructura.](./media/infrastructure-persistence-layer-design/repository-aggregate-database-table-relationships.png)

**Figura 7-17**. La relación entre repositorios, agregados y tablas de base de datos

En el diagrama anterior se muestran las relaciones entre las capas de dominio e infraestructura: el agregado Comprador depende del IBuyerRepository y el agregado Pedido depende de las interfaces de IOrderRepository, estas interfaces se implementan en el nivel de infraestructura por los repositorios correspondientes que dependen de UnitOfWork, también implementada allí, que accede a las tablas del nivel de datos.

### <a name="enforce-one-aggregate-root-per-repository"></a>Aplicación de una raíz agregada por repositorio

Puede ser útil implementar el diseño de repositorio de tal manera que aplique la regla de que solo las raíces agregadas deban tener repositorios. Puede crear un tipo de repositorio base o genérico que limite el tipo de las entidades con las que funciona para asegurarse de que tengan la interfaz de marcador `IAggregateRoot`.

Por tanto, cada clase de repositorio que se implemente en el nivel de infraestructura implementa su propio contrato o interfaz, como se muestra en el código siguiente:

```csharp
namespace Microsoft.eShopOnContainers.Services.Ordering.Infrastructure.Repositories
{
    public class OrderRepository : IOrderRepository
    {
      // ...
    }
}
```

Cada interfaz de repositorio específica implementa la interfaz genérica IRepository:

```csharp
public interface IOrderRepository : IRepository<Order>
{
    Order Add(Order order);
    // ...
}
```

Pero una manera mejor de que el código aplique la convención de que cada repositorio esté relacionado con un único agregado consiste en implementar un tipo de repositorio genérico. De este modo, es explícito que se está usando un repositorio para tener como destino un agregado concreto. Eso se puede hacer fácilmente mediante la implementación de una interfaz base `IRepository` genérica, como se muestra en el código siguiente:

```csharp
public interface IRepository<T> where T : IAggregateRoot
{
    //....
}
```

### <a name="the-repository-pattern-makes-it-easier-to-test-your-application-logic"></a>El modelo de repositorio facilita probar la lógica de la aplicación

El modelo de repositorio permite probar fácilmente la aplicación en pruebas unitarias. Recuerde que en las pruebas unitarias solo se prueba el código, no la infraestructura, por lo que las abstracciones de repositorio facilitan alcanzar ese objetivo.

Como se indicó en una sección anterior, se recomienda definir y colocar las interfaces de repositorio en el nivel de modelo de dominio para que el nivel de aplicación (como el microservicio de API web) no dependa directamente del nivel de infraestructura en el que se han implementado las clases de repositorio reales. Al hacer esto y usar la inserción de dependencias en los controladores de la API web, puede implementar repositorios ficticios que devuelven datos falsos en lugar de datos de la base de datos. Ese enfoque desacoplado permite crear y ejecutar pruebas unitarias que centran la lógica de la aplicación sin necesidad de conectividad a la base de datos.

Se pueden producir errores en las conexiones a las bases de datos y, más importante aún, la ejecución de centenares de pruebas en una base de datos no es recomendable por dos motivos. En primer lugar, puede tardar mucho tiempo debido al gran número de pruebas. En segundo lugar, es posible que los registros de base de datos cambien y afecten a los resultados de las pruebas, por lo que podrían no ser coherentes. Realizar pruebas en la base de datos no es una prueba unitaria sino una prueba de integración. Debería tener muchas pruebas unitarias que se ejecuten con rapidez, pero menos pruebas de integración sobre las bases de datos.

En cuanto a la separación de intereses para las pruebas unitarias, la lógica funciona en entidades de dominio en memoria, ya que supone que la clase de repositorio las ha entregado. Una vez que la lógica modifica las entidades de dominio, asume que la clase del repositorio las almacenará correctamente. El aspecto importante aquí es crear pruebas unitarias para el modelo de dominio y su lógica de dominio. Las raíces agregadas son los límites de coherencia principales en DDD.

Los repositorios que se implementan en eShopOnContainers se basan en la implementación de DbContext de EF Core de los patrones de repositorio y unidad de trabajo mediante el seguimiento de cambios, por lo que no duplican esta funcionalidad.

### <a name="the-difference-between-the-repository-pattern-and-the-legacy-data-access-class-dal-class-pattern"></a>La diferencia entre el modelo de repositorio y el patrón de clases de acceso a datos (DAL) heredado

Un objeto de acceso a datos realiza directamente operaciones de acceso y persistencia de datos en el almacenamiento. Un repositorio marca los datos con las operaciones que se quieren realizar en la memoria de un objeto de unidad de trabajo (como sucede en EF al usar la clase <xref:Microsoft.EntityFrameworkCore.DbContext>), pero estas actualizaciones no se realizan de forma inmediata en la base de datos.

Una unidad de trabajo se conoce como una sola transacción que implica varias operaciones de inserción, actualización o eliminación. En otras palabras, significa que para una acción de usuario específica (como el registro en un sitio web) todas las transacciones de inserción, actualización o eliminación se administran en una única operación. Esto es más eficaz que el control de varias transacciones de base de datos de una manera profusa.

Estos operaciones de persistencia múltiples se realizan más adelante en una sola acción cuando el código del nivel de aplicación lo ordena. La decisión sobre cómo aplicar los cambios en memoria al almacenamiento de base de datos real normalmente se basa en el [patrón de unidades de trabajo](https://martinfowler.com/eaaCatalog/unitOfWork.html). En EF, el patrón de unidades de trabajo se implementa como el <xref:Microsoft.EntityFrameworkCore.DbContext>.

En muchos casos, este patrón o forma de aplicar operaciones en el almacenamiento puede aumentar el rendimiento de la aplicación y reducir la posibilidad de incoherencias. También reduce el bloqueo de transacciones en las tablas de base de datos, ya que todas las operaciones previstas se confirman como parte de una transacción. Esto es más eficaz en comparación con la ejecución de muchas operaciones aisladas en la base de datos. Por tanto, el ORM seleccionado puede optimizar la ejecución en la base de datos mediante la agrupación de varias acciones de actualización en la misma transacción, en lugar de muchas ejecuciones de transacciones pequeñas e independientes.

### <a name="repositories-shouldnt-be-mandatory"></a>Los repositorios no deben ser obligatorios

Los repositorios personalizados son útiles por los motivos citados anteriormente, y es el enfoque para el microservicio de pedidos de eShopOnContainers. Pero no es un patrón esencial para implementar en un diseño de DDD o incluso en el desarrollo general de .NET.

Por ejemplo, Jimmy Bogard, al proporcionar información directa para esta guía, afirmó lo siguiente:

> Este probablemente sea mi comentario más importante. No soy un gran defensor de los repositorios, sobre todo porque ocultan los detalles importantes del mecanismo de persistencia subyacente. Por ese motivo también prefiero MediatR para los comandos. Puedo usar toda la funcionalidad de la capa de persistencia e insertar todo ese comportamiento de dominio en las raíces agregadas. Normalmente no me interesa simular los repositorios: sigo necesitando que esa prueba de integración esté con la acción real. La elección de CQRS significaba que realmente ya no necesitábamos los repositorios.

Los repositorios pueden ser útiles, pero no esenciales para el diseño de DDD, de la misma forma que el patrón de agregado y el modelo de dominio enriquecido lo son. Por tanto, use el modelo de repositorio o no, como considere oportuno. En cualquier caso, se usará el modelo de repositorio siempre que se use EF Core aunque, en este caso, el repositorio abarca todo el microservicio o contexto delimitado.

## <a name="additional-resources"></a>Recursos adicionales

### <a name="repository-pattern"></a>Modelo de repositorio

- **Edward Hieatt y Rob Mee. Modelo de repositorio.** \
  <https://martinfowler.com/eaaCatalog/repository.html>

- **The Repository Pattern** \ (El modelo de repositorio)\
  <https://docs.microsoft.com/previous-versions/msp-n-p/ff649690(v=pandp.10)>

- **Eric Evans. Diseño orientado al dominio: Tackling Complexity in the Heart of Software.** (Diseño orientado al dominio: abordar la complejidad en el corazón del software)\ (Libro; incluye un debate sobre el patrón de repositorio) \
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

### <a name="unit-of-work-pattern"></a>Patrón de unidades de trabajo

- **Martin Fowler. Unit of Work pattern** (Patrón de unidades de trabajo).\ \
  <https://martinfowler.com/eaaCatalog/unitOfWork.html>

- **Implementing the Repository and Unit of Work Patterns in an ASP.NET MVC Application** \ (Implementación de los patrones de repositorio y unidad de trabajo en una aplicación ASP.NET MVC)\
  <https://docs.microsoft.com/aspnet/mvc/overview/older-versions/getting-started-with-ef-5-using-mvc-4/implementing-the-repository-and-unit-of-work-patterns-in-an-asp-net-mvc-application>

>[!div class="step-by-step"]
>[Anterior](domain-events-design-implementation.md)
>[Siguiente](infrastructure-persistence-layer-implemenation-entity-framework-core.md)
