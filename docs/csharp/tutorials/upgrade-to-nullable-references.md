---
title: Actualización a tipos de referencias que aceptan valores NULL
description: En este tutorial avanzado se muestra cómo migrar código existente con tipos de referencias que aceptan valores NULL.
ms.date: 02/19/2019
ms.technology: csharp-null-safety
ms.custom: mvc
ms.openlocfilehash: 9767493059623e770cc100b83b9284e8d0bdf0f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156459"
---
# <a name="tutorial-migrate-existing-code-with-nullable-reference-types"></a>Tutorial: Migración del código existente con tipos de referencia que admiten valores NULL

C#8 presenta **tipos de referencia que aceptan valores NULL**, qué complementan a los tipos de referencia del mismo modo que los tipos de valor que aceptan valores NULL complementan a los tipos de valor. Declarará una variable para que sea un **tipo de referencia que acepta valores NULL** anexando un elemento `?` al tipo. Por ejemplo, `string?` representa un elemento `string` que acepta valores NULL. Puede utilizar estos nuevos tipos para expresar más claramente la intención del diseño: algunas variables *siempre deben tener un valor*, y a otras *les puede faltar un valor*. Las variables existentes de un tipo de referencia se interpretarían como un tipo de referencia que no admite valores NULL.

En este tutorial aprenderá lo siguiente:

> [!div class="checklist"]
>
> - Habilitar las comprobaciones de referencia NULL mientras trabaja con código.
> - Diagnosticar y corregir diferentes advertencias relacionadas con los valores NULL.
> - Administrar la interfaz entre contextos habilitados y deshabilitados que admiten valores NULL.
> - Controlar contextos de anotación que admiten valores NULL.

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET Core, incluido el compilador de C# 8.0. El compilador de C# 8 está disponible a partir de la [versión 16.3 de Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o del [SDK de .NET Core 3.0](https://dotnet.microsoft.com/download).

En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.

## <a name="explore-the-sample-application"></a>Exploración de la aplicación de ejemplo

La aplicación de ejemplo que va a migrar es una aplicación web de lector de fuentes RSS. Esta aplicación lee una única fuente RSS y muestra los resúmenes de los artículos más recientes. Puede seleccionar cualquiera de los artículos para visitar el sitio. La aplicación es relativamente nueva, pero se escribió antes de que estuvieran disponibles los tipos de referencia que admiten valores NULL. Las decisiones de diseño para la aplicación representaban principios de sonido, pero no aprovechan esta importante característica del lenguaje.

La aplicación de ejemplo incluye una biblioteca de pruebas unitarias que valida la funcionalidad principal de la aplicación. Ese proyecto facilitará la actualización de forma segura si cambia cualquiera de las implementaciones en función de las advertencias generadas. Puede descargar el código de inicio del repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/nullable-reference-migration/start) de GitHub.

El objetivo al migrar un proyecto debe ser aprovechar las nuevas características del lenguaje para que exprese claramente su intención sobre la capacidad de admitir valores NULL de las variables, y hacerlo de tal manera que el compilador no genere advertencias cuando los contextos de anotación y advertencia que admiten valores NULL estén establecidos en `enabled`.

## <a name="upgrade-the-projects-to-c-8"></a>Actualización de proyectos a C# 8

Un buen primer paso es determinar el ámbito de la tarea de migración. Empiece por actualizar el proyecto a C# 8.0 (o posterior). Agregue el elemento `LangVersion` a PropertyGroup en ambos archivos csproj para el proyecto web y el proyecto de prueba unitaria:

```xml
<LangVersion>8.0</LangVersion>
```

La actualización de la versión de idioma selecciona C# 8.0, pero no habilita los contextos de anotación y de advertencia que admiten valores NULL. Recompile el proyecto para asegurarse de que se compila sin advertencias.

Un buen paso es activar el contexto de anotación que admite valores NULL y ver cuántas advertencias se generan. Agregue el siguiente elemento a ambos archivos csproj de la solución, directamente bajo el elemento `LangVersion`:

```xml
<Nullable>enable</Nullable>
```

Realice una compilación de prueba y observe la lista de advertencias. En esta pequeña aplicación, el compilador genera cinco advertencias, por lo que es probable que dejara el contexto de anotación que admite valores NULL habilitado y empezara a corregir las advertencias para todo el proyecto.

Esa estrategia solo funciona para los proyectos más pequeños. Para los proyectos más grandes, el número de advertencias generadas al habilitar el contexto de anotación que admite valores NULL para todo el código base dificulta la corrección de las advertencias de forma sistemática. Para los proyectos empresariales más grandes, suele ser conveniente migrar los proyectos de uno en uno. En cada proyecto, migre una clase o un archivo de uno en uno.

