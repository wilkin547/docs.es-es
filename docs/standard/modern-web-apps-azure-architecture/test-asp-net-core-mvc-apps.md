---
title: Prueba de aplicaciones ASP.NET Core MVC
description: Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Prueba de aplicaciones ASP.NET Core MVC
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: 96a004cc49773346eeb8f88e2ba99beebf8598bf
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154208"
---
# <a name="test-aspnet-core-mvc-apps"></a><span data-ttu-id="db56b-103">Prueba de aplicaciones ASP.NET Core MVC</span><span class="sxs-lookup"><span data-stu-id="db56b-103">Test ASP.NET Core MVC apps</span></span>

> <span data-ttu-id="db56b-104">*"Si no le gusta realizar pruebas unitarias de su producto, lo más probable es que a los clientes tampoco les guste probarlo".*</span><span class="sxs-lookup"><span data-stu-id="db56b-104">*"If you don't like unit testing your product, most likely your customers won't like to test it, either."*</span></span>
 > <span data-ttu-id="db56b-105">\_- Anónimo-</span><span class="sxs-lookup"><span data-stu-id="db56b-105">\_- Anonymous-</span></span>

<span data-ttu-id="db56b-106">En el software de cualquier complejidad se pueden producir errores inesperados en respuesta a los cambios.</span><span class="sxs-lookup"><span data-stu-id="db56b-106">Software of any complexity can fail in unexpected ways in response to changes.</span></span> <span data-ttu-id="db56b-107">Por tanto, es necesario realizar pruebas después de realizar cambios en todas las aplicaciones menos en las más triviales (o las menos críticas).</span><span class="sxs-lookup"><span data-stu-id="db56b-107">Thus, testing after making changes is required for all but the most trivial (or least critical) applications.</span></span> <span data-ttu-id="db56b-108">Las pruebas manuales son la forma más lenta, menos confiable y más costosa de probar software.</span><span class="sxs-lookup"><span data-stu-id="db56b-108">Manual testing is the slowest, least reliable, most expensive way to test software.</span></span> <span data-ttu-id="db56b-109">Desafortunadamente, si las aplicaciones no están diseñadas para que se puedan probar, puede ser el único medio disponible.</span><span class="sxs-lookup"><span data-stu-id="db56b-109">Unfortunately, if applications are not designed to be testable, it can be the only means available.</span></span> <span data-ttu-id="db56b-110">Las aplicaciones escritas para seguir los principios arquitectónicos descritos en el capítulo X deben poder someterse a pruebas unitarias y las aplicaciones ASP.NET Core también admiten pruebas de integración y funcionales automatizadas.</span><span class="sxs-lookup"><span data-stu-id="db56b-110">Applications written following the architectural principles laid out in chapter X should be unit testable, and ASP.NET Core applications support automated integration and functional testing as well.</span></span>

## <a name="kinds-of-automated-tests"></a><span data-ttu-id="db56b-111">Tipos de pruebas automatizadas</span><span class="sxs-lookup"><span data-stu-id="db56b-111">Kinds of automated tests</span></span>

<span data-ttu-id="db56b-112">Hay muchos tipos de pruebas automatizadas para las aplicaciones de software.</span><span class="sxs-lookup"><span data-stu-id="db56b-112">There are many kinds of automated tests for software applications.</span></span> <span data-ttu-id="db56b-113">La prueba más sencilla y de nivel más bajo es la prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="db56b-113">The simplest, lowest level test is the unit test.</span></span> <span data-ttu-id="db56b-114">En un nivel ligeramente superior se encuentran las pruebas de integración y las pruebas funcionales.</span><span class="sxs-lookup"><span data-stu-id="db56b-114">At a slightly higher level there are integration tests and functional tests.</span></span> <span data-ttu-id="db56b-115">Otros tipos de pruebas, como las de interfaz de usuario, de carga, de esfuerzo y de humo, quedan fuera del ámbito de este documento.</span><span class="sxs-lookup"><span data-stu-id="db56b-115">Other kinds of tests, like UI tests, load tests, stress tests, and smoke tests, are beyond the scope of this document.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="db56b-116">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="db56b-116">Unit tests</span></span>

<span data-ttu-id="db56b-117">Una prueba unitaria prueba un único elemento de la lógica de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db56b-117">A unit test tests a single part of your application's logic.</span></span> <span data-ttu-id="db56b-118">Se puede describir aún más enumerando algunas de las cosas que no hace.</span><span class="sxs-lookup"><span data-stu-id="db56b-118">One can further describe it by listing some of the things that it isn't.</span></span> <span data-ttu-id="db56b-119">Una prueba unitaria no prueba el funcionamiento del código con dependencias o infraestructura; eso lo comprueban las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="db56b-119">A unit test doesn't test how your code works with dependencies or infrastructure – that's what integration tests are for.</span></span> <span data-ttu-id="db56b-120">Una prueba unitaria no prueba el marco para el que se escribe el código; se debe asumir que funciona o, si se detecta que no lo hace, registrar un error y codificar una solución alternativa.</span><span class="sxs-lookup"><span data-stu-id="db56b-120">A unit test doesn't test the framework your code is written on – you should assume it works or, if you find it doesn't, file a bug and code a workaround.</span></span> <span data-ttu-id="db56b-121">Una prueba unitaria se ejecuta completamente en memoria y en proceso.</span><span class="sxs-lookup"><span data-stu-id="db56b-121">A unit test runs completely in memory and in process.</span></span> <span data-ttu-id="db56b-122">No se comunica con el sistema de archivos, la red o una base de datos.</span><span class="sxs-lookup"><span data-stu-id="db56b-122">It doesn't communicate with the file system, the network, or a database.</span></span> <span data-ttu-id="db56b-123">Las pruebas unitarias solo deben probar el código.</span><span class="sxs-lookup"><span data-stu-id="db56b-123">Unit tests should only test your code.</span></span>

<span data-ttu-id="db56b-124">Las pruebas unitarias, como solo prueban una unidad del código, sin dependencias externas, se deben ejecutar muy rápidamente.</span><span class="sxs-lookup"><span data-stu-id="db56b-124">Unit tests, by virtue of the fact that they test only a single unit of your code, with no external dependencies, should execute extremely quickly.</span></span> <span data-ttu-id="db56b-125">Por tanto, debe ser capaz de ejecutar conjuntos de cientos de pruebas unitarias en unos segundos.</span><span class="sxs-lookup"><span data-stu-id="db56b-125">Thus, you should be able to run test suites of hundreds of unit tests in a few seconds.</span></span> <span data-ttu-id="db56b-126">Ejecute las pruebas con frecuencia, idealmente antes de cada inserción en un repositorio de control de código fuente compartido y, por supuesto, con cada compilación automatizada en el servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="db56b-126">Run them frequently, ideally before every push to a shared source control repository, and certainly with every automated build on your build server.</span></span>

### <a name="integration-tests"></a><span data-ttu-id="db56b-127">Pruebas de integración</span><span class="sxs-lookup"><span data-stu-id="db56b-127">Integration tests</span></span>

