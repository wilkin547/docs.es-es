---
title: Ejemplo de migración de eShop a ASP.NET Core
description: Un tutorial de migración de una aplicación de ASP.NET MVC existente a ASP.NET Core, mediante una aplicación de la tienda en línea de ejemplo como referencia.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 119ba64134813fa17848cf9f5fe02cb1a14f8a5d
ms.sourcegitcommit: b5d2290673e1c91260c9205202dd8b95fbab1a0b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "106122981"
---
# <a name="example-migration-of-eshop-to-aspnet-core"></a>Ejemplo de migración de eShop a ASP.NET Core

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

En este capítulo, verá cómo migrar una aplicación .NET Framework a .NET Core. En el capítulo se examina una aplicación de la tienda en línea de ejemplo escrita para ASP.NET 5,0. La aplicación usará muchos de los conceptos y herramientas descritos anteriormente en este libro. Encontrará la aplicación de punto de partida en el [repositorio de github de *eShopModernizing*](https://github.com/dotnet-architecture/eShopModernizing). Hay varias aplicaciones de punto de partida diferentes. Este capítulo se centra en el *eShopLegacyMVCSolution*.

La versión inicial del proyecto se muestra en la figura 4-1. Es una aplicación ASP.NET MVC 5 bastante estándar.

![Figura 4-1](media/Figure4-1.png)

**Figura 4-1.** Estructura del proyecto de ejemplo *eShopModernizing* MVC.

En este capítulo se muestra cómo realizar muchos de los pasos de actualización a mano. Como alternativa, puede usar la [herramienta del Asistente para actualización de .net](https://aka.ms/dotnet-upgrade-assistant) para realizar muchos de los pasos iniciales, como la conversión del archivo de proyecto, el cambio de la plataforma de destino y la actualización de paquetes NuGet.

## <a name="run-apiport-to-identify-problematic-apis"></a>Ejecución de *ApiPort* para identificar API problemáticas

El primer paso para preparar la migración es ejecutar la herramienta *ApiPort* . La herramienta identifica cuántas API de .NET Framework llama la aplicación y cuántas de ellas tienen .NET Standard o equivalentes de .NET Core. Céntrese principalmente en la lógica de su propia aplicación, no en las dependencias de terceros, y preste atención a las `System.Web` dependencias que se deben migrar. La herramienta ApiPort se presentó en el último capítulo sobre cómo [comprender y actualizar las dependencias](understand-update-dependencies.md).

Después de [instalar y configurar la herramienta *ApiPort*](../../standard/analyzers/portability-analyzer.md), ejecute el análisis desde dentro de Visual Studio, como se muestra en la figura 4-2.

![Figura 4-2](media/Figure4-2.png)

**Figura 4-2.** Analice la portabilidad de los ensamblados en Visual Studio.

Elija el ensamblado del proyecto web en la carpeta *bin* del proyecto, como se muestra en la figura 4-3.

![Figura 4-3](media/Figure4-3.png)

**Figura 4-3.** Elija el ensamblado web del proyecto.

Si la solución incluye varios proyectos, puede elegirlos todos. El ejemplo de *eShop* incluye solo un proyecto de MVC.

Una vez generado el informe, abra el archivo y revise los resultados. El Resumen proporciona una vista de alto nivel del porcentaje de llamadas .NET Framework que la aplicación está realizando con versiones compatibles. En la figura 4-4 se muestra el resumen del proyecto de *eShop* MVC.

![Figura 4-4](media/Figure4-4.png)

**Figura 4-4.** Resumen de ApiPort.

Para esta aplicación, el 80 por ciento de las llamadas .NET Framework son compatibles. el 20 por ciento de las llamadas deben solucionarse durante el proceso de portabilidad. La visualización de los detalles revela que todas las llamadas incompatibles forman parte de `System.Web` , que es una incompatibilidad esperada. Las dependencias de las `System.Web` llamadas se dirigirán cuando se migren los controladores de la aplicación y las clases relacionadas en un paso posterior. En la figura 4-5 se enumeran algunos de los tipos específicos que se encuentran en la herramienta:

![Figura 4-5](media/Figure4-5.png)

**Figura 4-5.** *ApiPort* detalles de tipo incompatible.

La mayoría de los tipos incompatibles hacen referencia a `Controller` y varios atributos relacionados que tienen equivalentes en ASP.net Core.

## <a name="update-project-files-and-nuget-reference-syntax"></a>Actualizar archivos de proyecto y sintaxis de referencia de NuGet

A continuación, migre de la estructura del archivo *. csproj* anterior a la estructura más reciente y más sencilla introducida con .net Core. Al hacerlo, también migrará de mediante un archivo *packages.config* para que las referencias de NuGet usen `<PackageReference>` elementos del archivo de proyecto. Los archivos de proyecto de estilo antiguo también pueden usar `<PackageReference>` elementos, por lo que normalmente tiene sentido migrar primero todas las referencias de paquetes NuGet a este formato, antes de actualizar al nuevo formato de archivo de proyecto.

El archivo *eShopLegacyMVC. csproj* del proyecto original tiene 418 líneas de longitud. En la figura 4-6 se muestra un ejemplo del archivo de proyecto. Para ofrecer una idea de su tamaño y complejidad generales, el lado derecho de la imagen contiene una vista en miniatura del archivo completo.

![Figura 4-6](media/Figure4-6.png)

**Figura 4-6.** Estructura del archivo *eShopLegacyMVC. csproj* .

Una forma habitual de crear un nuevo archivo de proyecto para un proyecto de ASP.net existente consiste en crear una nueva aplicación de ASP.net Core con `dotnet new` o **archivo**  >  **nuevo**  >  **proyecto** en Visual Studio. Después, los archivos se pueden copiar del proyecto anterior al nuevo para completar la migración.

Además del archivo de proyecto de C#, las dependencias de NuGet se almacenan en un archivo de *packages.config* de línea de 45 independiente, como se muestra en la figura 4-7.

![Figura 4-7](media/Figure4-7.png)

**Figura 4-7.** El archivo de *packages.config* .

Puede migrar *packages.config* en proyectos de biblioteca de clases con Visual Studio. No obstante, esta funcionalidad no funciona con proyectos de ASP.NET. [Obtenga más información sobre cómo migrar *packages.config* a `<PackageReference>` en Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference). Si tiene un gran número de proyectos que migrar, [esta herramienta de la comunidad puede servir de ayuda](https://github.com/MarkKharitonov/NuGetPCToPRMigrator). Si usa una herramienta para migrar el archivo de proyecto al nuevo formato, debe hacerlo después de haber terminado de migrar todas las referencias de NuGet para usarlas `<PackageReverence>` .

## <a name="create-new-aspnet-core-project"></a>Crear nuevo proyecto de ASP.NET Core

Agregue un nuevo proyecto de ASP.NET Core a la solución de la aplicación existente para facilitar el traslado de archivos, ya que la mayor parte del trabajo se puede realizar desde el **Explorador de soluciones** de Visual Studio. En Visual Studio, haga clic con el botón derecho en la solución de la aplicación y elija **Agregar nuevo proyecto**. Elija **ASP.net Core aplicación web** y asigne un nombre al nuevo proyecto como se muestra en la figura 4-8.

![Figura 4-8](media/Figure4-8.png)

**Figura 4-8.** Agregue una nueva ASP.NET Core aplicación Web.

El siguiente cuadro de diálogo le pedirá que elija la plantilla que desea usar. Seleccione la plantilla **Vacía**. Asegúrese también de cambiar la lista desplegable de **.net Core** a **.NET Framework**. Seleccione **ASP.NET Core 2,2**, como se muestra en la figura 4-9.

![Figura 4-9](media/Figure4-9.png)

**Figura 4-9.** Elija una plantilla de proyecto vacía que tenga como destino .NET Framework con ASP.NET Core 2,2.

### <a name="migrating-nuget-packages"></a>Migración de paquetes NuGet

Dado que la herramienta de migración integrada para migrar *packages.config* a `<PackageReference>` no funciona en proyectos de ASP.net, puede usar una herramienta de la comunidad en su lugar o migrar a mano. Una [herramienta](https://gist.github.com/tomkuijsten/2d75074d9a3c19c04ee8ea19a6289ddf) de la comunidad que he usado usa un archivo XSL para transformar de un formato a otro. Para usarlo, copie primero el archivo de *packages.config* en la carpeta del proyecto ASP.net Core recién creada. Realice una copia de seguridad de los archivos, ya que este script quita el archivo *packages.config* de todas las carpetas en las que se ejecuta el script. Después, ejecute estos comandos desde la carpeta del proyecto (o para toda la solución si lo prefiere):

```powershell
iwr https://git.io/vdKaV -OutFile Convert-ToPackageReference.ps1
iwr https://git.io/vdKar -OutFile  Convert-ToPackageReference.xsl
./Convert-ToPackageReference.ps1 | Out-Null
```

Los dos primeros comandos descargan archivos para que existan localmente. La última línea ejecuta el script. Después de ejecutarlo, intente compilar el nuevo proyecto. Lo más probable es que reciba algunos errores. Para resolverlos, querrá eliminar algunas referencias (como la mayoría de los `Microsoft.AspNet` `System` paquetes y) y puede que tenga que quitar algunos `xmlns` atributos.

En la mayoría de las aplicaciones de ASP.NET MVC, muchas dependencias del lado cliente como bootstrap y jQuery se han implementado mediante paquetes de NuGet. En ASP.NET Core, los paquetes NuGet solo se usan para la funcionalidad del lado servidor. Los archivos de cliente deben administrarse a través de otros medios. Revise la lista de `<PackageReference>` elementos agregados y quite y tome nota de las bibliotecas de cliente, entre las que se incluyen:

- Bootstrap
- jQuery
- jQuery. Validation
- Modernizr
- popper.js
- Respuesta

Los archivos de cliente estáticos instalados por NuGet para estos paquetes se copiarán en la carpeta *wwwroot* del nuevo proyecto y se hospedarán desde allí. Merece la pena tener en cuenta si estos archivos siguen siendo necesarios para la aplicación y si tiene sentido continuar con su hospedaje o usar una red de entrega de contenido (CDN) en su lugar. Estas versiones de la biblioteca se pueden administrar en tiempo de compilación mediante herramientas como [LibMan](/aspnet/core/client-side/libman/) o [NPM](https://www.npmjs.com/). En la figura 4-10 se muestra el archivo *eShopPorted. csproj* completo después de migrar las referencias de paquete mediante la herramienta de conversión que se muestra y se quitan los paquetes innecesarios.

![Figura 4-10](media/Figure4-10.png)

**Figura 4-10.** Referencias de paquete en el archivo *eShopPorted. csproj* .

Las referencias del paquete se pueden compactar más haciendo que el `<Version>1.0.0.0</Version>` elemento sea un `Version=1.0.0.0` atributo `<PackageReference>` .

### <a name="migrate-static-files"></a>Migrar archivos estáticos

Los archivos estáticos que usa la aplicación, incluidos los scripts y los marcos de terceros, pero también las imágenes personalizadas y las hojas de estilo, se deben copiar del proyecto antiguo al nuevo. En las aplicaciones ASP.NET MVC, normalmente se a los archivos en función de su ubicación dentro de la carpeta del proyecto. En ASP.NET Core aplicaciones, se tendrá acceso a estos archivos estáticos en función de su ubicación dentro de la carpeta *wwwroot* . En el caso del proyecto de *eShop* , hay archivos estáticos en las siguientes carpetas:

* *Contenido*
* *éstas*
* *Imágenes*
* *Selecciones*
* *Scripts*

La plantilla de proyecto **vacía** que se usó en el paso anterior no incluye esta carpeta de forma predeterminada o el middleware necesario para que funcione. Deberá agregarlos.

Agregue una carpeta *wwwroot* a la raíz del proyecto.

Agregue la versión 2.2.0 del `Microsoft.AspNetCore.StaticFiles` paquete NuGet.

En *Startup. CS*, agregue una llamada a `app.UseStaticFiles()` en el `Configure` método:

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseStaticFiles();

    // ...
}
```

Copie la carpeta de *contenido* de la aplicación ASP.NET MVC en la carpeta *wwwroot* del nuevo proyecto.

Ejecute la aplicación y vaya a la carpeta */Content/base.CSS* para comprobar que el archivo estático se atiende correctamente desde su ruta de acceso esperada. Siga copiando el resto de las carpetas que contienen archivos estáticos en el nuevo proyecto. También querrá copiar el archivo *favicon. ico* de la raíz del proyecto en la carpeta *wwwroot* . En la figura 4-11 se muestran los resultados tras copiar todos los archivos y sus carpetas.

![Figura 4-11](media/Figure4-11.png)

**Figura 4-11.** Carpetas estáticas copiadas en la carpeta *wwwroot* .

### <a name="migrate-c-files"></a>Migración de archivos de C#

A continuación, copie los archivos de C# usados por la aplicación, incluidas las carpetas estándar de MVC y su contenido, como *Controladores*, *modelos*, *ViewModel* y *servicios*. Lo más probable es que se necesiten algunos cambios en estos archivos. Es mejor copiar una carpeta (o subcarpeta) cada vez y compilar para ver qué errores deben solucionarse a medida que avanza.

En el ejemplo de *eShop* , la primera carpeta que se puede migrar es la carpeta *Models* , que incluye las entidades de C# y las clases de Entity Framework. La mayoría de los demás usan las clases de esta carpeta, por lo que no funcionarán hasta que se hayan copiado estas clases. Después de copiar la carpeta y la compilación, el compilador revelaba errores relacionados con el espacio de nombres que falta `System.Web.Hosting` , el acceso relacionado a `HostingEnvironment` y una referencia a `ConfigurationManager.AppSettings` . La solución a estos problemas será pasar los datos de la ruta de acceso necesaria. por ahora, las líneas de interrupción están comentadas y `TODO:` se agrega un comentario a cada una de ellas para realizar el seguimiento. Después de cambiar cinco líneas, el **lista de tareas** muestra cinco elementos y las compilaciones del proyecto.

A continuación, se copia la carpeta *ViewModel* , con su clase. Es fácil de crear y se compila de inmediato.

Se copia la carpeta *servicios* . Las clases de esta carpeta dependen de Entity Framework clases de la carpeta *Models* , por lo que es necesario copiarlas después de esa carpeta. Afortunadamente, se compilan sin errores.

Que deja la carpeta *Controllers* y sus dos `Controller` clases. Después de copiar la carpeta en el nuevo proyecto y compilar, hay siete errores de compilación. Cuatro de ellos están relacionados con el `ViewBag` acceso y notifican un error de:

> `Missing compiler required member 'Microsoft.CSharp.RuntimeBinder.CSharpArgumentInfo.Create'`

Para resolver este error, agregue una referencia de paquete NuGet a C#:

```xml
<PackageReference Include="Microsoft.CSharp" Version="4.7.0" />
```

Los tres errores restantes especifican los tipos que se definen en un ensamblado al que no se hace referencia. En concreto, estos tipos:

- `HttpServerUtilityBase`
- `RouteValueDictionary`
- `HttpRequestBase`

Echemos un vistazo a cada error de uno en uno. El primer error se produce al intentar hacer referencia a la `Server` propiedad de `Controller` , que ya no existe. El objetivo de la operación es obtener la ruta de acceso a un archivo de imagen en la aplicación:

```csharp
if (item != null)
{
    var webRoot = Server.MapPath("~/Pics"); // compiler error on this line
    var path = Path.Combine(webRoot, item.PictureFileName);

    string imageFileExtension = Path.GetExtension(item.PictureFileName);
    string mimetype = GetImageMimeTypeFromImageFileExtension(imageFileExtension);

    var buffer = System.IO.File.ReadAllBytes(path);

    return File(buffer, mimetype);
}
```

Existen dos posibles soluciones para este problema. La primera es mantener la funcionalidad tal cual. En este caso, en lugar de usar `Server.MapPath` , se debe usar una ruta de acceso fija que haga referencia a la ubicación de los archivos de imagen en *wwwroot* . Como alternativa, puesto que el único propósito de este método de acción es devolver un archivo de imagen estático, las referencias a esta acción en los archivos de vista se pueden actualizar para hacer referencia a los archivos estáticos directamente, lo que mejora el rendimiento en tiempo de ejecución. Dado que no se realiza ningún procesamiento como parte de esta acción, no hay ninguna razón para no servir solo a los archivos directamente. Si no se tenable actualizar todas las referencias a esta acción, se podría volver a escribir la acción para producir una redirección a la ubicación del archivo estático.

Los dos errores siguientes se producen en el mismo método privado en la misma línea de código:

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    item.PictureUri = this.Url.RouteUrl(PicController.GetPicRouteName, new { catalogItemId = item.Id }, this.Request.Url.Scheme);
}
```

`this.Url`Y `this.Request` causan errores del compilador. En cuanto a cómo se usa este código, su finalidad es crear un vínculo a la `PicController` acción que representa los archivos de imagen. Probablemente, la misma que se acaba de detectar podría reemplazarse por vínculos directos a los archivos estáticos ubicados en *wwwroot*. Por ahora, merece la pena comentar este código y agregar un `TODO:` Comentario para hacer referencia al método pics de otra manera.

Merece la pena mencionar que la clase base `Controller` , usada por la `CatalogController` clase en la que aparece este código, sigue haciendo referencia a `System.Web.Mvc.Controller` . Sin duda habrá más errores que corregir una vez que lo actualicemos para usar ASP.NET Core. En primer lugar, quite la `using System.Web.Mvc;` línea de la lista de `using` instrucciones de `CatalogController` . A continuación, agregue el paquete NuGet `Microsoft.AspNetCore.Mvc` . Por último, agregue una `using Microsoft.AspNetCore.Mvc;` instrucción y vuelva a compilar la aplicación.

Esta vez, hay 16 errores:

- `Include` no es un argumento de atributo con nombre válido (2)
- `HttpStatusCodeResult` no encontrado (3)
- `HttpNotFound` no existe (3)
- `SelectList` no encontrado (8)

Una vez más, vamos a revisar estos errores uno a uno. En primer lugar, `SelectList` se puede corregir agregando `using Microsoft.AspNetCore.Mvc.Rendering;` , lo que elimina la mitad de los errores.

Todas las referencias a `return HttpNotFound();` deben reemplazarse por `return NotFound();` .

Todas las referencias a `return new HttpStatusCodeResult(HttpStatusCode.BadRequest);` deben reemplazarse por `return BadRequest();` .

Esto solo deja el uso de `Include` con un `[Bind]` atributo en un par de métodos de acción que tienen el siguiente aspecto:

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create([Bind(Include = "Id,Name,Description,Price,PictureFileName,CatalogTypeId,CatalogBrandId,AvailableStock,RestockThreshold,MaxStockThreshold,OnReorder")] CatalogItem catalogItem)
{
```

El código anterior restringe el enlace de modelos a las propiedades enumeradas en la `Include` cadena. En ASP.NET Core MVC, el `[Bind]` atributo sigue existiendo, pero ya no necesita el `Include =` argumento. Pase la lista de propiedades directamente al `[Bind]` atributo:

```csharp
[HttpPost]
[ValidateAntiForgeryToken]
public ActionResult Create([Bind("Id,Name,Description,Price,PictureFileName,CatalogTypeId,CatalogBrandId,AvailableStock,RestockThreshold,MaxStockThreshold,OnReorder")] CatalogItem catalogItem)
{
```

Con estos cambios, el proyecto se compila una vez más. Por lo general, es mejor usar tipos de modelo independientes para las entradas del controlador, en lugar de usar el enlace de modelos directamente con el modelo de dominio o los tipos de modelo de datos.

## <a name="migrate-views"></a>Migrar vistas

Las dos características más importantes ASP.NET Core MVC relacionadas con las vistas son [Razor pages](/aspnet/core/razor-pages/) y las [aplicaciones auxiliares de etiquetas](/aspnet/core/mvc/views/tag-helpers/built-in/). Para la migración inicial, no usaremos ninguna de estas características. Sin embargo, debe tener en cuenta las características si sigue dando soporte a la aplicación una vez que se ha migrado. El siguiente paso consiste en copiar la carpeta *views* del proyecto original en la nueva. Después de compilar, hay nueve errores:

- HttpContext no existe (2)
- Los scripts no existen (5)
- No existe ningún estilo (1)
- No se encontró HtmlString (1)

La investigación de estos errores descubre que la mayoría de ellos se encuentran en el *_Layout. cshtml* principal, con varios relacionados con la representación de etiquetas de script y estilo, o que se muestran cuando el servidor que hospeda la aplicación se reinició por última vez. La lista de código siguiente muestra las áreas problemáticas en el archivo *_Layout. cshtml* :

```razor
// other lines omitted; only errors shown
@Styles.Render("~/Content/css")
@Scripts.Render("~/bundles/modernizr")

@{ var sessionInfo = new HtmlString($"{HttpContext.Current.Session["MachineName"]}, {HttpContext.Current.Session["SessionStartTime"]}");}

@Scripts.Render("~/bundles/jquery")
@Scripts.Render("~/bundles/bootstrap")
```

Se puede quitar la referencia a Modernizr. Las referencias a bootstrap y jQuery se pueden reemplazar por vínculos de red CDN a la versión adecuada.

Reemplazar `@Styles.Render` línea por:

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
```

Reemplace las dos últimas `Scripts.Render` líneas por:

```html
<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
```

Por último, después del bootstrap `<link>` , agregue `<link>` elementos adicionales para los estilos locales que use la aplicación. En el caso de *eShop*, el resultado se muestra aquí:

```html
<link rel="stylesheet" href="~/Content/custom.css" />
<link rel="stylesheet" href="~/Content/base.css" />
<link rel="stylesheet" href="~/Content/Site.css" />
```

Para determinar el orden en el que `<link>` deben aparecer los elementos, mire el HTML representado de la aplicación original. Como alternativa, revise *BundleConfig. CS*, que para el ejemplo de *eShop* incluye este código que indica la secuencia adecuada:

```csharp
bundles.Add(new StyleBundle("~/Content/css").Include(
          "~/Content/bootstrap.css",
          "~/Content/custom.css",
          "~/Content/base.css",
          "~/Content/site.css"));
```

Al volver a compilar, se revela un error más al cargar la validación de jQuery en las vistas *crear* y *Editar* . Reemplácelo por este script:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-validate/1.17.0/jquery.validate.min.js" integrity="sha512-O/nUTF5mdFkhEoQHFn9N5wmgYyW323JO6v8kr6ltSRKriZyTr/8417taVWeabVS4iONGk2V444QD0P2cwhuTkg==" crossorigin="anonymous"></script>
```

Lo último que hay que corregir en las vistas es la referencia a `Session` para mostrar cuánto tiempo se ha estado ejecutando la aplicación y en qué máquina. Estos datos se pueden mostrar directamente en el *_Layout. cshtml* del sitio mediante `System.Environment.MachineName` y `System.Diagnostics.Process.GetCurrentProcess().StartTime` :

```razor
<section class="col-sm-6">
    <img class="esh-app-footer-text hidden-xs" src="~/images/main_footer_text.png" width="335" height="26" alt="footer text image" />
    <br />
<small>@Environment.MachineName - @System.Diagnostics.Process.GetCurrentProcess().StartTime.ToString() UTC</small>
</section>
```

Llegados a este punto, la aplicación se compilará correctamente. Sin embargo, intentar ejecutarlo solo produce *Hola mundo.* Dado que la plantilla de ASP.NET Core **vacía** solo está configurada para mostrarla en respuesta a cualquier solicitud. En la siguiente sección, se completa la migración mediante la configuración de la aplicación para usar ASP.NET Core MVC, incluida la inserción de dependencias y la configuración. Una vez que se haya implementado, la aplicación debe ejecutarse. A continuación, será el momento de corregir las `TODO:` tareas que se crearon anteriormente.

## <a name="migrate-app-startup-components"></a>Migrar componentes de inicio de la aplicación

El último paso de migración consiste en realizar las tareas de inicio de la aplicación desde *global. asax* y las clases a las que llama, y migrarlas a sus ASP.net Core equivalentes. Estas tareas incluyen la configuración de MVC, la configuración de la inserción de dependencias y el trabajo con el nuevo sistema de configuración. En ASP.NET Core, estas tareas se controlan en el archivo *Startup. CS* .

### <a name="configure-mvc"></a>Configurar MVC

La aplicación ASP.NET MVC original tiene el código siguiente en su `Application_Start` en *global. asax*, que se ejecuta cuando se inicia la aplicación:

```csharp
protected void Application_Start()
{
    container = RegisterContainer();
    AreaRegistration.RegisterAllAreas();
    FilterConfig.RegisterGlobalFilters(GlobalFilters.Filters);
    RouteConfig.RegisterRoutes(RouteTable.Routes);
    BundleConfig.RegisterBundles(BundleTable.Bundles);
    ConfigDataBase();
}
```

Al examinar estas líneas de una en una, el `RegisterContainer` método configura la inserción de dependencias, que se migrará a continuación. Las tres líneas siguientes configuran distintas partes de MVC: áreas, filtros y rutas. Los paquetes se sustituyen por archivos estáticos en la aplicación migrada. La última línea configura el acceso a los datos de la aplicación, que se mostrará en una sección posterior.

Dado que esta aplicación no utiliza realmente áreas, no es necesario hacer nada para migrar la llamada de registro de área. Si la aplicación necesita migrar áreas, los [documentos especifican cómo configurar áreas en ASP.net Core](/aspnet/core/mvc/controllers/areas).

La llamada para registrar filtros globales invoca una aplicación auxiliar en la `FilterConfig` clase de la carpeta de *App_Start* de la aplicación:

```csharp
public static void RegisterGlobalFilters(GlobalFilterCollection filters)
{
    filters.Add(new HandleErrorAttribute());
}
```

El único atributo que se agrega a la aplicación es el filtro de MVC de ASP.NET, `HandleErrorAttribute` . Este filtro garantiza que cuando se produce una excepción como parte de una solicitud, se muestran una acción y vista predeterminadas, en lugar de los detalles de la excepción. En ASP.NET Core, el middleware realiza esta misma funcionalidad `UseExceptionHandler` . Los mensajes de error detallados no están habilitados de forma predeterminada. Deben configurarse con el `UseDeveloperExceptionPage` middleware. Para configurar este comportamiento para que coincida con la aplicación original, debe agregarse el código siguiente al inicio del `Configure` método en *Startup. CS*:

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Error");
    }
    // ...
}
```

Esto se encarga del único filtro que usa la aplicación de eShop y, en este caso, se realizó mediante el middleware integrado. Si tiene filtros globales que se deben configurar en la aplicación, esto se hace cuando se agrega MVC en el `ConfigureServices` método, que se muestra más adelante en este capítulo.

La última parte de la lógica relacionada con MVC que se debe migrar son las rutas predeterminadas de la aplicación. La llamada a `RouteConfig.RegisterRoutes(RouteTable.Routes)` pasa la tabla de rutas MVC al `RegisterRoutes` método auxiliar, donde se ejecuta el código siguiente cuando se inicia la aplicación:

```csharp
public static void RegisterRoutes(RouteCollection routes)
{
    routes.MapMvcAttributeRoutes();
    routes.IgnoreRoute("{resource}.axd/{*pathInfo}");

    routes.MapRoute(
        name: "Default",
        url: "{controller}/{action}/{id}",
        defaults: new { controller = "Catalog", action = "Index", id = UrlParameter.Optional }
    );
}
```

Tomando este código línea a línea, la primera línea configura la compatibilidad con las rutas de atributo. Esto está integrado en ASP.NET Core, por lo que no es necesario configurarlo por separado. Del mismo modo, los archivos *{Resource}. axd* no se usan con ASP.net Core, por lo que no es necesario pasar por alto dichas rutas. El `MapRoute` método configura el predeterminado para MVC, que utiliza la `{controller}/{action}/{id}` plantilla de ruta típica. También especifica los valores predeterminados para esta plantilla, de modo que `CatalogController` es el controlador predeterminado que se usa y el `Index` método es la acción predeterminada. Las aplicaciones más grandes suelen incluir más llamadas a `MapRoute` para configurar rutas adicionales.

ASP.NET Core MVC admite [enrutamiento convencional y enrutamiento de atributos](/aspnet/core/mvc/controllers/routing?preserve-view=true&view=aspnetcore-2.2). El enrutamiento convencional es análogo al modo en que se configura la tabla de rutas en el `RegisterRoutes` método mencionado anteriormente. Para configurar el enrutamiento convencional con una ruta predeterminada como la usada en la aplicación de *eShop* , agregue el código siguiente a la parte inferior del `Configure` método en *Startup. CS*:

```csharp
app.UseMvc(routes =>
{
   routes.MapRoute("default", "{controller=Catalog}/{action=Index}/{id?}");
});
```

> [!NOTE]
> Con ASP.NET Core 3,0 y versiones posteriores, se cambia para utilizar extremos. Para que el puerto inicial ASP.NET Core 2,2, se trata de la sintaxis adecuada para asignar rutas convencionales.

Una vez realizados estos cambios, el `Configure` método está casi terminado. El método de la plantilla original `app.Run` que imprime *Hola mundo.* se debe eliminar. En este punto, el método es como se muestra aquí:

```csharp
public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Home/Error");
    }

    app.UseStaticFiles();

    app.UseMvc(routes =>
    {
        routes.MapRoute("default", "{controller=Catalog}/{action=Index}/{id?}");
    });
}
```

Ahora es el momento de configurar los servicios MVC, seguido del resto de la compatibilidad de la aplicación con la inserción de dependencias (DI). Hasta ahora, el método del proyecto *eShopPorted* `ConfigureServices` permaneció vacío. Ahora es el momento de empezar a rellenarlo.

En primer lugar, para obtener ASP.NET Core MVC funcione correctamente, debe agregarse:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
}
```

El código anterior es la configuración mínima necesaria para poder trabajar con las características de MVC. Hay muchas características adicionales que se pueden configurar desde esta llamada (algunas de las cuales se detallan más adelante en este capítulo), pero por ahora basta con compilar la aplicación. Al ejecutarlo, se enruta correctamente la solicitud predeterminada, pero como todavía no se ha configurado DI, se produce un error durante la activación porque todavía no se ha `CatalogController` proporcionado ninguna implementación de tipo `ICatalogService` . Volveremos a configurar MVC más en un momento. Por ahora, vamos a migrar la inserción de dependencias de la aplicación.

#### <a name="migrate-dependency-injection-configuration"></a>Migrar la configuración de inserción de dependencias

El archivo *global. asax* de la aplicación original define el método siguiente, al que se llama cuando se inicia la aplicación:

```csharp
protected IContainer RegisterContainer()
{
  var builder = new ContainerBuilder();

  builder.RegisterControllers(typeof(MvcApplication).Assembly);

  var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
  builder.RegisterModule(new ApplicationModule(mockData));

  var container = builder.Build();
  DependencyResolver.SetResolver(new AutofacDependencyResolver(container));

  return container;
}
```

Este código configura un contenedor [Autofac](https://autofac.org/) , lee un valor de configuración para determinar si se deben usar datos reales o ficticios, y pasa esta configuración a un módulo Autofac (se encuentra en el directorio */modules* de la aplicación). Afortunadamente, Autofac es compatible con .NET Core, por lo que el módulo se puede migrar directamente. Copie la carpeta en el nuevo proyecto y actualice el espacio de nombres de la clase y se debe compilar.

ASP.NET Core tiene compatibilidad integrada para la inserción de dependencias, pero puede conectar un contenedor de terceros como Autofac fácilmente si es necesario. En este caso, puesto que la aplicación ya está configurada para usar Autofac, la solución más sencilla consiste en mantener su uso. Para ello, `ConfigureServices` se debe modificar la firma del método para que devuelva un objeto `IServiceProvider` y la instancia del contenedor Autofac debe estar configurada y devuelta desde el método.

**Nota:** En .NET Core 3,0 y versiones posteriores, el proceso de integración de un contenedor de DI de terceros ha cambiado.

Parte de la configuración de Autofac requiere una llamada a `builder.Populate(services)` . Esta extensión se encuentra en el `Autofac.Extensions.DependencyInjection` paquete NuGet, que debe instalarse antes de que se compile el código.

Después de modificar `ConfigureServices` para configurar un contenedor de Autofac, el nuevo método es como se muestra aquí:

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddMvc();

    // Create Autofac container builder
    var builder = new ContainerBuilder();
    builder.Populate(services);
    bool useMockData = true; // TODO: read from config
    builder.RegisterModule(new ApplicationModule(useMockData));

    ILifetimeScope container = builder.Build();

    return new AutofacServiceProvider(container);
}
```

Por ahora, el valor de `useMockData` se establece en `true` . Esta configuración se leerá de la configuración en un momento. En este punto, la aplicación se compila y debe cargarse correctamente cuando se ejecuta, como se muestra en la figura 4-12.

![Figura 4-12](media/Figure4-12.png)

**Figura 4-12.** Aplicación de *eShop* trasladada que se ejecuta localmente con datos ficticios.

#### <a name="migrate-app-settings"></a>Migrar la configuración de la aplicación

ASP.NET Core usa un nuevo [sistema de configuración](/aspnet/core/fundamentals/configuration/?preserve-view=true&view=aspnetcore-2.2), que de forma predeterminada aprovecha una *appsettings.jsen* el archivo. Con `CreateDefaultBuilder` en *Program. CS*, la configuración predeterminada ya está configurada en la aplicación. Para tener acceso a la configuración, las clases solo deben solicitarla en su constructor. La `Startup` clase no es ninguna excepción. Para iniciar el acceso a la configuración en `Startup` y el resto de la aplicación, solicite una instancia de `IConfiguration` a partir de su constructor:

```csharp
public Startup(IConfiguration configuration)
{
    Configuration = configuration;
}

public IConfiguration Configuration { get; }
```

La aplicación original hacía referencia a su configuración mediante `ConfigurationManager.AppSettings` . Una búsqueda rápida de todas las referencias de este término da como resultado el conjunto de valores que necesita la nueva aplicación. Solo hay dos:

- `UseMockData`
- `UseCustomizationData`

Si la aplicación tiene una configuración más compleja, especialmente si usa secciones de configuración personalizadas, es probable que quiera crear y enlazar objetos a diferentes partes de la configuración de la aplicación. A continuación, se puede tener acceso a estos tipos mediante el [patrón de opciones](../../core/extensions/options.md). Sin embargo, como se indica en el documento al que se hace referencia, este patrón no debe usarse en `ConfigureServices` . En su lugar, la aplicación migrada hará referencia al `UseMockData` valor de configuración directamente.

En primer lugar, modifique el archivo de la aplicación migrada `appsettings.json` y agregue los dos valores en la raíz:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "UseMockData": "true",
  "UseCustomizationData" :  "true"
}
```

Ahora, modifique `ConfigureServices` para tener acceso a la `UseMockData` configuración de la `Configuration` propiedad (en la que previamente se establece el valor en `true` ):

```csharp
  bool useMockData = Configuration.GetValue<bool>("UseMockData");
```

En este momento, la configuración se extrae de la configuración. El otro valor, `UseCustomizationData` , lo utiliza la `CatalogDBInitializer` clase. La primera vez que se portó esta clase, se marca el acceso a `ConfigurationManager.AppSettings["UseCustomizationData"]` . Ahora es el momento de modificarlo para usar ASP.NET Core configuración. Modifique el constructor de de la `CatalogDBInitializer` siguiente manera:

```csharp
  // add using Microsoft.Extensions.Configuration
  public CatalogDBInitializer(CatalogItemHiLoGenerator indexGenerator,
      IConfiguration configuration)
  {
      this.indexGenerator = indexGenerator;
      useCustomizationData = configuration.GetValue<bool>("UseCustomizationData");
  }
```

Todo acceso a la configuración dentro de la aplicación Web debe modificarse de esta manera para usar el nuevo `IConfiguration` tipo. Las dependencias que requieren acceso a la configuración de .NET Framework pueden incluir estos valores en un archivo *app.config* agregado al proyecto Web. Los proyectos dependientes pueden trabajar con `ConfigurationManager` para obtener acceso a la configuración y no deben realizar cambios si ya utilizan este enfoque. Sin embargo, como ASP.NET Core aplicaciones se ejecutan como su propio ejecutable, no hacen referencia a *web.config* sino *app.config*. Al migrar la configuración del archivo de *web.config* de la aplicación heredada a un nuevo archivo de *app.config* en la aplicación ASP.net Core, los componentes que usan `ConfigurationManager` para tener acceso a su configuración seguirán funcionando correctamente.

La migración de la aplicación está casi completa. La única tarea restante es la configuración de acceso a datos.
  
## <a name="data-access-considerations"></a>Consideraciones sobre el acceso a datos

ASP.NET Core aplicaciones que se ejecutan en .NET Framework pueden seguir aprovechando Entity Framework (EF). Si realiza una migración incremental, el hecho de que la aplicación funcione con EF 6 antes de intentar migrar su acceso a datos para usar EF Core puede merecer la pena. De esta manera, cualquier problema con la migración de la aplicación puede identificarse y abordarse antes de que se haya iniciado otro bloque de trabajo de migración.

Como sucede, la configuración de EF 6 en la migración de ejemplo de eShop no requiere ningún trabajo especial, ya que este trabajo se realizó en Autofac `ApplicationModule` . El único problema es que actualmente la `CatalogDBContext` clase intenta leer su cadena de conexión de *web.config*. Para solucionar este paso, es necesario agregar los detalles de conexión para *appsettings.jsen*. A continuación, se debe pasar la cadena de conexión `CatalogDBContext` cuando se crea.

Actualice el *appsettings.jsen* para incluir la cadena de conexión. El archivo completo se muestra aquí:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=eShopPorted;Trusted_Connection=True;MultipleActiveResultSets=true"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "UseMockData": "false",
  "UseCustomizationData": "true"
}
```

La cadena de conexión se debe pasar al constructor cuando `DbContext` se crea. Dado que las instancias se crean mediante Autofac, el cambio debe realizarse en `ApplicationModule` . Modifique el módulo para que tome en `connectionString` su constructor y asígnelo a un campo. A continuación, modifique el registro de `CatalogDBContext` para agregar la cadena de conexión como parámetro:

```csharp
builder.RegisterType<CatalogDBContext>()
  .WithParameter("connectionString", _connectionString)
  .InstancePerLifetimeScope();
```

El parámetro también debe agregarse a una nueva sobrecarga del constructor en `CatalogDBContext` sí mismo:

```csharp
public CatalogDBContext(string connectionString) : base(connectionString)
{
}
```

Por último, `ConfigureServices` debe leer la cadena de conexión de `Config` y pasarla a `ApplicationModule` cuando cree una instancia de ella:

```csharp
bool useMockData = Configuration.GetValue<bool>("UseMockData");
string connectionString = Configuration.GetConnectionString("DefaultConnection");
builder.RegisterModule(new ApplicationModule(useMockData, connectionString));
```

Con este código en su lugar, la aplicación se ejecuta como antes, conectándose a una base de datos de SQL Server cuando `UseMockData` es `false` .

La aplicación se puede implementar y ejecutar en producción en este momento, convertirla en ASP.NET Core pero seguir ejecutándose en .NET Framework y EF 6. Si lo desea, se puede migrar la aplicación para que se ejecute en .NET Core y Entity Framework Core, lo que aportará más ventajas que se describen en los capítulos anteriores. Específico de Entity Framework, [esta documentación compara EF Core y EF 6](/ef/efcore-and-ef6/) e incluye una cuadrícula que muestra la biblioteca que admite cada una de las docenas de características individuales.

### <a name="migrate-to-entity-framework-core"></a>Migrar a Entity Framework Core

Suponiendo que se haya tomado la decisión de migrar a EF Core, los pasos pueden ser bastante sencillos, especialmente si la aplicación original usaba un enfoque de modelo basado en código. Al [preparar el puerto de EF 6 a EF Core](/ef/efcore-and-ef6/porting/), revise la disponibilidad de las características en la versión de destino de EF Core que va a usar. Revise la documentación sobre la [migración desde y el modelo basado en EDMX](/ef/efcore-and-ef6/porting/port-edmx) en comparación con la [migración de un modelo basado en código](/ef/efcore-and-ef6/porting/port-code).

Para actualizar a EF Core 2,2, los pasos básicos que conlleva son agregar los paquetes de NuGet adecuados y actualizar los espacios de nombres. A continuación, ajuste el modo en que se pasa la cadena de conexión al `DbContext` tipo y cómo se conecta para la inserción de dependencias.

EF Core se agrega como una referencia de paquete al proyecto:

```xml
<PackageReference Include="Microsoft.EntityFrameworkCore" Version="2.2.6" />
```

Se quita la referencia a EF 6:

```xml
<PackageReference Include="EntityFramework" Version="6.2.0" />
```

El compilador notificará los errores en `CatalogDBContext` y `CatalogDBInitializer` . `CatalogDbContext` es necesario que los espacios de nombres antiguos se hayan quitado y se hayan reemplazado por `Microsoft.EntityFrameworkCore` . Se pueden quitar sus constructores. `DbModelBuilder` debe reemplazarse por `ModelBuilder` . Los métodos auxiliares para configurar tipos se mueven a clases independientes que implementan `IEntityTypeConfiguration<T>` . A continuación, el `CatalogDBContext` método de la clase `OnModelCreating` simplemente se convierte en:

```csharp
protected override void OnModelCreating(ModelBuilder builder)
{
    builder.ApplyConfigurationsFromAssembly(Assembly.GetExecutingAssembly());

    base.OnModelCreating(builder);
}
```

Otros cambios implicados incluyen:

- `HasDatabaseGeneratedOption(DatabaseGeneratedOption.None)` reemplazado por `ValueGeneratedNever()`
- `HasRequired<T>` reemplazado por `HasOne<T>`
- `Microsoft.EntityFrameworkCore.Relational`Paquete instalado
- Agregar un constructor para `CatalogDBContext` tomarlo `DbContextOptions` y pasarlo al constructor base

Aquí se muestra una clase de configuración de ejemplo para `CatalogType` :

```csharp
using Microsoft.EntityFrameworkCore;
using Microsoft.EntityFrameworkCore.Metadata.Builders;

namespace eShopPorted.Models.Config
{
    public class CatalogTypeConfig : IEntityTypeConfiguration<CatalogType>
    {
        public void Configure(EntityTypeBuilder<CatalogType> builder)
        {
            builder.ToTable(nameof(CatalogType));

            builder.HasKey(ci => ci.Id);

            builder.Property(ci => ci.Id)
               .IsRequired();

            builder.Property(cb => cb.Type)
                .IsRequired()
                .HasMaxLength(100);
        }
    }
}
```

`CatalogDBInitializer`Y su clase base, `CreateDatabaseIfNotExists<T>` , son incompatibles con EF Core. El propósito de esta clase es crear e inicializar la base de datos. [El uso de EF Core creará y quitará la base `DbContext` de datos asociada para un](/ef/core/managing-schemas/ensure-created) mediante estos métodos:

```csharp
dbContext.Database.EnsureDeleted();
dbContext.Database.EnsureCreated();
```

La propagación de datos en EF Core se puede realizar con scripts manuales o como parte de la configuración del tipo. Junto con otras propiedades de entidad, los datos de inicialización se pueden configurar en `IEntityTypeConfiguration` clases mediante `builder.HasData()` . La aplicación original cargó datos de inicialización de archivos CSV en el directorio de *instalación* . Dado que solo hay unos pocos elementos, estos registros de datos se pueden agregar como parte de la configuración de la entidad. Este enfoque funciona bien para los datos de búsqueda en tablas que cambian con poca frecuencia. Agregar lo siguiente al `CatalogTypeConfig` `Configure` método de garantiza que las filas asociadas están presentes cuando se crea la base de datos:

```csharp
builder.HasData(
    new CatalogType { Id = 1, Type = "Mug" },
    new CatalogType { Id = 2, Type = "T-Shirt" },
    new CatalogType { Id = 3, Type = "Sheet" },
    new CatalogType { Id = 4, Type = "USB Memory Stick" }
);
```

La aplicación inicial incluye una `PreconfiguredData` clase, que incluye los datos de `CatalogBrand` y `CatalogType` , por lo que el uso de este método `HasData` reduce la llamada a:

```csharp
builder.HasData(
    PreconfiguredData.GetPreconfiguredCatalogBrands()
);
```

Los `CatalogItem` datos también se pueden extraer de `PreconfiguredData` y, suponiendo que las imágenes asociadas se mantienen en el control de código fuente, es la última tabla necesaria para que la aplicación funcione. La `CatalogDBInitializer` clase se puede quitar, junto con las referencias a ella. `CatalogItemHiLoGenerator`También se quitan la clase y los archivos SQL del `Infrastructure` directorio, junto con las referencias a ellos (en `CatalogService` , `ApplicationModule` ).

Con la eliminación de las clases de generador de claves especiales para `CatalogItem` , este código ahora se quita de `CatalogItemConfig` :

```csharp
builder.Property(ci => ci.Id)
    .ValueGeneratedNever()
    .IsRequired();
```

Con estas modificaciones, la aplicación ASP.NET Core se compila, pero aún no funciona con EF Core, que todavía se debe configurar para la inserción de dependencias. Con EF Core, la manera más sencilla de configurarla es en `ConfigureServices` :

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    bool useMockData = Configuration.GetValue<bool>("UseMockData");
    if (!useMockData)
    {
        string connectionString = Configuration.GetConnectionString("DefaultConnection");

        services.AddDbContext<CatalogDBContext>(options =>
            options.UseSqlServer(connectionString)
        );
    }

    // Create Autofac container builder
    var builder = new ContainerBuilder();
    builder.Populate(services);
    builder.RegisterModule(new ApplicationModule(useMockData));

    ILifetimeScope container = builder.Build();

    return new AutofacServiceProvider(container);
}
```

La versión final de Autofac `ApplicationModule` solo configura un tipo, en función de si la aplicación está configurada para usar datos ficticios:

```csharp
public class ApplicationModule : Module
{
    private bool _useMockData;

    public ApplicationModule(bool useMockData)
    {
        _useMockData = useMockData;
    }

    protected override void Load(ContainerBuilder builder)
    {
        if (_useMockData)
        {
            builder.RegisterType<CatalogServiceMock>()
                .As<ICatalogService>()
                .SingleInstance();
        }
        else
        {
            builder.RegisterType<CatalogService>()
                .As<ICatalogService>()
                .InstancePerLifetimeScope();
        }
    }
}
```

La aplicación migrada se ejecuta, pero no muestra ningún dato si está configurado para usar datos no ficticios. Los datos de inicialización agregados mediante `HasData` solo se insertan cuando se aplican las migraciones. La aplicación de origen no usó migraciones y, si la hubiera, no se migraría tal cual. El mejor enfoque es empezar con un nuevo script de migración. Para ello, agregue una referencia de paquete para `Microsoft.EntityFrameworkCore.Design` y abra una ventana de terminal en la raíz del proyecto. A continuación, ejecute:

```dotnetcli
dotnet ef migrations add Initial
```

Quite la base de datos de *eShopPorted* existente si existe y, a continuación, ejecute:

```dotnetcli
dotnet ef database update
```

Así se crea y se inicializa la base de datos. Ahora está listo para ejecutarse, con algunas pequeñas actualizaciones que quedan en dirección.

## <a name="fix-all-todo-tasks"></a>Corregir todas las tareas TODO

La ejecución de la aplicación migrada en este momento revela que no se muestra ninguna imagen en la página. Esto se debe a que la `PictureUri` propiedad de `CatalogItem` nunca se establece. Al examinar la lista de `TODO` elementos que creamos con el **lista de tareas** de Visual Studio, el único que permanece en `CatalogController` , con una nota para "hacer referencia a PIC desde wwwroot". El código en cuestión es:

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    //TODO: Reference pic from wwwroot
    //item.PictureUri = this.Url.RouteUrl(PicController.GetPicRouteName, new { catalogItemId = item.Id }, this.Request.Url.Scheme);
}
```

La solución más sencilla consiste en hacer referencia a los archivos de imagen públicos en el directorio público de *wwwroot/pics* del sitio. Esta tarea se puede llevar a cabo reemplazando el método por el código siguiente:

```csharp
private void AddUriPlaceHolder(CatalogItem item)
{
    item.PictureUri = $"/Pics/{item.Id}.png";
}
```

Con este cambio, la ejecución de la aplicación revela que las imágenes funcionan como antes.

## <a name="additional-mvc-customizations"></a>Personalizaciones de MVC adicionales

La aplicación *eShopLegacyMVC* es bastante simple, por lo que no hay mucho que configurar en términos de comportamiento predeterminado de MVC. Sin embargo, si necesita configurar componentes de MVC adicionales, como CORS, filtros y restricciones de ruta, normalmente proporciona esta información en `Startup.ConfigureServices` , donde `UseMvc` se llama a. Por ejemplo, en la lista de código siguiente se configura [CORS](/aspnet/core/security/cors?preserve-view=true&view=aspnetcore-2.2) y se configura un filtro de acción global:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddCors(options =>
    {
        options.AddPolicy(MyAllowSpecificOrigins,
            builder =>
                builder.WithOrigins("http://example.com", "http://www.contoso.com")
                    .AllowAnyHeader()
                    .AllowAnyMethod());
    });

    services.AddMvc(options =>
    {
      options.Filters.Add(new SampleGlobalActionFilter());
    }).SetCompatibilityVersion(CompatibilityVersion.Version_2_2);
}
```

> [!Note]
> Para finalizar la configuración de CORS, también debe llamar a `app.UseCors()` en `Configure` .

Otros escenarios avanzados, como agregar [enlazadores de modelos personalizados](/aspnet/core/mvc/advanced/custom-model-binding?preserve-view=true&view=aspnetcore-2.2), formateadores, etc., se explican en los documentos de ASP.net Core detallados. Por lo general, se pueden aplicar en un controlador o en una función individual, o globalmente con el mismo enfoque de opciones que se muestra en la lista de código anterior.

## <a name="other-dependencies"></a>Otras dependencias

Las dependencias que usan características de .NET Framework que tenían una dependencia en el modelo de configuración heredado, como el tipo de cliente de WCF y el código de seguimiento, deben modificarse cuando se portan. En lugar de que estos tipos extraigan su información de configuración directamente, deben configurarse en el código. Por ejemplo, una conexión a un servicio WCF que se configuró en el *web.config* de la aplicación ASP.net que se va a usar `basicHttpBinding` podría configurarse mediante programación con el código siguiente:

```csharp
var binding = new BasicHttpBinding();
binding.MaxReceivedMessageSize = 2_000_000;

var endpointAddress = new EndpointAddress("http://localhost:9200/ExampleService");

var myClient = new MyServiceClient(binding, endpointAddress);
```

En lugar de basarse en los archivos de configuración para su configuración, los clientes de WCF y otros tipos de .NET Framework deben tener su configuración especificada en el código. De esta manera, estos tipos pueden seguir funcionando en ASP.NET Core aplicaciones 2,2.

## <a name="references"></a>Referencias

- [repositorio de GitHub de eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)
- [Herramienta del Asistente para actualización de .NET](https://aka.ms/dotnet-upgrade-assistant)
- [La API y ViewModels no deben hacer referencia a los modelos de dominio](https://ardalis.com/your-api-and-view-models-should-not-reference-domain-models/)
- [Middleware de la página de excepciones para desarrolladores](/aspnet/core/fundamentals/error-handling#developer-exception-page)
- [Profundice en EF Core HasData](/archive/msdn-magazine/2018/august/data-points-deep-dive-into-ef-core-hasdata-seeding)

>[!div class="step-by-step"]
>[Anterior](more-migration-scenarios.md)
>[Siguiente](deployment-scenarios.md)
