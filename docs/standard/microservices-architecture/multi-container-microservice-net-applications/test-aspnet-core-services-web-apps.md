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
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="b3a97-104">Probar aplicaciones web y servicios principales de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b3a97-104">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="b3a97-105">Los controladores son una parte fundamental de cualquier servicio de API de núcleo de ASP.NET y la aplicación Web de MVC de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b3a97-105">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="b3a97-106">Por lo tanto, debe tener confianza que se comportan según lo previsto para su aplicación.</span><span class="sxs-lookup"><span data-stu-id="b3a97-106">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="b3a97-107">Las pruebas automatizadas pueden proporcionarle esta confianza y pueden detectar errores antes de que lleguen a producción.</span><span class="sxs-lookup"><span data-stu-id="b3a97-107">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="b3a97-108">Debe probar cómo se comporta según las entradas válidas o no es válidas el dispositivo y probar las respuestas de controlador en función del resultado de la operación de negocio que lleva a cabo.</span><span class="sxs-lookup"><span data-stu-id="b3a97-108">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="b3a97-109">Sin embargo, debe tener su microservicios estos tipos de pruebas:</span><span class="sxs-lookup"><span data-stu-id="b3a97-109">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="b3a97-110">Las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b3a97-110">Unit tests.</span></span> <span data-ttu-id="b3a97-111">Esto garantiza que los componentes individuales de la aplicación funcionan según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="b3a97-111">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="b3a97-112">Las aserciones de la API de componente de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3a97-112">Assertions test the component API.</span></span>

