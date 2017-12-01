---
title: Probar aplicaciones MVC de ASP.NET Core
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | Probar aplicaciones MVC de ASP.NET Core"
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 4611ffa8334e124946e849306d3281b695830eb1
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="test-aspnet-core-mvc-apps"></a>Probar aplicaciones MVC de ASP.NET Core

> _"Si no le gusta el producto de pruebas unitarias, más probable es que los clientes no desean probarlo, ya sea."_
> _ - Anónimo:

## <a name="summary"></a>Resumen

Software de cualquier complejidad puede producir errores inesperados en respuesta a los cambios en. Por lo tanto, es necesario para todas las aplicaciones más triviales (o menos críticas) realizar pruebas después de realizar cambios. Son la más lenta, manera menos confiable y más costosa pruebas manuales para probar software. Desgraciadamente, si las aplicaciones no están diseñadas para ser pueden someterse a prueba, puede ser el único medio disponible. Las aplicaciones escritas siguiente los principios arquitectónicos dispuestos en el capítulo X deben ser pueden someterse a prueba de unidad y las aplicaciones de ASP.NET Core admiten integración automatizada y también las pruebas funcionales.

## <a name="kinds-of-automated-tests"></a>Tipos de pruebas automatizadas

Hay muchos tipos de pruebas automatizadas para las aplicaciones de software. La forma más sencilla, prueba de nivel más bajo es la prueba unitaria. En un nivel ligeramente superior hay pruebas de integración y pruebas funcionales. Otros tipos de pruebas, como pruebas de interfaz de usuario, las pruebas de carga, las pruebas de esfuerzo y pruebas de humo, quedan fuera del ámbito de este documento.

### <a name="unit-tests"></a>Pruebas unitarias

Una prueba unitaria prueba un único elemento de la lógica de la aplicación. Uno puede describir aún más haciendo una lista de algunas de las cosas que no se encuentra. Una prueba unitaria no probar cómo su código funciona con dependencias o infraestructura – comprueba qué integración es para. Una prueba unitaria no prueba el código se escribe en el marco de trabajo, debe asumir que funciona o, si te parece no, registre un error y codificar una solución alternativa. Una prueba unitaria se ejecuta completamente en la memoria y en proceso. No se comunican con el sistema de archivos, la red o una base de datos. Pruebas unitarias solo deben probar el código.

Pruebas unitarias, en virtud del hecho de que se prueba únicamente una sola unidad del código, no tiene dependencias externas, deben ejecutar muy rápidamente. Por lo tanto, debe ser capaz de ejecutar conjuntos de pruebas de cientos de pruebas unitarias en unos segundos. Ejecutar con frecuencia, lo ideal es que antes de cada inserción a un repositorio de control de código fuente compartido y, por supuesto, con cada compilación automatizada en el servidor de compilación.

### <a name="integration-tests"></a>Pruebas de integración

Aunque es una buena idea para encapsular el código que interactúa con la infraestructura, como los sistemas de archivos y bases de datos, seguirá disponiendo de parte de ese código y, probablemente deseará probarlo. Además, debe comprobar que las capas de su código interactúan según lo esperado cuando se resolverán completamente las dependencias de la aplicación. Se trata de la responsabilidad de pruebas de integración. Pruebas de integración tienden a ser más lento y más difíciles de configurar que las pruebas unitarias, porque a menudo dependen de infraestructura y dependencias externas. Por lo tanto, debe evitar, lo que podría ser pruebas con pruebas unitarias en las pruebas de integración de pruebas. Si un escenario determinado se puede probar con una prueba unitaria, debe probar con una prueba unitaria. Si no es posible, considere la posibilidad de usar una prueba de integración.

Pruebas de integración a menudo tendrá el programa de instalación más compleja y procedimientos de destrucción de pruebas unitarias. Por ejemplo, una prueba de integración que va en una base de datos real será necesario un modo para devolver la base de datos a un estado conocido antes de cada serie de pruebas. Cuando se agregan nuevas pruebas y el esquema de base de datos de producción evoluciona, estas secuencias de comandos tienden a aumentar de tamaño y la complejidad de la prueba. En muchos sistemas de gran tamaño, no resulta práctico ejecutar completas conjuntos de pruebas de integración en las estaciones de trabajo de desarrollador antes de proteger los cambios en el control de código fuente compartido. En estos casos, se pueden ejecutar pruebas de integración en un servidor de compilación.