<span data-ttu-id="db56b-128">Aunque es una buena idea encapsular el código que interactúa con la infraestructura como bases de datos y sistemas de archivos, seguirá disponiendo de parte de ese código y, probablemente le interesará probarlo.</span><span class="sxs-lookup"><span data-stu-id="db56b-128">Although it's a good idea to encapsulate your code that interacts with infrastructure like databases and file systems, you will still have some of that code, and you will probably want to test it.</span></span> <span data-ttu-id="db56b-129">Además, debe comprobar que las capas del código interactúan según lo esperado cuando se resuelvan completamente las dependencias de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db56b-129">Additionally, you should verify that your code's layers interact as you expect when your application's dependencies are fully resolved.</span></span> <span data-ttu-id="db56b-130">Esta es la responsabilidad de las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="db56b-130">This is the responsibility of integration tests.</span></span> <span data-ttu-id="db56b-131">Las pruebas de integración tienden a ser más lentas y más difíciles de configurar que las pruebas unitarias, porque a menudo dependen de la infraestructura y de dependencias externas.</span><span class="sxs-lookup"><span data-stu-id="db56b-131">Integration tests tend to be slower and more difficult to set up than unit tests, because they often depend on external dependencies and infrastructure.</span></span> <span data-ttu-id="db56b-132">Por tanto, debe evitar realizar pruebas de cosas que podrían ser pruebas con pruebas unitarias en pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="db56b-132">Thus, you should avoid testing things that could be tests with unit tests in integration tests.</span></span> <span data-ttu-id="db56b-133">Si un escenario determinado se puede probar con una prueba unitaria, debe probarlo con una prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="db56b-133">If you can test a given scenario with a unit test, you should test it with a unit test.</span></span> <span data-ttu-id="db56b-134">Si no es posible, considere la posibilidad de usar una prueba de integración.</span><span class="sxs-lookup"><span data-stu-id="db56b-134">If you can't, then consider using an integration test.</span></span>

<span data-ttu-id="db56b-135">Las pruebas de integración a menudo tendrán procedimientos más complejos de instalación y desmontaje que las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="db56b-135">Integration tests will often have more complex setup and teardown procedures than unit tests.</span></span> <span data-ttu-id="db56b-136">Por ejemplo, una prueba de integración dirigida a una base de datos real necesitará un modo de devolver la base de datos a un estado conocido antes de cada serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="db56b-136">For example, an integration test that goes against an actual database will need a way to return the database to a known state before each test run.</span></span> <span data-ttu-id="db56b-137">Cuando se agregan nuevas pruebas y el esquema de base de datos de producción evoluciona, estos scripts de prueba tienden a aumentar de tamaño y complejidad.</span><span class="sxs-lookup"><span data-stu-id="db56b-137">As new tests are added and the production database schema evolves, these test scripts will tend to grow in size and complexity.</span></span> <span data-ttu-id="db56b-138">En muchos sistemas de gran tamaño, no resulta práctico ejecutar conjuntos completos de pruebas de integración en las estaciones de trabajo de desarrollador antes de insertar en el repositorio los cambios en el control de código fuente compartido.</span><span class="sxs-lookup"><span data-stu-id="db56b-138">In many large systems, it is impractical to run full suites of integration tests on developer workstations before checking in changes to shared source control.</span></span> <span data-ttu-id="db56b-139">En estos casos, las pruebas de integración se pueden ejecutar en un servidor de compilación.</span><span class="sxs-lookup"><span data-stu-id="db56b-139">In these cases, integration tests may be run on a build server.</span></span>

<span data-ttu-id="db56b-140">La clase de implementación LocalFileImageService implementa la lógica para recuperar y devolver los bytes de un archivo de imagen de una carpeta concreta con un identificador dado:</span><span class="sxs-lookup"><span data-stu-id="db56b-140">The LocalFileImageService implementation class implements the logic for fetching and returning the bytes of an image file from a particular folder given an id:</span></span>

