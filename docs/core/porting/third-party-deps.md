---
title: Análisis de las dependencias para trasladar código
description: Obtenga información sobre cómo analizar dependencias externas para trasladar el proyecto de .NET Framework a .NET.
author: cartermp
ms.date: 03/04/2021
ms.openlocfilehash: 4619243cf300e248be45e4b2a4d5541c3b3e1cb5
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604923"
---
# <a name="analyze-your-dependencies-to-port-code-from-net-framework-to-net"></a>Análisis de las dependencias para trasladar código de .NET Framework a .NET

Para trasladar el código a .NET o .NET Standard, debe comprender las dependencias. Las dependencias externas son los paquetes NuGet o archivos `.dll` a los que hace referencia en el proyecto, pero que no compila por su cuenta.

Al trasladar el código a .NET Standard 2.0 o una versión inferior, se garantiza que se puede usar con .NET Framework y .NET. Pero si no necesita usar la biblioteca con .NET Framework, considere la posibilidad de establecer como destino la versión más reciente de .NET.

## <a name="migrate-your-nuget-packages-to-packagereference"></a>Migración de los paquetes NuGet a `PackageReference`

.NET no puede usar el archivo [_packages.config_](/nuget/reference/packages-config) para las referencias de NuGet. Tanto .NET como .NET Framework pueden usar [PackageReference](/nuget/consume-packages/package-references-in-project-files) para especificar dependencias de paquetes. Si usa _packages.config_ para especificar los paquetes en el proyecto, debe convertirlo al formato `PackageReference`.

Para obtener información sobre cómo migrar, consulte el artículo [Migración de packages.config a PackageReference](/nuget/reference/migrate-packages-config-to-package-reference).

## <a name="upgrade-your-nuget-packages"></a>Actualización de los paquetes NuGet

Después de realizar la migración del proyecto al formato `PackageReference`, compruebe si los paquetes son compatibles con .NET.

En primer lugar, actualice los paquetes a la versión más reciente posible. Esto se puede realizar con la interfaz de usuario del administrador de paquetes NuGet en Visual Studio. Es probable que las versiones más recientes de las dependencias del paquete ya sean compatibles con .NET Core.

## <a name="analyze-your-package-dependencies"></a>Análisis de las dependencias de paquetes

Si aún no se ha comprobado que las dependencias de paquetes convertidas y actualizadas funcionan en .NET Core, hay varias formas de lograrlo:

### <a name="analyze-nuget-packages-using-nugetorg"></a>Analizar los paquetes NuGet mediante nuget.org