La clase de implementación LocalFileImageService implementa la lógica para buscar y devolver los bytes de un archivo de imagen de una carpeta concreta con un identificador dada:

```cs
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
```

### <a name="functional-tests"></a>Pruebas funcionales

Pruebas de integración se escriben desde la perspectiva del desarrollador, para comprobar que algunos componentes del sistema funcionen correctamente entre sí. Pruebas funcionales se escriben desde la perspectiva del usuario y comprobar la exactitud del sistema en función de sus requisitos. El extracto siguiente ofrece una analogía útil para saber cómo pensar acerca de las pruebas funcionales, en comparación con pruebas unitarias:

> "Muchas veces el desarrollo de un sistema es asemejarse a la generación de una casa. Mientras esta analogía no es bastante correcta, podemos ampliarlo para explicar la diferencia entre unitarias y pruebas funcionales. Pruebas unitarias están análogo a un inspector de creación visitar el sitio de la construcción de una casa. Se ha centrado en los distintos sistemas internos de la casa, la base, tramas, eléctrica, conexión y así sucesivamente. Asegura de (pruebas) que las partes de la casa funcionará correctamente y responder de manera segura, es decir, el código de creación. Pruebas funcionales en este escenario son análogas a los propietarios de casas visitar este mismo sitio de construcción. Da por supuesto que los sistemas internos se comportarán de forma adecuada, que el inspector de creación está realizando su tarea. Los propietarios de casas se centra en ¿qué se va a viven en casa de este. Se ocupa del aspecto de la casa, son las distintas salas un tamaño cómodo y la casa ajustarse a las necesidades de la familia, son las ventanas en una zona adecuada para detectar el sol por la mañana. Los propietarios de casas está realizando pruebas funcionales de la casa. Tiene la perspectiva del usuario. El inspector de creación está realizando pruebas unitarias en la casa. Tiene perspectiva del generador".

Origen: [pruebas frente a funcionales pruebas unitarias](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)

Soy aficionado de decir "que los desarrolladores, se producirá un error de dos maneras: ampliaremos lo incorrecto, o se cree nada incorrecto." Aseguran de pruebas unitarias que está generando la derecha cosa; pruebas funcionales aseguran de que está creando lo correcto.

Puesto que las pruebas funcionales funcionan en el nivel de sistema, pueden requerir cierto grado de automatización de la interfaz de usuario. Al igual que las pruebas de integración, suelen funcionar con algún tipo de infraestructura de pruebas también. Esto hace que sean más lento y más complicado que las pruebas unitarias y la integración. Debe tener solo pruebas funcionales tantos como necesite para estar seguro que el sistema se comporta tal y como se espera que los usuarios.

### <a name="testing-pyramid"></a>Pruebas piramidal

Martin Fowler escribió acerca de la pirámide prueba, se muestra un ejemplo de los cuales en la figura 9-1.

![](./media/image9-1.png)

Figura 9-1 pruebas piramidal

Los diferentes niveles de la pirámide y sus tamaños relativos, representan distintos tipos de pruebas y cuántas debe escribir para la aplicación. Como puede ver, la recomendación es tiene una gran cantidad de pruebas unitarias, compatible con una capa más pequeña de pruebas de integración, con un nivel incluso más pequeño de pruebas funcionales. Cada capa lo ideal es que sólo debería haber pruebas que no se puede realizar de manera adecuada en un nivel inferior. Tenga presente la pirámide prueba al tratar de decidir qué tipo de prueba necesita para un escenario determinado.

### <a name="what-to-test"></a>Qué se va a probar

Un problema común para los desarrolladores sin experiencia con la escritura de las pruebas automatizadas viene a continuación con lo que se debe probar. Es un buen punto de partida probar la lógica condicional. En cualquier lugar tiene un método con un comportamiento que los cambios se basan en una instrucción condicional (if-else, cambiar, etc.), debe poder dar al menos un par de pruebas que confirman que el comportamiento correcto para ciertas condiciones. Si el código tiene condiciones de error, es conveniente escribir al menos una prueba para la "ruta feliz" a través del código (con ningún error) y al menos una prueba para la "ruta sad" (con errores o resultados poco frecuente) para confirmar que la aplicación se comporta según lo previsto en el caso de errores. Por último, pruebe a centrarse en pruebas, lo que puede producir un error, en lugar de centrarse en las métricas como cobertura de código. Cobertura de código más es mejor que menor, por lo general. Sin embargo, escribir unas pruebas más de un método muy compleja y críticos para la empresa suele ser un mejor uso de la hora de escribir pruebas para propiedades automáticas mejorar métrica de cobertura de código de prueba.

