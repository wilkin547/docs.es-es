---
title: Migración de .NET Core desde project.json
description: Aprenda a migrar un proyecto anterior de .NET Core con project.json.
ms.date: 07/19/2017
ms.openlocfilehash: 8a9dc05c82fd5476a70ee36a294a287abbfb68c4
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450692"
---
# <a name="migrating-net-core-projects-from-projectjson"></a>Migración de proyectos de .NET Core desde project.json

En este documento se tratan los tres escenarios de migración siguientes para los proyectos de .NET Core:

1. [Migración desde un esquema válido más reciente de *project.json* a *csproj*](#migration-from-projectjson-to-csproj)
2. [Migración desde DNX a csproj](#migration-from-dnx-to-csproj)
3. [Migración desde proyectos de csproj de .NET Core RC3 y anteriores al formato final](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

Este documento solo es aplicable a proyectos antiguos de .NET Core que usan project.json. No se aplica a la migración de .NET Framework a .NET Core.

## <a name="migration-from-projectjson-to-csproj"></a>Migración desde project.json a csproj

La migración desde *project.json* a *.csproj* puede realizarse mediante uno de los métodos siguientes:

- [Visual Studio](#visual-studio)
- [Herramienta de línea de comandos dotnet migrate](#dotnet-migrate)

Ambos métodos usan el mismo motor subyacente para migrar los proyectos, por lo que los resultados serán los mismos para ambos. En la mayoría de los casos, tan solo será necesario usar una de estas dos formas de migrar *project.json* a *csproj*, y no se requerirá ninguna otra edición manual del archivo del proyecto. El archivo *.csproj* resultante tendrá el mismo nombre que el directorio que lo contiene.

### <a name="visual-studio"></a>Programa para la mejora

Al abrir un archivo *.xproj* o un archivo de solución que hace referencia a archivos *.xproj* en Visual Studio 2017 o Visual Studio 2019, versión 16.2 y versiones anteriores, se abre el cuadro de diálogo **Actualización unidireccional**. El cuadro de diálogo muestra los proyectos que se van a migrar. Si se abre un archivo de solución, se enumeran todos los proyectos especificados en el archivo de solución. Revise la lista de proyectos que se van a migrar y haga clic en **Aceptar**.

![Cuadro de diálogo Actualización unidireccional con la lista de proyectos que se van a migrar](media/one-way-upgrade.jpg)

Visual Studio migra automáticamente los proyectos seleccionados. Al migrar una solución, si no elige todos los proyectos, aparece el mismo cuadro de diálogo preguntando si quiere actualizar los proyectos restantes de esa solución. Después de migrar el proyecto, puede ver y modificar su contenido. Para ello, haga clic con el botón derecho en el proyecto en la ventana del **Explorador de soluciones** y seleccione **Editar \<nombre del proyecto>.csproj**.

Los archivos que se migraron (*project.json*, *global.json*, *.xproj* y el archivo de solución) se mueven a una carpeta *Copia de seguridad*. El archivo de solución migrado se actualiza a Visual Studio 2017 o Visual Studio 2019 y no podrá abrir ese archivo de solución en Visual Studio 2015 ni en versiones anteriores. También se guarda y se abre automáticamente un archivo denominado *UpgradeLog.htm* que contiene un informe de migración.

> [!IMPORTANT]
> En la versión 16.3 de Visual Studio 2019 y versiones posteriores, no se puede cargar ni migrar un archivo *.xproj* . Además, Visual Studio 2015 no permite migrar un archivo *.xproj*. Si utiliza una de estas versiones de Visual Studio, instale una versión adecuada de Visual Studio o use la herramienta de migración de la línea de comandos que se indica a continuación.

### <a name="dotnet-migrate"></a>dotnet migrate

En el escenario de la línea de comandos, puede usar el comando [`dotnet migrate`](../tools/dotnet-migrate.md). Se migra un proyecto, una solución o un conjunto de carpetas, en ese orden, dependiendo de lo que se encuentre. Cuando se migra un proyecto, se migra el proyecto y todas sus dependencias.

Los archivos que se migraron (*project.json*, *global.json* y *.xproj*) se mueven a una carpeta *Copia de seguridad*.

> [!NOTE]
> Si se usa Visual Studio Code, el comando `dotnet migrate` no modifica archivos específicos de Visual Studio Code, como *tasks.json*. Estos archivos deben modificarse de forma manual.
> Esto también sucede si se usa cualquier editor o entorno de desarrollo integrado (IDE) que no sea Visual Studio.

Consulte [Una asignación entre propiedades project.json y csproj](../tools/project-json-to-csproj.md) para una comparación de los formatos *project.json* y *.csproj*.

Si se produce un error que indica que

> no se encuentra ningún archivo que coincida con el comando dotnet-migrate,

Ejecute `dotnet --version` para ver qué versión está usando. [`dotnet migrate`](../tools/dotnet-migrate.md) se presentó en la versión 1.0.0 del SDK de .NET Core y se quitó en la versión 3.0.100.
Obtendrá este error si tiene un archivo *global.json* en el directorio actual o principal y la versión de `sdk` que especifica está fuera de este rango.

## <a name="migration-from-dnx-to-csproj"></a>Migración desde DNX a csproj

Si aún usa DNX para el desarrollo de .NET Core, el proceso de migración debe realizarse en dos fases:

1. Use la [guía de migración de DNX existente](from-dnx.md) para migrar desde DNX a la CLI compatible con project.json.
2. Siga los pasos de la sección anterior para migrar desde *project.json* a *.csproj*.

> [!NOTE]
> DNX quedó oficialmente en desuso durante la versión Preview 1 de la CLI de .NET Core.

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a>Migración desde formatos anteriores de csproj de .NET Core a csproj RTM

El formato de csproj de .NET Core ha cambiado y evolucionado con cada nueva versión preliminar de las herramientas. No hay ninguna herramienta que migre el archivo del proyecto de versiones anteriores de csproj a la versión más reciente, por lo que tendrá que editar manualmente el archivo del proyecto. Los pasos reales dependen de la versión del archivo del proyecto que se va a migrar. Tenga en cuenta los siguientes consejos basados en los cambios que se produjeron entre las versiones:

- Quite la propiedad de versión de las herramientas del elemento `<Project>`, si existe.
- Quite el espacio de nombres XML (`xmlns`) del elemento `<Project>`.
- Si no existe, agregue el atributo `Sdk` al elemento `<Project>` y establézcalo en `Microsoft.NET.Sdk` o `Microsoft.NET.Sdk.Web`. Este atributo especifica que el proyecto usa el SDK que se va a usar. `Microsoft.NET.Sdk.Web` se usa para las aplicaciones web.
- Quite las instrucciones `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` e `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` de la parte superior e inferior del proyecto. Estas instrucciones de importación están implícitas en el SDK, por lo que no es necesario que estén en el proyecto.
- Si tiene elementos `Microsoft.NETCore.App` o `NETStandard.Library` `<PackageReference>` en el proyecto, debe quitarlos. Estas referencias de paquete son [implícitas para el SDK ](https://aka.ms/sdkimplicitrefs).
- Quite el elemento `Microsoft.NET.Sdk` `<PackageReference>`, si existe. La referencia del SDK procede del atributo `Sdk` del elemento `<Project>`.
- Quite los [globs](https://en.wikipedia.org/wiki/Glob_(programming)) que están [implícitos en el SDK](../project-sdk/overview.md#default-compilation-includes). Dejar estos patrones globales en el proyecto producirá un error de compilación porque se duplicarán los elementos de compilación.

Tras seguir estos pasos, el proyecto debe ser totalmente compatible con el formato csproj RTM de .NET Core.

Para obtener ejemplos de antes y después de la migración desde el formato csproj antiguo al nuevo, vea el artículo [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://devblogs.microsoft.com/dotnet/updating-visual-studio-2017-rc-net-core-tooling-improvements/) (Actualización de Visual Studio 2017 RC: Mejoras de las herramientas de .NET Core) en el blog de .NET.

## <a name="see-also"></a>Vea también

- [Portar, migrar y actualizar proyectos de Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