En la sección **Dependencias** de la página de un paquete de [nuget.org](https://www.nuget.org/) puede ver los moniker de la plataforma de destino (TFM) que admite cada paquete.

Aunque el uso del sitio es un método más sencillo para comprobar la compatibilidad, la información de las **Dependencias** no está disponible en el sitio para todos los paquetes.

### <a name="analyze-nuget-packages-using-nuget-package-explorer"></a>Analizar los paquetes NuGet con NuGet Package Explorer

Los paquetes NuGet son un conjunto de carpetas que contienen ensamblados específicos de plataforma, Compruebe si hay una carpeta que contenga un ensamblado compatible dentro del paquete.

La manera más fácil de inspeccionar las carpetas de paquetes NuGet consiste en usar la herramienta [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer). Después de instalarla, siga estos pasos para ver los nombres de las carpetas:

1. Abra NuGet Package Explorer.
2. Haga clic en **Open package from online feed** (Abrir paquete desde fuente en línea).
3. Busque el nombre del paquete.
4. Seleccione el nombre del paquete en los resultados de la búsqueda y haga clic en **Open** (Abrir).
5. Expanda la carpeta *lib* de la derecha y examine los nombres de las carpetas.

Busque una carpeta con nombres en los que se use uno de los patrones siguientes: `netstandardX.Y`, `netX.Y` o `netcoreappX.Y`.

Estos valores son los [monikers de la plataforma de destino (TFM)](../../standard/frameworks.md) que se asignan a versiones de [.NET Standard](../../standard/net-standard.md), .NET y .NET Core, todas compatibles con .NET.

> [!IMPORTANT]
> Al examinar los TFM que admite un paquete, tenga en cuenta que un TFM distinto de `netstandard*` se destina a una implementación concreta de .NET, como .NET 5, .NET Core o .NET Framework. A partir de .NET 5, el TFM `net*` (sin una designación de sistema operativo) reemplaza de manera efectiva a `netstandard*` como un [destino portátil](../../standard/net-standard.md#net-5-and-net-standard). Por ejemplo, `net5.0` tiene como destino la superficie de API de .NET 5 y es compatible con varias plataformas, pero `net5.0-windows` tiene como destino la superficie de API de .NET 5 como se ha implementado en el sistema operativo Windows.

## <a name="net-framework-compatibility-mode"></a>Modo de compatibilidad de .NET Framework

Después de analizar los paquetes NuGet, puede que observe que solo tienen como destino .NET Framework.

A partir de .NET Standard 2.0 se ha introducido el modo de compatibilidad de .NET Framework. Este modo de compatibilidad permite que los proyectos de .NET Standard y .NET Core hagan referencia a bibliotecas de .NET Framework. La acción de hacer referencias a bibliotecas de .NET Framework no funciona para todos los proyectos; por ejemplo, si la biblioteca usa API de Windows Presentation Foundation (WPF) pero desbloquea muchos escenarios de portabilidad.

Al hacer referencia a paquetes NuGet que tienen como destino .NET Framework en el proyecto, como [`Huitian.PowerCollections`](https://www.nuget.org/packages/Huitian.PowerCollections), recibirá una advertencia de reserva de paquete ([NU1701](/nuget/reference/errors-and-warnings/nu1701)) similar al ejemplo siguiente:

`NU1701: Package ‘Huitian.PowerCollections 1.0.0’ was restored using ‘.NETFramework,Version=v4.6.1’ instead of the project target framework ‘.NETStandard,Version=v2.0’. This package may not be fully compatible with your project.`

Esta advertencia se muestra cuando agrega el paquete y cada vez que compila para asegurarse de que prueba ese paquete con el proyecto. Si el proyecto funciona según lo previsto, puede suprimir la advertencia editando las propiedades del paquete en Visual Studio o editando manualmente el archivo del proyecto en su editor de código favorito.

Para suprimir la advertencia editando el archivo del proyecto, busque la entrada `PackageReference` del paquete del que quiere suprimir la advertencia y agregue el atributo `NoWarn`. El atributo `NoWarn` acepta una lista separada por comas de todos los identificadores de advertencia. En el ejemplo siguiente se muestra cómo suprimir la advertencia `NU1701` del paquete `Huitian.PowerCollections` editando manualmente el archivo del proyecto:

```xml
<ItemGroup>
  <PackageReference Include="Huitian.PowerCollections" Version="1.0.0" NoWarn="NU1701" />
</ItemGroup>
```

Para más información sobre cómo suprimir advertencias del compilador en Visual Studio, vea [Supresión de las advertencias para paquetes NuGet](/visualstudio/ide/how-to-suppress-compiler-warnings#suppress-warnings-for-nuget-packages).

## <a name="if-nuget-packages-wont-run-on-net"></a>Si los paquetes NuGet no se van a ejecutar en .NET

Si un paquete NuGet del que depende no se ejecuta en .NET Core, puede hacer lo siguiente:

- Si el proyecto es de código abierto y está hospedado en algún lugar como GitHub, puede implicar directamente a los desarrolladores.
- Puede ponerse en contacto directamente con el autor en [nuget.org](https://www.nuget.org/). Busque el paquete y haga clic en **Contact Owners** (Póngase en contacto con los propietarios) a la izquierda de la página del paquete.
- Puede buscar otro paquete que se ejecute en .NET Core que efectúe la misma tarea que el paquete que estaba usando.
- Puede intentar volver a escribir el código de lo que hacía el paquete usted mismo.
- Puede eliminar la dependencia en el paquete mediante el cambio de la funcionalidad de la aplicación, al menos hasta que esté disponible una versión compatible del paquete.

No olvide que los mantenedores de los proyectos de código abierto y los publicadores de paquetes NuGet suelen ser voluntarios. Colaboran porque les importa un dominio determinado, lo hacen de forma gratuita y en muchas ocasiones tienen otro trabajo, Sea consciente de ello al ponerse en contacto con ellos para solicitar soporte técnico de .NET Core.

Si no puede resolver el problema con ninguna de estas opciones, puede que deba efectuar la portabilidad a .NET Core en otro momento.

Al equipo de .NET le gustaría saber qué bibliotecas son las más importantes para que sean compatibles con .NET Core. Puede enviar un correo electrónico a dotnet@microsoft.com indicando las bibliotecas que le gustaría usar.

## <a name="analyze-non-nuget-dependencies"></a>Análisis de dependencias que no son de NuGet

Puede que tenga una dependencia que no sea un paquete NuGet, como un archivo DLL, en el sistema de archivos. La única manera de determinar la portabilidad de esa dependencia consiste en ejecutar la herramienta [.NET Portability Analyzer](https://github.com/Microsoft/dotnet-apiport). La herramienta analiza ensamblados que tienen como destino .NET Framework e identifica API que no se pueden portar a otras plataformas de .NET, como .NET Core. Puede ejecutar la herramienta como una aplicación de consola o como [extensión de Visual Studio](../../standard/analyzers/portability-analyzer.md).

## <a name="next-steps"></a>Pasos siguientes

- [Introducción a la portabilidad de .NET Framework a .NET](index.md)
- [Portabilidad de las bibliotecas](libraries.md)
