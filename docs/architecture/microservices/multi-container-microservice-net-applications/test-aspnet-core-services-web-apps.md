---
title: Probar aplicaciones web y servicios ASP.NET Core
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Descubra una arquitectura para probar aplicaciones web y servicios ASP.NET Core en contenedores.
ms.date: 08/07/2020
ms.openlocfilehash: af1187fb1e2afbb9fa953db5a280c9cc317ab6a8
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804775"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="4923f-103">Probar aplicaciones web y servicios ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4923f-103">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="4923f-104">Los controladores son una parte fundamental de cualquier servicio de la API de ASP.NET Core y de la aplicación web de ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="4923f-104">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="4923f-105">Por lo tanto, debe tener la seguridad de que se comportan según lo previsto en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4923f-105">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="4923f-106">Las pruebas automatizadas pueden darle esta seguridad, así como detectar errores antes de que lleguen a la fase producción.</span><span class="sxs-lookup"><span data-stu-id="4923f-106">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="4923f-107">Debe probar cómo se comporta el controlador según las entradas válidas o no válidas y probar las respuestas del controlador en función del resultado de la operación comercial que lleve a cabo.</span><span class="sxs-lookup"><span data-stu-id="4923f-107">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="4923f-108">Pero debe realizar estos tipos de pruebas en los microservicios:</span><span class="sxs-lookup"><span data-stu-id="4923f-108">However, you should have these types of tests for your microservices:</span></span>

- <span data-ttu-id="4923f-109">Pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="4923f-109">Unit tests.</span></span> <span data-ttu-id="4923f-110">Esto garantiza que los componentes individuales de la aplicación funcionan según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="4923f-110">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="4923f-111">Las aserciones prueban la API del componente.</span><span class="sxs-lookup"><span data-stu-id="4923f-111">Assertions test the component API.</span></span>

- <span data-ttu-id="4923f-112">Pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="4923f-112">Integration tests.</span></span> <span data-ttu-id="4923f-113">Esto garantiza que las interacciones del componente funcionen según lo previsto con los artefactos externos como bases de datos.</span><span class="sxs-lookup"><span data-stu-id="4923f-113">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="4923f-114">Las aserciones pueden poner a prueba la API del componente, la interfaz de usuario o los efectos secundarios de acciones como la E/S de la base de datos, el registro, etc.</span><span class="sxs-lookup"><span data-stu-id="4923f-114">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

- <span data-ttu-id="4923f-115">Pruebas funcionales para cada microservicio.</span><span class="sxs-lookup"><span data-stu-id="4923f-115">Functional tests for each microservice.</span></span> <span data-ttu-id="4923f-116">Esto garantiza que la aplicación funcione según lo esperado desde la perspectiva del usuario.</span><span class="sxs-lookup"><span data-stu-id="4923f-116">These ensure that the application works as expected from the user's perspective.</span></span>

