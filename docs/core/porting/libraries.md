---
title: 'Traslado a .NET Core: bibliotecas'
description: Obtenga información sobre cómo portar proyectos de .NET Framework a .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 07/14/2017
ms.openlocfilehash: 0f1d79623b4ece836732010e76a3c93fbbf8099f
ms.sourcegitcommit: f9e38d31288fe5962e6be5b0cc286da633482873
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37028050"
---
# <a name="porting-to-net-core---libraries"></a>Traslado a .NET Core: bibliotecas

En este artículo se trata cómo portar el código de biblioteca a .NET Core, para poder ejecutarlo en entornos multiplataforma.

## <a name="prerequisites"></a>Requisitos previos

En este artículo se asume lo siguiente:

- Se usa Visual Studio 2017 o posterior.
  - .NET Core no es compatible con versiones anteriores de Visual Studio.
- Se conoce el [proceso de portabilidad recomendado](index.md).
- Se han resuelto los problemas con las [dependencias de terceros](third-party-deps.md).

También debe estar familiarizado con el contenido de los temas siguientes:

[Estándar .NET](~/docs/standard/net-standard.md)   
En este tema se describe la especificación formal de las API de .NET que se prevé que estén disponibles en todas las implementaciones de .NET.

[Paquetes, metapaquetes y marcos de trabajo](~/docs/core/packages.md)   
En este artículo se trata cómo .NET Core define y usa paquetes y cómo los paquetes admiten el código que se ejecuta en varias implementaciones de .NET.

[Desarrollo de bibliotecas con herramientas multiplataforma](~/docs/core/tutorials/libraries.md)   
En este tema se explica cómo escribir bibliotecas para .NET mediante el uso de herramientas multiplataforma de la CLI.

[Adiciones al formato *csproj* para .NET Core](~/docs/core/tools/csproj.md)   
En este artículo se describen los cambios que se han agregado al archivo de proyecto como parte del cambio a *csproj* y MSBuild.

[Migración a .NET Core - Análisis de las dependencias de terceros](~/docs/core/porting/third-party-deps.md)   
En este tema se trata la portabilidad de dependencias de terceros y qué hacer cuando una dependencia de paquetes de .NET Core no se ejecuta en .NET Core.

## <a name="net-framework-technologies-unavailable-on-net-core"></a>Tecnologías de .NET Framework no disponibles en .NET Core