```csharp
public class LocalFileImageService : IImageService
{
    private readonly IHostingEnvironment _env;
    public LocalFileImageService(IHostingEnvironment env)
    {
        _env = env;
    }
    public byte[] GetImageBytesById(int id)
    {
        try
        {
            var contentRoot = _env.ContentRootPath + "//Pics";
            var path = Path.Combine(contentRoot, id + ".png");
            return File.ReadAllBytes(path);
        }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

### <a name="functional-tests"></a><span data-ttu-id="db56b-141">Pruebas funcionales</span><span class="sxs-lookup"><span data-stu-id="db56b-141">Functional tests</span></span>

<span data-ttu-id="db56b-142">Las pruebas de integración se escriben desde la perspectiva del desarrollador, para comprobar que algunos componentes del sistema funcionen correctamente entre sí.</span><span class="sxs-lookup"><span data-stu-id="db56b-142">Integration tests are written from the perspective of the developer, to verify that some components of the system work correctly together.</span></span> <span data-ttu-id="db56b-143">Las pruebas funcionales se escriben desde la perspectiva del usuario y comprueban la exactitud del sistema en función de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="db56b-143">Functional tests are written from the perspective of the user, and verify the correctness of the system based on its requirements.</span></span> <span data-ttu-id="db56b-144">En el fragmento siguiente se ofrece una analogía útil para saber cómo pensar en las pruebas funcionales, en comparación con las pruebas unitarias:</span><span class="sxs-lookup"><span data-stu-id="db56b-144">The following excerpt offers a useful analogy for how to think about functional tests, compared to unit tests:</span></span>

> <span data-ttu-id="db56b-145">"En muchas ocasiones, el desarrollo de un sistema se asemeja a la construcción de una casa.</span><span class="sxs-lookup"><span data-stu-id="db56b-145">"Many times the development of a system is likened to the building of a house.</span></span> <span data-ttu-id="db56b-146">Aunque esta analogía no es del todo correcta, podemos ampliarla para explicar la diferencia entre las pruebas unitarias y las funcionales.</span><span class="sxs-lookup"><span data-stu-id="db56b-146">While this analogy isn't quite correct, we can extend it for the purposes of understanding the difference between unit and functional tests.</span></span> <span data-ttu-id="db56b-147">Las pruebas unitarias son similares a un inspector municipal que visita la obra de construcción de una casa.</span><span class="sxs-lookup"><span data-stu-id="db56b-147">Unit testing is analogous to a building inspector visiting a house's construction site.</span></span> <span data-ttu-id="db56b-148">Se centra en los distintos sistemas internos de la casa, los cimientos, los muros, la instalación eléctrica, la fontanería y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="db56b-148">He is focused on the various internal systems of the house, the foundation, framing, electrical, plumbing, and so on.</span></span> <span data-ttu-id="db56b-149">Se asegura (prueba) de que las partes de la casa funcionarán correctamente y de manera segura, es decir, cumplen el código de construcción.</span><span class="sxs-lookup"><span data-stu-id="db56b-149">He ensures (tests) that the parts of the house will work correctly and safely, that is, meet the building code.</span></span> <span data-ttu-id="db56b-150">En este escenario, las pruebas funcionales son análogas al propietario que visita esta misma obra.</span><span class="sxs-lookup"><span data-stu-id="db56b-150">Functional tests in this scenario are analogous to the homeowner visiting this same construction site.</span></span> <span data-ttu-id="db56b-151">Da por supuesto que los sistemas internos se comportarán de forma adecuada, que el inspector municipal está realizando su trabajo.</span><span class="sxs-lookup"><span data-stu-id="db56b-151">He assumes that the internal systems will behave appropriately, that the building inspector is performing his task.</span></span> <span data-ttu-id="db56b-152">El propietario se centra en cómo será vivir en esta casa.</span><span class="sxs-lookup"><span data-stu-id="db56b-152">The homeowner is focused on what it will be like to live in this house.</span></span> <span data-ttu-id="db56b-153">Le preocupa el aspecto de la casa, si las distintas habitaciones tienen un tamaño cómodo, si la casa se ajusta a las necesidades de la familia, si las ventanas están en una zona adecuada para captar el sol por la mañana.</span><span class="sxs-lookup"><span data-stu-id="db56b-153">He is concerned with how the house looks, are the various rooms a comfortable size, does the house fit the family's needs, are the windows in a good spot to catch the morning sun.</span></span> <span data-ttu-id="db56b-154">El propietario está realizando pruebas funcionales de la casa.</span><span class="sxs-lookup"><span data-stu-id="db56b-154">The homeowner is performing functional tests on the house.</span></span> <span data-ttu-id="db56b-155">Tiene la perspectiva del usuario.</span><span class="sxs-lookup"><span data-stu-id="db56b-155">He has the user's perspective.</span></span> <span data-ttu-id="db56b-156">El inspector municipal está realizando pruebas unitarias en la casa.</span><span class="sxs-lookup"><span data-stu-id="db56b-156">The building inspector is performing unit tests on the house.</span></span> <span data-ttu-id="db56b-157">Tiene la perspectiva del constructor".</span><span class="sxs-lookup"><span data-stu-id="db56b-157">He has the builder's perspective."</span></span>

<span data-ttu-id="db56b-158">Fuente: [Unit Testing versus Functional Tests](https://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html) (Diferencias entre pruebas unitarias y pruebas funcionales)</span><span class="sxs-lookup"><span data-stu-id="db56b-158">Source: [Unit Testing versus Functional Tests](https://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)</span></span>

<span data-ttu-id="db56b-159">Me gusta decir: "Como desarrolladores, fallamos de dos maneras: creamos algo de forma incorrecta o creamos algo incorrecto".</span><span class="sxs-lookup"><span data-stu-id="db56b-159">I'm fond of saying "As developers, we fail in two ways: we build the thing wrong, or we build the wrong thing."</span></span> <span data-ttu-id="db56b-160">Las pruebas unitarias aseguran que se cree algo de forma correcta y las pruebas funcionales que se cree algo correcto.</span><span class="sxs-lookup"><span data-stu-id="db56b-160">Unit tests ensure you are building the thing right; functional tests ensure you are building the right thing.</span></span>

<span data-ttu-id="db56b-161">Como las pruebas funcionales operan en el nivel de sistema, pueden requerir cierto grado de automatización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="db56b-161">Since functional tests operate at the system level, they may require some degree of UI automation.</span></span> <span data-ttu-id="db56b-162">Al igual que las pruebas de integración, también suelen funcionar con algún tipo de infraestructura de pruebas.</span><span class="sxs-lookup"><span data-stu-id="db56b-162">Like integration tests, they usually work with some kind of test infrastructure as well.</span></span> <span data-ttu-id="db56b-163">Esto hace que sean más lentas y frágiles que las pruebas unitarias y las de integración.</span><span class="sxs-lookup"><span data-stu-id="db56b-163">This makes them slower and more brittle than unit and integration tests.</span></span> <span data-ttu-id="db56b-164">Solo se deben tener las pruebas funcionales necesarias para estar seguro de que el sistema se comporta tal y como esperan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="db56b-164">You should have only as many functional tests as you need to be confident the system is behaving as users expect.</span></span>

### <a name="testing-pyramid"></a><span data-ttu-id="db56b-165">Pirámide de pruebas</span><span class="sxs-lookup"><span data-stu-id="db56b-165">Testing Pyramid</span></span>

<span data-ttu-id="db56b-166">Martin Fowler escribió sobre la pirámide de pruebas, de la que se muestra un ejemplo en la figura 9-1.</span><span class="sxs-lookup"><span data-stu-id="db56b-166">Martin Fowler wrote about the testing pyramid, an example of which is shown in Figure 9-1.</span></span>

![](./media/image9-1.png)

<span data-ttu-id="db56b-167">Figura 9-1 Pirámide de pruebas</span><span class="sxs-lookup"><span data-stu-id="db56b-167">Figure 9-1 Testing Pyramid</span></span>

<span data-ttu-id="db56b-168">Los diferentes niveles de la pirámide y sus tamaños relativos representan distintos tipos de pruebas y cuántas se deben escribir para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db56b-168">The different layers of the pyramid, and their relative sizes, represent different kinds of tests and how many you should write for your application.</span></span> <span data-ttu-id="db56b-169">Como se puede ver, la recomendación es tener una base grande de pruebas unitarias, respaldada por un nivel más pequeño de pruebas de integración, con un nivel incluso más pequeño de pruebas funcionales.</span><span class="sxs-lookup"><span data-stu-id="db56b-169">As you can see, the recommendation is to have a large base of unit tests, supported by a smaller layer of integration tests, with an even smaller layer of functional tests.</span></span> <span data-ttu-id="db56b-170">Idealmente, cada nivel solo debería incluir las pruebas que no se puedan realizar de forma adecuada en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="db56b-170">Each layer should ideally only have tests in it that cannot be performed adequately at a lower layer.</span></span> <span data-ttu-id="db56b-171">Tenga presente la pirámide de pruebas al tratar de decidir qué tipo de prueba necesita para un escenario determinado.</span><span class="sxs-lookup"><span data-stu-id="db56b-171">Keep the testing pyramid in mind when you are trying to decide which kind of test you need for a particular scenario.</span></span>

### <a name="what-to-test"></a><span data-ttu-id="db56b-172">Qué se va a probar</span><span class="sxs-lookup"><span data-stu-id="db56b-172">What to test</span></span>

<span data-ttu-id="db56b-173">Un problema común para los desarrolladores sin experiencia con la escritura de pruebas automatizadas es determinar lo que se debe probar.</span><span class="sxs-lookup"><span data-stu-id="db56b-173">A common problem for developers who are inexperienced with writing automated tests is coming up with what to test.</span></span> <span data-ttu-id="db56b-174">Un buen punto de partida es probar la lógica condicional.</span><span class="sxs-lookup"><span data-stu-id="db56b-174">A good starting point is to test conditional logic.</span></span> <span data-ttu-id="db56b-175">Siempre que haya un método con un comportamiento que cambia en función de una instrucción condicional (if-else, switch, etc.), debería poder dar idear al menos un par de pruebas que confirmen el comportamiento correcto para determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="db56b-175">Anywhere you have a method with behavior that changes based on a conditional statement (if-else, switch, etc.), you should be able to come up at least a couple of tests that confirm the correct behavior for certain conditions.</span></span> <span data-ttu-id="db56b-176">Si el código tiene condiciones de error, es conveniente escribir al menos una prueba para la "ruta feliz" a través del código (sin errores) y al menos una prueba para la "ruta triste" (con errores o resultados pocos frecuentes) para confirmar que la aplicación se comporta según lo previsto ante los errores.</span><span class="sxs-lookup"><span data-stu-id="db56b-176">If your code has error conditions, it's good to write at least one test for the "happy path" through the code (with no errors), and at least one test for the "sad path" (with errors or atypical results) to confirm your application behaves as expected in the face of errors.</span></span> <span data-ttu-id="db56b-177">Por último, intente centrarse en probar cosas en las que se pueda producir un error, en lugar de centrarse en métricas como la cobertura de código.</span><span class="sxs-lookup"><span data-stu-id="db56b-177">Finally, try to focus on testing things that can fail, rather than focusing on metrics like code coverage.</span></span> <span data-ttu-id="db56b-178">Por lo general, es mejor tener más cobertura de código que menos.</span><span class="sxs-lookup"><span data-stu-id="db56b-178">More code coverage is better than less, generally.</span></span> <span data-ttu-id="db56b-179">Pero escribir algunas pruebas más de un método muy complejo y esencial para la empresa suele ser un mejor uso del tiempo que escribir pruebas para propiedades automáticas solo para mejorar la métrica de cobertura del código de prueba.</span><span class="sxs-lookup"><span data-stu-id="db56b-179">However, writing a few more tests of a very complex and business-critical method is usually a better use of time than writing tests for auto-properties just to improve test code coverage metrics.</span></span>

## <a name="organizing-test-projects"></a><span data-ttu-id="db56b-180">Organización de los proyectos de prueba</span><span class="sxs-lookup"><span data-stu-id="db56b-180">Organizing test projects</span></span>

<span data-ttu-id="db56b-181">Los proyectos de prueba se pueden organizar de la manera que mejor funcione.</span><span class="sxs-lookup"><span data-stu-id="db56b-181">Test projects can be organized however works best for you.</span></span> <span data-ttu-id="db56b-182">Es una buena idea separar las pruebas por tipo (prueba unitaria, prueba de integración) y por lo que van a probar (por proyecto, por espacio de nombres).</span><span class="sxs-lookup"><span data-stu-id="db56b-182">It's a good idea to separate tests by type (unit test, integration test) and by what they are testing (by project, by namespace).</span></span> <span data-ttu-id="db56b-183">Que esta separación conste de carpetas dentro de un único proyecto de prueba o de varios es una decisión de diseño.</span><span class="sxs-lookup"><span data-stu-id="db56b-183">Whether this separation consists of folders within a single test project, or multiple test projects, is a design decision.</span></span> <span data-ttu-id="db56b-184">Lo más sencillo es un proyecto, pero para proyectos grandes con muchas pruebas, o bien para ejecutar más fácilmente otros conjuntos de pruebas, es posible que le interese tener varios proyectos de prueba distintos.</span><span class="sxs-lookup"><span data-stu-id="db56b-184">One project is simplest, but for large projects with many tests, or in order to more easily run different sets of tests, you might want to have several different test projects.</span></span> <span data-ttu-id="db56b-185">Muchos equipos organizan los proyectos de prueba en función del proyecto que se está probando, que para las aplicaciones con más de unos pocos proyectos puede provocar un gran número de proyectos de prueba, en especial si se siguen dividiendo según el tipo de pruebas de cada proyecto.</span><span class="sxs-lookup"><span data-stu-id="db56b-185">Many teams organize test projects based on the project they are testing, which for applications with more than a few projects can result in a large number of test projects, especially if you still break these down according to what kind of tests are in each project.</span></span> <span data-ttu-id="db56b-186">Un enfoque de compromiso consiste en disponer de un proyecto por tipo de prueba, por aplicación, con carpetas dentro de los proyectos de prueba para indicar el proyecto (y la clase) que se van a probar.</span><span class="sxs-lookup"><span data-stu-id="db56b-186">A compromise approach is to have one project per kind of test, per application, with folders inside the test projects to indicate the project (and class) being tested.</span></span>

<span data-ttu-id="db56b-187">Un enfoque común consiste en organizar los proyectos de la aplicación en una carpeta "src" y los proyectos de prueba en una carpeta "tests" paralela.</span><span class="sxs-lookup"><span data-stu-id="db56b-187">A common approach is to organize the application projects under a ‘src' folder, and the application's test projects under a parallel ‘tests' folder.</span></span> <span data-ttu-id="db56b-188">Si esta organización le parece útil, puede crear carpetas de solución coincidentes en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="db56b-188">You can create matching solution folders in Visual Studio, if you find this organization useful.</span></span>

![](./media/image9-2.png)

<span data-ttu-id="db56b-189">Figura 9-2 Organización de las pruebas en la solución</span><span class="sxs-lookup"><span data-stu-id="db56b-189">Figure 9-2 Test organization in your solution</span></span>

<span data-ttu-id="db56b-190">Puede usar el marco de pruebas que prefiera.</span><span class="sxs-lookup"><span data-stu-id="db56b-190">You can use whichever test framework you prefer.</span></span> <span data-ttu-id="db56b-191">El marco de trabajo xUnit funciona bien y es en el que se escriben todas las pruebas de ASP.NET Core y EF Core.</span><span class="sxs-lookup"><span data-stu-id="db56b-191">The xUnit framework works well and is what all of the ASP.NET Core and EF Core tests are written in.</span></span> <span data-ttu-id="db56b-192">Puede agregar un proyecto de prueba de xUnit en Visual Studio con la plantilla que se muestra en la figura 9-3 o desde la CLI mediante dotnet new xunit.</span><span class="sxs-lookup"><span data-stu-id="db56b-192">You can add an xUnit test project in Visual Studio using the template shown in Figure 9-3, or from the CLI using dotnet new xunit.</span></span>

![](./media/image9-3.png)

<span data-ttu-id="db56b-193">Figura 9-3 Agregar un proyecto de prueba de xUnit en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="db56b-193">Figure 9-3 Add an xUnit Test Project in Visual Studio</span></span>

### <a name="test-naming"></a><span data-ttu-id="db56b-194">Nombres de pruebas</span><span class="sxs-lookup"><span data-stu-id="db56b-194">Test naming</span></span>

<span data-ttu-id="db56b-195">Debe asignar nombres a las pruebas de forma coherente, con un nombre que indique lo que hace cada prueba.</span><span class="sxs-lookup"><span data-stu-id="db56b-195">You should name your tests in a consistent fashion, with names that indicate what each test does.</span></span> <span data-ttu-id="db56b-196">Un enfoque con el que he tenido buenos resultados consiste en asignar nombres a las clases de prueba en función de la clase y el método que estén probando.</span><span class="sxs-lookup"><span data-stu-id="db56b-196">One approach I've had great success with is to name test classes according to the class and method they are testing.</span></span> <span data-ttu-id="db56b-197">Esto da como resultado muchas clases de prueba pequeñas, pero deja muy claro la responsabilidad de cada una.</span><span class="sxs-lookup"><span data-stu-id="db56b-197">This results in many small test classes, but it makes it extremely clear what each test is responsible for.</span></span> <span data-ttu-id="db56b-198">Con el nombre de la clase de prueba configurado para identificar la clase y el método que se van a probar, se puede usar el nombre del método de prueba para especificar el comportamiento que se está probando.</span><span class="sxs-lookup"><span data-stu-id="db56b-198">With the test class name set up to identify the class and method to be tested, the test method name can be used to specify the behavior being tested.</span></span> <span data-ttu-id="db56b-199">Esto debe incluir el comportamiento esperado y las entradas o suposiciones que deban producir este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="db56b-199">This should include the expected behavior and any inputs or assumptions that should yield this behavior.</span></span> <span data-ttu-id="db56b-200">Algunos nombres de prueba de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="db56b-200">Some example test names:</span></span>

- `CatalogControllerGetImage.CallsImageServiceWithId`

- `CatalogControllerGetImage.LogsWarningGivenImageMissingException`

- `CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess`

- `CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException`

<span data-ttu-id="db56b-201">Una variante de este enfoque finaliza cada nombre de clase de prueba con "Should" (Debería) y modifica ligeramente el tiempo:</span><span class="sxs-lookup"><span data-stu-id="db56b-201">A variation of this approach ends each test class name with "Should" and modifies the tense slightly:</span></span>

- <span data-ttu-id="db56b-202">`CatalogControllerGetImage`**Should**`.`**Call**`ImageServiceWithId`</span><span class="sxs-lookup"><span data-stu-id="db56b-202">`CatalogControllerGetImage`**Should**`.`**Call**`ImageServiceWithId`</span></span>

- <span data-ttu-id="db56b-203">`CatalogControllerGetImage`**Should**`.`**Log**`WarningGivenImageMissingException`</span><span class="sxs-lookup"><span data-stu-id="db56b-203">`CatalogControllerGetImage`**Should**`.`**Log**`WarningGivenImageMissingException`</span></span>

<span data-ttu-id="db56b-204">Para algunos equipos el segundo método de nomenclatura es más claro, aunque un poco más detallado.</span><span class="sxs-lookup"><span data-stu-id="db56b-204">Some teams find the second naming approach clearer, though slightly more verbose.</span></span> <span data-ttu-id="db56b-205">En cualquier caso, intente usar una convención de nomenclatura que proporcione información del comportamiento de la prueba, para que cuando se produzca un error en una o varias pruebas, sea obvio a partir de los nombres en qué casos se ha producido el error.</span><span class="sxs-lookup"><span data-stu-id="db56b-205">In any case, try to use a naming convention that provides insight into test behavior, so that when one or more tests fail, it's obvious from their names what cases have failed.</span></span> <span data-ttu-id="db56b-206">Evite asignar nombres a las pruebas de forma vaga, como PruebasControlador.Prueba1, dado que no ofrecen ningún valor cuando se ven en los resultados de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="db56b-206">Avoid naming you tests vaguely, such as ControllerTests.Test1, as these offer no value when you see them in test results.</span></span>

<span data-ttu-id="db56b-207">Si sigue una convención de nomenclatura como la anterior que genera muchas clases de prueba pequeñas, es aconsejable organizar más las pruebas mediante carpetas y espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="db56b-207">If you follow a naming convention like the one above that produces many small test classes, it's a good idea to further organize your tests using folders and namespaces.</span></span> <span data-ttu-id="db56b-208">En la figura 9-4 se muestra un enfoque para organizar las pruebas por carpeta en varios proyectos de prueba.</span><span class="sxs-lookup"><span data-stu-id="db56b-208">Figure 9-4 shows one approach to organizing tests by folder within several test projects.</span></span>

![](./media/image9-4.png)

<span data-ttu-id="db56b-209">**Figura 9-4.**</span><span class="sxs-lookup"><span data-stu-id="db56b-209">**Figure 9-4.**</span></span> <span data-ttu-id="db56b-210">Organización de las clases de prueba por carpeta en función de la clase que se está probando.</span><span class="sxs-lookup"><span data-stu-id="db56b-210">Organizing test classes by folder based on class being tested.</span></span>

<span data-ttu-id="db56b-211">Evidentemente, si una clase de aplicación determinada tiene muchos métodos para probar (y, por tanto, muchas clases de prueba), tiene sentido colocarlos en una carpeta correspondiente a la clase de aplicación.</span><span class="sxs-lookup"><span data-stu-id="db56b-211">Of course, if a particular application class has many methods being tested (and thus many test classes), it may make sense to place these in a folder corresponding to the application class.</span></span> <span data-ttu-id="db56b-212">Esta organización es similar a cómo se podrían organizar los archivos en carpetas en otra parte.</span><span class="sxs-lookup"><span data-stu-id="db56b-212">This organization is no different than how you might organize files into folders elsewhere.</span></span> <span data-ttu-id="db56b-213">Si tiene más de tres o cuatro archivos relacionados en una carpeta que contiene otros muchos archivos, suele resultar útil moverlos a su propia subcarpeta.</span><span class="sxs-lookup"><span data-stu-id="db56b-213">If you have more than three or four related files in a folder containing many other files, it's often helpful to move them into their own subfolder.</span></span>

## <a name="unit-testing-aspnet-core-apps"></a><span data-ttu-id="db56b-214">Pruebas unitarias de aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="db56b-214">Unit testing ASP.NET Core apps</span></span>

<span data-ttu-id="db56b-215">En una aplicación ASP.NET Core bien diseñada, la mayor parte de la complejidad y la lógica de negocios se encapsulará en entidades de negocio y una variedad de servicios.</span><span class="sxs-lookup"><span data-stu-id="db56b-215">In a well-designed ASP.NET Core application, most of the complexity and business logic will be encapsulated in business entities and a variety of services.</span></span> <span data-ttu-id="db56b-216">La propia aplicación ASP.NET Core MVC con sus controladores, filtros, modelos de vista y vistas, no debería requerir muchas pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="db56b-216">The ASP.NET Core MVC app itself, with its controllers, filters, viewmodels, and views, should require very few unit tests.</span></span> <span data-ttu-id="db56b-217">Gran parte de la funcionalidad de una acción determinada se encuentra fuera del propio método de acción.</span><span class="sxs-lookup"><span data-stu-id="db56b-217">Much of the functionality of a given action lies outside the action method itself.</span></span> <span data-ttu-id="db56b-218">Comprobar si el enrutamiento funciona correctamente o el control de errores global, no se puede realizar de forma eficaz con una prueba unitaria.</span><span class="sxs-lookup"><span data-stu-id="db56b-218">Testing whether routing works correctly, or global error handling, cannot be done effectively with a unit test.</span></span> <span data-ttu-id="db56b-219">Del mismo modo, los filtros, incluidos los de autenticación y validación del modelo y los de autorización, no se pueden someter a pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="db56b-219">Likewise, any filters, including model validation and authentication and authorization filters, cannot be unit tested.</span></span> <span data-ttu-id="db56b-220">Sin estas fuentes de comportamiento, la mayoría de los métodos de acción deberían ser pequeños, y delegar la mayor parte de su trabajo a servicios que se puedan probar de forma independiente al controlador que los usa.</span><span class="sxs-lookup"><span data-stu-id="db56b-220">Without these sources of behavior, most action methods should be trivially small, delegating the bulk of their work to services that can be tested independent of the controller that uses them.</span></span>

<span data-ttu-id="db56b-221">En ocasiones tendrá que refactorizar el código para poder realizar pruebas unitarias en él.</span><span class="sxs-lookup"><span data-stu-id="db56b-221">Sometimes you'll need to refactor your code in order to unit test it.</span></span> <span data-ttu-id="db56b-222">Con frecuencia, esto implica la identificación de abstracciones y el uso de la inserción de dependencias para tener acceso a la abstracción en el código que se quiere probar, en lugar de codificar directamente en la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="db56b-222">Frequently this involves identifying abstractions and using dependency injection to access the abstraction in the code you'd like to test, rather than coding directly against infrastructure.</span></span> <span data-ttu-id="db56b-223">Por ejemplo, considere este método de acción simple para mostrar imágenes:</span><span class="sxs-lookup"><span data-stu-id="db56b-223">For example, consider this simple action method for displaying images:</span></span>

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

<span data-ttu-id="db56b-224">La realización de pruebas unitarias en este método se complica debido a su dependencia directa de System.IO.File, que usa para leer del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="db56b-224">Unit testing this method is made difficult by its direct dependency on System.IO.File, which it uses to read from the file system.</span></span> <span data-ttu-id="db56b-225">Puede probar este comportamiento para asegurarse de que funciona de la forma esperada, pero si lo hace con archivos reales será una prueba de integración.</span><span class="sxs-lookup"><span data-stu-id="db56b-225">You can test this behavior to ensure it works as expected, but doing so with real files is an integration test.</span></span> <span data-ttu-id="db56b-226">Cabe mencionar que no se puede probar la ruta de este método: verá cómo hacerlo con una prueba funcional en breve.</span><span class="sxs-lookup"><span data-stu-id="db56b-226">It's worth noting you can't test this method's route – you'll see how to do this with a functional test shortly.</span></span>

<span data-ttu-id="db56b-227">Si no se pueden realizar directamente pruebas unitarias del comportamiento del sistema de archivos y no se puede probar la ruta, ¿qué se puede probar?</span><span class="sxs-lookup"><span data-stu-id="db56b-227">If you can't unit test the file system behavior directly, and you can't test the route, what is there to test?</span></span> <span data-ttu-id="db56b-228">Después de la refactorización para que las pruebas unitarias sean posibles, puede detectar varios casos de prueba y comportamiento que falta, como el control de errores.</span><span class="sxs-lookup"><span data-stu-id="db56b-228">Well, after refactoring to make unit testing possible, you may discover some test cases and missing behavior, such as error handling.</span></span> <span data-ttu-id="db56b-229">¿Qué hace el método cuando no se encuentra un archivo?</span><span class="sxs-lookup"><span data-stu-id="db56b-229">What does the method do when a file isn't found?</span></span> <span data-ttu-id="db56b-230">¿Qué debería hacer?</span><span class="sxs-lookup"><span data-stu-id="db56b-230">What should it do?</span></span> <span data-ttu-id="db56b-231">En este ejemplo, el método refactorizado tiene el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="db56b-231">In this example, the refactored method looks like this:</span></span>

```csharp
[HttpGet("[controller]/pic/{id}")\]
public IActionResult GetImage(int id)
{
    byte[] imageBytes;
    try
    {
        imageBytes = _imageService.GetImageBytesById(id);
    }
    catch (CatalogImageMissingException ex)
    {
        _logger.LogWarning($"No image found for id: {id}");
        return NotFound();
    }
    return File(imageBytes, "image/png");
}
```

<span data-ttu-id="db56b-232">\_logger e \_imageService se insertan como dependencias.</span><span class="sxs-lookup"><span data-stu-id="db56b-232">The \_logger and \_imageService are both injected as dependencies.</span></span> <span data-ttu-id="db56b-233">Ahora se puede probar que el mismo identificador que se pasa al método de acción se pasa a \_imageService, y que los bytes resultantes se devuelven como parte de FileResult.</span><span class="sxs-lookup"><span data-stu-id="db56b-233">Now you can test that the same id that is passed to the action method is passed to the \_imageService, and that the resulting bytes are returned as part of the FileResult.</span></span> <span data-ttu-id="db56b-234">También se puede probar que el registro de errores se está realizando de la forma esperada y que se devuelve un resultado de NotFound si la imagen no se encuentra, suponiendo que se trate de un comportamiento importante de la aplicación (es decir, no solo código temporal que el desarrollador agregó para diagnosticar un problema).</span><span class="sxs-lookup"><span data-stu-id="db56b-234">You can also test that error logging is happening as expected, and that a NotFound result is returned if the image is missing, assuming this is important application behavior (that is, not just temporary code the developer added to diagnose an issue).</span></span> <span data-ttu-id="db56b-235">La lógica real del archivo se ha trasladado a un servicio de implementación independiente y se ha ampliado para devolver una excepción específica de la aplicación en el caso de un archivo que falta.</span><span class="sxs-lookup"><span data-stu-id="db56b-235">The actual file logic has moved into a separate implementation service, and has been augmented to return an application-specific exception for the case of a missing file.</span></span> <span data-ttu-id="db56b-236">Puede probar esta implementación de forma independiente, con una prueba de integración.</span><span class="sxs-lookup"><span data-stu-id="db56b-236">You can test this implementation independently, using an integration test.</span></span>

## <a name="integration-testing-aspnet-core-apps"></a><span data-ttu-id="db56b-237">Pruebas de integración en aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="db56b-237">Integration testing ASP.NET Core apps</span></span>

<span data-ttu-id="db56b-238">Para comprobar que LocalFileImageService funciona correctamente mediante una prueba de integración, tendrá que crear un archivo de imagen de prueba conocida y comprobar que el servicio lo devuelve si se proporciona una entrada específica.</span><span class="sxs-lookup"><span data-stu-id="db56b-238">To test that a LocalFileImageService works correctly using an integraiton test, you need to create a known test image file and verify that the service returns it given a specific input.</span></span> <span data-ttu-id="db56b-239">También debe evitar el uso de objetos ficticios en el comportamiento que se quiere probar (en este caso, leer del sistema de archivos).</span><span class="sxs-lookup"><span data-stu-id="db56b-239">You should take care not to use mock objects on the behavior you actually want to test (in this case, reading from the file system).</span></span> <span data-ttu-id="db56b-240">Pero los objetos ficticios pueden seguir siendo útiles para configurar pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="db56b-240">However, mock objects may still be useful to set up integration tests.</span></span> <span data-ttu-id="db56b-241">En este caso, se puede simular IHostingEnvironment para que su ContentRootPath apunte a la carpeta que se va a usar para la imagen de prueba.</span><span class="sxs-lookup"><span data-stu-id="db56b-241">In this case, you can mock IHostingEnvironment so that its ContentRootPath points to the folder you're going to use for your test image.</span></span> <span data-ttu-id="db56b-242">La clase de prueba de integración funcional completa se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="db56b-242">The complete working integration test class is shown here:</span></span>

```csharp
public class LocalFileImageServiceGetImageBytesById
{
    private byte[] _testBytes = new byte[] { 0x01, 0x02, 0x03 };
    private readonly Mock<IHostingEnvironment> _mockEnvironment = new Mock<IHostingEnvironment>();
    private int _testImageId = 123;
    private string _testFileName = "123.png";