- <span data-ttu-id="4923f-117">Pruebas de servicio.</span><span class="sxs-lookup"><span data-stu-id="4923f-117">Service tests.</span></span> <span data-ttu-id="4923f-118">Esto garantiza que se pongan a prueba todos los casos de uso de servicio de un extremo a otro, incluidas pruebas de servicios múltiples al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4923f-118">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="4923f-119">Para este tipo de prueba, primero debe preparar el entorno.</span><span class="sxs-lookup"><span data-stu-id="4923f-119">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="4923f-120">En este caso, esto significa iniciar los servicios (por ejemplo, mediante el uso de docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="4923f-120">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="4923f-121">Implementación de pruebas unitarias para las API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4923f-121">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="4923f-122">Las pruebas unitarias conllevan probar una parte de una aplicación de forma aislada con respecto a su infraestructura y dependencias.</span><span class="sxs-lookup"><span data-stu-id="4923f-122">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="4923f-123">Cuando se realizan pruebas unitarias de la lógica de controlador, solo se comprueba el método o el contenido de una única acción, no el comportamiento de sus dependencias o del marco en sí.</span><span class="sxs-lookup"><span data-stu-id="4923f-123">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="4923f-124">Con todo, las pruebas unitarias no detectan problemas de interacción entre componentes; este es el propósito de las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="4923f-124">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="4923f-125">Cuando realice pruebas unitarias de sus acciones de controlador, asegúrese de centrarse solamente en su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="4923f-125">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="4923f-126">Una prueba unitaria de controlador evita elementos como filtros, el enrutamiento o enlaces de modelos (la asignación de datos de solicitud a un ViewModel o DTO).</span><span class="sxs-lookup"><span data-stu-id="4923f-126">A controller unit test avoids things like filters, routing, or model binding (the mapping of request data to a ViewModel or DTO).</span></span> <span data-ttu-id="4923f-127">Como se centran en comprobar solo una cosa, las pruebas unitarias suelen ser fáciles de escribir y rápidas de ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4923f-127">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="4923f-128">Un conjunto de pruebas unitarias bien escrito se puede ejecutar con frecuencia sin demasiada sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="4923f-128">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="4923f-129">Las pruebas unitarias se implementan en función de los marcos de pruebas como xUnit.net, MSTest, Moq o NUnit.</span><span class="sxs-lookup"><span data-stu-id="4923f-129">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="4923f-130">En la aplicación de ejemplo eShopOnContainers, se usa XUnit.</span><span class="sxs-lookup"><span data-stu-id="4923f-130">For the eShopOnContainers sample application, we are using xUnit.</span></span>

<span data-ttu-id="4923f-131">Al escribir una prueba unitaria para un controlador de API web, puede ejemplificar directamente la clase de controlador mediante la nueva palabra clave en C\#, para que la prueba se ejecute tan rápido como sea posible.</span><span class="sxs-lookup"><span data-stu-id="4923f-131">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="4923f-132">En el ejemplo siguiente se muestra cómo hacerlo con [XUnit](https://xunit.github.io/) como marco de pruebas.</span><span class="sxs-lookup"><span data-stu-id="4923f-132">The following example shows how to do this when using [xUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="4923f-133">Implementación de pruebas funcionales y de integración para cada microservicio</span><span class="sxs-lookup"><span data-stu-id="4923f-133">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="4923f-134">Como se ha indicado, las pruebas funcionales y de integración tienen objetivos y propósitos diferentes.</span><span class="sxs-lookup"><span data-stu-id="4923f-134">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="4923f-135">Pero la forma de implementarlas para probar los controladores de ASP.NET Core es similar, por lo que en esta sección nos centraremos en las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="4923f-135">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="4923f-136">Las pruebas de integración garantizan que los componentes de una aplicación funcionen correctamente durante el ensamblaje.</span><span class="sxs-lookup"><span data-stu-id="4923f-136">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="4923f-137">ASP.NET Core admite las pruebas de integración que usan marcos de pruebas unitarias y un host de web de prueba integrado que puede usarse para controlar las solicitudes sin sobrecargar la red.</span><span class="sxs-lookup"><span data-stu-id="4923f-137">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="4923f-138">A diferencia de las pruebas unitarias, las pruebas de integración suelen incluir problemas de infraestructura de la aplicación, como base de datos, sistema de archivos, recursos de red o solicitudes web, y sus respuestas.</span><span class="sxs-lookup"><span data-stu-id="4923f-138">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="4923f-139">Para las pruebas unitarias se usan emulaciones u objetos ficticios en lugar de estos problemas.</span><span class="sxs-lookup"><span data-stu-id="4923f-139">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="4923f-140">Pero el propósito de las pruebas de integración es confirmar que el sistema funciona según lo previsto con estos sistemas, por lo que para las pruebas de integración no se usan simulaciones ni objetos ficticios.</span><span class="sxs-lookup"><span data-stu-id="4923f-140">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="4923f-141">En cambio, se incluye la infraestructura, como el acceso a la base de datos o la invocación del servicio desde otros servicios.</span><span class="sxs-lookup"><span data-stu-id="4923f-141">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="4923f-142">Como las pruebas de integración usan segmentos de código más grandes que las pruebas unitarias y dependen de los elementos de infraestructura, tienden a ser órdenes de envergadura, más lentas que las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="4923f-142">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="4923f-143">Por lo tanto, es conveniente limitar el número de pruebas de integración que va a escribir y a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4923f-143">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="4923f-144">ASP.NET Core incluye un host web de prueba integrado que puede usarse para controlar las solicitudes HTTP sin causar una sobrecarga en la red, lo que significa que puede ejecutar dichas pruebas más rápidamente si usa un host de web real.</span><span class="sxs-lookup"><span data-stu-id="4923f-144">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster than when using a real web host.</span></span> <span data-ttu-id="4923f-145">El host web de prueba (TestServer) está disponible en un componente NuGet como Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="4923f-145">The test web host (TestServer) is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="4923f-146">Se puede agregar a proyectos de prueba de integración y utilizarlo para hospedar aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4923f-146">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="4923f-147">Como puede ver en el código siguiente, al crear pruebas de integración para controladores de ASP.NET Core, los controladores se ejemplifican a través del host de prueba.</span><span class="sxs-lookup"><span data-stu-id="4923f-147">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="4923f-148">Esto se puede comparar a una solicitud HTTP, pero se ejecuta con mayor rapidez.</span><span class="sxs-lookup"><span data-stu-id="4923f-148">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="4923f-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4923f-149">Additional resources</span></span>