## <a name="organizing-test-projects"></a>Organizar los proyectos de prueba

Sin embargo, funciona mejor para usted, se pueden organizar proyectos de prueba. Es una buena idea separe las pruebas por tipo (pruebas unitarias, pruebas de integración) y por lo que va a probar (proyecto por espacio de nombres). Si esta separación consta de carpetas dentro de un proyecto de prueba único o varios proyectos de prueba, es una decisión de diseño. Un proyecto es más sencillo, pero para los proyectos grandes con muchas pruebas, o con el fin de ejecutar más fácilmente diferentes conjuntos de pruebas, puede tener varios proyectos de prueba diferentes. Muchos equipos de organizan los proyectos de prueba basados en el proyecto está probando, que para las aplicaciones con más de unos pocos proyectos puede provocar un gran número de proyectos de prueba, sobre todo si todavía descomponen estos según qué tipo de pruebas que están en cada proyecto. Un enfoque de compromiso consiste en disponer de un proyecto por tipo de prueba, por aplicación, con carpetas dentro de los proyectos de prueba para indicar el proyecto (y la clase) que se está probando.

Un enfoque común es organizar los proyectos de aplicación en una carpeta de 'src' y los proyectos de prueba de la aplicación en una carpeta paralelo 'prueba'. Puede crear carpetas coincidente de la solución en Visual Studio, si se encuentra esta organización útil.

![](./media/image9-2.png)

Organización de prueba de la figura 9-2 en la solución

Puede usar cualquier marco de pruebas que prefiera. El marco de trabajo de xUnit funciona bien y es lo que todas las pruebas de EF y de núcleo de ASP.NET se escriben. Puede agregar un proyecto de prueba de xUnit en Visual Studio con la plantilla que se muestra en la figura 9-3 o de la CLI mediante dotnet nueva xunit.

![](./media/image9-3.png)

Figura 9-3 Agregar un proyecto de prueba de xUnit en Visual Studio

### <a name="test-naming"></a>Nomenclatura de prueba

Debe asignar el nombre de las pruebas de forma coherente, con un nombre que indique lo que hace cada prueba. Un enfoque que tengo desde muy buenos resultados con consiste en las clases de prueba de nombre según la clase y el método que se están probando. Esto provoca en muchas clases de prueba pequeñas, pero deja muy claro lo que es responsable de cada prueba. Con el nombre de clase de prueba configurado para identificar la clase y el método se va a probar, el nombre del método de prueba puede utilizarse para especificar el comportamiento que se está probando. Esto debe incluir el comportamiento esperado y entradas ni suposiciones que deben producir este comportamiento. Algunos ejemplos de nombres de prueba:

-   CatalogControllerGetImage.CallsImageServiceWithId

-   CatalogControllerGetImage.LogsWarningGivenImageMissingException

-   CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess

-   CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException

Una variación de este enfoque finaliza cada nombre de clase de prueba con "Debería" y modifica ligeramente el tiempo:

-   CatalogControllerGetImage**debe**. **Llame a**ImageServiceWithId

-   CatalogControllerGetImage**debe**. **Registro**WarningGivenImageMissingException

Algunos equipos encuentran el segundo método de nomenclatura más claro, aunque un poco más detallado. En cualquier caso, pruebe a utilizar una convención de nomenclatura que proporciona una visión general de comportamiento de la prueba, para que cuando se produce un error en una o varias pruebas, es obvio desde sus nombres que se han producido un error en los casos. Evitar nombres pruebas vagamente, como ControllerTests.Test1, tal y como no se ofrece ningún valor cuando se ven en los resultados de pruebas.

