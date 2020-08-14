---
title: Probar aplicaciones web y servicios ASP.NET Core
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Descubra una arquitectura para probar aplicaciones web y servicios ASP.NET Core en contenedores.
ms.date: 08/07/2020
ms.openlocfilehash: a27b3b8d392c5e1a7d1961307e6de95659cd823e
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024607"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a>Probar aplicaciones web y servicios ASP.NET Core

Los controladores son una parte fundamental de cualquier servicio de la API de ASP.NET Core y de la aplicación web de ASP.NET MVC. Por lo tanto, debe tener la seguridad de que se comportan según lo previsto en la aplicación. Las pruebas automatizadas pueden darle esta seguridad, así como detectar errores antes de que lleguen a la fase producción.

Debe probar cómo se comporta el controlador según las entradas válidas o no válidas y probar las respuestas del controlador en función del resultado de la operación comercial que lleve a cabo. Pero debe realizar estos tipos de pruebas en los microservicios:

- Pruebas unitarias. Esto garantiza que los componentes individuales de la aplicación funcionan según lo previsto. Las aserciones prueban la API del componente.

- Pruebas de integración. Esto garantiza que las interacciones del componente funcionen según lo previsto con los artefactos externos como bases de datos. Las aserciones pueden poner a prueba la API del componente, la interfaz de usuario o los efectos secundarios de acciones como la E/S de la base de datos, el registro, etc.

- Pruebas funcionales para cada microservicio. Esto garantiza que la aplicación funcione según lo esperado desde la perspectiva del usuario.

- Pruebas de servicio. Esto garantiza que se pongan a prueba todos los casos de uso de servicio de un extremo a otro, incluidas pruebas de servicios múltiples al mismo tiempo. Para este tipo de prueba, primero debe preparar el entorno. En este caso, esto significa iniciar los servicios (por ejemplo, mediante el uso de docker-compose up).

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>Implementación de pruebas unitarias para las API web de ASP.NET Core

Las pruebas unitarias conllevan probar una parte de una aplicación de forma aislada con respecto a su infraestructura y dependencias. Cuando se realizan pruebas unitarias de la lógica de controlador, solo se comprueba el método o el contenido de una única acción, no el comportamiento de sus dependencias o del marco en sí. Con todo, las pruebas unitarias no detectan problemas de interacción entre componentes; este es el propósito de las pruebas de integración.

Cuando realice pruebas unitarias de sus acciones de controlador, asegúrese de centrarse solamente en su comportamiento. Una prueba unitaria de controlador evita elementos como filtros, el enrutamiento o enlaces de modelos (la asignación de datos de solicitud a un ViewModel o DTO). Como se centran en comprobar solo una cosa, las pruebas unitarias suelen ser fáciles de escribir y rápidas de ejecutar. Un conjunto de pruebas unitarias bien escrito se puede ejecutar con frecuencia sin demasiada sobrecarga.

Las pruebas unitarias se implementan en función de los marcos de pruebas como xUnit.net, MSTest, Moq o NUnit. En la aplicación de ejemplo eShopOnContainers, se usa XUnit.

Al escribir una prueba unitaria para un controlador de API web, puede ejemplificar directamente la clase de controlador mediante la nueva palabra clave en C\#, para que la prueba se ejecute tan rápido como sea posible. En el ejemplo siguiente se muestra cómo hacerlo con [XUnit](https://xunit.github.io/) como marco de pruebas.

