---
title: Una introducción a Blazor para desarrolladores de formularios Web Forms de ASP.net
description: Introducción Blazor y escritura de aplicaciones Web de pila completa con .net
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- WebAssembly
ms.date: 11/20/2020
ms.openlocfilehash: f1967dac0f46ba7cfefab62c5528dd1db8029514
ms.sourcegitcommit: 2f485e721f7f34b87856a51181b5b56624b31fd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2020
ms.locfileid: "96509720"
---
# <a name="an-introduction-to-no-locblazor-for-aspnet-web-forms-developers"></a>Una introducción a Blazor para desarrolladores de formularios Web Forms de ASP.net

El marco de trabajo de formularios Web Forms de ASP.NET ha sido una grapa del desarrollo web de .NET, dado que el .NET Framework se envió por primera vez en 2002. De nuevo, cuando la web todavía se encontraba en su gran cantidad de aplicaciones Web, los formularios Web Forms ASP.NET crearon muchos de los patrones que se usaban para el desarrollo de escritorio. En los formularios Web Forms de ASP.NET, las páginas web se pueden crear rápidamente a partir de controles de interfaz de usuario reutilizables. Las interacciones del usuario se administran de forma natural como eventos. Existe un completo ecosistema de controles de interfaz de usuario de formularios Web Forms que proporcionan los proveedores de Microsoft y de control. Los controles facilitan los esfuerzos de conectarse a orígenes de datos y mostrar visualizaciones de datos enriquecidas. En el caso de la inclinación visual, el diseñador de formularios Web Forms proporciona una sencilla interfaz de arrastrar y colocar para administrar controles.

A lo largo de los años, Microsoft ha incorporado nuevos marcos Web basados en ASP.NET para abordar las tendencias de desarrollo web. Algunos de estos marcos web incluyen ASP.NET MVC, ASP.NET Web Pages y ASP.NET Core más recientemente. Con cada nuevo marco de trabajo, algunos han predicho la disminución inminente de formularios Web Forms de ASP.NET y criticized como un marco web outmoded obsoleto. A pesar de estas predicciones, muchos desarrolladores web de .NET continúan ASP.NET Web Forms de forma sencilla, estable y productiva para realizar su trabajo.

En el momento de la escritura, casi la mitad de un millón de desarrolladores web usan formularios Web Forms de ASP.NET cada mes. El marco de trabajo de formularios Web Forms ASP.NET es estable hasta el punto en que los documentos, ejemplos, libros y entradas de blog desde hace una década siguen siendo útiles y relevantes. Para muchos desarrolladores web de .NET, "ASP.NET" sigue siendo sinónimo de "ASP.NET Web Forms", tal y como era cuando se diseñó .NET por primera vez. Los argumentos de las ventajas y desventajas de los formularios Web Forms de ASP.NET en comparación con los otros marcos Web de .NET nuevos pueden aparecer en Rage. Los formularios Web Forms de ASP.NET siguen siendo un marco popular para la creación de aplicaciones Web.

Aún así, las innovaciones en el desarrollo de software no se ralentizan. Todos los desarrolladores de software deben mantenerse al día de las nuevas tecnologías y tendencias. Merece la pena considerar dos tendencias en particular:

1. El cambio a código abierto y multiplataforma
2. El cambio de la lógica de la aplicación al cliente

## <a name="an-open-source-and-cross-platform-net"></a>.NET de código abierto y multiplataforma

Cuando se distribuyen los formularios Web de .NET y ASP.NET por primera vez, el ecosistema de la plataforma parecía mucho diferente de lo que tiene actualmente. Windows domina los mercados de escritorio y servidor. Las plataformas alternativas, como macOS y Linux, todavía lucharon a ganar. Los formularios Web Forms de ASP.NET se distribuyen con el .NET Framework como componente solo de Windows, lo que significa que las aplicaciones de formularios Web Forms de ASP.NET solo se pueden ejecutar en máquinas con Windows Server. Muchos entornos modernos ahora usan diferentes tipos de plataformas para servidores y equipos de desarrollo, de modo que la compatibilidad entre plataformas para muchos usuarios es un requisito absoluto.

La mayoría de los marcos web modernos ahora también son de código abierto, que ofrece una serie de ventajas. Los usuarios no se mantienen en un único propietario del proyecto para corregir errores y agregar características. Los proyectos de código abierto proporcionan una mayor transparencia en el progreso de desarrollo y en los próximos cambios. Los proyectos de código abierto disfrutan de las contribuciones de una comunidad completa y fomentan un ecosistema de código abierto compatible. A pesar de los riesgos de código abierto, muchos consumidores y colaboradores han encontrado mitigaciones adecuadas que les permiten disfrutar de las ventajas de un ecosistema de código abierto de forma segura y razonable. Algunos ejemplos de estas mitigaciones son los contratos de licencia de colaborador, las licencias descriptivas, los exámenes de pedigrí y las bases auxiliares.