Si sigue una convención de nomenclatura que se muestra arriba genera muchas clases de prueba pequeñas, es una buena idea para organizar mejor las pruebas mediante las carpetas y los espacios de nombres. Figura 9-4 muestra un enfoque para organizar las pruebas en la carpeta en varios proyectos de prueba.

![](./media/image9-4.png)

**Figura 9-4.** Organizar las clases de prueba por carpeta en función de la clase que se está probando.

Por supuesto, si una clase de aplicación determinada tiene muchos métodos que se está probados (y, por tanto, muchas clases de prueba), que tiene sentido para colocarlos en una carpeta correspondiente a la clase de aplicación. Esta organización es similar a cómo puede organizar los archivos en carpetas en otra parte. Si tiene más de tres o cuatro archivos en una carpeta que contiene muchos otros archivos relacionados, a menudo resulta útil moverlas a su propia subcarpeta.

## <a name="unit-testing-aspnet-core-apps"></a>Probar aplicaciones de ASP.NET Core la unidad

En una aplicación de ASP.NET Core bien diseñada, la mayor parte de la complejidad y la lógica de negocios se encapsulará en entidades de negocio y una variedad de servicios. La propia aplicación de MVC de ASP.NET Core con sus controladores, filtros, viewmodels y vistas, es necesario muy pocas pruebas unitarias. Gran parte de la funcionalidad de una acción determinada se encuentra fuera del propio método de acción. Comprobar si el enrutamiento funciona correctamente o el control de errores global, no puede realizarse de forma eficaz con una prueba unitaria. Del mismo modo, los filtros, incluida la autenticación y validación de modelo y los filtros de autorización, no se puede pasar la prueba unitaria. Sin estos orígenes de comportamiento, la mayoría de los métodos de acción deben ser trivial pequeños, delegar la mayor parte de su trabajo a los servicios que puede probar de forma independiente del controlador que los usa.

A veces debe refactorizar el código en el pedido a la prueba unitaria. Con frecuencia, esto implica identificar abstracciones y mediante la inserción de dependencia para tener acceso a la abstracción en el código que desea probar, en lugar de codificar directamente en la infraestructura. Por ejemplo, considere la posibilidad de este método de acción simple para mostrar imágenes:

```cs
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

Este método de prueba unitaria se hace difícil su dependencia directa en System.IO.File, que utiliza para leer desde el sistema de archivos. Puede probar este comportamiento para asegurarse de que funciona como esperaba, pero si lo hace, con los archivos reales es una prueba de integración. Cabe mencionar no puede probar la ruta de este método: verá cómo hacerlo con una prueba funcional en breve.

¿Si no prueba unitaria el comportamiento del sistema de archivos directamente y no se puede probar la ruta, lo está probar? Bueno, después de refactorización para que sea posible pruebas unitarias, puede detectar varios casos de prueba y un comportamiento que faltan, como control de errores. ¿Qué hace el método cuando no se encuentra un archivo? ¿Qué debe hacer? En este ejemplo, el método refactorizado tiene el siguiente aspecto:

```cs
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

El \_registrador y \_imageService se insertan como dependencias. Ahora puede probar que el mismo identificador que se pasa al método de acción se pasa a la \_imageService, y que los bytes resultantes se devuelven como parte de la FileResult. También puede probar que se está realizando el registro de errores como se esperaba y que se devuelve un resultado de NotFound si la imagen no se encuentra, suponiendo que se trata de comportamiento de la aplicación importante (es decir, no solo código temporal al desarrollador agregado para diagnosticar un problema). La lógica real del archivo se ha trasladado a un servicio de implementación independiente y se ha ampliado para devolver una excepción específica de la aplicación en el caso de un archivo que falta. Puede probar esta implementación de forma independiente, con una prueba de integración.

## <a name="integration-testing-aspnet-core-apps"></a>Probar la integración aplicaciones de ASP.NET Core