    public LocalFileImageServiceGetImageBytesById()
    {
        // create folder if necessary
        Directory.CreateDirectory(Path.Combine(GetFileDirectory(), "Pics"));
        string filePath = GetFilePath(_testFileName);
        System.IO.File.WriteAllBytes(filePath, _testBytes);
        _mockEnvironment.SetupGet<string>(m => m.ContentRootPath).Returns(GetFileDirectory());
    }

    private string GetFilePath(string fileName)
    {
        return Path.Combine(GetFileDirectory(), "Pics", fileName);
        }
            private string GetFileDirectory()
        {
        var location = System.Reflection.Assembly.GetEntryAssembly().Location;
        return Path.GetDirectoryName(location);
    }

    [Fact]
    public void ReturnsFileContentResultGivenValidId()
    {
        var fileService = new LocalFileImageService(_mockEnvironment.Object);
        var result = fileService.GetImageBytesById(_testImageId);
        Assert.Equal(_testBytes, result);
    }
}
```

> [!NOTE]
> <span data-ttu-id="db56b-243">La propia prueba es muy sencilla: la mayor parte del código es necesaria para configurar el sistema y crear la infraestructura de pruebas (en este caso, un archivo real que se va a leer del disco).</span><span class="sxs-lookup"><span data-stu-id="db56b-243">The test itself is very simple – the bulk of the code is necessary to configure the system and create the testing infrastructure (in this case, an actual file to be read from disk).</span></span> <span data-ttu-id="db56b-244">Esto es normal para las pruebas de integración, que a menudo requieren un trabajo de configuración más complejo que las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="db56b-244">This is typical for integration tests, which often require more complex setup work than unit tests.</span></span>

## <a name="functional-testing-aspnet-core-apps"></a><span data-ttu-id="db56b-245">Pruebas funcionales en aplicaciones ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="db56b-245">Functional testing ASP.NET Core apps</span></span>

<span data-ttu-id="db56b-246">Para las aplicaciones ASP.NET Core, la clase TestServer facilita considerablemente la creación de pruebas funcionales.</span><span class="sxs-lookup"><span data-stu-id="db56b-246">For ASP.NET Core applications, the TestServer class makes functional tests fairly easy to write.</span></span> <span data-ttu-id="db56b-247">Se configura un TestServer mediante un WebHostBuilder directamente (como haría normalmente para la aplicación), o bien con el tipo WebApplicationFactory (disponible en 2.1).</span><span class="sxs-lookup"><span data-stu-id="db56b-247">You configure a TestServer using a WebHostBuilder directly (just as you normally do for your application), or with the WebApplicationFactory type (available in 2.1).</span></span> <span data-ttu-id="db56b-248">Debe intentar que el host de prueba coincida lo máximo posible con el host de producción, para que las pruebas ejecuten un comportamiento similar al que tendrá la aplicación en producción.</span><span class="sxs-lookup"><span data-stu-id="db56b-248">You should try match your test host to your production host as closely as possible, so your tests will exercise behavior similar to what the app will do in production.</span></span> <span data-ttu-id="db56b-249">La clase WebApplicationFactory es útil para la configuración de ContentRoot de TestServer, que ASP.NET Core usa para localizar recursos estáticos como las vistas.</span><span class="sxs-lookup"><span data-stu-id="db56b-249">The WebApplicationFactory class is helpful for configuring the TestServer's ContentRoot, which is used by ASP.NET Core to locate static resource like Views.</span></span>

<span data-ttu-id="db56b-250">Puede crear pruebas funcionales sencillas si crea una clase de prueba que implemente IClassFixture\<WebApplicationFactory\<TEntry>> donde TEntry es la clase de inicio de la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="db56b-250">You can create simple functional tests by creating a test class that implements IClassFixture\<WebApplicationFactory\<TEntry>> where TEntry is your web application's Startup class.</span></span> <span data-ttu-id="db56b-251">Después de agregar esto, el accesorio de prueba puede crear un cliente con el método CreateClient de la fábrica:</span><span class="sxs-lookup"><span data-stu-id="db56b-251">With this in place, your test fixture can create a client using the factory's CreateClient method:</span></span>

```cs
public class BasicWebTests : IClassFixture<WebApplicationFactory<Startup>>
{
    protected readonly HttpClient _client;

