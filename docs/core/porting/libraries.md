---
title: 'Traslado a .NET Core: bibliotecas'
description: 'Traslado a .NET Core: bibliotecas'
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: a0fd860d-d6b6-4659-b325-8a6e6f5fa4a1
ms.translationtype: Human Translation
ms.sourcegitcommit: 50e128137fde445f64e10cf7c2a1ee5fdecb34e6
ms.openlocfilehash: 883745ca26a9c0d4bd1db805da603aa6e2c41972
ms.contentlocale: es-es
ms.lasthandoff: 05/01/2017

---

# <a name="porting-to-net-core---libraries"></a>Traslado a .NET Core: bibliotecas

Con el lanzamiento de la versión 1.0 de .NET Core, hay una oportunidad de trasladar el código de biblioteca existente para su ejecución multiplataforma. En este artículo se analizan la Biblioteca estándar de .NET, las tecnologías no disponibles, cómo contabilizar el menor número de API disponibles en .NET Core 1.0, cómo usar las herramientas que acompañan la versión preliminar de .NET Core SDK 2 y los enfoques recomendados para trasladar el código.

El traslado es una tarea que puede demorar, especialmente si tiene una base de código de gran tamaño. También debe estar preparado para adaptar la orientación que se proporciona aquí según corresponda para ajustarla mejor al código. Cada base de código es distinta, por lo que este artículo pretende plantear todos los aspectos de manera flexible; sin embargo, es posible que necesite desviarse de la orientación prescrita.

## <a name="prerequisites"></a>Requisitos previos

En este artículo se presupone que usa Visual Studio 2017 o posterior en Windows. Los bits necesarios para compilar el código de .NET Core no están disponibles en las versiones anteriores de Visual Studio.

En este artículo se supone, además, que comprende el [proceso de traslado recomendado](index.md) y que solucionó cualquier problema que pudiera existir con las [dependencias de terceros](third-party-deps.md).

## <a name="targeting-the-net-standard-library"></a>Enfoque a la Biblioteca estándar de .NET

La mejor forma de compilar una biblioteca multiplataforma para .NET Core es enfocarse a la [Biblioteca estándar de .NET](../../standard/library.md). La Biblioteca estándar de .NET es la especificación formal de las API de .NET que están pensadas para estar disponibles en todos los entornos de ejecución de .NET. Es compatible con el entorno de ejecución de .NET.

Esto significa que tendrá que encontrar un equilibrio entre las API que puede usar y las plataformas que puede admitir, y elegir la versión del estándar de plataforma .NET que mejor se adapta al equilibrio que desea lograr.

A partir de ahora, hay 7 versiones distintas que debe considerar: Estándar .NET, versión 1.0 a 1.6. Si elige una versión superior, obtiene acceso a más API, pero a costa de ejecutarse en menos destinos. Si elige una versión inferior, el código puede ejecutarse en más destinos, pero a costa de tener disponibles menos API.

Para su comodidad, aquí puede encontrar una matriz de cada versión del estándar .NET y cada área específica en la que se ejecuta:

| Nombre de la plataforma | Alias |  |  |  |  |  | | |
| :---------- | :--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |
|Estándar .NET | netstandard | 1.0 | 1.1 | 1.2 | 1.3 | 1.4 | 1.5 | 1.6 |
|Núcleo de .NET|netcoreapp|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|1.0|
|.NET Framework|net|&rarr;|4.5|4.5.1|4.6|4.6.1|4.6.2|4.6.3|
|Plataformas Mono/Xamarin||&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|*|
|Plataforma universal de Windows|uap|&rarr;|&rarr;|&rarr;|&rarr;|10.0|||
|Windows|win|&rarr;|8.0|8.1|||||
|Windows Phone|wpa|&rarr;|&rarr;|8.1|||||
|Windows Phone Silverlight|wp|8.0|||||||

Un factor clave que se debe comprender es que **un proyecto que apunta a una versión inferior no puede hacer referencia a un proyecto que apunta a una versión superior**. Por ejemplo, un proyecto que apunta a la versión 1.2 de la plataforma del estándar .NET no puede hacer referencia a proyectos que apuntan a la versión 1.3 (o superior) de la plataforma del estándar .NET. Sin embargo, los proyectos **sí pueden** hacer referencia a versiones inferiores, por lo que un proyecto que apunta a la versión 1.3 de la plataforma del estándar .NET puede hacer referencia a un proyecto que apunta a la versión 1.2 (o inferior) de la plataforma del estándar .NET.