-   <span data-ttu-id="b3a97-113">Pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="b3a97-113">Integration tests.</span></span> <span data-ttu-id="b3a97-114">Esto garantiza que las interacciones de componente funcionan según lo previsto con los artefactos externos como bases de datos.</span><span class="sxs-lookup"><span data-stu-id="b3a97-114">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="b3a97-115">Pueden probar las aserciones de la API de componente, interfaz de usuario o los efectos secundarios de acciones como la E/S de base de datos, registro, etcetera.</span><span class="sxs-lookup"><span data-stu-id="b3a97-115">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="b3a97-116">Pruebas funcionales para cada microservicio.</span><span class="sxs-lookup"><span data-stu-id="b3a97-116">Functional tests for each microservice.</span></span> <span data-ttu-id="b3a97-117">Esto garantiza que la aplicación funciona según lo esperado desde la perspectiva del usuario.</span><span class="sxs-lookup"><span data-stu-id="b3a97-117">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="b3a97-118">Servicio de prueba.</span><span class="sxs-lookup"><span data-stu-id="b3a97-118">Service tests.</span></span> <span data-ttu-id="b3a97-119">Esto garantiza que todos los casos de uso de service to-end, incluidas las pruebas de varios servicios al mismo tiempo, se prueban.</span><span class="sxs-lookup"><span data-stu-id="b3a97-119">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="b3a97-120">Para este tipo de prueba, debe preparar el entorno en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="b3a97-120">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="b3a97-121">En este caso, significa que a partir de los servicios (por ejemplo, mediante el uso de docker-constituyen una).</span><span class="sxs-lookup"><span data-stu-id="b3a97-121">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="b3a97-122">Implementación pruebas unitarias para las API Web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b3a97-122">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="b3a97-123">Pruebas unitarias implica probar una parte de una aplicación de forma aislada de su infraestructura y las dependencias.</span><span class="sxs-lookup"><span data-stu-id="b3a97-123">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="b3a97-124">Cuando realice pruebas unitarias en lógica de controlador, solo el contenido de una sola acción o método se ha probado, no el comportamiento de sus dependencias o el marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b3a97-124">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="b3a97-125">Pruebas unitarias no detectan problemas en la interacción entre componentes, es decir, el propósito de las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="b3a97-125">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="b3a97-126">Como unidad probar las acciones de controlador, asegúrese de que solo se centran en su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="b3a97-126">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="b3a97-127">Una prueba unitaria de controlador evita aspectos como filtros, enrutamiento o el enlace de modelos.</span><span class="sxs-lookup"><span data-stu-id="b3a97-127">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="b3a97-128">Dado que se centran en las pruebas de un solo elemento, pruebas unitarias suelen ser fáciles de escribir y rápida ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b3a97-128">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="b3a97-129">Con frecuencia se puede ejecutar un conjunto de pruebas unitarias bien escrito sin mucho sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="b3a97-129">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="b3a97-130">Pruebas unitarias se implementan en función de los marcos de pruebas como xUnit.net, MSTest, Moq o NUnit.</span><span class="sxs-lookup"><span data-stu-id="b3a97-130">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="b3a97-131">Para la aplicación de ejemplo eShopOnContainers, usamos XUnit.</span><span class="sxs-lookup"><span data-stu-id="b3a97-131">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="b3a97-132">Al escribir una prueba unitaria para un controlador de API Web, cree una instancia de la clase de controlador directamente mediante la palabra clave new en C\#, para que la prueba se ejecute tan rápido como sea posible.</span><span class="sxs-lookup"><span data-stu-id="b3a97-132">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="b3a97-133">En el ejemplo siguiente se muestra cómo hacer esto si usa [XUnit](https://xunit.github.io/) como el marco de pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3a97-133">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="b3a97-134">Implementación de la integración y pruebas funcionales para cada microservicio</span><span class="sxs-lookup"><span data-stu-id="b3a97-134">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="b3a97-135">Como se indicó, pruebas de integración y pruebas funcionales tengan objetivos y propósitos diferentes.</span><span class="sxs-lookup"><span data-stu-id="b3a97-135">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="b3a97-136">Sin embargo, la forma de implementar ambos al probar los controladores de ASP.NET Core es similar, por lo que en esta sección se concentrarse en las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="b3a97-136">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="b3a97-137">Pruebas de integración garantizan que los componentes de una aplicación funcionan correctamente cuando se ensambla.</span><span class="sxs-lookup"><span data-stu-id="b3a97-137">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="b3a97-138">Integración de es compatible con ASP.NET Core pruebas con marcos de pruebas unitarias y un host de web de prueba integrados que puede usarse para controlar las solicitudes sin la sobrecarga de la red.</span><span class="sxs-lookup"><span data-stu-id="b3a97-138">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="b3a97-139">A diferencia de pruebas unitarias, pruebas de integración suelen incluyen problemas de infraestructura de la aplicación, como una base de datos, sistema de archivos, recursos de red, o las solicitudes web y las respuestas.</span><span class="sxs-lookup"><span data-stu-id="b3a97-139">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="b3a97-140">Pruebas unitarias usar fakes o simular objetos en lugar de estos problemas.</span><span class="sxs-lookup"><span data-stu-id="b3a97-140">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="b3a97-141">Pero el propósito de las pruebas de integración confirmar que el sistema funciona según lo previsto con estos sistemas, por lo que para las pruebas de integración no usar fakes o simular objetos.</span><span class="sxs-lookup"><span data-stu-id="b3a97-141">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="b3a97-142">En su lugar, se incluye la infraestructura, como la invocación de acceso o de servicio de base de datos de otros servicios.</span><span class="sxs-lookup"><span data-stu-id="b3a97-142">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="b3a97-143">Dado las pruebas de integración ejercer mayor segmentos de código de pruebas unitarias, y debido a las pruebas de integración se basan en los elementos de infraestructura, tienden a ser órdenes de magnitud más lentas que las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="b3a97-143">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="b3a97-144">Por lo tanto, es conveniente limitar cuántas pruebas de integración se escribe y ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b3a97-144">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="b3a97-145">ASP.NET Core incluye un host de web prueba integrados que puede usarse para controlar las solicitudes HTTP sin la sobrecarga de la red, lo que significa que puede ejecutar dichas pruebas más rápidamente cuando se utiliza un host de web real.</span><span class="sxs-lookup"><span data-stu-id="b3a97-145">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="b3a97-146">El host de prueba web está disponible en un componente de NuGet como Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="b3a97-146">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="b3a97-147">Se pueden agregar a proyectos de prueba de integración y utilizado para hospedar ASP.NET Core aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b3a97-147">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="b3a97-148">Como puede ver en el código siguiente, al crear pruebas de integración de ASP.NET Core controladores, para crear instancias de los controladores a través del host de prueba.</span><span class="sxs-lookup"><span data-stu-id="b3a97-148">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="b3a97-149">Esto es comparable a una solicitud HTTP, pero se ejecuta con mayor rapidez.</span><span class="sxs-lookup"><span data-stu-id="b3a97-149">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="b3a97-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b3a97-150">Additional resources</span></span>