    public BaseWebTest(WebApplicationFactory<Startup> factory)
    {
        _client = factory.CreateClient();
    }

    // write tests that use _client
}
```

<span data-ttu-id="db56b-252">Con frecuencia, le interesará configurar opciones adicionales del sitio antes de ejecutar cada prueba, como configurar la aplicación para que use un almacén de datos en memoria y, después, propagar datos de prueba en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="db56b-252">Frequently, you'll want to perform some additional configuration of your site before each test runs, such as configuring the application to use an in memory data store and then seeding the application with test data.</span></span> <span data-ttu-id="db56b-253">Para ello, debe crear una subclase de WebApplicationFactory<TEntry> propia y reemplazar su método ConfigureWebHost.</span><span class="sxs-lookup"><span data-stu-id="db56b-253">To do this, you should create your own subclass of WebApplicationFactory<TEntry> and override its ConfigureWebHost method.</span></span> <span data-ttu-id="db56b-254">El ejemplo siguiente es del proyecto eShopOnWeb FunctionalTests y se usa como parte de las pruebas en la aplicación web principal.</span><span class="sxs-lookup"><span data-stu-id="db56b-254">The example below is from the eShopOnWeb FunctionalTests project and is used as part of the tests on the main web application.</span></span>

```cs
using Infrastructure.Data;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc.Testing;
using Microsoft.eShopWeb;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Logging;
using System;
using Microsoft.EntityFrameworkCore;
using Infrastructure.Identity;