La comunidad de .NET ha adoptado compatibilidad entre plataformas y código abierto. .NET Core es una implementación multiplataforma y de código abierto de .NET que se ejecuta en una gran cantidad de plataformas, como Windows, macOS y diversas distribuciones de Linux. Xamarin proporciona mono, una versión de código abierto de .NET. Mono se ejecuta en Android, iOS y otros factores de forma, incluidos los relojes y los televisores inteligentes. Microsoft ha lanzado [.net 5](https://devblogs.microsoft.com/dotnet/announcing-net-5-0/) que reconciliaba .net Core y mono en "un solo entorno de tiempo de ejecución .net y un marco de trabajo que se pueden usar en cualquier lugar y que tiene comportamientos de tiempo de ejecución uniformes y experiencias del desarrollador".

¿Se beneficiará de los formularios Web Forms de ASP.NET para la compatibilidad multiplataforma y de código abierto? La respuesta, desafortunadamente, es no o, al menos, no es la misma extensión que el resto de la plataforma. El equipo de .NET [lo hizo poco claro](https://devblogs.microsoft.com/dotnet/net-core-is-the-future-of-net/) que los formularios web forms de ASP.net no se trasladarán a .net Core o .net 5. ¿A qué se debe?

Se produjeron esfuerzos en los primeros días de .NET Core para ASP.NET formularios Web Forms. Se encontró que el número de cambios importantes necesarios era demasiado drástico. También hay una admisión aquí que, incluso para Microsoft, existe un límite en cuanto al número de Marcos web que puede admitir simultáneamente. Es posible que alguien de la Comunidad asuma la causa de la creación de una versión de código abierto y multiplataforma de formularios Web Forms de ASP.NET. El [código fuente de los formularios Web Forms de ASP.net](https://github.com/microsoft/referencesource) se ha puesto a disposición públicamente en forma de referencia. Pero, por el momento, parece que los formularios Web Forms de ASP.NET seguirán siendo Windows y sin un modelo de contribución de código abierto. Si la compatibilidad entre plataformas o el código abierto son importantes para los escenarios, deberá buscar algo nuevo.

¿Esto significa que los formularios Web Forms de ASP.NET están *inactivos* y ya no se deben usar? Por supuesto, no. Siempre que el .NET Framework se distribuya como parte de Windows, los formularios Web Forms de ASP.NET serán un marco compatible. Para muchos desarrolladores de formularios Web Forms, la falta de Compatibilidad multiplataforma y de código abierto no es un problema. Si no tiene un requisito para la compatibilidad multiplataforma, código abierto o cualquiera de las otras características nuevas de .NET Core o .NET 5, el paso de los formularios Web Forms de ASP.NET en Windows es correcto. Los formularios Web Forms de ASP.NET seguirán siendo una manera productiva de escribir aplicaciones web durante muchos años.

Pero hay otra tendencia que merece la pena tener en cuenta, y eso es el cambio al cliente.

## <a name="client-side-web-development"></a>Desarrollo web del lado cliente

Todos los. Los marcos Web basados en .net, incluidos los formularios Web Forms de ASP.NET, han tenido históricamente algo en común: están *representados por el servidor*. En las aplicaciones web representadas por el servidor, el explorador realiza una solicitud al servidor, que ejecuta código (código .NET en aplicaciones ASP.NET) para generar una respuesta. Esa respuesta se devuelve al explorador para controlar. En este modelo, el explorador se usa como un motor de representación fino. El trabajo duro de producir la interfaz de usuario, la ejecución de la lógica de negocios y el estado de administración se produce en el servidor.

Sin embargo, los exploradores se han convertido en plataformas versátiles. Implementan un número cada vez mayor de estándares web abiertos que conceden acceso a las capacidades del equipo del usuario. ¿Por qué no sacar provecho de la potencia de proceso, el almacenamiento, la memoria y otros recursos del dispositivo cliente? Las interacciones de la interfaz de usuario en particular pueden beneficiarse de una sensación más enriquecida y más interactiva cuando se administran al menos parcial o totalmente del lado cliente. La lógica y los datos que deben administrarse en el servidor todavía se pueden controlar en el lado servidor. Se pueden usar llamadas de API Web o incluso protocolos en tiempo real, como WebSockets. Estas ventajas están disponibles para los desarrolladores web de forma gratuita si están dispuestos a escribir JavaScript. Los marcos de interfaz de usuario del lado cliente, como angular, reAct y Vue, simplifican el desarrollo web del lado cliente y han crecido la popularidad. Los desarrolladores de formularios Web Forms de ASP.NET también pueden beneficiarse del uso del cliente de e incluso tener compatibilidad con marcos de JavaScript integrados como ASP.NET AJAX.

Pero el puente de dos plataformas y ecosistemas diferentes (.NET y JavaScript) se incluye con un costo. La experiencia es necesaria en dos mundos en paralelo con diferentes lenguajes, marcos y herramientas. El código y la lógica no se pueden compartir fácilmente entre el cliente y el servidor, lo que produce una sobrecarga de ingeniería y duplicación. También puede ser difícil mantenerse al día con el ecosistema de JavaScript, que tiene un historial de evolución a velocidad vértigo. Las preferencias del marco front-end y de la herramienta de compilación cambian rápidamente. El sector ha observado la progresión desde la imparte a Gulp a WebPack, etc. Se ha producido la misma renovación de Restless con Marcos front-end como jQuery, Knockout, angular, reAct y Vue. Pero dado el monopolio del explorador de JavaScript, había pocas opciones en la materia. Es decir, hasta que la comunidad web se reunió y causó que se produjera un *Miracle* .

## <a name="no-locwebassembly-fulfills-a-need"></a>WebAssembly satisface una necesidad

En 2015, los principales proveedores de exploradores se han unido a las fuerzas de un grupo de la comunidad de W3C para crear un nuevo estándar abierto denominado WebAssembly . WebAssembly es un código de bytes para la Web. Si puede compilar el código en WebAssembly , se puede ejecutar en cualquier explorador de cualquier plataforma a la velocidad nativa. Esfuerzos iniciales centrados en C/C++. El resultado era una demostración dramática de la ejecución directa de motores de gráficos 3D nativos en el explorador sin complementos. WebAssembly ha sido normalizado e implementado por todos los exploradores principales.

El trabajo en ejecución de .NET en WebAssembly se anunció a finales de 2017 y se lanzó en 2020, incluida la compatibilidad de .net 5. La capacidad de ejecutar código .NET directamente en el explorador habilita el desarrollo web de pila completa con .NET.

## <a name="no-locblazor-full-stack-web-development-with-net"></a>Blazor: desarrollo web de pila completa con .NET

Por su cuenta, la capacidad de ejecutar código .NET en un explorador no proporciona una experiencia de un extremo a otro para crear aplicaciones web del lado cliente. Aquí es donde Blazor entra. Blazor es una plataforma de interfaz de usuario web del lado cliente basada en C#, en lugar de JavaScript. Blazor se puede ejecutar directamente en el explorador mediante WebAssembly . No se requiere ningún complemento de explorador. Como alternativa, las Blazor aplicaciones pueden ejecutar el lado servidor en .net y controlar todas las interacciones del usuario a través de una conexión en tiempo real con el explorador.

Blazor tiene una gran compatibilidad con las herramientas en Visual Studio y Visual Studio Code. El marco también incluye un modelo completo de componentes de interfaz de usuario y tiene funciones integradas para:

- Formularios y validación
- Inserción de dependencias
- Enrutamiento del lado cliente
- Diseños
- Depuración en el explorador
- Interoperabilidad de JavaScript

Blazor tiene mucho en común con los formularios Web Forms de ASP.NET. Ambos marcos ofrecen modelos de programación de interfaz de usuario con estado basados en componentes, controlados por eventos. La principal diferencia arquitectónica es que ASP.NET Web Forms solo se ejecuta en el servidor. Blazor se puede ejecutar en el cliente en el explorador. Pero si procede de un fondo de formularios Web Forms ASP.NET, hay mucho en Blazor que le resultará familiar. Blazor es una solución natural para los desarrolladores de formularios Web Forms de ASP.NET que buscan una manera de aprovechar el desarrollo del lado cliente y el futuro de .NET multiplataforma de código abierto.

Este libro proporciona una introducción a Blazor que se ofrece específicamente a los desarrolladores de formularios Web Forms de ASP.net. Cada Blazor concepto se presenta en el contexto de las características y procedimientos de formularios Web Forms análogos de ASP.net. Al final de este libro, tendrá conocimientos sobre:

- Cómo compilar Blazor aplicaciones.
- Cómo Blazor funciona.
- Cómo Blazor se relaciona con .net.
- Estrategias razonables para migrar aplicaciones de formularios Web Forms de ASP.NET existentes a Blazor cuando corresponda.

## <a name="get-started-with-no-locblazor"></a>Introducción a los Blazor

Empezar a trabajar con Blazor es fácil. Vaya a <https://blazor.net> y siga los vínculos para instalar el SDK de .net adecuado y Blazor las plantillas de proyecto. También encontrará instrucciones para configurar las Blazor herramientas en Visual Studio o Visual Studio Code.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](architecture-comparison.md)