```csharp
[Fact]
public async Task Get_order_detail_success()
{
    //Arrange
    var fakeOrderId = "12";
    var fakeOrder = GetFakeOrder();

    //...

    //Act
    var orderController = new OrderController(
        _orderServiceMock.Object,
        _basketServiceMock.Object,
        _identityParserMock.Object);

    orderController.ControllerContext.HttpContext = _contextMock.Object;
    var actionResult = await orderController.Detail(fakeOrderId);

    //Assert
    var viewResult = Assert.IsType<ViewResult>(actionResult);
    Assert.IsAssignableFrom<Order>(viewResult.ViewData.Model);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>Implementación de pruebas funcionales y de integración para cada microservicio

Como se ha indicado, las pruebas funcionales y de integración tienen objetivos y propósitos diferentes. Pero la forma de implementarlas para probar los controladores de ASP.NET Core es similar, por lo que en esta sección nos centraremos en las pruebas de integración.

Las pruebas de integración garantizan que los componentes de una aplicación funcionen correctamente durante el ensamblaje. ASP.NET Core admite las pruebas de integración que usan marcos de pruebas unitarias y un host de web de prueba integrado que puede usarse para controlar las solicitudes sin sobrecargar la red.

A diferencia de las pruebas unitarias, las pruebas de integración suelen incluir problemas de infraestructura de la aplicación, como base de datos, sistema de archivos, recursos de red o solicitudes web, y sus respuestas. Para las pruebas unitarias se usan emulaciones u objetos ficticios en lugar de estos problemas. Pero el propósito de las pruebas de integración es confirmar que el sistema funciona según lo previsto con estos sistemas, por lo que para las pruebas de integración no se usan simulaciones ni objetos ficticios. En cambio, se incluye la infraestructura, como el acceso a la base de datos o la invocación del servicio desde otros servicios.

Como las pruebas de integración usan segmentos de código más grandes que las pruebas unitarias y dependen de los elementos de infraestructura, tienden a ser órdenes de envergadura, más lentas que las pruebas unitarias. Por lo tanto, es conveniente limitar el número de pruebas de integración que va a escribir y a ejecutar.

ASP.NET Core incluye un host web de prueba integrado que puede usarse para controlar las solicitudes HTTP sin causar una sobrecarga en la red, lo que significa que puede ejecutar dichas pruebas más rápidamente si usa un host de web real. El host web de prueba (TestServer) está disponible en un componente NuGet como Microsoft.AspNetCore.TestHost. Se puede agregar a proyectos de prueba de integración y utilizarlo para hospedar aplicaciones de ASP.NET Core.

Como puede ver en el código siguiente, al crear pruebas de integración para controladores de ASP.NET Core, los controladores se ejemplifican a través del host de prueba. Esto se puede comparar a una solicitud HTTP, pero se ejecuta con mayor rapidez.

```csharp
public class PrimeWebDefaultRequestShould
{
    private readonly TestServer _server;
    private readonly HttpClient _client;

    public PrimeWebDefaultRequestShould()
    {
        // Arrange
        _server = new TestServer(new WebHostBuilder()
           .UseStartup<Startup>());
           _client = _server.CreateClient();
    }

