---
title: Componentes de la arquitectura .NET
description: Aquí se describen los componentes de la arquitectura .NET, como .NET Standard, las implementaciones de .NET, los entornos de ejecución .NET y las herramientas.
author: cartermp
ms.date: 10/05/2020
ms.openlocfilehash: 00d05ee328087042f7603779438436656c45be48
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819427"
---
# <a name="net-architectural-components"></a>Componentes de la arquitectura .NET

Una aplicación de .NET se desarrolla y se ejecuta en una o varias *implementaciones de .NET*. Las implementaciones de .NET incluyen .NET Framework, .NET 5 (y .NET Core) y Mono. Hay una especificación de API común a varias implementaciones de .NET que se denomina .NET Standard. En este artículo, se ofrece una breve introducción a cada uno de estos conceptos.

## <a name="net-standard"></a>.NET Standard

.NET Standard es un conjunto de API que se implementan mediante la biblioteca de clases base de una implementación de .NET. Más formalmente, es una especificación de API de .NET que constituyen un conjunto uniforme de contratos contra los que se compila el código. Estos contratos se implementan en varias implementaciones de .NET.

.NET Standard es una [plataforma de destino](glossary.md#target-framework). Si el código tiene como destino una versión de .NET Standard, se puede ejecutar en cualquier implementación de .NET que sea compatible con esa versión de .NET Standard.

.NET Standard se creó para permitir la portabilidad en diferentes implementaciones de .NET, pero ahora .NET 5 ofrece una mejor manera de compartir código entre varias plataformas y cargas de trabajo. Para obtener más información, vea [.NET 5 y .NET Standard](net-standard.md#net-5-and-net-standard).

## <a name="net-implementations"></a>Implementaciones de .NET

Cada implementación de .NET incluye los siguientes componentes:

- Uno o varios entornos de ejecución. Ejemplos: CLR de .NET Framework, CLR de .NET 5.
- Una biblioteca de clases. Ejemplos: biblioteca de clases base de .NET Framework, biblioteca de clases base de .NET 5.
- Opcionalmente, uno o varios marcos de trabajo de la aplicación. Ejemplos: [ASP.NET](https://www.asp.net/), [Windows Forms](/dotnet/desktop/winforms/windows-forms-overview) y [Windows Presentation Foundation (WPF)](/dotnet/desktop/wpf/) se incluyen en .NET Framework y .NET 5.
- Opcionalmente, herramientas de desarrollo. Algunas herramientas de desarrollo se comparten entre varias implementaciones.

Microsoft admite cuatro implementaciones de .NET:

- .NET 5 (y .NET Core) y versiones posteriores
- .NET Framework
- Mono
- UWP

.NET 5 es ahora la implementación principal, la que recibe desarrollo continuo. .NET 5 se basa en una única base de código que admite varias plataformas y muchas cargas de trabajo, como aplicaciones de escritorio de Windows y aplicaciones de consola multiplataforma, servicios en la nube y sitios web.

### <a name="net-5"></a>.NET 5

.NET 5 es una implementación multiplataforma de .NET diseñada para controlar cargas de trabajo de servidor y en la nube a escala. También admite otras cargas de trabajo, incluidas las aplicaciones de escritorio. Se ejecuta en Windows, macOS y Linux. Implementa .NET Standard, de forma que cualquier código que tenga como destino .NET Standard se puede ejecutar en .NET 5. [ASP.NET Core](https://dotnet.microsoft.com/learn/aspnet/what-is-aspnet-core), [Windows Forms](/dotnet/desktop/winforms/windows-forms-overview) y [Windows Presentation Foundation (WPF)](/dotnet/desktop/wpf/) se ejecutan en .NET 5.

Para obtener más información, vea los siguientes recursos:

- [Introducción a .NET](../core/introduction.md)
- [Elección entre .NET 5 y .NET Framework para aplicaciones de servidor](choosing-core-framework-server.md)
- [.NET 5 y .NET Standard](net-standard.md#net-5-and-net-standard)

### <a name="net-framework"></a>.NET Framework

.NET Framework es la implementación de .NET original que existe desde 2002. Las versiones 4.5 y posteriores implementan .NET Standard, de forma que el código que tiene como destino .NET Standard se puede ejecutar en esas versiones de .NET Framework. Contiene API específicas de Windows adicionales, como API para el desarrollo de escritorio de Windows con Windows Forms y WPF. .NET Framework está optimizado para crear aplicaciones de escritorio de Windows.

Para obtener más información, vea la [guía de .NET Framework](../framework/index.yml).

### <a name="mono"></a>Mono

Mono es una implementación de .NET que se usa principalmente cuando se requiere un entorno de ejecución pequeño. Es el entorno de ejecución que activa las aplicaciones Xamarin en Android, macOS, iOS, tvOS y watchOS, y se centra principalmente en una superficie pequeña. Mono también proporciona juegos creados con el motor de Unity.

Admite todas las versiones de .NET Standard publicadas actualmente.

Históricamente, Mono implementaba la API de .NET Framework más grande y emulaba algunas de las funciones más populares en Unix. A veces, se usa para ejecutar aplicaciones de .NET que se basan en estas capacidades en Unix.

Mono se suele usar con un compilador Just-In-Time, pero también incluye un compilador estático completo (compilación Ahead Of Time) que se usa en plataformas como iOS.

Para obtener más información, vea la [documentación de Mono](https://www.mono-project.com/docs/).

### <a name="universal-windows-platform-uwp"></a>Plataforma universal de Windows (UWP)

UWP es una implementación de .NET que se usa para compilar aplicaciones Windows modernas y táctiles y software para Internet de las cosas (IoT). Se ha diseñado para unificar los diferentes tipos de dispositivos de destino, incluidos equipos, tabletas, teléfonos e incluso la consola Xbox. UWP proporciona muchos servicios, como una tienda de aplicaciones centralizada, un entorno de ejecución (AppContainer) y un conjunto de API de Windows para usar en lugar de Win32 (WinRT). Pueden escribirse aplicaciones en C++, C#, Visual Basic y JavaScript.

Para obtener más información, vea [Introducción a la Plataforma universal de Windows](/windows/uwp/get-started/universal-application-platform-guide).

## <a name="net-runtimes"></a>Entornos de tiempo de ejecución .NET

Un entorno de ejecución es el entorno de ejecución de un programa administrado. El sistema operativo forma parte del entorno de ejecución, pero no del entorno de ejecución .NET. Estos son algunos ejemplos de los entornos de ejecución .NET:

- Common Language Runtime (CLR) para .NET Framework
- Common Language Runtime (CLR) para .NET 5
- .NET Native para la Plataforma universal de Windows
- El entorno de ejecución Mono para Xamarin.iOS, Xamarin.Android, Xamarin.Mac y el marco de escritorio de Mono

## <a name="net-tooling-and-common-infrastructure"></a>Herramientas de .NET e infraestructura común

Tiene acceso a un amplio conjunto de herramientas y componentes de infraestructura que funcionan con todas las implementaciones de .NET. Estas herramientas y componentes incluyen:

- Los lenguajes .NET y sus compiladores
- El sistema de proyectos de .NET (basado en archivos *.csproj*, *.vbproj* y *.fsproj*)
- [MSBuild](/visualstudio/msbuild/msbuild), el motor de compilación usado para compilar proyectos
- [NuGet](/nuget/), administrador de paquetes de Microsoft para .NET
- Herramientas de organización de compilación de código abierto, como [CAKE](https://cakebuild.net/) y [FAKE](https://fake.build/)

Para obtener más información, vea [Herramientas y productividad](../core/introduction.md#tools-and-productivity).

## <a name="applicable-standards"></a>Estándares aplicables

El lenguaje C# y las especificaciones de Common Language Infrastructure (CLI) se normalizan a través de [Ecma International&reg;](https://www.ecma-international.org/). Las primeras ediciones de estos estándares las publicó ECMA en diciembre de 2001.

Las revisiones posteriores de los estándares las han desarrollado los grupos de tareas TC49-TG2 (C#) y TC49-TG3 (CLI) en el Comité Técnico de Lenguajes de Programación ([TC49](https://www.ecma-international.org/memento/tc49.htm)) y adoptadas por la Asamblea general de ECMA y, posteriormente, por ISO/IEC JTC 1 a través del proceso Fast-Track de ISO.

### <a name="latest-standards"></a>Estándares más recientes

Los siguientes documentos oficiales de ECMA están disponibles para [C#](http://www.ecma-international.org/publications/standards/Ecma-334.htm) y la [CLI](http://www.ecma-international.org/publications/standards/Ecma-335.htm) ([TR-84](http://www.ecma-international.org/publications/techreports/E-TR-084.htm)):

- **El estándar del lenguaje C# (versión 5.0)** : [ECMA-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)
- **Common Language Infrastructure**: disponible en los formatos [pdf](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.pdf) y [zip](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-335.zip).
- **Información derivada del archivo XML de la parte IV**: disponible en los formatos [pdf](https://www.ecma-international.org/publications/files/ECMA-TR/ECMA%20TR-084.pdf) y [zip](https://www.ecma-international.org/publications/files/ECMA-TR/TR-084.zip).

Los documentos ISO/IEC oficiales están disponibles en la página ISO/IEC [Estándares disponibles públicamente](https://standards.iso.org/ittf/PubliclyAvailableStandards/). Estos vínculos son directos de esa página:

- **Tecnología de la información: lenguajes de programación, C#** : [ISO/IEC 23270:2018](https://standards.iso.org/ittf/PubliclyAvailableStandards/c075178_ISO_IEC_23270_2018.zip)
- **Tecnologías de la información: Common Language Infrastructure (CLI), partes I a VI**: [ISO/IEC 23271:2012](https://standards.iso.org/ittf/PubliclyAvailableStandards/c058046_ISO_IEC_23271_2012(E).zip)
- **Tecnología de la información: Common Language Infrastructure (CLI); informe técnico sobre la información derivada del archivo XML de la parte IV**: [ISO/IEC TR 23272:2011](https://standards.iso.org/ittf/PubliclyAvailableStandards/c057955_ISO_IEC_TR_23272_2011.zip)

## <a name="see-also"></a>Vea también

- [Introducción a .NET](../core/introduction.md)
- [Introducción a .NET Standard](net-standard.md)
- [Elección entre .NET 5 y .NET Framework para aplicaciones de servidor](choosing-core-framework-server.md)
- [Guía de .NET Framework](../framework/index.yml)
- [Guía de C#](../csharp/index.yml)
- [Guía de F#](../fsharp/index.yml)
- [Guía de Visual Basic](../visual-basic/index.yml)
