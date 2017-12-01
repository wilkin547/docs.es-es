---
title: "Migración a .NET Core - Análisis de las dependencias de terceros"
description: "Migración a .NET Core - Análisis de las dependencias de terceros"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: b446e9e0-72f6-48f6-92c6-70ad0ce3f86a
ms.openlocfilehash: a074978f2817abafa7b8a9fefe7c67c9c52195b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="porting-to-net-core---analyzing-your-third-party-party-dependencies"></a>Migración a .NET Core - Análisis de las dependencias de terceros

El primer paso en el proceso de conversión es comprender las dependencias de terceros.  Debe averiguar cuáles de ellos, si los hay, todavía no se ejecuta en .NET Core y desarrollar un plan de contingencia para aquellos que no se ejecutan en .NET Core.

## <a name="prerequisites"></a>Requisitos previos

En este artículo se supone que usa Windows y Visual Studio, y que tiene un código que se ejecuta en .NET Framework.

## <a name="analyzing-nuget-packages"></a>Análisis de paquetes NuGet

Es muy fácil analizar los paquetes NuGet para la portabilidad.  Como un paquete NuGet es en sí mismo un conjunto de carpetas que contienen los ensamblados específicos de la plataforma, todo lo que tiene que hacer es comprobar si hay una carpeta que contiene un ensamblado de .NET Core.

La inspección de las carpetas de paquetes NuGet es mucho más sencillo con la herramienta [Explorador de paquetes NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer).  A continuación le mostramos cómo hacerlo.

1. Descargue y abra el Explorador de paquetes NuGet.
2. Haga clic en "Open package from online feed" (Abrir paquete de fuente en línea).
3. Busque el nombre del paquete.
4. Expanda la carpeta "lib" en la parte derecha y examine los nombres de carpeta.

También puede ver lo que admite un paquete en [nuget.org](https://www.nuget.org/) bajo la sección **Dependencias** de la página.

En cualquier caso, debe buscar una carpeta o una entrada en [nuget.org](https://www.nuget.org/) con cualquiera de los nombres siguientes:

```
netstandard1.0
netstandard1.1
netstandard1.2
netstandard1.3
netstandard1.4
netstandard1.5
netstandard1.6
netcoreapp1.0
portable-net45-win8
portable-win8-wpa8
portable-net451-win81
portable-net45-win8-wpa8-wpa81
```

Estos son los Moniker de la versión de .NET Framework de destino (TFM) que se asignan a las versiones de los perfiles del [estándar .NET](../../standard/net-standard.md) y de la Biblioteca de clases portables (PCL) que son compatibles con .NET Core.  Tenga en cuenta que `netcoreapp1.0`, mientras sea compatible, es para aplicaciones y no para bibliotecas.  Aunque no hay ningún problema con el uso de una biblioteca que está basada en `netcoreapp1.0`, dicha biblioteca solo está diseñada *para* el consumo por otras aplicaciones `netcoreapp1.0`.

También hay algunos TFM heredados utilizados en versiones preliminares de .NET Core que pueden ser compatibles:

```
dnxcore50
dotnet5.0
dotnet5.1
dotnet5.2
dotnet5.3
dotnet5.4
dotnet5.5
```

**Aunque es probable que estos funcionen con el código, no hay ninguna garantía de compatibilidad**.  Los paquetes con estos TFM se crearon con paquetes de .NET Core de versión preliminar.  Tome nota de cuando paquetes como estos se actualizan para estar basados en `netstandard`, y de si lo hacen.

> [!NOTE]
> Para utilizar un paquete destinado a una PCL tradicional o .NET Core de versión preliminar, debe usar la directiva `imports` en su archivo `project.json`.

### <a name="what-to-do-when-your-nuget-package-dependency-doesnt-run-on-net-core"></a>Qué hacer cuando su dependencia del paquete NuGet no se ejecuta en .NET Core

Hay algunas cosas que puede hacer si un paquete NuGet en el que depende no se ejecuta en .NET Core.

1. Si el proyecto es de código abierto y está hospedado en algún lugar como GitHub, puede implicar directamente a los programadores.
2. Póngase en contacto con el autor en [nuget.org](https://www.nuget.org/) buscando el paquete y haciendo clic en "Contact Owners" (Ponerse en contacto con los propietarios) a la izquierda de la página del paquete.
3. Puede buscar otro paquete que se ejecuta en .NET Core que realiza la misma tarea que el paquete que estaba utilizando.
4. Puede intentar volver a escribir el código de lo que hacía el paquete usted mismo.
5. Puede eliminar la dependencia en el paquete mediante el cambio de la funcionalidad de la aplicación, al menos hasta que esté disponible una versión compatible del paquete.

Recuerde que los responsables del mantenimiento del proyecto de código abierto y los editores de paquetes NuGet suelen ser voluntarios que contribuyen porque están al cuidado de dominio determinado, lo hacen de forma gratuita y a menudo tienen otro trabajo durante el día. Si accede a ellos, puede comenzar con una declaración positiva sobre la biblioteca antes de preguntarles sobre la compatibilidad de .NET Core.

Si no puede resolver el problema con las sugerencias anteriores, tendrá que realizar la portabilidad a .NET Core en otro momento.

El equipo de .NET le gustaría saber qué bibliotecas son las más importantes para que sean compatibles con .NET Core. También puede enviarnos un correo electrónico a dotnet@microsoft.com sobre las bibliotecas que le gustaría utilizar.

## <a name="analyzing-dependencies-which-arent-nuget-packages"></a>Análisis de dependencias que no son paquetes NuGet

Puede que tenga una dependencia que no sea un paquete NuGet, como un archivo DLL en el sistema de archivos.  La única manera de determinar la portabilidad de esa dependencia es ejecutar la [herramienta ApiPort](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).

## <a name="next-steps"></a>Pasos siguientes

Si está realizando la portabilidad de una biblioteca, consulte [Porting your Libraries](libraries.md) (Portabilidad de las bibliotecas).
