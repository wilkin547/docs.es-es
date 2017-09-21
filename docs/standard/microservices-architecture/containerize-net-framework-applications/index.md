---
title: "Migrar aplicaciones de .NET Framework monolíticas heredadas a contenedores de Windows"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Migrar aplicaciones de .NET Framework monolíticas heredadas a contenedores de Windows"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 1756ff0f49d9bb243fa561ba760418eba79de1f0
ms.contentlocale: es-es
ms.lasthandoff: 09/05/2017

---
# <a name="migrating-legacy-monolithic-net-framework-applications-to-windows-containers"></a>Migrar aplicaciones de .NET Framework monolíticas heredadas a contenedores de Windows

*Los contenedores de Windows pueden usarse como una manera para mejorar los entornos de desarrollo y pruebas y para implementar aplicaciones que se basan en tecnologías de .NET Framework heredadas, como formularios Web* *Forms. El uso de contenedores para aplicaciones heredadas de esta manera se conoce como “migración mediante lift-and-shift”.*

Las secciones anteriores de esta guía han abogado por el uso de una arquitectura de microservicios en la que las aplicaciones empresariales se distribuyen entre diferentes contenedores, cada uno de los cuales ejecuta un pequeño servicio especializado. Este objetivo tiene numerosas ventajas. En el desarrollo nuevo, se recomienda encarecidamente este enfoque. Las aplicaciones fundamentales para la empresa también se verán lo bastante beneficiadas como para justificar el costo que supone el cambio de arquitectura y la reimplementación.

Pero no todas las aplicaciones se beneficiarán lo suficiente como para justificar dicho costo. Esto no significa que esas aplicaciones no se puedan usar en escenarios de contenedor.

En esta sección, exploraremos una aplicación para eShopOnContainers, mostrada en la figura 7-1. Los usuarios de esta aplicación serían los miembros del equipo empresarial de eShopOnContainers, que la utilizarían para ver y editar el catálogo de productos.

![](./media/image1.png)

**Figura 7-1**. Aplicación de formularios Web Forms ASP.NET (tecnología heredada) en un contenedor de Windows.

Se trata de una aplicación de formularios Web Forms que se usa para examinar y modificar las entradas del catálogo. La dependencia de formularios Web Forms significa que esta aplicación no se ejecutará en .NET Core, a menos que se reescriba sin formularios Web Forms y use en su lugar MVC de ASP.NET Core. Verá cómo puede ejecutar aplicaciones como estas en contenedores sin ningún cambio. También verá cómo puede realizar cambios mínimos para trabajar en un modo híbrido en el que alguna función se ha movido a un microservicio independiente, pero la mayoría de las funciones permanece en la aplicación monolítica.

## <a name="benefits-of-containerizing-a-monolithic-application"></a>Ventajas de incluir en un contenedor una aplicación monolítica

