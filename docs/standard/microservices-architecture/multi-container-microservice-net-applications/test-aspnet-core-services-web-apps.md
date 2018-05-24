---
title: Probar aplicaciones web y servicios ASP.NET Core
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Probar aplicaciones web y servicios ASP.NET Core
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: b3aa0d50ba3ab64440ef51201d611177fea78ce4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="testing-aspnet-core-services-and-web-apps"></a>Probar aplicaciones web y servicios ASP.NET Core

Los controladores son una parte fundamental de cualquier servicio de la API de ASP.NET Core y de la aplicación web de ASP.NET MVC. Por lo tanto, debe tener la seguridad de que se comportan según lo previsto en la aplicación. Las pruebas automatizadas pueden darle esta seguridad, así como detectar errores antes de que lleguen a la fase producción.

Debe probar cómo se comporta el controlador según las entradas válidas o no válidas y probar las respuestas del controlador en función del resultado de la operación comercial que lleve a cabo. Pero debe realizar estos tipos de pruebas en sus microservicios:

-   Pruebas unitarias. Esto garantiza que los componentes individuales de la aplicación funcionan según lo previsto. Las aserciones prueban la API del componente.

-   Pruebas de integración. Esto garantiza que las interacciones del componente funcionen según lo previsto con los artefactos externos como bases de datos. Las aserciones pueden poner a prueba la API del componente, la interfaz de usuario o los efectos secundarios de acciones como la E/S de la base de datos, el registro, etc.

-   Pruebas funcionales para cada microservicio. Esto garantiza que la aplicación funcione según lo esperado desde la perspectiva del usuario.

-   Pruebas de servicio. Esto garantiza que se pongan a prueba todos los casos de uso de servicio de un extremo a otro, incluidas pruebas de servicios múltiples al mismo tiempo. Para este tipo de prueba, primero debe preparar el entorno. En este caso, esto significa iniciar los servicios (por ejemplo, mediante el uso de Docker Compose).

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>Implementación de pruebas unitarias para las API web de ASP.NET Core

Las pruebas unitarias conllevan probar una parte de una aplicación de forma aislada con respecto a su infraestructura y dependencias. Cuando se realizan pruebas unitarias de la lógica de controlador, solo se comprueba el método o el contenido de una única acción, no el comportamiento de sus dependencias o del marco en sí. Con todo, las pruebas unitarias no detectan problemas de interacción entre componentes; este es el propósito de las pruebas de integración.

Cuando realice pruebas unitarias de sus acciones de controlador, asegúrese de centrarse solamente en su comportamiento. Una prueba unitaria de controlador evita tener que recurrir a elementos como los filtros, el enrutamiento o el enlace de modelos. Como se centran en comprobar solo una cosa, las pruebas unitarias suelen ser fáciles de escribir y rápidas de ejecutar. Un conjunto de pruebas unitarias bien escrito se puede ejecutar con frecuencia sin demasiada sobrecarga.

Las pruebas unitarias se implementan en función de los marcos de pruebas como xUnit.net, MSTest, Moq o NUnit. Para la aplicación de ejemplo eShopOnContainers, usamos XUnit.

Al escribir una prueba unitaria para un controlador de API web, puede ejemplificar directamente la clase de controlador mediante la nueva palabra clave en C\#, para que la prueba se ejecute tan rápido como sea posible. En el ejemplo siguiente se muestra cómo hacerlo utilizando [XUnit](https://xunit.github.io/) como marco de pruebas.

