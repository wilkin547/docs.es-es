---
title: "Migración de .NET Core al formato csproj"
description: "Migración de project.json de .NET Core a csproj"
keywords: ".NET, .NET Core, migración de .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 07/19/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 1feadf3d-3cfc-41dd-abb5-a4fc303a7b53
ms.openlocfilehash: 1d972489536e929c8694bd6a4cab31c9f2d624a8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="migrating-net-core-projects-to-the-csproj-format"></a>Migración de proyectos de .NET Core al formato .csproj

En este documento se tratarán los escenarios de migración para los proyectos de .NET Core y se repasarán los tres siguientes escenarios de migración:

1. [Migración desde un esquema válido más reciente de *project.json* a *csproj*](#migration-from-projectjson-to-csproj)
2. [Migración desde DNX a csproj](#migration-from-dnx-to-csproj)
3. [Migración desde proyectos de csproj de .NET Core RC3 y anteriores al formato final](#migration-from-earlier-net-core-csproj-formats-to-rtm-csproj)

## <a name="migration-from-projectjson-to-csproj"></a>Migración desde project.json a csproj
La migración desde *project.json* a *.csproj* puede realizarse mediante uno de los métodos siguientes:

- [Visual Studio 2017](#visual-studio-2017)
- [Herramienta de línea de comandos dotnet migrate](#dotnet-migrate)
 
Ambos métodos usan el mismo motor subyacente para migrar los proyectos, por lo que los resultados serán los mismos para ambos. En la mayoría de los casos, tan solo será necesario usar una de estas dos formas de migrar *project.json* a *csproj*, y no se requerirá ninguna otra edición manual del archivo del proyecto. El archivo *.csproj* resultante tendrá el mismo nombre que el directorio que lo contiene.

### <a name="visual-studio-2017"></a>Visual Studio 2017

Cuando se abre un archivo *.xproj* o un archivo de solución que hace referencia a archivos *.xproj*, aparece el cuadro de diálogo **Actualización unidireccional**. El cuadro de diálogo muestra los proyectos que se van a migrar. Si se abre un archivo de solución, se enumerarán todos los proyectos especificados en el archivo de solución. Revise la lista de proyectos que se van a migrar y haga clic en **Aceptar**.

![Cuadro de diálogo Actualización unidireccional con la lista de proyectos que se van a migrar](media/one-way-upgrade.jpg)

Visual Studio migrará automáticamente los proyectos seleccionados. Al migrar una solución, si no elige todos los proyectos, aparecerá el mismo cuadro de diálogo preguntando si quiere actualizar los proyectos restantes de esa solución. Después de migrar el proyecto, puede ver y modificar su contenido. Para ello, haga clic con el botón derecho en el proyecto en la ventana del **Explorador de soluciones** y seleccione **Editar \<nombre del proyecto>.csproj**.

Los archivos que se migraron (*project.json*, *global.json*, *.xproj* y el archivo de solución) se moverán a una carpeta *Copia de seguridad*. El archivo de solución que se migra se actualizará a Visual Studio 2017 y no se podrá abrir en versiones anteriores de Visual Studio. También se guarda y se abre automáticamente un archivo denominado *UpgradeLog.htm* que contiene un informe de migración.

> [!IMPORTANT]
> Las nuevas herramientas no están disponibles en Visual Studio 2015, por lo que no puede migrar los proyectos mediante esa versión de Visual Studio.

### <a name="dotnet-migrate"></a>dotnet migrate

En el escenario de la línea de comandos, puede usar el comando [`dotnet migrate`](../tools/dotnet-migrate.md). Se migrará un proyecto, una solución o un conjunto de carpetas, en ese orden, dependiendo de lo que se encuentre. Cuando se migra un proyecto, se migra el proyecto y todas sus dependencias.

Los archivos que se migraron (*project.json*, *global.json* y *.xproj*) se moverán a una carpeta *Copia de seguridad*.

> [!NOTE]
> Si se usa Visual Studio Code, el comando `dotnet migrate` no modificará archivos específicos de Visual Studio Code, como `tasks.json`. Estos archivos deben modificarse de forma manual. Esto también sucede si se usa Project Ryder o cualquier editor o entorno de desarrollo integrado (IDE) que no sea Visual Studio. 

Consulte [Una asignación entre propiedades project.json y csproj](../tools/project-json-to-csproj.md) para una comparación de los formatos project.json y csproj.

### <a name="common-issues"></a>Problemas comunes

- Si se produce un error: "No se encuentra ningún archivo que coincida con el comando dotnet-migrate":

Ejecute `dotnet --version` para ver qué versión está usando. [`dotnet migrate`](../tools/dotnet-migrate.md) requiere .NET Core CLI RC3 o superior.
Obtendrá este error si tiene un archivo *global.json* en el directorio actual o principal y la versión de `sdk` está establecida en una versión anterior.

## <a name="migration-from-dnx-to-csproj"></a>Migración desde DNX a csproj
Si aún usa DNX para el desarrollo de .NET Core, el proceso de migración debe realizarse en dos fases:

1. Use la [guía de migración de DNX existente](from-dnx.md) para migrar desde DNX a la CLI compatible con project.json.
2. Siga los pasos de la sección anterior para migrar desde *project.json* a *.csproj*.  

> [!NOTE]
> DNX quedó oficialmente en desuso durante la versión Preview 1 de la CLI de .NET Core. 

## <a name="migration-from-earlier-net-core-csproj-formats-to-rtm-csproj"></a>Migración desde formatos anteriores de csproj de .NET Core a csproj RTM
El formato de csproj de .NET Core ha cambiado y evolucionado con cada nueva versión preliminar de las herramientas. No hay ninguna herramienta que migre el archivo del proyecto de versiones anteriores de csproj a la versión más reciente, por lo que tendrá que editar manualmente el archivo del proyecto. Los pasos reales dependen de la versión del archivo del proyecto que se va a migrar. Tenga en cuenta los siguientes consejos basados en los cambios que se produjeron entre las versiones:

* Quite la propiedad de versión de las herramientas del elemento `<Project>`, si existe. 
* Quite el espacio de nombres XML (`xmlns`) del elemento `<Project>`.
* Si no existe, agregue el atributo `Sdk` al elemento `<Project>` y establézcalo en `Microsoft.NET.Sdk` o `Microsoft.NET.Sdk.Web`. Este atributo especifica que el proyecto usa el SDK que se va a usar. `Microsoft.NET.Sdk.Web` se usa para las aplicaciones web.
* Quite las instrucciones `<Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />` e `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` de la parte superior e inferior del proyecto. Estas instrucciones de importación están implícitas en el SDK, por lo que no es necesario que estén en el proyecto. 
* Si tiene elementos `Microsoft.NETCore.App` o `NETStandard.Library` `<PackageReference>` en el proyecto, debe quitarlos. Estas referencias de paquete son [implícitas para el SDK ](https://aka.ms/sdkimplicitrefs). 
* Quite el elemento `Microsoft.NET.Sdk` `<PackageReference>`, si existe. La referencia del SDK procede del atributo `Sdk` del elemento `<Project>`. 
* Quite los [globs](https://en.wikipedia.org/wiki/Glob_(programming)) que están [implícitos en el SDK](../tools/csproj.md#default-compilation-includes-in-net-core-projects). Dejar estos patrones globales en el proyecto producirá un error de compilación porque se duplicarán los elementos de compilación. 

Tras seguir estos pasos, el proyecto debe ser totalmente compatible con el formato csproj RTM de .NET Core. 

Para obtener ejemplos de antes y después de la migración desde el formato csproj antiguo al nuevo, vea el artículo [Updating Visual Studio 2017 RC – .NET Core Tooling improvements](https://blogs.msdn.microsoft.com/dotnet/2016/12/12/updating-visual-studio-2017-rc-net-core-tooling-improvements/) (Actualización de Visual Studio 2017 RC: Mejoras de las herramientas de .NET Core) en el blog de .NET.

## <a name="see-also"></a>Vea también
[Portar, migrar y actualizar proyectos de Visual Studio](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects)
