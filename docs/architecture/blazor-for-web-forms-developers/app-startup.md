---
title: Inicio de la aplicación
description: Obtenga información sobre cómo definir la lógica de inicio de la aplicación.
author: csharpfritz
ms.author: jefritz
ms.date: 11/20/2020
ms.openlocfilehash: d812079f84f67409334d07c4c10c5577446503be
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509707"
---
# <a name="app-startup"></a>Inicio de la aplicación

Las aplicaciones escritas para ASP.NET suelen tener un `global.asax.cs` archivo que define el `Application_Start` evento que controla qué servicios están configurados y están disponibles para la representación en HTML y el procesamiento de .net. En este capítulo se examina el modo en que las cosas son ligeramente diferentes con el servidor de ASP.NET Core y el increíble.

## <a name="application_start-and-web-forms"></a>Application_Start y formularios Web Forms

El método predeterminado de formularios Web Forms `Application_Start` ha crecido en el propósito de los años para administrar muchas tareas de configuración.  Un nuevo proyecto de formularios Web Forms con la plantilla predeterminada en Visual Studio 2019 ahora contiene la lógica de configuración siguiente:

- `RouteConfig` -Enrutamiento de URL de la aplicación
- `BundleConfig` -Agrupación de CSS y JavaScript y minificación

Cada uno de estos archivos individuales reside en la `App_Start` carpeta y se ejecuta solo una vez al principio de la aplicación.  `RouteConfig` en la plantilla de proyecto predeterminada, agrega el `FriendlyUrlSettings` para formularios Web Forms para permitir que las direcciones URL de la aplicación omitan la `.ASPX` extensión de archivo.  La plantilla predeterminada también contiene una directiva que proporciona códigos de estado de redirección HTTP permanente (HTTP 301) para las `.ASPX` páginas a la dirección URL descriptiva con el nombre de archivo que omite la extensión.

Con ASP.NET Core y increíbles, estos métodos se han simplificado y consolidado en la `Startup` clase o se eliminan en favor de las tecnologías web comunes.

## <a name="blazor-server-startup-structure"></a>Estructura de inicio del servidor extraordinaria

Las aplicaciones de servidor de extraordinarias residen en un ASP.NET Core 3,0 o una versión posterior.  ASP.NET Core las aplicaciones web se configuran a través de un par de métodos en la `Startup.cs` clase en la carpeta raíz de la aplicación.  A continuación se muestra el contenido predeterminado de la clase de inicio

```csharp
public class Startup
{
  public Startup(IConfiguration configuration)
  {
    Configuration = configuration;
  }

  public IConfiguration Configuration { get; }

  // This method gets called by the runtime. Use this method to add services to the container.
  // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
  public void ConfigureServices(IServiceCollection services)
  {
    services.AddRazorPages();
    services.AddServerSideBlazor();
    services.AddSingleton<WeatherForecastService>();
  }

  // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
  public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
  {
    if (env.IsDevelopment())
    {
      app.UseDeveloperExceptionPage();
    }
    else
    {
      app.UseExceptionHandler("/Error");
      // The default HSTS value is 30 days. You may want to change this for production scenarios, see https://aka.ms/aspnetcore-hsts.
      app.UseHsts();
    }

    app.UseHttpsRedirection();
    app.UseStaticFiles();

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
      endpoints.MapBlazorHub();
      endpoints.MapFallbackToPage("/_Host");
   });
  }
 }
```

Al igual que el resto de ASP.NET Core, la clase startup se crea con principios de inyección de dependencia.  `IConfiguration`Se proporciona al constructor y se guarda en un oculto en una propiedad pública para el acceso posterior durante la configuración.

El `ConfigureServices` método introducido en ASP.net Core permite configurar los diversos servicios de ASP.net Core Framework para el contenedor de inserción de dependencias integrado de Framework.  Los distintos `services.Add*` métodos agregan servicios que habilitan características como la autenticación, las páginas de Razor, el enrutamiento del controlador MVC, signalr y las interacciones de servidor increíbles entre muchos otros.  Este método no era necesario en formularios Web Forms, ya que el análisis y el control de los archivos ASPX, ASCX, ASHX y ASMX se definieron al hacer referencia a ASP.NET en el archivo de configuración de web.config.  Puede encontrar más información sobre la inserción de dependencias en ASP.NET Core en la [documentación en línea](/aspnet/core/fundamentals/dependency-injection).

