---
title: Componentes de la arquitectura .NET
description: "Describe los componentes de la arquitectura .NET, como .NET Standard, las implementaciones de .NET, los entornos de ejecución de .NET y las herramientas."
author: cartermp
ms.author: mairaw
ms.date: 08/23/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.openlocfilehash: ce3368f4c34a8e4b20a7deb2a6c6e4d163927cd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="net-architectural-components"></a>Componentes de la arquitectura .NET

Una aplicación de .NET se desarrolla y se ejecuta en una o varias *implementaciones de .NET*.  Las implementaciones de .NET incluyen .NET Framework, .NET Core y Mono. Hay una especificación de API común a todas las implementaciones de .NET que se denomina .NET Standard. En este artículo, se ofrece una breve introducción a cada uno de estos conceptos.

## <a name="net-standard"></a>Estándar .NET

.NET Standard es un conjunto de API que se implementan mediante la biblioteca de clases base de una implementación de .NET. Más formalmente, es una especificación de API de .NET que constituyen un conjunto uniforme de contratos contra los que se compila el código. Estos contratos se implementan en cada implementación de .NET. Esto permite la portabilidad entre diferentes implementaciones de .NET, de forma que el código se puede ejecutar en cualquier parte.

.NET Standard es también una [plataforma de destino](glossary.md#target-framework). Si el código tiene como destino una versión de .NET Standard, se puede ejecutar en cualquier implementación de .NET que sea compatible con esa versión de .NET Standard.

Para obtener más información sobre .NET Standard y cómo tenerlo como destino, vea el tema [.NET Standard](net-standard.md).

## <a name="net-implementations"></a>Implementaciones de .NET

Cada implementación de .NET incluye los siguientes componentes:

- Uno o varios entornos de ejecución. Ejemplos: CLR para .NET Framework, CoreCLR y CoreRT para .NET Core.
- Una biblioteca de clases que implementa .NET Standard y puede implementar API adicionales. Ejemplos: biblioteca de clases base de .NET Framework, biblioteca de clases base de .NET Core.
- Opcionalmente, uno o varios marcos de trabajo de la aplicación. Ejemplos: [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md) y [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) se incluyen en .NET Framework.
- Opcionalmente, herramientas de desarrollo. Algunas herramientas de desarrollo se comparten entre varias implementaciones.

Hay cuatro implementaciones principales de .NET que Microsoft desarrolla y mantiene activamente: .NET Core, .NET Framework, Mono y UWP.

### <a name="net-core"></a>Núcleo de .NET

.NET Core es una implementación multiplataforma de .NET diseñada para controlar cargas de trabajo de servidor y en la nube a escala. Se ejecuta en Windows, macOS y Linux. Implementa .NET Standard, de forma que cualquier código que tenga como destino .NET Standard se puede ejecutar en .NET Core. ASP.NET Core se ejecuta en .NET Core. 

Para obtener más información sobre .NET Core, consulte [Guía de .NET Core](../core/index.md) y [Selección entre .NET Core y .NET Framework para aplicaciones de servidor](choosing-core-framework-server.md).

### <a name="net-framework"></a>.NET Framework

.NET Framework es la implementación de .NET original que existe desde 2002. Es el mismo .NET Framework que los desarrolladores existentes de .NET han usado siempre. Las versiones 4.5 y posteriores implementan .NET Standard, de forma que el código que tiene como destino .NET Standard se puede ejecutar en esas versiones de .NET Framework. Contiene API específicas de Windows adicionales, como API para el desarrollo de escritorio de Windows con Windows Forms y WPF. .NET Framework está optimizado para crear aplicaciones de escritorio de Windows.

Para más información sobre .NET Framework, consulte la [Guía de .NET Framework](../framework/index.md).

### <a name="mono"></a>Mono

Mono es una implementación de .NET que se usa principalmente cuando se requiere un entorno de ejecución pequeño. Es el entorno de ejecución que activa las aplicaciones de Xamarin en Android, Mac, iOS, tvOS y watchOS, y se centra principalmente en una superficie pequeña.

Admite todas las versiones de .NET Standard publicadas actualmente.

Históricamente, Mono implementaba la API de .NET Framework más grande y emulaba algunas de las funciones más populares en Unix. A veces, se usa para ejecutar aplicaciones de .NET que se basan en estas capacidades en Unix.

Mono se suele usar con un compilador Just-In-Time, pero también incluye un compilador estático completo (compilación Ahead Of Time) que se usa en plataformas como iOS.

Para más información sobre Mono, consulte la [documentación de Mono](http://www.mono-project.com/docs/).

### <a name="universal-windows-platform-uwp"></a>Plataforma universal de Windows (UWP)

UWP es una implementación de .NET que se usa para compilar aplicaciones Windows modernas y táctiles y software para Internet de las cosas (IoT). Se ha diseñado para unificar los diferentes tipos de dispositivos de destino, incluidos equipos, tabletas, phablets, teléfonos e incluso la consola Xbox. UWP proporciona muchos servicios, como una tienda de aplicaciones centralizada, un entorno de ejecución (AppContainer) y un conjunto de API de Windows para usar en lugar de Win32 (WinRT). Las aplicaciones pueden escribirse en C++, C#, VB.NET y JavaScript. Al usar C# y VB.NET, .NET Core proporciona las API de .NET.

Para obtener más información sobre UWP, vea [Introducción a la Plataforma universal de Windows](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide).

## <a name="net-runtimes"></a>Entornos de tiempo de ejecución .NET

Un entorno de ejecución es el entorno de ejecución de un programa administrado. El sistema operativo forma parte del entorno de ejecución, pero no del entorno de ejecución .NET. Estos son algunos ejemplos de los entornos de ejecución .NET:
 
 - Common Language Runtime (CLR) para .NET Framework
 - Core Common Language Runtime (CoreCLR) para .NET Core
 - .NET Native para la Plataforma universal de Windows 
 - El entorno de ejecución Mono para Xamarin.iOS, Xamarin.Android, Xamarin.Mac y el marco de escritorio de Mono

## <a name="net-tooling-and-common-infrastructure"></a>Herramientas de .NET e infraestructura común

Tiene acceso a un amplio conjunto de herramientas y componentes de infraestructura que funcionan con todas las implementaciones de .NET. Se incluyen, entre otros:

- Los lenguajes .NET y sus compiladores
- El sistema de proyectos de .NET (basado en archivos *.csproj*, *.vbproj* y *.fsproj*)
- [MSBuild](/visualstudio/msbuild/msbuild), el motor de compilación usado para compilar proyectos
- [NuGet](/nuget/), administrador de paquetes de Microsoft para .NET
- Herramientas de organización de compilación de código abierto, como [CAKE](http://cakebuild.net/) y [FAKE](https://fake.build/)

## <a name="see-also"></a>Vea también
[Selección entre .NET Core y .NET Framework para aplicaciones de servidor](choosing-core-framework-server.md)   
[.NET Standard](net-standard.md)  
[Guía de .NET Core](../core/index.md)  
[Guía de .NET Framework](../framework/index.md)  
[Guía de C#](../csharp/index.md)  
[Guía de F#](../fsharp/index.md)  
[Guía de VB.NET](../visual-basic/index.md)  