- <span data-ttu-id="4923f-150">**Steve Smith. Controladores de pruebas** (ASP.NET Core) </span><span class="sxs-lookup"><span data-stu-id="4923f-150">**Steve Smith. Testing controllers** (ASP.NET Core) </span></span>\
    [https://docs.microsoft.com/aspnet/core/mvc/controllers/testing](/aspnet/core/mvc/controllers/testing)

- <span data-ttu-id="4923f-151">**Steve Smith. Pruebas de integración** (ASP.NET Core) </span><span class="sxs-lookup"><span data-stu-id="4923f-151">**Steve Smith. Integration testing** (ASP.NET Core) </span></span>\
    [https://docs.microsoft.com/aspnet/core/test/integration-tests](/aspnet/core/test/integration-tests)

- <span data-ttu-id="4923f-152">**Pruebas unitarias en .NET Core con dotnet test** </span><span class="sxs-lookup"><span data-stu-id="4923f-152">**Unit testing in .NET Core using dotnet test** </span></span>\
    [https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test](../../../core/testing/unit-testing-with-dotnet-test.md)

- <span data-ttu-id="4923f-153">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="4923f-153">**xUnit.net**.</span></span> <span data-ttu-id="4923f-154">Sitio oficial.</span><span class="sxs-lookup"><span data-stu-id="4923f-154">Official site.</span></span> \
    <https://xunit.github.io/>

- <span data-ttu-id="4923f-155">**Unit Test Basics** (Conceptos básicos de prueba unitaria).</span><span class="sxs-lookup"><span data-stu-id="4923f-155">**Unit Test Basics.**</span></span> \
    [https://docs.microsoft.com/visualstudio/test/unit-test-basics](/visualstudio/test/unit-test-basics)

- <span data-ttu-id="4923f-156">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="4923f-156">**Moq**.</span></span> <span data-ttu-id="4923f-157">Repositorio de GitHub.</span><span class="sxs-lookup"><span data-stu-id="4923f-157">GitHub repo.</span></span> \
    <https://github.com/moq/moq>

- <span data-ttu-id="4923f-158">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="4923f-158">**NUnit**.</span></span> <span data-ttu-id="4923f-159">Sitio oficial.</span><span class="sxs-lookup"><span data-stu-id="4923f-159">Official site.</span></span> \
    <https://nunit.org/>

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="4923f-160">Implementación de pruebas de servicio en una aplicación con varios contenedores</span><span class="sxs-lookup"><span data-stu-id="4923f-160">Implementing service tests on a multi-container application</span></span>

<span data-ttu-id="4923f-161">Como se indicó anteriormente, al probar aplicaciones con varios contenedores, todos los microservicios deben ejecutarse en el host de Docker o en un clúster de contenedor.</span><span class="sxs-lookup"><span data-stu-id="4923f-161">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="4923f-162">Las pruebas de servicio de un extremo a otro que incluyen varias operaciones que implican varios microservicios requieren que implemente e inicie la aplicación en el host de Docker mediante la ejecución de docker-compose up (o un mecanismo comparable si usa un orquestador).</span><span class="sxs-lookup"><span data-stu-id="4923f-162">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="4923f-163">Cuando la aplicación y todos sus servicios se estén ejecutando, podrá ejecutar pruebas funcionales y de integración de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="4923f-163">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="4923f-164">Puede usar diferentes enfoques.</span><span class="sxs-lookup"><span data-stu-id="4923f-164">There are a few approaches you can use.</span></span> <span data-ttu-id="4923f-165">En el archivo docker-compose.yml que se usa para implementar la aplicación en el nivel de solución puede expandir el punto de entrada para usar [dotnet test](../../../core/tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="4923f-165">In the docker-compose.yml file that you use to deploy the application at the solution level you can expand the entry point to use [dotnet test](../../../core/tools/dotnet-test.md).</span></span> <span data-ttu-id="4923f-166">También puede usar otro archivo de composición que ejecute las pruebas en la imagen de destino.</span><span class="sxs-lookup"><span data-stu-id="4923f-166">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="4923f-167">Si utiliza otro archivo de composición para las pruebas de integración, que incluyan sus microservicios y bases de datos en contenedores, puede comprobar que los datos relacionados siempre se restablecen a su estado original antes de ejecutar las pruebas.</span><span class="sxs-lookup"><span data-stu-id="4923f-167">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="4923f-168">Si ejecuta Visual Studio, cuando la aplicación de redacción esté en funcionamiento, podrá aprovechar los puntos de interrupción y las excepciones.</span><span class="sxs-lookup"><span data-stu-id="4923f-168">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="4923f-169">También podrá ejecutar las pruebas de integración automáticamente en la canalización de integración continua en Azure DevOps Services o en cualquier otro sistema de integración continua o de entrega continua que admita los contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="4923f-169">Or you can run the integration tests automatically in your CI pipeline in Azure DevOps Services or any other CI/CD system that supports Docker containers.</span></span>

## <a name="testing-in-eshoponcontainers"></a><span data-ttu-id="4923f-170">Realización de pruebas en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="4923f-170">Testing in eShopOnContainers</span></span>

<span data-ttu-id="4923f-171">Recientemente se han reestructurado las pruebas de referencia de la aplicación (eShopOnContainers) y ahora hay cuatro categorías:</span><span class="sxs-lookup"><span data-stu-id="4923f-171">The reference application (eShopOnContainers) tests were recently restructured and now there are four categories:</span></span>

1. <span data-ttu-id="4923f-172">**Pruebas unitarias**, simples pruebas unitarias normales, incluidas en los proyectos **{MicroserviceName}.UnitTests**</span><span class="sxs-lookup"><span data-stu-id="4923f-172">**Unit** tests, just plain old regular unit tests, contained in the **{MicroserviceName}.UnitTests** projects</span></span>

2. <span data-ttu-id="4923f-173">**Pruebas de integración o funcionales de microservicio**, con casos de prueba que implican la infraestructura para cada microservicio, pero aisladas de los demás, y están incluidas en los proyectos **{MicroserviceName}. FunctionalTests**.</span><span class="sxs-lookup"><span data-stu-id="4923f-173">**Microservice functional/integration tests**, with test cases involving the infrastructure for each microservice but isolated from the others and are contained in the **{MicroserviceName}.FunctionalTests** projects.</span></span>

3. <span data-ttu-id="4923f-174">**Pruebas funcionales o de integración de aplicación**, que se centran en la integración de microservicios, con casos de prueba para ejercer varios microservicios.</span><span class="sxs-lookup"><span data-stu-id="4923f-174">**Application functional/integration tests**, which focus on microservices integration, with test cases that exert several microservices.</span></span> <span data-ttu-id="4923f-175">Estas pruebas se encuentran en el proyecto **Application.FunctionalTests**.</span><span class="sxs-lookup"><span data-stu-id="4923f-175">These tests are located in project **Application.FunctionalTests**.</span></span>

<span data-ttu-id="4923f-176">Mientras que las pruebas unitarias y de integración se organizan en una carpeta de prueba en el proyecto de microservicio, las pruebas de carga y aplicación se administran por separado en la carpeta raíz, como se muestra en la figura 6-25.</span><span class="sxs-lookup"><span data-stu-id="4923f-176">While unit and integration tests are organized in a test folder within the microservice project, application and load tests are managed separately under the root folder, as shown in Figure 6-25.</span></span>

![Captura de pantalla de VS que apunta a algunos de los proyectos de prueba de la solución.](./media/test-aspnet-core-services-web-apps/eshoponcontainers-test-folder-structure.png)

<span data-ttu-id="4923f-178">**Figura 6-25**.</span><span class="sxs-lookup"><span data-stu-id="4923f-178">**Figure 6-25**.</span></span> <span data-ttu-id="4923f-179">Estructura de carpetas de prueba en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="4923f-179">Test folder structure in eShopOnContainers</span></span>

<span data-ttu-id="4923f-180">Las pruebas de integración y funcionales de microservicios y aplicaciones se ejecutan desde Visual Studio, mediante el ejecutor de pruebas periódicas, pero primero debe iniciar los servicios de infraestructura necesarios, por medio de un conjunto de archivos docker-compose incluidos en la carpeta de prueba de la solución:</span><span class="sxs-lookup"><span data-stu-id="4923f-180">Microservice and Application functional/integration tests are run from Visual Studio, using the regular tests runner, but first you need to start the required infrastructure services, by means of a set of docker-compose files contained in the solution test folder:</span></span>

<span data-ttu-id="4923f-181">**docker-compose-test.yml**</span><span class="sxs-lookup"><span data-stu-id="4923f-181">**docker-compose-test.yml**</span></span>

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

<span data-ttu-id="4923f-182">**docker-compose-test.override.yml**</span><span class="sxs-lookup"><span data-stu-id="4923f-182">**docker-compose-test.override.yml**</span></span>

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

<span data-ttu-id="4923f-183">Por tanto, para ejecutar las pruebas de integración y funcionales primero debe ejecutar este comando, desde la carpeta de prueba de la solución:</span><span class="sxs-lookup"><span data-stu-id="4923f-183">So, to run the functional/integration tests you must first run this command, from the solution test folder:</span></span>

```console
docker-compose -f docker-compose-test.yml -f docker-compose-test.override.yml up
```

<span data-ttu-id="4923f-184">Como puede ver, estos archivos docker-compose solo inician los microservicios Redis, RabbitMQ, SQL Server y MongoDB.</span><span class="sxs-lookup"><span data-stu-id="4923f-184">As you can see, these docker-compose files only start the Redis, RabbitMQ, SQL Server and MongoDB microservices.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4923f-185">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4923f-185">Additional resources</span></span>

- <span data-ttu-id="4923f-186">**Pruebas unitarias y de integración** en eShopOnContainers </span><span class="sxs-lookup"><span data-stu-id="4923f-186">**Unit & Integration testing** on the eShopOnContainers </span></span>\
    <https://github.com/dotnet-architecture/eShopOnContainers/wiki/Unit-and-integration-testing>

- <span data-ttu-id="4923f-187">**Pruebas de carga** en eShopOnContainers </span><span class="sxs-lookup"><span data-stu-id="4923f-187">**Load testing** on the eShopOnContainers </span></span>\
    <https://github.com/dotnet-architecture/eShopOnContainers/wiki/Load-testing>

> [!div class="step-by-step"]
> <span data-ttu-id="4923f-188">[Anterior](subscribe-events.md)
> [Siguiente](background-tasks-with-ihostedservice.md)</span><span class="sxs-lookup"><span data-stu-id="4923f-188">[Previous](subscribe-events.md)
[Next](background-tasks-with-ihostedservice.md)</span></span>