Se recomienda que elija la versión más baja posible del estándar .NET y la use en todo el proyecto.

Más información en [Biblioteca estándar de la plataforma .NET](../../standard/library.md).

## <a name="key-technologies-not-yet-available-on-the-net-standard-or-net-core"></a>Tecnologías clave no disponibles todavía en el estándar .NET o .NET Core

Es posible que use algunas tecnologías disponibles para .NET Framework que no están actualmente disponibles en .NET Core. Cada una de las siguientes subsecciones corresponde a una esas tecnologías. Si es factible adoptarlas, se muestran opciones alternativas.

### <a name="app-domains"></a>Dominios de aplicación

Es posible usar AppDomains con distintos fines en .NET Framework. En el caso del aislamiento del código, recomendamos contenedores o procesos independientes como alternativa. Para la carga dinámica de ensamblados, se recomienda la nueva clase @System.Runtime.Loader.AssemblyLoadContext.

### <a name="remoting"></a>Comunicación remota

Para la comunicación entre procesos, se pueden usar mecanismos de comunicación entre procesos (IPC) como alternativa a la comunicación remota, como [canalizaciones](https://docs.microsoft.com/dotnet/core/api/system.io.pipes) o [archivos asignados en memoria](https://docs.microsoft.com/dotnet/core/api/system.io.memorymappedfiles.memorymappedfile).

Como alternativa, en los equipos puede usar una solución basada en la nube, de preferencia un protocolo de texto sin formato con poca sobrecarga, como HTTP. [KestrelHttpServer](https://github.com/aspnet/KestrelHttpServer), el servidor web que usa ASP.NET Core, se puede usar como opción aquí. También se puede considerar como opción la generación de proxy remoto a través de [Castle.Core](https://github.com/castleproject/Core).

### <a name="binary-serialization"></a>Serialización binaria

Como alternativa a la serialización binaria, es posible elegir entre varias tecnologías de serialización distintas. Debe elegir una que se ajuste a los objetivos de formato y superficie. Las opciones populares son las siguientes:

* [JSON.NET](http://www.newtonsoft.com/json) para JSON
* @System.Runtime.Serialization.DataContractSerializer para XML y JSON
* @System.Xml.Serialization.XmlSerializer para XML
* [protobuf-net](https://github.com/mgravell/protobuf-net) para búferes de protocolo

Consulte los recursos vinculados para obtener información sobre sus beneficios y elija los más adecuados para sus necesidades. Existe una gran cantidad de otras tecnologías y formatos de serialización, muchos de los cuales son de código abierto.

### <a name="sandboxes"></a>Espacios aislados

Como alternativa a los espacios aislados, puede usar los límites de seguridad que proporciona el sistema operativo, como cuentas de usuario para ejecutar procesos con el menor conjunto de privilegios.

## <a name="overview-of-projectjson"></a>Información general de `project.json`

El [modelo de proyecto project.json](../tools/project-json.md) es un modelo de proyecto que acompaña la versión preliminar 2 de .NET Core SDK 1.0. Ofrece algunas ventajas que le gustaría aprovechar hoy:

* Compatibilidad simple con múltiples versiones (multi-targeting) donde los ensamblados específicos de destino se puedan generar a partir de una sola compilación.
* La capacidad de generar fácilmente un paquete NuGet con una compilación del proyecto.
* No es necesario enumerar los archivos en el archivo del proyecto.
* Unificación de las dependencias del paquete NuGet y las dependencias proyecto a proyecto.

> A pesar de que `project.json` entrará indefectiblemente en desuso, se puede usar hoy para compilar bibliotecas en el estándar .NET.

### <a name="the-project-file-projectjson"></a>El archivo del proyecto: `project.json`

Los proyectos de .NET están definidos por un directorio que contiene un archivo `project.json`. En este archivo se declaran los aspectos del proyecto, como las dependencias de paquete, la configuración de compilador y la configuración del entorno de ejecución, etc.

El comando `dotnet restore` lee este archivo de proyecto, restaura todas las dependencias del proyecto y genera un archivo `project.lock.json`. Este archivo incluye toda la información que el sistema de compilación necesita para compilar el proyecto.

Para más información sobre el archivo `project.json`, lea la [referencia de project.json](../tools/project-json.md).

### <a name="the-solution-file-globaljson"></a>Archivo de solución: `global.json`

`global.json` es un archivo opcional que se puede incluir en una solución que contiene varios proyectos. Habitualmente se encuentra en el directorio raíz de un conjunto de proyectos. Se puede usar para informar al sistema de compilación los distintos subdirectorios que pueden contener proyectos. Está pensado para sistemas de mayor tamaño que constan de varios proyectos.

Por ejemplo, puede organizar el código en las carpetas `/src` y `/test` de primer nivel de la siguiente manera:

```json
{
    "projects":[ "src", "test" ]
}
```

A continuación, puede tener varios `project.json` archivos en sus propias subcarpetas dentro de `/src` y `/test`.

### <a name="how-to-multitarget-with-projectjson"></a>Cómo lograr compatibilidad con múltiples versiones con `project.json`

Muchas bibliotecas son compatibles con múltiples versiones para tener el alcance más amplio posible. Con .NET Core, la compatibilidad con múltiples versiones es una característica "de primera categoría", lo que significa que puede generar fácilmente ensamblados específicos de la plataforma con una compilación única.

La compatibilidad con múltiples versiones es tan simple como agregar el moniker de plataforma de destino (TFM) correcto al archivo`project.json`, con las dependencias correctas para cada destino (`dependencies` para .NET Core y `frameworkAssemblies` para .NET Framework) y, posiblemente, con directivas `#if` para compilar de manera condicional el código fuente para el uso de API específica de la plataforma.

Por ejemplo, imagine que compila una biblioteca en la que deseaba ejecutar ciertas operaciones de red y su intención era que esa biblioteca se ejecutará en todas las versiones de .NET Framework, un perfil de Biblioteca de clases portable (PCL) y .NET Core. En el caso de los destinos de .NET Core y .NET Framework 4.5+, puede usar la biblioteca `System.Net.Http` y `async`/`await`. Sin embargo, esas API no se encuentran disponibles para versiones anteriores de .NET Framework.

La siguiente es una sección `frameworks` de ejemplo para un `project.json` que apunta a .NET Framework en las versiones 2.0, 3.5, 4.0, 4.5 y el estándar .NET 1.6:

```javascript
{
    "frameworks":{
        "net20":{
            "frameworkAssemblies":{
                "System.Net":""
            }
        },
        "net35":{
            "frameworkAssemblies":{
                "System.Net":""
            }
        },
        "net40":{
            "frameworkAssemblies":{
                "System.Net":""
            }
        },
        "net45":{
            "frameworkAssemblies":{
                "System.Net.Http":"",
                "System.Threading.Tasks":""
            }
        },
        ".NETPortable,Version=v4.5,Profile=Profile259": {
            "buildOptions": {
                "define": [ "PORTABLE" ]
             },
             "frameworkAssemblies":{
                 "mscorlib":"",
                 "System":"",
                 "System.Core":"",
                 "System.Net.Http":""
             }
        },
        "netstandard16":{
            "dependencies":{
                "NETStandard.Library":"1.6.0",
                "System.Net.Http":"4.0.1",
                "System.Threading.Tasks":"4.0.11"
            }
        },
    }
}
```

Tenga en cuenta que los destinos de PCL son especiales: requieren que especifique una definición de compilación para que la reconozca el compilador y, además, requieren que especifique todos los ensamblados que usa, incluido `mscorlib`.

Luego, el código fuente podría usar las dependencias de la manera siguiente:

```csharp
#if (NET20 || NET35 || NET40 || PORTABLE)
using System.Net;
#else
using System.Net.Http;
using System.Threading.Tasks;
#endif
```

Observe que todos los destinos de .NET Framework y el estándar .NET tienen nombres que el compilador reconoce:

```
.NET Framework 2.0   --> NET20
.NET Framework 3.5   --> NET35
.NET Framework 4.0   --> NET40
.NET Framework 4.5   --> NET45
.NET Framework 4.5.1 --> NET451
.NET Framework 4.5.2 --> NET452
.NET Framework 4.6   --> NET46
.NET Framework 4.6.1 --> NET461
.NET Framework 4.6.2 --> NET462
.NET Standard 1.0    --> NETSTANDARD1_0
.NET Standard 1.1    --> NETSTANDARD1_1
.NET Standard 1.2    --> NETSTANDARD1_2
.NET Standard 1.3    --> NETSTANDARD1_3
.NET Standard 1.4    --> NETSTANDARD1_4
.NET Standard 1.5    --> NETSTANDARD1_5
.NET Standard 1.6    --> NETSTANDARD1_6
```

Como se mencionó anteriormente, si apunta a una PCL, deberá especificar una definición de compilación para que el compilador entienda la operación. No existe ninguna definición predeterminada que el compilador pueda usar.

### <a name="using-projectjson-in-visual-studio"></a>Uso de `project.json` en Visual Studio

Tiene dos opciones para usar `project.json` en Visual Studio:

1. Un nuevo tipo de proyecto xproj.
2. Un proyecto PCL redestinado que admite el estándar .NET.

Hay distintas ventajas y desventajas para cada una de estas opciones.

#### <a name="when-to-pick-an-xproj-project"></a>Cuándo se debe elegir un proyecto Xproj

El sistema de proyecto Xproj nuevo en Visual Studio usa las funcionalidades del modelo de proyecto basado en `project.json` para ofrecer dos características importantes sobre los tipos de proyecto existentes: compatibilidad con múltiples versiones y la capacidad de generar directamente un paquete NuGet en compilación.

Sin embargo, llega a costa de ciertas características que podría usar, como las siguientes:

- Compatibilidad con F# o Visual Basic.
- Generación de ensamblados satélites con cadenas de recurso localizadas.
- Referencia directa a un archivo `.dll` en el sistema de archivos.
- La capacidad de hacer referencia a un proyecto basado en csproj en el Administrador de referencias (sin embargo, se admite en función del archivo `.dll` directamente).

Si las necesidades del proyecto son relativamente mínimas y puede aprovechar las nuevas características de xproj, debe elegirlo como el sistema del proyecto. Puede hacerlo en Visual Studio de la manera siguiente:

1. Asegúrese de que usa Visual Studio 2015 o posterior.
2. Seleccione Archivo| Nuevo proyecto.
3. En Visual C#, seleccione ".NET Core".
4. Seleccione la plantilla "Biblioteca de clases (.NET Core)". 

#### <a name="when-to-pick-a-pcl-project"></a>Cuándo se debe elegir un proyecto PCL

Puede apuntar a .NET Core con el sistema de proyecto tradicional en Visual Studio. Para ello, cree una biblioteca de clases portable (PCL) y seleccione ".NET Core" en el cuadro de diálogo de configuración del proyecto. Luego, deberá redestinar el proyecto para basarlo en el estándar .NET:

1. Haga clic con el botón derecho en el archivo de proyecto en Visual Studio y seleccione Propiedades.
2. En Compilar, seleccione "Convert to .NET Standard" ("Convertir al estándar .NET").

Si tiene necesidades de sistema del proyecto más avanzadas, esta debería ser su opción. Tenga en cuenta que si desea tener compatibilidad con múltiples versiones a través de la generación de ensamblados específicos de la plataforma, como con el sistema de proyecto `xproj`, deberá crear una PCL de tipo "señuelo y engaño", tal como se describe en [How to Make Portable Class Libraries Work for You](https://blogs.msdn.microsoft.com/dsplaisted/2012/08/27/how-to-make-portable-class-libraries-work-for-you/) ("Cómo hacer que las bibliotecas de clases portables funcionen para usted").

## <a name="retargeting-your-net-framework-code-to-net-framework-462"></a>Redestinar el código de .NET Framework a .NET Framework 4.6.2

Si el código no apunta a .NET Framework 4.6.2, se recomienda que lo redestine. Con esto se garantiza que puede usar las alternativas de API más recientes en los casos donde el estándar .NET no puede admitir las API existentes.

Haga lo siguiente para cada uno de los proyectos de Visual Studio que desea trasladar:

1. Haga clic con el botón derecho en el proyecto y seleccione Propiedades.
2. En la lista desplegable "Plataforma de destino", seleccione ".NET Framework 4.6.2".
3. Vuelva a compilar los proyectos.

Y listo. Debido a que sus proyectos ahora apuntan a .NET Framework 4.6.2, puede usar esa versión de .NET Framework como la base para trasladar el código.

## <a name="determining-the-portability-of-your-code"></a>Determinar la portabilidad del código

El paso siguiente es ejecutar API Portability Analyzer (ApiPort) para generar un informe de portabilidad que puede comenzar a analizar.

Deberá asegurarse de que comprende la [herramienta API Portability (ApiPort)](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/) y que puede generar informes de portabilidad para destinar .NET Core. La manera en que hace esto probablemente variará en función de sus necesidades y preferencias personales. A continuación en este artículo se muestran algunos enfoques distintos. Es probable que combine un poco de cada uno de ellos según cómo está estructurado el código.

### <a name="dealing-primarily-with-the-compiler"></a>Gestionar principalmente el compilador

Este puede ser el mejor enfoque para proyectos pequeños o proyectos que no usan muchas API de .NET Framework. El enfoque es muy simple:

1. De manera opcional, ejecute ApiPort en el proyecto.
2. Si ejecutó ApiPort, consulte el informe.
3. Copie todo el código a un nuevo proyecto de .NET Core.
4. Solucione los errores que se puedan generar en el compilador hasta que realice la compilación. En caso de ser necesario, consulte el informe de portabilidad.
5. Repita según sea necesario.

A pesar de que este informe es muy poco estructurado, el enfoque centrado en el código puede permitir solucionar rápidamente cualquier problema y es posible que sea el mejor enfoque para las bibliotecas o proyectos más pequeños. Aquí, un proyecto que solo contiene modelos de datos puede ser un candidato ideal.

### <a name="staying-on-the-net-framework-until-portability-issues-are-resolved"></a>Permanecer en .NET Framework hasta solucionar los problemas de portabilidad

Este puede ser el mejor enfoque si prefiere que el código se compile durante todo el proceso. El enfoque es el siguiente:

1. Ejecute ApiPort en un proyecto.
2. Use distintas API portátil para solucionar los problemas.
3. Tome nota de las áreas en las que no puede usar una alternativa directa.
4. Repita los pasos 1 a 3 para todos los proyectos que traslada hasta que esté seguro de haber copiado cada uno de ellos a un proyecto .NET Core.
5. Copie el código a un nuevo proyecto .NET Core.
6. Solucione cualquier problema que haya notado.

Este enfoque prudente es más estructurado que simplemente solucionar los errores del compilador, pero de todos modos está relativamente centrado en el código y tiene la ventaja de que siempre hay código que se puede compilar. La manera en que puede solucionar ciertos problemas que no se podrían solucionar si solo se usa otra API. Es posible que deba desarrollar un plan más integral para ciertos proyectos, un aspecto que se abarca en el enfoque siguiente.

### <a name="developing-a-comprehensive-plan-of-attack"></a>Desarrollar un plan integral de ataque

Este puede ser el mejor enfoque para proyectos de mayor tamaño y más complejos, en los que puede ser necesario volver a estructurar el código o reescribir ciertas áreas para admitir .NET Core. El enfoque es el siguiente:

1. Ejecute ApiPort en un proyecto.
2. Observe en qué parte del código se usa cada tipo no portátil y cómo ese uso puede afectar la portabilidad general.

   a. Comprenda la naturaleza de esos tipos. ¿Son pocos, pero se usan con frecuencia? ¿Son muchos, pero no se usan con frecuencia? ¿Se usan de manera concentrada o se distribuyen en todo el código?
   
   b. ¿Es simple aislar código no portátil para poder trabajar con él más fácilmente?
   
   c. ¿Sería necesario refactorizar el código?
   
   d. En el caso de los tipos no portátiles, ¿existen API alternativas que permitan realizar la misma tarea? Por ejemplo, si usa la clase `WebClient`, es posible que, en lugar de esta, pueda usar la clase `HttpClient`.
   
   e. ¿Hay API portátiles distintas que puede usar para realizar una tarea, incluso si no se trata de un reemplazo? Por ejemplo, si usa `XmlSchema` para ayudar a analizar XML, pero no requiere la detección de esquemas XML, podría usar API de `System.Linq.Xml` y analizar los datos a mano.

3. Si tiene ensamblados difíciles de trasladar, ¿debe pensarse en dejarlos en .NET Framework por ahora? Algunos aspectos que debe considerar:

   a. Puede que en la biblioteca tenga cierta funcionalidad no compatible con .NET Core, porque depende demasiado de la funcionalidad específica de Windows o específica de .NET Framework. ¿Debe considerarse la posibilidad de dejar atrás esa funcionalidad por ahora y lanzar por el momento una versión para .NET Core de la librería con menos características?
   
   b. ¿Ayudaría aquí una refactorización?
   
4. ¿Es razonable escribir su propia implementación de una API de .NET Framework no disponible?

   En lugar de eso, podría considerar copiar, modificar y usar código del [código fuente de referencia de .NET Framework](https://github.com/Microsoft/referencesource). Cuenta con [Licencia MIT](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt), por lo que tiene gran libertad para hacerlo. Solo debe asegurarse de atribuir adecuadamente la propiedad de Microsoft en el código.
   
5. Repita este proceso las veces que sea necesario para proyectos distintos.
6. Una vez que tenga un plan, ejecútelo.
 
La fase de análisis puede demorar un poco en función del tamaño de la base de código. Dedicar tiempo en esta fase a comprender profundamente el ámbito de los cambios que se necesitan y para desarrollar un plan puede, a la larga, ahorrarle mucho tiempo, principalmente si tiene una base de código más compleja.

El plan podría significar realizar cambios importantes en la base de código mientras se sigue apuntando a .NET Framework 4.6.2, lo que hace que esta sea una versión más estructurada del enfoque anterior. Cómo ejecuta el plan dependerá de la base de código.

### <a name="mixing-approaches"></a>Combinar informes

Es probable que vaya a combinar los enfoques anteriores en función de cada proyecto. Debe hacer lo que corresponda para usted y su base de código.

## <a name="porting-your-tests"></a>Trasladar las pruebas

La mejor forma de asegurarse de que todo funciona correctamente cuando traslada el código es probarlo mientras lo traslada a .NET Core. Para ello, deberá usar un marco de pruebas que compilará y ejecutará pruebas para .NET Core. Actualmente tiene 3 opciones:

* [xUnit](https://xunit.github.io/)
   - [Introducción](http://xunit.github.io/docs/getting-started-dotnet-core.html)
   - [Herramienta para convertir un proyecto MSTest en xUnit](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
* [NUnit](http://www.nunit.org/)
  - [Introducción](https://github.com/nunit/docs/wiki/Installation)
  - [Entrada de blog sobre la migración de MSTest a NUnit.](http://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
* [MSTest](https://msdn.microsoft.com/library/ms243147.aspx)

## <a name="recommended-approach-to-porting"></a>Enfoque recomendado de traslado

Finalmente llegamos al traslado mismo del código. En última instancia, el verdadero esfuerzo de traslado va a depender principalmente de la estructura del código .NET Framework. Dicho esto, mostramos un enfoque recomendado que podría funcionar correctamente con la base de código.

Una buena forma de trasladar el código es comenzar con la "base" de la biblioteca. Pueden ser los modelos de datos u otras clases y métodos fundamentales que todo lo demás usa directa o indirectamente.

1. Traslade el proyecto de prueba que prueba el nivel de la biblioteca que está trasladando.
2. Copie la "base" de la biblioteca en un nuevo proyecto de .NET Core y seleccione la versión del estándar .NET que desea admitir.
3. Haga los cambios necesarios para la compilación del código. Muchas de estas acciones pueden requerir agregar dependencias del paquete NuGet al archivo `project.json`.
4. Ejecute las pruebas y haga los ajustes que sean necesarios.
5. Elija el nivel de código siguiente que se va a trasladar y repita los pasos 2 y 3.

Si metódicamente sale de la base de la biblioteca y prueba cada nivel según sea necesario, el traslado será un proceso sistemático en el que se aíslan los problemas a un nivel de código a la vez.