El `Configure` método introduce el concepto de la canalización http en ASP.net Core.  En este método, se declara desde la parte superior a la inferior el [middleware](middleware.md) que controlará todas las solicitudes enviadas a la aplicación. La mayoría de estas características en la configuración predeterminada estaban diseminadas en los archivos de configuración de formularios Web Forms y ahora se encuentran en un solo lugar para facilitar la referencia.

Ya no es la configuración de la página de errores personalizada colocada en un `web.config` archivo, sino que ahora está configurada para mostrarse siempre si el entorno de la aplicación no tiene la etiqueta `Development` .  Además, ASP.NET Core aplicaciones ahora están configuradas para atender páginas seguras con TLS de forma predeterminada con la `UseHttpsRedirection` llamada al método.

A continuación, se muestra un método de configuración inesperado en `UseStaticFiles` .  En ASP.NET Core, la compatibilidad con las solicitudes de archivos estáticos (por ejemplo, JavaScript, CSS y archivos de imagen) debe estar habilitada explícitamente, y solo los archivos de la carpeta *wwwroot* de la aplicación se pueden direccionar públicamente de forma predeterminada.

La siguiente línea es la primera que replica una de las opciones de configuración de formularios Web Forms: `UseRouting` .  Este método agrega la ASP.NET Core enrutador a la canalización y se puede configurar aquí o en los archivos individuales a los que puede tener en cuenta el enrutamiento.  Puede encontrar más información sobre la configuración de enrutamiento en la [sección enrutamiento](pages-routing-layouts.md).

La última instrucción de este método define los extremos en los que está escuchando el ASP.NET Core.  Estas rutas son las ubicaciones accesibles desde web a las que se puede tener acceso en el servidor Web y reciben algún contenido controlado por .NET y que se le devuelvan.  La primera entrada `MapBlazorHub` configura un concentrador signalr para utilizarlo en el suministro de la conexión persistente y en tiempo real al servidor en el que se controla el estado y la representación de los componentes increíbles.  La `MapFallbackToPage` llamada al método indica la ubicación accesible desde la Web de la página que inicia la aplicación increíblemente alta y también configura la aplicación para controlar las solicitudes de vinculación profunda desde el lado cliente.  Verá esta característica en el trabajo si abre un explorador y navega directamente a la ruta de control más impresionante de la aplicación, como `/counter` en la plantilla de proyecto predeterminada. La solicitud se controla mediante la página de reserva de *_Host. cshtml* , que luego ejecuta el enrutador increíble y representa la página del contador.

## <a name="upgrading-the-bundleconfig-process"></a>Actualización del proceso BundleConfig

Las tecnologías para la agrupación de recursos, como hojas de estilos CSS y archivos JavaScript, han evolucionado significativamente, con otras tecnologías que proporcionan herramientas y técnicas que se están desarrollando con rapidez para administrar estos recursos.  Para este fin, se recomienda usar una herramienta de línea de comandos de nodo como el uso de los recursos estáticos, como,

Las herramientas de línea de comandos de disgustas, Gulp y WebPack, así como sus configuraciones asociadas, se pueden agregar a la aplicación y ASP.NET Core omitirán silenciosamente esos archivos durante el proceso de compilación de la aplicación.  Puede Agregar una llamada para ejecutar sus tareas agregando un `Target` dentro del archivo de proyecto con una sintaxis similar a la siguiente que desencadenaría un script de Gulp y el `min` destino dentro de ese script.

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="gulp min" />
</Target>
```

Puede encontrar más información sobre las dos estrategias para administrar los archivos CSS y JavaScript en la [agrupación y minimizar de recursos estáticos en ASP.net Core documentación de](/aspnet/core/client-side/bundling-and-minification) .

>[!div class="step-by-step"]
>[Anterior](project-structure.md)
>[Siguiente](components.md)