La aplicación Catalog.WebForms está disponible en el repositorio de GitHub eShopOnContainers (<https://github.com/dotnet/eShopOnContainers>). Se trata de una aplicación web independiente que tiene acceso a un almacén de datos de alta disponibilidad. Aun así, resulta beneficioso ejecutar la aplicación en un contenedor. Cree una imagen de la aplicación. A partir de ese momento, todas las implementaciones se ejecutarán en el mismo entorno. Cada contenedor usa la misma versión de sistema operativo, tiene instalada la misma versión de dependencias, usa el mismo marco de trabajo y se compila con el mismo proceso. En la figura 7-2 verá la aplicación cargada en Visual Studio 2017.

![](./media/image2.png)

**Figura 7-2**. Aplicación de formularios Web Forms de administración de catálogos en Visual Studio de 2017.

Además, todos los desarrolladores pueden ejecutar la aplicación en este entorno coherente. Los problemas que solo se manifiestan con determinadas versiones aparecerán de inmediato para los desarrolladores, en lugar de surgir en un entorno de ensayo o de producción. Las diferencias entre los entornos de desarrollo dejan de ser tan importantes para el equipo de desarrollo una vez que las aplicaciones se ejecutan en contenedores.

Por último, las aplicaciones en contenedor tienen una curva de escalado horizontal más plana. Ya ha aprendido que las aplicaciones en contenedor permiten la existencia de más contenedores en una máquina virtual o más contenedores en una máquina física. Esto supone una mayor densidad y requiere menos recursos.

Por todas estas razones, considere la posibilidad de ejecutar aplicaciones monolíticas heredadas en un contenedor de Docker mediante una operación de “migración mediante lift-and-shift”. La expresión “lift-and-shift” describe el ámbito de la tarea: extrae (*lift*) toda la aplicación de una máquina física o virtual y la traslada (*shift*) a un contenedor. En situaciones ideales, no es necesario realizar ningún cambio en el código de la aplicación para que se ejecute en un contenedor.

## <a name="possible-migration-paths"></a>Posibles procedimientos de migración

La aplicación monolítica Catalog.Webforms es una aplicación web que contiene todo el código, incluidas las bibliotecas de acceso a datos. La base de datos se ejecuta en un equipo independiente de alta disponibilidad. Esta configuración se simula en el código de ejemplo mediante el uso de un servicio de catálogo ficticio. Esto significa que puede ejecutar la aplicación Catalog.WebForms con esos datos falsos para simular un escenario puro de migración mediante lift-and-shift. Esto muestra el procedimiento de migración más sencillo, según el cual se mueven los activos existentes para ejecutarlos en un contenedor sin realizar ningún cambio en el código. Este procedimiento es adecuado para las aplicaciones que están completas y que tienen una interacción mínima con las funciones que se van a mover a microservicios.

Pero el sitio web de eShopOnContainers ya tiene acceso al almacenamiento de datos mediante microservicios para diferentes escenarios. Se pueden realizar algunos pequeños cambios adicionales en el editor del catálogo para aprovechar el microservicio de catálogo, en lugar de tener acceso directamente al almacenamiento de datos del catálogo.

Estos cambios muestran el continuo de sus propias aplicaciones. Puede hacer de todo, desde mover a contenedores una aplicación existente sin cambiarla en absoluto, hasta realizar pequeños cambios que permiten que las aplicaciones existentes tengan acceso a algunos de los nuevos microservicios, pasando por reescribir completamente una aplicación para participar de lleno en una nueva arquitectura basada en microservicios. El procedimiento que elija dependerá del costo y de las ventajas de la migración.

## <a name="application-tour"></a>Paseo por la aplicación

Puede cargar la solución Catalog.WebForms y ejecutar la aplicación como una aplicación independiente. En esta configuración, en lugar de una base de datos de almacenamiento persistente, la aplicación usa un servicio falso para devolver los datos. La aplicación usa Autofac (<https://autofac.org/>) como contenedor de inversión de control (IOC). Mediante la inserción de dependencias (DI), puede configurar la aplicación para que use los datos falsos o el servicio de datos de catálogo activo. (Más adelante explicaremos con más detalle la inserción de dependencias). El código de inicio lee un valor useFake en los archivos web.config y configura el contenedor Autofac para insertar el servicio de datos falsos o el servicio de catálogo activo. Si ejecuta la aplicación con useFake establecido en false en el archivo web.config, verá que la aplicación de formularios Web Forms muestra los datos del catálogo.

La mayoría de las técnicas usadas en esta aplicación le resultarán conocidas a cualquier persona que haya usado formularios Web Forms. Aun así, el microservicio de catálogo introduce dos técnicas con las que probablemente no esté familiarizado: la inserción de dependencias (DI) mencionada anteriormente y el trabajo con almacenes de datos asincrónicos en formularios Web Forms.

DI invierte la estrategia típica orientada a objetos consistente en escribir clases que asignan todos los recursos necesarios. En su lugar, las clases solicitan sus dependencias a un contenedor de servicios. La ventaja de DI es que puede reemplazar a los servicios externos por emulaciones (objetos ficticios) para admitir entornos de pruebas o de otro tipo.

El contenedor de DI usa la configuración appSettings de web.config para controlar si se van a usar los datos falsos del catálogo o los datos activos del servicio en ejecución. La aplicación registra un objeto HttpModule que crea el contenedor y registra un controlador de solicitud previa para insertar las dependencias. Puede ver ese código en el archivo Modules/AutoFacHttpModule.cs, que es similar al ejemplo siguiente:

```cs
private static IContainer CreateContainer()
{
  // Configure AutoFac:
  // Register Containers:

  var settings = WebConfigurationManager.AppSettings;
  var useFake = settings["usefake"];
  bool fake = useFake == "true";
  var builder = new ContainerBuilder();

  if (fake)
  {
    builder.RegisterType<CatalogMockService>()
    .As<ICatalogService>();
  }
  else
  {
    builder.RegisterType<CatalogService>()
    .As<ICatalogService>();
    builder.RegisterType<RequestProvider>()
    .As<IRequestProvider>();
  }

  var container = builder.Build();
  return container;
}

private void InjectDependencies()
{
  if (HttpContext.Current.CurrentHandler is Page page)
  {
    // Get the code-behind class that we may have written
    var pageType = page.GetType().BaseType;

    // Determine if there is a constructor to inject, and grab it
    var ctor = (from c in pageType.GetConstructors()
                where c.GetParameters().Length > 0
                select c).FirstOrDefault();

    if (ctor != null)
    {
      // Resolve the parameters for the constructor
      var args = (from parm in ctor.GetParameters()
                  select Container.Resolve(parm.ParameterType))
                  .ToArray();

      // Execute the constructor method with the arguments resolved
      ctor.Invoke(page, args);
    }

    // Use the Autofac method to inject any
    // properties that can be filled by Autofac
    Container.InjectProperties(page);
  }
}
```

Las páginas de la aplicación (Default.aspx.cs y EditPage.aspx.cs) definen constructores que toman estas dependencias. Observe que el constructor predeterminado sigue estando presente y es accesible. La infraestructura necesita el código siguiente.

```cs
protected _Default() { }

public _Default(ICatalogService catalog) => this.catalog = catalog;
```

Todas las API de catálogo son métodos asincrónicos. Los formularios Web Forms ahora las admiten para todos los controles de datos. La aplicación Catalog.WebForms usa el enlace de modelos para las páginas de lista y edición; los controles de las páginas definen las propiedades SelectMethod, UpdateMethod, InsertMethod y DeleteMethod que especifican las operaciones asincrónicas de devolución de tarea. Los controles de los formularios Web Forms entienden cuándo son asincrónicos los métodos enlazados a un control. La única restricción con la que se encontrará al usar determinados métodos asincrónicos es que no se admite la paginación. La firma de paginación requiere un parámetro out y los métodos asincrónicos no pueden tener parámetros out. Esta misma técnica se usa en otras páginas que requieren datos del servicio de catálogo.

La configuración predeterminada de la aplicación de catálogo de formularios Web Forms usa una implementación ficticia del servicio catalog.api. Dicha implementación ficticia usa un conjunto de datos codificados de forma rígida para sus datos, lo que simplifica algunas tareas al quitar la dependencia del servicio catalog.api en entornos de desarrollo.

## <a name="lifting-and-shifting"></a>Migración mediante lift-and-shift

Visual Studio proporciona una excelente compatibilidad para incluir una aplicación en un contenedor. Haga clic con el botón derecho en el nodo del proyecto y seleccione **Agregar** y **Compatibilidad con Docker**. La plantilla de proyecto de Docker agrega un nuevo proyecto a la solución denominado **docker-compose**. El proyecto contiene los activos de Docker que componen (o compilan) las imágenes que necesita y empieza a ejecutar los contenedores necesarios, tal como se muestra en la figura 7-3.

En los escenarios más simples de migración mediante lift-and-shift, la aplicación será el único servicio que usará para la aplicación de formularios Web Forms. La plantilla también cambia el proyecto de inicio para que apunte al proyecto **docker-compose**. Ahora, al presionar CTRL+F5 o F5, creará la imagen de Docker e iniciará el contenedor de Docker.

![](./media/image3.png)

**Figura 7-3**. El proyecto **docker-compose** en la solución de formularios Web Forms.

Antes de ejecutar la solución, debe asegurarse de que ha configurado Docker para usar contenedores de Windows. Para ello, haga clic con el botón derecho en el icono de la barra de tareas de Docker en Windows y seleccione **Switch to Windows Containers** (Cambiar a contenedores de Windows), como se muestra en la figura 7-4.

![](./media/image4.png)

**Figura 7-4**. Cambiar a contenedores de Windows desde el icono de la barra de tareas de Docker en Windows.

Si el elemento de menú indica **Switch to Linux containers** (Cambiar a contenedores de Linux), ya está ejecutando Docker con contenedores de Windows.

Al ejecutar la solución, se reinicia el host de Docker. Al compilar, la aplicación y la imagen de Docker se compilan para el proyecto de formularios Web Forms. La primera vez que lo haga, tardará bastante. Esto se debe a que el proceso de compilación extrae la imagen base de Windows Server y la imagen adicional para ASP.NET. Los ciclos posteriores de compilación y ejecución serán mucho más rápidos.

Examinemos con detalle los archivos que ha agregado la plantilla de proyecto de Docker. Ha creado varios archivos que Visual Studio usa para crear la imagen de Docker e iniciar un contenedor. Puede usar los mismos archivos desde la CLI para ejecutar comandos de Docker manualmente.

En el siguiente ejemplo de Dockerfile se muestra la configuración básica para compilar una imagen de Docker basada en la imagen de ASP.NET de Windows que ejecuta un sitio de ASP.NET.

```
FROM microsoft/aspnet

ARG source

WORKDIR /inetpub/wwwroot

COPY ${source:-obj/Docker/publish} .
```

Este archivo Dockerfile tendrá un aspecto muy similar a los creados para ejecutar una aplicación de ASP.NET Core en contenedores de Linux. Aun así, hay algunas diferencias importantes. La más importante es que la imagen base es microsoft/aspnet, que es la imagen actual de Windows Server que incluye .NET Framework. Otra diferencia es que los directorios copiados del directorio de origen son diferentes.

Los demás archivos del proyecto **docker-compose** son los activos de Docker necesarios para compilar y configurar los contenedores. Visual Studio coloca los diversos archivos docker-compose.yml en un nodo para resaltar cómo se usan. El archivo base docker-compose contiene las directivas que son comunes a todas las configuraciones. El archivo docker-compose.override.yml contiene variables de entorno y los reemplazos relacionados para una configuración de desarrollador. Las variantes con .vs.debug y .vs.release proporcionan una configuración de entorno que permite a Visual Studio adjuntar elementos al contenedor en ejecución y administrarlo.

Aunque la integración de Visual Studio forma parte de la compatibilidad con la adición de Docker a la solución, también puede compilar y ejecutar desde la línea de comandos mediante el comando docker-compose up, como ha visto en secciones anteriores.

## <a name="getting-data-from-the-existing-catalog-net-core-microservice"></a>Obtener datos del microservicio de catálogo existente de .NET Core

Puede configurar la aplicación de formularios Web Forms para usar el microservicio de catálogo eShopOnContainers para obtener datos en lugar de usar datos falsos. Para ello, edite el archivo web.config y establezca el valor de la clave useFake en false. El contenedor de inserción de dependencias usará la clase que tiene acceso al microservicio de catálogo activo en lugar de la clase que devuelve los datos codificados de forma rígida. No se necesita ningún otro cambio de código.

Para obtener acceso al servicio de catálogo activo tiene que actualizar el proyecto **docker-compose** para compilar la imagen del servicio de catálogo e iniciar el contenedor de servicio de catálogo. Docker CE para Windows es compatible con contenedores de Linux y con contenedores de Windows, pero no al mismo tiempo. Para ejecutar el microservicio de catálogo, debe compilar una imagen que ejecute el microservicio de catálogo sobre un contenedor de Windows. Este enfoque requiere para el proyecto de microservicios un archivo Dockerfile diferente del que ha visto en secciones anteriores. El archivo Dockerfile.windows contiene los valores de configuración necesarios para compilar la imagen de contenedor de la API de catálogo de modo que se ejecute en un contenedor de Windows, por ejemplo, para usar una imagen de Docker de Windows Nano.

El catálogo de microservicio se fundamenta en la base de datos de SQL Server. Por lo tanto, debe usar también una imagen de Docker de SQL Server basada en Windows.

Después de estos cambios, el proyecto docker-compose lleva a cabo más acciones para iniciar la aplicación. El proyecto inicia ahora SQL Server con la imagen de SQL Server basada en Windows, inicia el microservicio de catálogo en un contenedor de Windows e inicia el contenedor del editor de catálogo de formularios Web Forms, también en un contenedor de Windows. Si es necesario compilar alguna de las imágenes, se crean en primer lugar.

## <a name="development-and-production-environments"></a>Entornos de desarrollo y producción

Hay un par de diferencias entre la configuración de desarrollo y la configuración de producción. En el entorno de desarrollo, puede ejecutar la aplicación de formularios Web Forms, el microservicio de catálogo y SQL Server en contenedores de Windows, como parte del mismo host de Docker. En las secciones anteriores, hemos mencionado imágenes de SQL Server implementadas en el mismo host de Docker que los demás servicios basados en .NET Core en un host de Docker basado en Linux. La ventaja de ejecutar los diversos microservicios en el mismo host de Docker (o clúster) es que hay menos comunicación de red y la comunicación entre los contenedores tiene una latencia inferior.

En el entorno de desarrollo, debe ejecutar todos los contenedores en el mismo sistema operativo. Docker CE para Windows no admite la ejecución simultánea de contenedores basados en Windows y en Linux. En producción, puede decidir si quiere ejecutar el microservicio de catálogo en un contenedor de Windows en un solo host de Docker (o clúster), o bien si prefiere que la aplicación de formularios Web Forms se comunique con una instancia del microservicio de catálogo que se ejecuta en un contenedor de Linux en un host de Docker diferente. Depende de cómo quiera optimizar la latencia de red. En la mayoría de los casos, le interesará que los microservicios de los que dependen sus aplicaciones se ejecuten en el mismo host de Docker (o conjunto) para facilitar la implementación y para que la latencia de comunicación sea inferior. En estas configuraciones, la única comunicación costosa es la que se establece entre las instancias de microservicios y los servidores de alta disponibilidad para el almacenamiento de datos persistentes.

>[!div class="step-by-step"]
[Anterior] (../net-core-single-containers-linux-windows-server-hosts/index.md) [Siguiente] (../multi-container-microservice-net-applications/index.md)