## <a name="warnings-help-discover-original-design-intent"></a>Las advertencias ayudan a detectar la intención del diseño original

Hay dos clases que generan varias advertencias. Empiece con la clase `NewsStoryViewModel`. Quite el elemento `Nullable` de ambos archivos csproj de forma que pueda limitar el ámbito de las advertencias para las secciones de código con las que está trabajando. Abra el archivo *NewsStoryViewModel.cs* y agregue las siguientes directivas para habilitar el contexto de anotación que admite valores NULL para `NewsStoryViewModel` y restáurelo siguiendo esa definición de clase:

```csharp
#nullable enable
public class NewsStoryViewModel
{
    public DateTimeOffset Published { get; set; }
    public string Title { get; set; }
    public string Uri { get; set; }
}
#nullable restore
```

Estas dos directivas le ayudan a centrar sus esfuerzos en la migración. Las advertencias que admiten valores NULL se generan para el área del código en el que está trabajando activamente. Podrá dejarlas hasta que esté listo para activar las advertencias para todo el proyecto. Debe usar `restore` en lugar del valor `disable` para que no deshabilite accidentalmente el contexto más adelante cuando haya activado las anotaciones que admiten valores NULL para todo el proyecto. Cuando haya activado el contexto de anotación que admite valores NULL para todo el proyecto, podrá quitar todas las pragmas `#nullable` de ese proyecto.

La clase `NewsStoryViewModel` es un objeto de transferencia de datos (DTO) y dos de las propiedades son cadenas de lectura y escritura:

