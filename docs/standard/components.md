---
title: Componentes de la arquitectura .NET
description: "Describe los componentes principales de la arquitectura .NET, como la biblioteca .NET Standard, los entornos de tiempo de ejecución .NET y las herramientas."
keywords: .NET, biblioteca de .NET Standard, .NET Standard, .NET Core, .NET Framework, Xamarin, MSBuild, C#, F#, VB, compiladores
author: cartermp
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 2e38e9d9-8284-46ee-a15f-199adc4f26f4
translationtype: Human Translation
ms.sourcegitcommit: 254e89abefd28419bd2f36a047e4df939f7ff8da
ms.openlocfilehash: d0cd8f44876038167db23e7fd1e5a893460f3d73

---

# <a name="net-architectural-components"></a>Componentes de la arquitectura .NET

.NET se compone de una serie de componentes clave.  Tiene una biblioteca estándar, denominada la biblioteca .NET Standard, que es un gran conjunto de API que se ejecuta en todas partes.  Esta biblioteca estándar se implementa mediante tres entornos de tiempo de ejecución .NET: .NET Framework, .NET Core y Mono para Xamarin.  Los lenguajes .NET también se ejecutan en cualquier entorno de tiempo de ejecución .NET.  Además, existen herramientas en cada plataforma que permiten crear proyectos.  Estas herramientas son las mismas con independencia de la elección del entorno de tiempo de ejecución.

Le presentamos una visión general gráfica de cada uno de los componentes de .NET mencionados anteriormente y cómo encajan.

![Todos los componentes de la arquitectura .NET juntos](media/components.png)

Lo que viene a continuación es una breve explicación de cada uno de los componentes clave mostrados anteriormente.  

## <a name="net-standard-library"></a>Biblioteca estándar de .NET

La biblioteca .NET Standard es un conjunto de API que se implementan mediante un entorno de tiempo de ejecución. NET.

Más formalmente, es una especificación de API de .NET que constituyen un conjunto uniforme de contratos con contra los que se compila el código.  Estos contratos tienen implementaciones subyacentes para cada entorno de tiempo de ejecución. NET.  Esto permite la portabilidad entre diferentes entorno de tiempo de ejecución. NET, de forma que el código se puede ejecutar en realidad en todas partes.

La biblioteca .NET Standard también es un destino de compilación, donde se conoce como .NET Standard.  Actualmente puede desarrollar para .NET Standard 1.0-1.6.  Si el código va dirigido a una versión de .NET Standard, se garantiza que se ejecuta en cualquier entorno de tiempo de ejecución .NET que implemente esa versión.

Para más información sobre la biblioteca .NET Standard y cómo desarrollar para .NET Standard, consulte [Biblioteca .NET Standard](library.md).

## <a name="net-runtimes"></a>Entornos de tiempo de ejecución .NET

Hay tres entornos de tiempo de ejecución .NET principales que Microsoft desarrolla y mantiene activamente: .NET Framework, .NET Core y Mono para Xamarin.

### <a name="net-core"></a>Núcleo de .NET

.NET Core es un entorno de tiempo de ejecución multiplataforma optimizado para cargas de trabajo de servidor.  Implementa la biblioteca .NET Standard, lo que significa que cualquier código dirigido a .NET Standard se puede ejecutar en .NET Core.  Es el entorno de tiempo de ejecución que se usa en ASP.NET Core y la Plataforma universal de Windows (UWP).  Es moderno, eficaz y está diseñado para controlar cargas de trabajo de servidor y de nube a escala.

Para aprender más sobre .NET Core, consulte la [Guía de .NET Core](../core/index.md).

### <a name="net-framework"></a>.NET Framework

.NET Framework es el entorno de tiempo de ejecución .NET histórico que existe desde 2002.  Es el mismo marco de .NET Framework existente que siempre han usado los desarrolladores de .NET.  Implementa la biblioteca .NET Standard, lo que significa que cualquier código dirigido a .NET Standard se puede ejecutar en .NET Framework.  Contiene API específicas de Windows adicionales, como API para el desarrollo de escritorio de Windows con Windows Forms y WPF.  .NET Framework está optimizado para crear aplicaciones de escritorio de Windows.

Para más información sobre .NET Framework, consulte la [Guía de .NET Framework](../framework/index.md).

### <a name="mono-for-xamarin"></a>Mono para Xamarin

Mono es el entorno de tiempo de ejecución utilizado en aplicaciones de Xamarin.  Implementa la biblioteca .NET Standard, lo que significa que cualquier código dirigido a .NET Standard se puede ejecutar en aplicaciones de Xamarin.  Contiene API adicionales para iOS, Android, Xamarin.Forms y Xamarin.Mac.  Está optimizado para la creación de aplicaciones móviles en iOS y Android.

Para más información sobre Mono, consulte la [documentación de Mono](http://www.mono-project.com/docs/).

## <a name="net-tooling-and-common-infrastructure"></a>Herramientas de .NET e infraestructura común

Las herramientas para .NET son también comunes en cada implementación de .NET.  Estas incluyen, entre otras:

* Los lenguajes .NET y sus compiladores
* Componentes de tiempo de ejecución, como JIT y el recolector de elementos no utilizados
* Sistema de proyecto de .NET (conocido en ocasiones como "csproj", "vbproj" o "fsproj")
* MSBuild, el motor de compilación usado para compilar proyectos
* NuGet, administrador de paquetes de Microsoft para .NET
* La CLI de .NET, una interfaz de línea de comandos multiplataforma para compilar proyectos .NET
* Herramientas de organización de compilación de código abierto, como CAKE y FAKE

La conclusión principal aquí debe ser que hay una gran cantidad de herramientas y una infraestructura que es común para cualquier tipo de .NET con el que decida compilar sus aplicaciones.

## <a name="next-steps"></a>Pasos siguientes

Para más información, consulte los temas siguientes:

* [Biblioteca de .NET Standard](library.md)
* [Guía de .NET Core](../core/index.md)
* [Guía de .NET Framework](../framework/index.md)
* [Guía de C#](../csharp/index.md)
* [Guía de F#](../csharp/index.md)
* [Guía de VB.NET](../csharp/index.md)


<!--HONumber=Nov16_HO3-->