```cs
    }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

Este servicio usa IHostingEnvironment, al igual que el CatalogController código hacía antes de se ha refactorizado en un servicio independiente. Ya que el único código en el controlador que usa IHostingEnvironment, esa dependencia se quitó del constructor del CatalogController.

Para comprobar que este servicio funciona correctamente, debe crear un archivo de imagen de prueba conocida y compruebe que el servicio devuelve que tiene una entrada específica. También debe tener cuidado para que no utilice objetos ficticios en el comportamiento que desea probar (en este caso, leer desde el sistema de archivos). Sin embargo, objetos ficticios pueden resultarle útiles para configurar las pruebas de integración. En este caso, puede simular IHostingEnvironment para que su ContentRootPath apunta a la carpeta que se va a utilizar para la imagen de prueba. La clase de prueba de integración de trabajo completo se muestra aquí:

```cs
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
> que la propia prueba es muy sencilla: la mayor parte del código es necesaria para crear la infraestructura de prueba (en este caso, un archivo real que se leen del disco) y configurar el sistema. Esto es normal para las pruebas de integración, que a menudo requieren un trabajo el programa de instalación más complejo que las pruebas unitarias.

## <a name="functional-testing-aspnet-core-apps"></a>Aplicaciones de ASP.NET Core pruebas funcionales

Para las aplicaciones de ASP.NET Core, la clase TestServer realiza pruebas funcionales bastante fáciles de crear. Configurar un TestServer mediante un WebHostBuilder, tal como se hace normalmente para la aplicación. Este WebHostBuilder debe configurarse como host de la aplicación real, pero puede modificar los aspectos del mismo que simplificar las pruebas. La mayoría de los casos, se podrá volver a usar el mismo TestServer para muchos de los casos de prueba, por lo que puede encapsular en un método reutilizable (por ejemplo, en una clase base):

```cs
public abstract class BaseWebTest
{
    protected readonly HttpClient _client;
    protected string _contentRoot;

    public BaseWebTest()
    {
        _client = GetClient();
    }
    
    protected HttpClient GetClient()
    {
        var startupAssembly = typeof(Startup).GetTypeInfo().Assembly;
        _contentRoot = GetProjectPath("src", startupAssembly);
        var builder = new WebHostBuilder()
        .UseContentRoot(_contentRoot)
        .UseStartup&lt;Startup&gt;();
        var server = new TestServer(builder);
        var client = server.CreateClient();
        return client;
    }
}
```

GetProjectPath (método) simplemente devuelve la ruta de acceso física al proyecto web (solución de ejemplo de descarga). El WebHostBuilder en este caso simplemente especifica donde es la raíz del contenido de la aplicación web y hace referencia a la misma clase de inicio que usa la aplicación web real. Para trabajar con la TestServer, se utilice el tipo de System.Net.HttpClient estándar para realizar solicitudes a él. TestServer expone un método CreateClient útil que proporciona a un cliente preconfigurado que está listo para realizar solicitudes a la aplicación se ejecuta en el TestServer. Utilice este cliente (establecido en el modo protegido \_miembro de cliente en la base de prueba anterior) al escribir las pruebas funcionales de la aplicación de ASP.NET Core:

```cs
public class CatalogControllerGetImage : BaseWebTest
{
    [Fact]
    public async Task ReturnsFileContentResultGivenValidId()
    {
        var testFilePath = Path.Combine(_contentRoot, "pics//1.png");
        var expectedFileBytes = File.ReadAllBytes(testFilePath);
        var response = await _client.GetAsync("/catalog/pic/1");
        response.EnsureSuccessStatusCode();
        var streamResponse = await response.Content.ReadAsStreamAsync();
        byte[] byteResult;
        using (var ms = new MemoryStream())
        {
            streamResponse.CopyTo(ms);
            byteResult = ms.ToArray();
        }
        Assert.Equal(expectedFileBytes, byteResult);
    }
}
```

Esta prueba funcional ejercita la pila completa de la aplicación de MVC de ASP.NET Core, incluidos todos los middleware, filtros, enlazadores, etc., que pueden estar en su lugar. Comprueba que un dada ruta ("/ catálogo/pic/1") devuelve la matriz de bytes esperado para un archivo en una ubicación conocida. Sin configurar un servidor web reales y así evita gran parte de la fragilidad que servidor para realizar pruebas puede experimentar (por ejemplo, problemas con la configuración de firewall) usando una web real. Pruebas funcionales que se ejecutan en TestServer son normalmente más lentas que la integración y pruebas unitarias, pero son mucho más rápidas que las pruebas que ejecutan a través de la red para un servidor de prueba web.

>[!div class="step-by-step"]
[Anterior] (work-with-data-in-asp-net-core-apps.md) [siguiente] (desarrollo-proceso-de-azure.md)