-   <span data-ttu-id="b3a97-151">**Steve Smith. Probar controladores** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="b3a97-151">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="b3a97-152">**Steve Smith. Pruebas de integración** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="b3a97-152">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="b3a97-153">**Pruebas unitarias en .NET Core con prueba dotnet**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span><span class="sxs-lookup"><span data-stu-id="b3a97-153">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span></span>

-   <span data-ttu-id="b3a97-154">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="b3a97-154">**xUnit.net**.</span></span> <span data-ttu-id="b3a97-155">Sitio oficial.</span><span class="sxs-lookup"><span data-stu-id="b3a97-155">Official site.</span></span>
    [<span data-ttu-id="b3a97-156">*https://xUnit.github.IO/*</span><span class="sxs-lookup"><span data-stu-id="b3a97-156">*https://xunit.github.io/*</span></span>](https://xunit.github.io/)

-   <span data-ttu-id="b3a97-157">**Conceptos básicos de prueba unitaria. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="b3a97-157">**Unit Test Basics.**
[*https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="b3a97-158">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="b3a97-158">**Moq**.</span></span> <span data-ttu-id="b3a97-159">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="b3a97-159">GitHub repo.</span></span>
    [<span data-ttu-id="b3a97-160">*https://github.com/moq/moq*</span><span class="sxs-lookup"><span data-stu-id="b3a97-160">*https://github.com/moq/moq*</span></span>](https://github.com/moq/moq)

-   <span data-ttu-id="b3a97-161">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="b3a97-161">**NUnit**.</span></span> <span data-ttu-id="b3a97-162">Sitio oficial.</span><span class="sxs-lookup"><span data-stu-id="b3a97-162">Official site.</span></span>
    [<span data-ttu-id="b3a97-163">*https://www.NUnit.org/*</span><span class="sxs-lookup"><span data-stu-id="b3a97-163">*https://www.nunit.org/*</span></span>](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="b3a97-164">Implementación de servicio de pruebas en una aplicación de contenedor de varios</span><span class="sxs-lookup"><span data-stu-id="b3a97-164">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="b3a97-165">Como se indicó anteriormente, al probar aplicaciones de contenedor múltiples, todas las microservicios deben ejecutar en el clúster de host o un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="b3a97-165">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="b3a97-166">Pruebas de servicio de extremo a extremo que incluyen varias operaciones que implican varias microservicios deberá implementar e iniciar toda la aplicación en el host Docker mediante la ejecución de docker-redactar arriba (o un mecanismo comparable si usas un orchestrator).</span><span class="sxs-lookup"><span data-stu-id="b3a97-166">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="b3a97-167">Una vez que se está ejecutando la aplicación completa y todos sus servicios, puede ejecutar pruebas funcionales e integración end-to-end.</span><span class="sxs-lookup"><span data-stu-id="b3a97-167">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="b3a97-168">Hay algunos enfoques que puede usar.</span><span class="sxs-lookup"><span data-stu-id="b3a97-168">There are a few approaches you can use.</span></span> <span data-ttu-id="b3a97-169">En el archivo compose.yml de docker que se usa para implementar la aplicación (u otras similares, como docker compose.ci.build.yml), en el nivel de solución se puede expandir el punto de entrada para usar [dotnet prueba](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span><span class="sxs-lookup"><span data-stu-id="b3a97-169">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span></span> <span data-ttu-id="b3a97-170">También puede usar otro archivo de composición que ejecuta las pruebas en la imagen de destino.</span><span class="sxs-lookup"><span data-stu-id="b3a97-170">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="b3a97-171">Mediante el uso de otro archivo de composición para pruebas de integración que incluye su microservicios y bases de datos en contenedores, puede asegurarse de que los datos relacionados siempre se restablece a su estado original antes de ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="b3a97-171">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="b3a97-172">Una vez que la aplicación de redacción está en funcionamiento, puede aprovechar las ventajas de los puntos de interrupción y excepciones si se está ejecutando Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b3a97-172">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="b3a97-173">O bien, puede ejecutar las pruebas de integración automáticamente en la canalización de integración continua en Visual Studio Team Services o cualquier otro sistema de CI/CD que admite contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="b3a97-173">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="b3a97-174">[Anterior] (suscribirse-events.md) [siguiente] (.. /microservice-ddd-CQRS-Patterns/index.MD)</span><span class="sxs-lookup"><span data-stu-id="b3a97-174">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>