namespace FunctionalTests.WebRazorPages
{
    public class CustomWebRazorPagesApplicationFactory<TStartup>
    : WebApplicationFactory<Startup>
    {
        protected override void ConfigureWebHost(IWebHostBuilder builder)
        {
            builder.ConfigureServices(services =>
            {
                // Create a new service provider.
                var serviceProvider = new ServiceCollection()
                    .AddEntityFrameworkInMemoryDatabase()
                    .BuildServiceProvider();

                // Add a database context (ApplicationDbContext) using an in-memory
                // database for testing.
                services.AddDbContext<CatalogContext>(options =>
                {
                    options.UseInMemoryDatabase("InMemoryDbForTesting");
                    options.UseInternalServiceProvider(serviceProvider);
                });

                services.AddDbContext<AppIdentityDbContext>(options =>
                {
                    options.UseInMemoryDatabase("Identity");
                    options.UseInternalServiceProvider(serviceProvider);
                });

                // Build the service provider.
                var sp = services.BuildServiceProvider();

                // Create a scope to obtain a reference to the database
                // context (ApplicationDbContext).
                using (var scope = sp.CreateScope())
                {
                    var scopedServices = scope.ServiceProvider;
                    var db = scopedServices.GetRequiredService<CatalogContext>();
                    var loggerFactory = scopedServices.GetRequiredService<ILoggerFactory>();

                    var logger = scopedServices
                        .GetRequiredService<ILogger<CustomWebRazorPagesApplicationFactory<TStartup>>>();

                    // Ensure the database is created.
                    db.Database.EnsureCreated();

                    try
                    {
                        // Seed the database with test data.
                        CatalogContextSeed.SeedAsync(db, loggerFactory).Wait();
                    }
                    catch (Exception ex)
                    {
                        logger.LogError(ex, $"An error occurred seeding the " +
                            "database with test messages. Error: {ex.Message}");
                    }
                }
            });
        }
    }
}
```

<span data-ttu-id="db56b-255">Las pruebas pueden hacer uso de esta clase WebApplicationFactory personalizada para crear a un cliente y, después, realizar solicitudes a la aplicación mediante esta instancia de cliente.</span><span class="sxs-lookup"><span data-stu-id="db56b-255">Tests can make use of this custom WebApplicationFactory by using it to create a client and then making requests to the application using this client instance.</span></span> <span data-ttu-id="db56b-256">La aplicación tendrá datos propagados que se pueden usar como parte de las aserciones de la prueba.</span><span class="sxs-lookup"><span data-stu-id="db56b-256">The application will have data seeded that can be used as part of the test's assertions.</span></span> <span data-ttu-id="db56b-257">Esta prueba comprueba que la página principal de la aplicación de Razor Pages eShopOnWeb se carga correctamente y que incluye una lista de productos que se agregó a la aplicación como parte de los datos de inicialización.</span><span class="sxs-lookup"><span data-stu-id="db56b-257">This test verifies that the home page of the eShopOnWeb Razor Pages application loads correctly and includes a product listing that was added to the application as part of the seed data.</span></span>

```cs
using Microsoft.eShopWeb.RazorPages;
using System.Net.Http;
using System.Threading.Tasks;
using Xunit;