```csharp
[Fact]
public void Add_new_Order_raises_new_event()
{
    // Arrange
    var street = " FakeStreet ";
    var city = "FakeCity";
    // Other variables omitted for brevity ...
    // Act
    var fakeOrder = new Order(new Address(street, city, state, country, zipcode),
        cardTypeId, cardNumber,
        cardSecurityNumber, cardHolderName,
        cardExpiration);
    // Assert
    Assert.Equal(fakeOrder.DomainEvents.Count, expectedResult);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>Implementación de pruebas funcionales y de integración para cada microservicio

Como se ha indicado, las pruebas funcionales y de integración tienen objetivos y propósitos diferentes. Pero la forma de implementarlas para probar los controladores de ASP.NET Core es similar, por lo que en esta sección nos centraremos en las pruebas de integración.

Las pruebas de integración garantizan que los componentes de una aplicación funcionen correctamente durante el ensamblaje. ASP.NET Core admite las pruebas de integración que usan marcos de pruebas unitarias y un host de web de prueba integrado que puede usarse para controlar las solicitudes sin sobrecargar la red.

A diferencia de las pruebas unitarias, las pruebas de integración suelen incluir problemas de infraestructura de la aplicación, como base de datos, sistema de archivos, recursos de red o solicitudes web, y sus respuestas. Para las pruebas unitarias se usan emulaciones u objetos ficticios en lugar de estos problemas. Pero el propósito de las pruebas de integración es confirmar que el sistema funciona según lo previsto con estos sistemas, por lo que para las pruebas de integración no se usan simulaciones ni objetos ficticios. En cambio, se incluye la infraestructura, como el acceso a la base de datos o la invocación del servicio desde otros servicios.

Como las pruebas de integración usan segmentos de código más grandes que las pruebas unitarias y dependen de los elementos de infraestructura, tienden a ser órdenes de envergadura, más lentas que las pruebas unitarias. Por lo tanto, es conveniente limitar el número de pruebas de integración que va a escribir y a ejecutar.

ASP.NET Core incluye un host de web de prueba integrado que puede usarse para controlar las solicitudes HTTP sin causar una sobrecarga en la red, lo que significa que puede ejecutar dichas pruebas más rápidamente si usa un host de web real. El host de web de prueba está disponible en un componente NuGet como Microsoft.AspNetCore.TestHost. Se puede agregar a proyectos de prueba de integración y utilizarlo para hospedar aplicaciones de ASP.NET Core.

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

-   **Steve Smith. Testing controllers** (ASP.NET Core) (Probar controladores [ASP.NET Core])[*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)

-   **Steve Smith. Integration testing** (ASP.NET Core) (Pruebas de integración [ASP.NET Core])[*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](/aspnet/core/testing/integration-testing)

-   **Unit testing in .NET Core using dotnet test (Pruebas unitarias de .NET Core con dotnet test)**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)

-   **xUnit.net**. Sitio oficial.
    [*https://xunit.github.io/*](https://xunit.github.io/)

-   **Conceptos básicos de prueba unitaria**
    [*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)

-   **Moq**. Repositorio de GitHub.
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   **NUnit**. Sitio oficial.
    [*https://www.nunit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a>Implementación de pruebas de servicio en una aplicación con varios contenedores 

Como se indicó anteriormente, al probar aplicaciones con varios contenedores, todos los microservicios deben ejecutarse en el host de Docker o en un clúster de contenedor. Las pruebas de servicio de un extremo a otro que incluyen varias operaciones que implican varios microservicios requieren que implemente e inicie la aplicación en el host de Docker mediante la ejecución de Docker Compose (o un mecanismo comparable si usa un orquestador). Cuando la aplicación y todos sus servicios se estén ejecutando, podrá ejecutar pruebas funcionales y de integración de un extremo a otro.

Puede usar diferentes enfoques. En el archivo docker-compose.yml que va a usar para implementar la aplicación (o en archivos similares, como docker-compose.ci.build.yml), en el nivel de solución puede expandir el punto de entrada para usar la [prueba de dotnet](../../../core/tools/dotnet-test.md). También puede usar otro archivo de composición que ejecute las pruebas en la imagen de destino. Si utiliza otro archivo de composición para las pruebas de integración, que incluyan sus microservicios y bases de datos en contenedores, puede comprobar que los datos relacionados siempre se restablecen a su estado original antes de ejecutar las pruebas.

Si ejecuta Visual Studio, cuando la aplicación de redacción esté en funcionamiento, podrá aprovechar los puntos de interrupción y las excepciones. También podrá ejecutar las pruebas de integración automáticamente en la canalización de integración continua en Visual Studio Team Services o en cualquier otro sistema de integración continua o de entrega continua que admita los contenedores de Docker.

>[!div class="step-by-step"]
[Anterior] (subscribe-events.md) [Siguiente] (../microservice-ddd-cqrs-patterns/index.md)
