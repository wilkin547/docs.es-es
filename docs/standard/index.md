---
title: Acerca de .NET
description: "Más información sobre la plataforma. NET."
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 10/31/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
translationtype: Human Translation
ms.sourcegitcommit: 254e89abefd28419bd2f36a047e4df939f7ff8da
ms.openlocfilehash: 8eb9274def2683fae20765cbf701b706293744fc

---

# <a name="net-platform-guide"></a>Guía de la plataforma .NET

> [!NOTE]
Este artículo se va a volver a escribir.

> Consulte los [tutoriales sobre "Introducción a .NET Core" ](../core/getting-started.md) para aprender a crear una aplicación .NET Core sencilla. En unos minutos su primera aplicación estará lista y funcionando.

.NET es una plataforma de desarrollo de uso general. Puede usarse para cualquier tipo de carga de trabajo o aplicación donde se usen soluciones de uso general. Tiene varias características clave que son atractivas para muchos desarrolladores, incluida la administración automática de la memoria y los lenguajes de programación modernos, que facilitan más la creación eficaz de aplicaciones de alta calidad. .NET hace posible un entorno de programación de alto nivel con muchas características útiles, a la vez que proporciona acceso de bajo nivel a la memoria nativa y a las API.

C#, F# y Visual Basic son lenguajes populares que se basan y confían en la plataforma .NET. Los lenguajes .NET son famosos por sus características clave, tales como su modelo de programación asincrónica, Language Integrated Query, los tipos genéricos y la reflexión de sistemas de tipos. Los lenguajes también proporcionan opciones excelentes para paradigmas de programación funcionales y orientados en objetos.

Estos lenguajes son muy diversos, desde el punto de vista de la filosofía y la sintaxis, pero también por la simetría proporcionada a través de un sistema de tipos compartidos. Este sistema de tipos está proporcionado por el entorno de tiempo de ejecución subyacente. .NET se diseñó teniendo en mente la idea de "Common Language Runtime" que podría admitir los requisitos de distintos lenguajes, por ejemplo, lenguajes de tipo dinámico o estático, y permitir la interoperabilidad entre ellos. Por ejemplo, es posible pasar una colección de objetos de `People` de un lenguaje a otro sin pérdida alguna de capacidad o semántica.

Hay disponibles varias [implementaciones y productos de .NET](components.md) basados en [estándares .NET](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) abiertos que especifican los fundamentos de la plataforma. Se optimizan independientemente para diferentes tipos de aplicaciones (por ejemplo, para escritorio, móviles, juegos o la nube) y admiten muchos chips (por ejemplo, x86/x64, ARM) y sistemas operativos (por ejemplo, Windows, Linux, iOS Android y macOS). El código abierto también es una parte importante del ecosistema de .NET, con varias implementaciones de .NET y muchas bibliotecas disponibles bajo licencias con aprobación de OSI.