[!code-csharp[InitialViewModel](~/samples/snippets/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/ViewModels/NewsStoryViewModel.cs#StarterViewModel)]

Estas dos propiedades generan `CS8618`, "La propiedad que admite valores NULL no está inicializada". Eso es muy claro: ambas propiedades `string` tienen el valor predeterminado de `null` cuando `NewsStoryViewModel` se construye. Lo que es importante descubrir es cómo se construyen los objetos `NewsStoryViewModel`. Examinando esta clase no puede saber si el valor de `null` es parte del diseño o si estos objetos se establecen en valores que no admiten valores NULL siembre que se crea uno. Los artículos de noticias se crean en el método `GetNews` de la clase `NewsService`:

[!code-csharp[StarterCreateNewsItem](~/samples/snippets/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Services/NewsService.cs#CreateNewsItem)]

Suceden algunas cosas en el bloque de código anterior. Esta aplicación usa el paquete NuGet [AutoMapper](https://automapper.org/) para construir un elemento de noticias a partir de `ISyndicationItem`. Ha detectado que los elementos de artículo de noticias se construyen y las propiedades se establecen en esa instrucción. Esto significa que el diseño de `NewsStoryViewModel` indica que estas propiedades nunca deben tener el valor `null`. Estas propiedades deben ser **tipos de referencia que no admiten valores NULL**. Eso expresa mejor la intención del diseño original. De hecho, para `NewsStoryViewModel`, *se* crean instancias correctamente con valores no NULL. Eso convierte al siguiente código de inicialización en una corrección válida:

```csharp
public class NewsStoryViewModel
{
    public DateTimeOffset Published { get; set; }
    public string Title { get; set; } = default!;
    public string Uri { get; set; } = default!;
}
```

La asignación de `Title` y `Uri` a `default` que es `null` para el `string` tipo no cambia el comportamiento en tiempo de ejecución del programa. `NewsStoryViewModel` se sigue construyendo con valores NULL, pero ahora el compilador no informa de ninguna advertencia. El **operador que permite valores NULL**, el carácter `!` que sigue a la expresión `default`, indica al compilador que la expresión anterior no es NULL. Esta técnica puede ser conveniente cuando otros cambios fuerzan cambios mucho mayores en una base de código, pero en esta aplicación hay una solución relativamente rápida y mejor: convierta a `NewsStoryViewModel` en un tipo inmutable donde todas las propiedades se establecen en el constructor. Realice los cambios siguientes en `NewsStoryViewModel`:

[!code-csharp[FinishedViewModel](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/ViewModels/NewsStoryViewModel.cs#FinishedViewModel)]

Una vez hecho esto, deberá actualizar el código que configura AutoMapper para que utilice el constructor en lugar de establecer las propiedades. Abra `NewsService.cs` y busque el código siguiente en la parte inferior del archivo:

[!code-csharp[StarterAutoMapper](~/samples/snippets/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Services/NewsService.cs#ConfigureAutoMapper)]

Ese código asigna las propiedades del objeto `ISyndicationItem` a las propiedades de `NewsStoryViewModel`. Desea AutoMapper para proporcionar la asignación mediante un constructor. Reemplace el código anterior con la siguiente configuración de AutoMapper:

[!code-csharp[FinishedViewModel](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#ConfigureAutoMapper)]

Tenga en cuenta que, dado que esta clase es pequeña y ha realizado un examinen meticuloso, debe activar la directiva `#nullable enable` sobre esta declaración de clase. El cambio en el constructor podría haberse interrumpido en cierta medida, por lo que vale la pena ejecutar todas las pruebas y probar la aplicación antes de continuar.

El primer conjunto de cambios le mostraba cómo detectar cuándo el diseño original indicaba que las variables no debían establecerse en `null`. La técnica se conoce como **correcto por construcción**. Declara que un objeto y sus propiedades no pueden ser `null` cuando se construye. El análisis de flujo del compilador proporciona garantía de que esas propiedades no están establecidas en `null` después de la construcción. Tenga en cuenta que el código externo llama a este constructor y, dicho código, es **ajeno a la admisión de valores NULL**. La nueva sintaxis no proporciona comprobación en tiempo de ejecución. El código externo podría eludir el análisis de flujo del compilador.

En otras ocasiones, la estructura de una clase proporciona pistas diferentes a la intención. Abra el archivo *Error.cshtml.cs* en la carpeta *Páginas*. `ErrorViewModel` contiene el código siguiente:

[!code-csharp[StarterErrorModel](~/samples/snippets/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Pages/Error.cshtml.cs#StartErrorModel)]

Agregue la directiva `#nullable enable` antes de la declaración de clase y una directiva `#nullable restore` después de ella. Recibirá una advertencia que indica que `RequestId` no se ha inicializado. Si examina la clase, debe decidir que la propiedad `RequestId` debe ser NULL en algunos casos. La existencia de la propiedad `ShowRequestId` indica que puede haber valores que faltan. Dado que `null` es válido, agregue `?` en el tipo `string` para indicar que la propiedad `RequestId` es un *tipo de referencia que admite valores NULL*. La clase final se parece al ejemplo siguiente:

[!code-csharp[FinishedErrorModel](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Error.cshtml.cs#ErrorModel)]

Compruebe los usos de la propiedad y verá que, en la página asociada, se comprueba si la propiedad es NULL antes de representarla en el marcado. Ese es un uso seguro de un tipo de referencia que admite valores NULL, por lo que ha terminado con esta clase.

## <a name="fixing-nulls-causes-change"></a>La corrección de valores NULL provoca cambio

Con frecuencia, la corrección de un conjunto de advertencias crea nuevas advertencias de código relacionado. Vamos a ver las advertencias en acción mediante la corrección de la clase `index.cshtml.cs`. Abra el archivo `index.cshtml.cs` y examine el código. Este archivo contiene el código de la página de índice:

[!code-csharp[StarterIndexModel](~/samples/snippets/csharp/tutorials/nullable-reference-migration/start/SimpleFeedReader/Pages/Index.cshtml.cs#IndexModelStart)]

Agregue la directiva `#nullable enable` y verá dos advertencias. Ni la propiedad `ErrorText` ni la propiedad `NewsItems` se inicializan. Al examinar esta clase se llegará a la conclusión de que ambas propiedades deben ser tipos de referencia que admiten valores NULL: Ambas tienen establecedores privados. Se asigna exactamente una en el método `OnGet`. Antes de realizar cambios, examine los consumidores de ambas propiedades. En la propia página, `ErrorText` se comprueba con NULL antes de generar el marcado para los errores. La colección `NewsItems` se compara con `null` y se comprueba para asegurar que tiene elementos. Una corrección rápida sería convertir ambas propiedades en tipos de referencia que admiten valores NULL. Una corrección mejor sería convertir a la colección en un tipo de referencia que no admite valores NULL y agregar elementos a la colección existente cuando se recuperan noticias. La primera corrección consiste en agregar `?` al tipo `string` para `ErrorText`:

[!code-csharp[UpdateErrorText](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#UpdateErrorText)]

Ese cambio no se propagará por otro código, porque cualquier acceso a la propiedad `ErrorText` ya estaba protegido por comprobaciones NULL. A continuación, inicialice la lista `NewsItems` y quite el establecedor de propiedad, convirtiéndola en una propiedad de solo lectura:

[!code-csharp[InitializeNewsItems](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#InitializeNewsItems)]

Esa acción corrigió la advertencia pero introdujo un error. La lista `NewsItems` es ahora **correcta por construcción**, pero el código que establece la lista en `OnGet` debe cambiar para que coincida con la nueva API. En lugar de una asignación, llame a `AddRange` para agregar los elementos de noticias a la lista existente:

[!code-csharp[AddRange](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Pages/Index.cshtml.cs#AddRange)]

El uso de `AddRange` en lugar de una asignación significa que el método `GetNews` puede devolver `IEnumerable` en lugar de `List`. Eso guarda una asignación. Cambie la firma del método y quite la llamada `ToList`, como se muestra en el ejemplo de código siguiente:

[!code-csharp[GetNews](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#GetNewsFinished)]

El cambio de firma también rompe una de las pruebas. Abra el archivo `NewsServiceTests.cs` de la carpeta `Services` del proyecto `SimpleFeedReader.Tests`. Vaya a la prueba `Returns_News_Stories_Given_Valid_Uri` y cambie el tipo de la variable `result` a `IEnumerable<NewsItem>`. El cambio de tipo significa que la propiedad `Count` ya no está disponible, por tanto, reemplace la propiedad `Count` en `Assert` con una llamada a `Any()`:

[!code-csharp[FixTests](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader.Tests/Services/NewsServiceTests.cs#FixTestSignature)]

También deberá agregar una instrucción `using System.Linq` al principio del archivo.

Este conjunto de cambios resalta una consideración especial al actualizar el código que incluye creación de instancias genéricas. La lista y los elementos de la lista de tipos que no admiten valores NULL. Uno o ambos podrían ser tipos que admiten valores NULL. Se permiten todas las declaraciones siguientes:

- `List<NewsStoryViewModel>`: lista que no admite valores NULL de modelos de vista que no admiten valores NULL.
- `List<NewsStoryViewModel?>`: lista que no admite valores NULL de modelos de vista que admiten valores NULL.
- `List<NewsStoryViewModel>?`: lista que admite valores NULL de modelos de vista que no admiten valores NULL.
- `List<NewsStoryViewModel?>?`: lista que admite valores NULL de modelos de vista que admiten valores NULL.

## <a name="interfaces-with-external-code"></a>Interfaces con código externo

Ha realizado cambios en la clase `NewsService`, así que active la anotación `#nullable enable` para esa clase. Esto no generará nuevas advertencias. Sin embargo, un examen cuidadoso de la clase ayuda a ilustrar algunas de las limitaciones del análisis de flujo del compilador. Examine el constructor:

[!code-csharp[ServiceConstructor](~/samples/snippets/csharp/tutorials/nullable-reference-migration/finished/SimpleFeedReader/Services/NewsService.cs#ServiceConstructor)]

El parámetro `IMapper` se escribe como una referencia que no admite valores NULL. El código de infraestructura de ASP.NET Core lo llama, por lo que el compilador realmente no sabe que `IMapper` nunca será NULL. El contenedor predeterminado de inyección de dependencias (DI) de ASP.NET Core inicia una excepción si no se puede resolver un servicio necesario, por lo que el código es correcto. El compilador no puede validar todas las llamadas a las API públicas, incluso si el código se compila con contextos de anotación que acepta valores NULL habilitados. Además, las bibliotecas pueden ser consumidas por proyectos que aún no han participado mediante tipos de referencia que admiten valores NULL. Valide las entradas en API públicas aunque las haya declarado como tipos que no admiten valores NULL.

## <a name="get-the-code"></a>Obtención del código

Ha corregido las advertencias que identificó en la compilación de prueba inicial, así que ahora puede activar el contexto de anotación que acepta valores NULL para ambos proyectos. Vuelva a compilar los proyectos; el compilador no notifica advertencias. Puede obtener el código del proyecto finalizado en el repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/nullable-reference-migration/finished) de GitHub.

Las nuevas características compatibles con tipos de referencia que admiten valores NULL le ayudan a encontrar y corregir los posibles errores en la forma de controlar valores `null` en el código. La habilitación del contexto de anotación que acepta valores NULL permite expresar la intención del diseño: algunas variables nunca deberían ser NULL y otras pueden contener valores NULL. Estas características hacen que sea más fácil declarar la intención del diseño. De forma similar, el contexto de advertencia que admite valores NULL indica al compilador que emita advertencias cuando se haya infringido dicha intención. Esas advertencias le guían para realizar actualizaciones que hacen que el código sea más resistente y tenga menos probabilidad de iniciar `NullReferenceException` durante la ejecución. Puede controlar el ámbito de estos contextos para que pueda centrarse en áreas locales del código que desea migrar mientras el código base restante permanece intacto. En la práctica, puede hacer que esta tarea de migración sea una parte del mantenimiento convencional de las clases. En este tutorial se ha mostrado el proceso para migrar una aplicación para usar tipos de referencia que admiten valores NULL. Puede explorar un ejemplo más grande real de este proceso mediante el examen del repositorio popular [Jon Skeet](https://github.com/jskeet) creado para incorporar tipos de referencia que admitan valores NULL en [NodaTime](https://github.com/nodatime/nodatime/pull/1240/commits). Además, puede aprender técnicas para usar tipos de referencias que aceptan valores NULL con Entity Framework Core en [Entity Framework Core: trabajar con tipos de referencia que aceptan valores NULL](/ef/core/miscellaneous/nullable-reference-types).
