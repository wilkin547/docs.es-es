---
title: Probar aplicaciones web y servicios principales de ASP.NET
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Probar aplicaciones web y servicios principales de ASP.NET
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f756a679befee676db2bf6d402fd7e34b1621b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="testing-aspnet-core-services-and-web-apps"></a>Probar aplicaciones web y servicios principales de ASP.NET

Los controladores son una parte fundamental de cualquier servicio de API de núcleo de ASP.NET y la aplicación Web de MVC de ASP.NET. Por lo tanto, debe tener confianza que se comportan según lo previsto para su aplicación. Las pruebas automatizadas pueden proporcionarle esta confianza y pueden detectar errores antes de que lleguen a producción.

Debe probar cómo se comporta según las entradas válidas o no es válidas el dispositivo y probar las respuestas de controlador en función del resultado de la operación de negocio que lleva a cabo. Sin embargo, debe tener su microservicios estos tipos de pruebas:

-   Las pruebas unitarias. Esto garantiza que los componentes individuales de la aplicación funcionan según lo previsto. Las aserciones de la API de componente de pruebas.

-   Pruebas de integración. Esto garantiza que las interacciones de componente funcionan según lo previsto con los artefactos externos como bases de datos. Pueden probar las aserciones de la API de componente, interfaz de usuario o los efectos secundarios de acciones como la E/S de base de datos, registro, etcetera.

-   Pruebas funcionales para cada microservicio. Esto garantiza que la aplicación funciona según lo esperado desde la perspectiva del usuario.

-   Servicio de prueba. Esto garantiza que todos los casos de uso de service to-end, incluidas las pruebas de varios servicios al mismo tiempo, se prueban. Para este tipo de prueba, debe preparar el entorno en primer lugar. En este caso, significa que a partir de los servicios (por ejemplo, mediante el uso de docker-constituyen una).

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>Implementación pruebas unitarias para las API Web de ASP.NET Core

Pruebas unitarias implica probar una parte de una aplicación de forma aislada de su infraestructura y las dependencias. Cuando realice pruebas unitarias en lógica de controlador, solo el contenido de una sola acción o método se ha probado, no el comportamiento de sus dependencias o el marco de trabajo. Pruebas unitarias no detectan problemas en la interacción entre componentes, es decir, el propósito de las pruebas de integración.

Como unidad probar las acciones de controlador, asegúrese de que solo se centran en su comportamiento. Una prueba unitaria de controlador evita aspectos como filtros, enrutamiento o el enlace de modelos. Dado que se centran en las pruebas de un solo elemento, pruebas unitarias suelen ser fáciles de escribir y rápida ejecutar. Con frecuencia se puede ejecutar un conjunto de pruebas unitarias bien escrito sin mucho sobrecarga.

Pruebas unitarias se implementan en función de los marcos de pruebas como xUnit.net, MSTest, Moq o NUnit. Para la aplicación de ejemplo eShopOnContainers, usamos XUnit.

Al escribir una prueba unitaria para un controlador de API Web, cree una instancia de la clase de controlador directamente mediante la palabra clave new en C\#, para que la prueba se ejecute tan rápido como sea posible. En el ejemplo siguiente se muestra cómo hacer esto si usa [XUnit](https://xunit.github.io/) como el marco de pruebas.

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>Implementación de la integración y pruebas funcionales para cada microservicio

Como se indicó, pruebas de integración y pruebas funcionales tengan objetivos y propósitos diferentes. Sin embargo, la forma de implementar ambos al probar los controladores de ASP.NET Core es similar, por lo que en esta sección se concentrarse en las pruebas de integración.

Pruebas de integración garantizan que los componentes de una aplicación funcionan correctamente cuando se ensambla. Integración de es compatible con ASP.NET Core pruebas con marcos de pruebas unitarias y un host de web de prueba integrados que puede usarse para controlar las solicitudes sin la sobrecarga de la red.

A diferencia de pruebas unitarias, pruebas de integración suelen incluyen problemas de infraestructura de la aplicación, como una base de datos, sistema de archivos, recursos de red, o las solicitudes web y las respuestas. Pruebas unitarias usar fakes o simular objetos en lugar de estos problemas. Pero el propósito de las pruebas de integración confirmar que el sistema funciona según lo previsto con estos sistemas, por lo que para las pruebas de integración no usar fakes o simular objetos. En su lugar, se incluye la infraestructura, como la invocación de acceso o de servicio de base de datos de otros servicios.

Dado las pruebas de integración ejercer mayor segmentos de código de pruebas unitarias, y debido a las pruebas de integración se basan en los elementos de infraestructura, tienden a ser órdenes de magnitud más lentas que las pruebas unitarias. Por lo tanto, es conveniente limitar cuántas pruebas de integración se escribe y ejecuta.

ASP.NET Core incluye un host de web prueba integrados que puede usarse para controlar las solicitudes HTTP sin la sobrecarga de la red, lo que significa que puede ejecutar dichas pruebas más rápidamente cuando se utiliza un host de web real. El host de prueba web está disponible en un componente de NuGet como Microsoft.AspNetCore.TestHost. Se pueden agregar a proyectos de prueba de integración y utilizado para hospedar ASP.NET Core aplicaciones.

Como puede ver en el código siguiente, al crear pruebas de integración de ASP.NET Core controladores, para crear instancias de los controladores a través del host de prueba. Esto es comparable a una solicitud HTTP, pero se ejecuta con mayor rapidez.

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

-   **Steve Smith. Probar controladores** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)

-   **Steve Smith. Pruebas de integración** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)

-   **Pruebas unitarias en .NET Core con prueba dotnet**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)

-   **xUnit.net**. Sitio oficial.
    [*https://xUnit.github.IO/*](https://xunit.github.io/)

-   **Conceptos básicos de prueba unitaria. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)

-   **Moq**. Repositorio de GitHub.
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   **NUnit**. Sitio oficial.
    [*https://www.NUnit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a>Implementación de servicio de pruebas en una aplicación de contenedor de varios 

Como se indicó anteriormente, al probar aplicaciones de contenedor múltiples, todas las microservicios deben ejecutar en el clúster de host o un contenedor de Docker. Pruebas de servicio de extremo a extremo que incluyen varias operaciones que implican varias microservicios deberá implementar e iniciar toda la aplicación en el host Docker mediante la ejecución de docker-redactar arriba (o un mecanismo comparable si usas un orchestrator). Una vez que se está ejecutando la aplicación completa y todos sus servicios, puede ejecutar pruebas funcionales e integración end-to-end.

Hay algunos enfoques que puede usar. En el archivo compose.yml de docker que se usa para implementar la aplicación (u otras similares, como docker compose.ci.build.yml), en el nivel de solución se puede expandir el punto de entrada para usar [dotnet prueba](https://docs.microsoft.com/dotnet/core/tools/dotnet-test). También puede usar otro archivo de composición que ejecuta las pruebas en la imagen de destino. Mediante el uso de otro archivo de composición para pruebas de integración que incluye su microservicios y bases de datos en contenedores, puede asegurarse de que los datos relacionados siempre se restablece a su estado original antes de ejecutar las pruebas.

Una vez que la aplicación de redacción está en funcionamiento, puede aprovechar las ventajas de los puntos de interrupción y excepciones si se está ejecutando Visual Studio. O bien, puede ejecutar las pruebas de integración automáticamente en la canalización de integración continua en Visual Studio Team Services o cualquier otro sistema de CI/CD que admite contenedores de Docker.

>[!div class="step-by-step"]
[Anterior] (suscribirse-events.md) [siguiente] (.. /microservice-ddd-CQRS-Patterns/index.MD)