    [Fact]
    public async Task ReturnHelloWorld()
    {
        // Act
        var response = await _client.GetAsync("/");
        response.EnsureSuccessStatusCode();
        var responseString = await response.Content.ReadAsStringAsync();
        // Assert
        Assert.Equal("Hello World!", responseString);
    }
}
```

#### <a name="additional-resources"></a>Recursos adicionales

- **Steve Smith. Controladores de pruebas** (ASP.NET Core) \
    [https://docs.microsoft.com/aspnet/core/mvc/controllers/testing](/aspnet/core/mvc/controllers/testing)

- **Steve Smith. Pruebas de integración** (ASP.NET Core) \
    [https://docs.microsoft.com/aspnet/core/test/integration-tests](/aspnet/core/test/integration-tests)

- **Pruebas unitarias en .NET Core con dotnet test** \
    [https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test](../../../core/testing/unit-testing-with-dotnet-test.md)

- **xUnit.net**. Sitio oficial. \
    <https://xunit.github.io/>

- **Unit Test Basics** (Conceptos básicos de prueba unitaria). \
    [https://docs.microsoft.com/visualstudio/test/unit-test-basics](/visualstudio/test/unit-test-basics)

- **Moq**. Repositorio de GitHub. \
    <https://github.com/moq/moq>

- **NUnit**. Sitio oficial. \
    <https://www.nunit.org/>

### <a name="implementing-service-tests-on-a-multi-container-application"></a>Implementación de pruebas de servicio en una aplicación con varios contenedores

Como se indicó anteriormente, al probar aplicaciones con varios contenedores, todos los microservicios deben ejecutarse en el host de Docker o en un clúster de contenedor. Las pruebas de servicio de un extremo a otro que incluyen varias operaciones que implican varios microservicios requieren que implemente e inicie la aplicación en el host de Docker mediante la ejecución de docker-compose up (o un mecanismo comparable si usa un orquestador). Cuando la aplicación y todos sus servicios se estén ejecutando, podrá ejecutar pruebas funcionales y de integración de un extremo a otro.

Puede usar diferentes enfoques. En el archivo docker-compose.yml que se usa para implementar la aplicación en el nivel de solución puede expandir el punto de entrada para usar [dotnet test](../../../core/tools/dotnet-test.md). También puede usar otro archivo de composición que ejecute las pruebas en la imagen de destino. Si utiliza otro archivo de composición para las pruebas de integración, que incluyan sus microservicios y bases de datos en contenedores, puede comprobar que los datos relacionados siempre se restablecen a su estado original antes de ejecutar las pruebas.

Si ejecuta Visual Studio, cuando la aplicación de redacción esté en funcionamiento, podrá aprovechar los puntos de interrupción y las excepciones. También podrá ejecutar las pruebas de integración automáticamente en la canalización de integración continua en Azure DevOps Services o en cualquier otro sistema de integración continua o de entrega continua que admita los contenedores de Docker.

## <a name="testing-in-eshoponcontainers"></a>Realización de pruebas en eShopOnContainers

Recientemente se han reestructurado las pruebas de referencia de la aplicación (eShopOnContainers) y ahora hay cuatro categorías:

1. **Pruebas unitarias**, simples pruebas unitarias normales, incluidas en los proyectos **{MicroserviceName}.UnitTests**

2. **Pruebas de integración o funcionales de microservicio**, con casos de prueba que implican la infraestructura para cada microservicio, pero aisladas de los demás, y están incluidas en los proyectos **{MicroserviceName}. FunctionalTests**.

3. **Pruebas funcionales o de integración de aplicación**, que se centran en la integración de microservicios, con casos de prueba para ejercer varios microservicios. Estas pruebas se encuentran en el proyecto **Application.FunctionalTests**.

Las pruebas unitarias y de integración por microservicio se incluyen en una carpeta de prueba en cada microservicio y las pruebas de carga y aplicación se incluyen en la carpeta de pruebas de la carpeta de soluciones, como se muestra en la figura 6-25.

![Captura de pantalla de VS que apunta a algunos de los proyectos de prueba de la solución.](./media/test-aspnet-core-services-web-apps/eshoponcontainers-test-folder-structure.png)

**Figura 6-25**. Estructura de carpetas de prueba en eShopOnContainers

Las pruebas de integración y funcionales de microservicios y aplicaciones se ejecutan desde Visual Studio, mediante el ejecutor de pruebas periódicas, pero primero debe iniciar los servicios de infraestructura necesarios, por medio de un conjunto de archivos docker-compose incluidos en la carpeta de prueba de la solución:

**docker-compose-test.yml**

```yml
version: '3.4'

services:
  redis.data:
    image: redis:alpine
  rabbitmq:
    image: rabbitmq:3-management-alpine
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
  nosqldata:
    image: mongo
```

**docker-compose-test.override.yml**

```yml
version: '3.4'

services:
  redis.data:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"
  sqldata:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
```

Por tanto, para ejecutar las pruebas de integración y funcionales primero debe ejecutar este comando, desde la carpeta de prueba de la solución:

```console
docker-compose -f docker-compose-test.yml -f docker-compose-test.override.yml up
```

Como puede ver, estos archivos docker-compose solo inician los microservicios Redis, RabbitMQ, SQL Server y MongoDB.

### <a name="additional-resources"></a>Recursos adicionales

- **Pruebas unitarias y de integración** en eShopOnContainers \
    <https://github.com/dotnet-architecture/eShopOnContainers/wiki/Unit-and-integration-testing>

- **Pruebas de carga** en eShopOnContainers \
    <https://github.com/dotnet-architecture/eShopOnContainers/wiki/Load-testing>

> [!div class="step-by-step"]
> [Anterior](subscribe-events.md)
> [Siguiente](background-tasks-with-ihostedservice.md)