- Más información sobre [C#](../csharp/index.md)
- Más información sobre [F#](../fsharp/index.md)
- Examinar la [biblioteca de API de .NET](../../api/index.md)
- [Introducción a Common Language Runtime](https://github.com/dotnet/coreclr/blob/master/Documentation/botr/intro-to-clr.md)

<a name="fundamentals"></a>Aspectos básicos
------------

**Varios idiomas**: .NET proporciona un sistema de tipos bien definido, formatos de archivo, tiempo de ejecución, framework y herramientas que pueden usar varios lenguajes, tanto para su propia ejecución como para interoperar con otros lenguajes usando los mismos componentes de .NET como su divisa compartida.

**Memoria administrada**: .NET le administra automáticamente memoria a través de un recolector de elementos no utilizados. Garantiza que siempre haga referencia a objetos activos, lo que le evita problemas desagradables como saturaciones del búfer e infracciones de acceso. Esto incluye la comprobación de límites de matriz.

**Seguridad de tipos**: el principal modelo de .NET para la funcionalidad y representación de memoria es "tipos". Los tipos definen la forma y, opcionalmente, el comportamiento. El tiempo de ejecución garantiza que el código de llamada solo pueda funcionar con tipos conforme a su definición y a la visibilidad especificada de los miembros, de modo que proporciona resultados coherentes, fiables y seguros.

<a name="features"></a>Características
--------

**Tipos de valores definidos por el usuario**: los tipos de valores son una categoría de tipos útil debido a que ofrecen la semántica de "paso por valor" en lugar de "paso por referencia", tal y como ocurre con las clases. Los tipos de valores son obviamente más útiles para los datos numéricos. .NET permite tipos de valores para los tipos primitivos, como enteros, y los tipos definidos por el usuario.

**Tipos genéricos**: los tipos genéricos son tipos con uno o más parámetros de tipo que se pueden especificar para cada instancia. Esto es útil para muchos tipos, que de no ser así podrían exponer el contenido como el tipo Objeto o requerir varias definiciones de tipo. Por ejemplo, una determinada instancia de un tipo de colección se puede realizar de forma específica para personas, ubicaciones de GPS o cadenas.

**Reflexión**: .NET define un formato de metadatos que describe los tipos dentro de un archivo binario. El subsistema de reflexión usa estos datos, exponiendo las API para leer y crear instancias de tipos en tiempo de ejecución. Este recurso es muy útil para escenarios dinámicos donde no es conveniente conocer la implementación exacta de un programa antes de tiempo.

**Generación de códigos flexible**: .NET no prescribe un enfoque específico para transformar archivos binarios de .NET en código máquina. Se han usado muchos enfoques correctamente, incluida la interpretación, la compilación just-in-time (JIT), la compilación ahead-of-time (AOT) con reserva JIT y la compilación de AOT sin reserva JIT. Cada una de estas estrategias puede ser valiosa y es posible usarlas conjuntamente.

**Multiplataforma**: .NET esté destinado a ser una multiplataforma desde sus inicios. El formato binario y el conjunto de instrucciones son independientes del sistema operativo, de la CPU y del tamaño del puntero. Un archivo binario de .NET concreto compilado en 2000 para ejecutarse en un equipo de Windows de 32 bits puede ejecutarse en el dispositivo iOS ARM64 en 2016 sin ninguna modificación.

<a name="open-source"></a>Abrir origen
-----------

Las implementaciones [.NET Core](https://github.com/dotnet/core) y [Mono](https://github.com/mono/mono) de .NET son código abierto, con la licencia MIT. La documentación usa la licencia [Creative Commons CC-BY](https://creativecommons.org/licenses/by/4.0/). .NET Core y Mono están patrocinados por Microsoft y cuentan con muchos colaboradores de la comunidad. 

Estos tiempos de ejecución de uso general pueden usarse como base para la investigación académica o los productos comerciales o de enseñanza y aprendizaje. Su naturaleza abierta también significa que cualquier persona puede contribuir al código de producto ascendente, dado un error o la necesidad de una nueva característica.

<a name="projects"></a>Proyectos
--------

- [CoreCLR](https://github.com/dotnet/coreclr): runtime de .NET, usado por .NET Core.
- [Mono](https://github.com/mono/mono): runtime de .NET, usado por Xamarin y otros.
- [CoreFX](https://github.com/dotnet/coreclr): bibliotecas de clases de .NET, usadas por .NET Core y en cierta medida por Mono mediante el uso compartido de código fuente.
- [Roslyn](https://github.com/dotnet/roslyn): compiladores de C# y Visual Basic, usados por la mayoría de las plataformas y herramientas de .NET. Expone las API para leer, escribir y analizar código fuente.
- [F#](https://github.com/microsoft/visualfsharp): compilador de F#.
- [Xamarin SDK](http://open.xamarin.com): herramientas y bibliotecas necesarias para escribir Android, iOS y macOS en C# y F#.

<a name="standardized"></a>Normalizado
------------

.NET se especifica a través de [normas ECMA](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) abiertas que destacan sus capacidades y que se pueden usar para realizar una nueva implementación. Existen otras implementaciones de .NET, y después de las de Microsoft, Mono y Unity son las más populares.




<!--HONumber=Nov16_HO3-->