namespace FunctionalTests.WebRazorPages
{
    public class HomePageOnGet : IClassFixture<CustomWebRazorPagesApplicationFactory<Startup>>
    {
        public HomePageOnGet(CustomWebRazorPagesApplicationFactory<Startup> factory)
        {
            Client = factory.CreateClient();
        }

        public HttpClient Client { get; }

        [Fact]
        public async Task ReturnsHomePageWithProductListing()
        {
            // Arrange & Act
            var response = await Client.GetAsync("/");
            response.EnsureSuccessStatusCode();
            var stringResponse = await response.Content.ReadAsStringAsync();

            // Assert
            Assert.Contains(".NET Bot Black Sweatshirt", stringResponse); // from seed data
        }
    }
}
```

<span data-ttu-id="db56b-258">Esta prueba funcional ejecuta la pila de la aplicación ASP.NET Core MVC o Razor Pages completa, incluidos todo el software intermedio, filtros, enlazadores, etc., que puedan estar definidos.</span><span class="sxs-lookup"><span data-stu-id="db56b-258">This functional test exercises the full ASP.NET Core MVC / Razor Pages application stack, including all middleware, filters, binders, etc. that may be in place.</span></span> <span data-ttu-id="db56b-259">Comprueba que una ruta determinada ("/") devuelve el código de estado correcto esperado y la salida HTML.</span><span class="sxs-lookup"><span data-stu-id="db56b-259">It verifies that a given route ("/") returns the expected success status code and HTML output.</span></span> <span data-ttu-id="db56b-260">Lo hace sin configurar un servidor web real y de ese modo evita gran parte de la fragilidad que supone el uso de un servidor web real para realizar pruebas (por ejemplo, problemas con la configuración de firewall).</span><span class="sxs-lookup"><span data-stu-id="db56b-260">It does so without setting up a real web server, and so avoids much of the brittleness that using a real web server for testing can experience (for example, problems with firewall settings).</span></span> <span data-ttu-id="db56b-261">Las pruebas funcionales que se ejecutan en TestServer normalmente son más lentas que las pruebas unitarias y de integración, pero son mucho más rápidas que las que se ejecutarían a través de la red a un servidor web de prueba.</span><span class="sxs-lookup"><span data-stu-id="db56b-261">Functional tests that run against TestServer are usually slower than integration and unit tests, but are much faster than tests that would run over the network to a test web server.</span></span> <span data-ttu-id="db56b-262">Debe usar las pruebas funcionales para garantizar que la pila de front-end de la aplicación funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="db56b-262">You should use functional tests to ensure your application's front end stack is working as expected.</span></span> <span data-ttu-id="db56b-263">Estas pruebas son especialmente útiles al buscar duplicados en controladores o páginas, y solucionar la duplicación mediante la adición de filtros.</span><span class="sxs-lookup"><span data-stu-id="db56b-263">These tests are especially useful when you find duplication in your controllers or pages and you address the duplication by adding filters.</span></span> <span data-ttu-id="db56b-264">Idealmente, esta refactorización no cambiará el comportamiento de la aplicación y un conjunto de pruebas funcionales comprobará que es así.</span><span class="sxs-lookup"><span data-stu-id="db56b-264">Ideally, this refactoring will not change the behavior of the application, and a suite of functional tests will verify this is the case.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="db56b-265">[Anterior](work-with-data-in-asp-net-core-apps.md)
>[Siguiente](development-process-for-azure.md)</span><span class="sxs-lookup"><span data-stu-id="db56b-265">[Previous](work-with-data-in-asp-net-core-apps.md)
[Next](development-process-for-azure.md)</span></span>