Varias tecnologías disponibles para las bibliotecas de .NET Framework no están disponibles para su uso con .NET Core, por ejemplo, dominios de aplicaciones, comunicación remota, seguridad de acceso del código (CAS) y transparencia de seguridad. Si las bibliotecas se basan en una o varias de estas tecnologías, considere los enfoques alternativos que se describen a continuación. Para más información sobre la compatibilidad con la API, el equipo de CoreFX mantiene una [lista de cambios de comportamiento/interrupciones de compatibilidad y API desusadas/heredadas](https://github.com/dotnet/corefx/wiki/ApiCompat) en GitHub.

El hecho de que una API o tecnología no estén implementadas actualmente no implica que sea incompatible deliberadamente. Informe de un problema en el [repositorio de problemas dotnet/corefx](https://github.com/dotnet/corefx/issues) en GitHub para solicitar tecnologías y API específicas. [Las solicitudes de portabilidad de los problemas](https://github.com/dotnet/corefx/labels/port-to-core) se marcan con la etiqueta `port-to-core`.

### <a name="appdomains"></a>Dominios de aplicaciones

Los dominios de aplicaciones aíslan las aplicaciones entre sí. Los dominios de aplicación requieren la compatibilidad con el runtime y suelen ser muy caros. No se implementan en .NET Core. No se pretende agregar esta compatibilidad en el futuro. En el caso del aislamiento del código, se recomiendan procesos independientes o usar contenedores como alternativa. Para la carga dinámica de ensamblados, se recomienda la nueva clase <xref:System.Runtime.Loader.AssemblyLoadContext>.

Para facilitar la migración de código de .NET Framework, se exponen algunas de las superficies de la API <xref:System.AppDomain> de .NET Core. Algunas de las API funcionan con normalidad (por ejemplo, <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), algunos miembros no hacen nada (por ejemplo, <xref:System.AppDomain.SetCachePath%2A>) y algunos de ellos generan <xref:System.PlatformNotSupportedException> (por ejemplo, <xref:System.AppDomain.CreateDomain%2A>). Compruebe los tipos que usa en la [fuente de referencias de `System.AppDomain`](https://github.com/dotnet/corefx/blob/master/src/System.Runtime.Extensions/src/System/AppDomain.cs) en el [repositorio dotnet/corefx de GitHub](https://github.com/dotnet/corefx), y asegúrese de que selecciona la rama correspondiente a la versión implementada.

### <a name="remoting"></a>Comunicación remota

La comunicación remota de .NET se identificó como una arquitectura problemática. Se usa para la comunicación entre dominios de aplicaciones, una funcionalidad que ya no es compatible. Además, la comunicación remota requiere la compatibilidad con el runtime, cuyo mantenimiento resulta caro. Por estos motivos, la comunicación remota de .NET no es compatible con .NET Core y no se prevé agregar esta compatibilidad en el futuro.

Para la comunicación entre procesos, considere la posibilidad de usar mecanismos de comunicación entre procesos (IPC) como alternativa a la comunicación remota, como las clases <xref:System.IO.Pipes> o <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>.

En los equipos, utilice una solución basada en red como una alternativa. Si es posible, use un protocolo de texto sin formato con poca sobrecarga, como HTTP. El [servidor web Kestrel](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), el servidor web que usa ASP.NET Core, se puede usar como opción aquí. También considere el uso de <xref:System.Net.Sockets> para escenarios de conexión entre equipos basada en red. Para obtener más opciones, vea [.NET Open Source Developer Projects: Messaging](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging) (Proyectos de desarrolladores de código abierto de .NET: mensajería).

### <a name="code-access-security-cas"></a>Seguridad de acceso del código (CAS)

El espacio aislado, que se basa en el runtime o en el marco para restringir qué recursos usa o ejecuta una aplicación administrada, [no es compatible con .NET Framework](~/docs/framework/misc/code-access-security.md) y, por tanto, tampoco se admite en .NET Core. Se considera que existen demasiados casos en .NET Framework y en el runtime en que se produce una elevación de privilegios para continuar tratando la seguridad de acceso del código (CAS) como un límite de seguridad. Además, la seguridad de acceso del código dificulta más la implementación y suele tener implicaciones en el rendimiento de corrección para las aplicaciones que no pretenden usar esta funcionalidad.

Use los límites de seguridad que proporciona el sistema operativo, como visualización, contenedores o cuentas de usuario para ejecutar procesos con el menor conjunto de privilegios.

### <a name="security-transparency"></a>Transparencia de seguridad

De forma similar a lo que ocurre con la seguridad de acceso del código, la transparencia de seguridad permite separar el código de espacios aislados del código crítico de seguridad de manera declarativa, pero [ya no se admite como un límite de seguridad](~/docs/framework/misc/security-transparent-code.md). Silverlight usa mucho esta característica. 

Use los límites de seguridad que proporciona el sistema operativo, como visualización, contenedores o cuentas de usuario para ejecutar procesos con el menor conjunto de privilegios.

## <a name="converting-a-pcl-project"></a>Conversión de un proyecto PCL

Puede convertir los destinos de un proyecto PCL en un estándar .NET cargando la biblioteca en Visual Studio 2017 y siguiendo estos pasos:

1. Haga clic con el botón derecho en el archivo de proyecto y seleccione **Propiedades**.
1. En **Biblioteca**, seleccione **Usar como destino la plataforma del estándar .NET**.

Si los paquetes admiten NuGet 3.0, el proyecto cambia el destino del estándar .NET.

Si los paquetes no admiten NuGet 3.0, aparecerá un cuadro de diálogo de Visual Studio para indicar que se deben desinstalar los paquetes actuales. Si recibe este aviso, realice los pasos siguientes:

1. Haga clic con el botón derecho en el proyecto y seleccione **Administrar paquetes NuGet**.
1. Tome nota de los paquetes del proyecto.
1. Desinstale los paquetes uno a uno.
1. Debe reiniciar Visual Studio para completar el proceso de desinstalación. De ser así, el botón **Reiniciar** aparece en la ventana **Administrador de paquetes de NuGet**.
1. Cuando se recarga el proyecto, el destino es el estándar .NET. Agregue los paquetes que se deben desinstalar.

## <a name="retargeting-your-net-framework-code-to-net-framework-462"></a>Redestinar el código de .NET Framework a .NET Framework 4.6.2

Si el código no apunta a .NET Framework 4.6.2, se recomienda que lo redestine. De esta forma, se garantiza la disponibilidad de las últimas alternativas de API en los casos donde el estándar .NET no admite las API existentes.

Haga lo siguiente para cada uno de los proyectos de Visual Studio que desea trasladar:

1. Haga clic con el botón derecho en el proyecto y seleccione Propiedades.
1. En la lista desplegable **Plataforma de destino**, seleccione **.NET Framework 4.6.2**.
1. Vuelva a compilar los proyectos.

Debido a que sus proyectos ahora apuntan a .NET Framework 4.6.2, use esa versión de .NET Framework como la base para portar el código.

## <a name="determining-the-portability-of-your-code"></a>Determinación de la portabilidad del código

El paso siguiente es ejecutar API Portability Analyzer (ApiPort), a fin de generar un informe de portabilidad para analizarlo.

Asegúrese de que comprende la herramienta [API Portability (ApiPort)](../../standard/analyzers/portability-analyzer.md) y de que puede generar informes de portabilidad que apunten a .NET Core. La forma de hacer esto posiblemente variará en función de sus necesidades y de sus preferencias personales. A continuación se muestran diferentes enfoques. Es probable que tenga que combinar los pasos de estos enfoques en función de cómo esté estructurado el código.

### <a name="dealing-primarily-with-the-compiler"></a>Trabajar primero con el compilador

Este puede ser el mejor enfoque para proyectos pequeños o proyectos que no usan muchas API de .NET Framework. El enfoque es sencillo:

1. De manera opcional, ejecute ApiPort en el proyecto. Si ejecuta ApiPort, consulte el informe para obtener información sobre los problemas que encontrará.
1. Copie todo el código a un nuevo proyecto de .NET Core.
1. Mientras consulta el informe de portabilidad (en caso de que se haya generado), solucione los errores del compilador hasta que el proyecto esté totalmente compilado.

A pesar de que este enfoque no es estructurado, el enfoque centrado en el código suele permitir solucionar rápidamente cualquier problema y es posible que sea el mejor enfoque para las bibliotecas o los proyectos más pequeños. Un proyecto que solo contiene modelos de datos puede ser un candidato ideal para este enfoque.

### <a name="staying-on-the-net-framework-until-portability-issues-are-resolved"></a>Permanecer en .NET Framework hasta solucionar los problemas de portabilidad

Este puede ser el mejor enfoque si prefiere que el código se compile durante todo el proceso. El enfoque es el siguiente:

1. Ejecute ApiPort en un proyecto.
1. Use distintas API portátiles para solucionar los problemas.
1. Anote todas las áreas en las que no se permite usar una alternativa directa.
1. Repita los pasos anteriores para todos los proyectos que desea trasladar hasta tener la seguridad de haber copiado cada uno de ellos a un proyecto nuevo de .NET Core.
1. Copie el código a un nuevo proyecto de .NET Core.
1. Solucione todos los problemas en los que se indica que no existe una alternativa directa.

Este enfoque prudente es más estructurado que simplemente solucionar los errores del compilador, pero de todos modos está relativamente centrado en el código y tiene la ventaja de que siempre hay código que se puede compilar. La manera en que puede solucionar ciertos problemas que no se podrían solucionar si solo se usa otra API varía considerablemente. Es posible que deba desarrollar un plan más integral para ciertos proyectos, un aspecto que se abarca en el enfoque siguiente.

### <a name="developing-a-comprehensive-plan-of-attack"></a>Desarrollar un plan integral de ataque

Este puede ser el mejor enfoque para proyectos de mayor tamaño y más complejos, en los que puede ser necesario volver a estructurar el código o reescribir ciertas áreas de código por completo para admitir .NET Core. El enfoque es el siguiente:

1. Ejecute ApiPort en un proyecto.
1. Observe dónde se usa cada tipo no portátil y cómo ese uso afecta a la portabilidad general.
   - Comprenda la naturaleza de esos tipos. ¿Son pocos, pero se usan con frecuencia? ¿Son muchos, pero no se usan con frecuencia? ¿Se usan de manera concentrada o se distribuyen en todo el código?
   - ¿Es simple aislar código no portátil para poder trabajar con él con más eficacia?
   - ¿Es necesario refactorizar el código?
   - En el caso de los tipos no portátiles, ¿existen API alternativas que permitan realizar la misma tarea? Por ejemplo, si usa la clase <xref:System.Net.WebClient>, es posible que, en lugar de esta, pueda usar la clase <xref:System.Net.Http.HttpClient>.
   - ¿Hay API portátiles distintas disponibles para realizar una tarea, incluso si no se trata de un reemplazo? Por ejemplo, si usa <xref:System.Xml.Schema.XmlSchema> para analizar un archivo XML, pero no necesita la detección de esquemas XML, puede usar las API <xref:System.Xml.Linq> e implementar el análisis por su cuenta en lugar de depender de una API.
1. Si tiene ensamblados difíciles de trasladar, ¿debe pensarse en dejarlos en .NET Framework por ahora? Algunos aspectos que debe considerar:
   - Puede que en la biblioteca tenga alguna funcionalidad no compatible con .NET Core, porque depende demasiado de la funcionalidad específica de Windows o específica de .NET Framework. ¿Debe considerarse la posibilidad de dejar atrás esa funcionalidad por ahora y lanzar una versión temporal para .NET Core de la biblioteca con menos características, hasta que haya recursos disponibles para portar las características?
   - ¿Sería útil una refactorización en este caso?
1. ¿Es razonable escribir su propia implementación de una API de .NET Framework no disponible?
   Podría considerar copiar, modificar y usar código del [código fuente de referencia de .NET Framework](https://github.com/Microsoft/referencesource). El código fuente de referencia está sujeto a la [licencia de MIT](https://github.com/Microsoft/referencesource/blob/master/LICENSE.txt), por lo que tiene plena libertad para usar la fuente como base para su propio código. Solo debe asegurarse de atribuir adecuadamente la propiedad de Microsoft en el código.
1. Repita este proceso las veces que sea necesario para proyectos distintos.
 
La fase de análisis puede tardar un poco en función del tamaño de la base de código. Dedicar tiempo en esta fase a comprender profundamente el ámbito de los cambios que se necesitan y para desarrollar un plan suele ahorrarle tiempo a largo plazo, principalmente si tiene una base de código compleja.

El plan podría significar realizar cambios importantes en la base de código mientras se sigue apuntando a .NET Framework 4.6.2, lo que hace que esta sea una versión más estructurada del enfoque anterior. La forma de ejecutar el plan depende de la base de código.

### <a name="mixing-approaches"></a>Combinación de enfoques

Es probable que vaya a combinar los enfoques anteriores en función de cada proyecto. Debe hacer lo que corresponda para usted y su base de código.

## <a name="porting-your-tests"></a>Portar las pruebas

La mejor forma de asegurarse de que todo funciona correctamente cuando traslada el código es probarlo mientras lo traslada a .NET Core. Para ello, debe usar un marco de pruebas que compila y ejecuta pruebas para .NET Core. Actualmente tiene 3 opciones:

- [xUnit](https://xunit.github.io/)
  * [Introducción](http://xunit.github.io/docs/getting-started-dotnet-core.html)
  * [Herramienta para convertir un proyecto MSTest en xUnit](https://github.com/dotnet/codeformatter/tree/master/src/XUnitConverter)
- [NUnit](http://www.nunit.org/)
  * [Introducción](https://github.com/nunit/docs/wiki/Installation)
  * [Entrada de blog sobre la migración de MSTest a NUnit.](http://www.florian-rappl.de/News/Page/275/convert-mstest-to-nunit)
- [MSTest](https://docs.microsoft.com/visualstudio/test/unit-test-basics)

## <a name="recommended-approach-to-porting"></a>Enfoque recomendado de portabilidad

En última instancia, el esfuerzo de portabilidad depende significativamente de la estructura del código .NET Framework. Una forma conveniente de portar el código consiste en comenzar por la *base* de la biblioteca, que son los componentes fundamentales del código. Pueden ser los modelos de datos u otras clases y métodos fundamentales que todo lo demás usa directa o indirectamente.

1. Porte el proyecto de prueba que comprueba el nivel de la biblioteca cuya portabilidad se está realizando actualmente.
1. Copie la base de la biblioteca en un nuevo proyecto .NET Core y seleccione la versión del estándar .NET que desea admitir.
1. Haga los cambios necesarios para la compilación del código. Muchas de estas acciones pueden requerir agregar dependencias del paquete NuGet al archivo *csproj*.
1. Ejecute las pruebas y haga los ajustes que sean necesarios.
1. Elija el nivel de código siguiente que se va a portar y repita los pasos anteriores.

Si empieza por la base de la biblioteca y avanza a partir de ella para probar cada nivel según sea necesario, la portabilidad es un proceso sistemático en el que se aíslan los problemas a un nivel de código a la vez.
