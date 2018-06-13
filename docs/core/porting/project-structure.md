---
title: Organización del proyecto para admitir .NET Framework y .NET Core
description: Ayuda para los propietarios del proyecto que quieren compilar su solución en .NET Framework y en .NET Core, en paralelo.
author: conniey
ms.author: mairaw
ms.date: 04/06/2017
ms.openlocfilehash: e6cd9c6d66996d9fd24fe71d48091723143e5849
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33211444"
---
# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a>Organización del proyecto para admitir .NET Framework y .NET Core

En este artículo se ofrece ayuda a los propietarios del proyecto que quieren compilar su solución en .NET Framework y en .NET Core, en paralelo. Se proporcionan varias opciones para organizar los proyectos a fin de permitir que los desarrolladores alcancen este objetivo. En la lista siguiente se proporcionan algunos escenarios típicos que debe considerar cuando decida cómo va a configurar el diseño del proyecto con .NET Core. Es posible que la lista no abarque todos los aspectos que quiere, pero debe darles prioridad en función de las necesidades del proyecto.

* [**Combinar los proyectos existentes y los proyectos de .NET Core en proyectos únicos**][option-csproj]

  *Para qué se usa:*
  * Para simplificar el proceso de compilación mediante la compilación de un proyecto único en lugar de compilar varios proyectos, donde cada uno de ellos tiene como destino una plataforma o versión distinta de .NET Framework.
  * Simplifique la administración de archivos de origen en proyectos con compatibilidad con múltiples versiones, porque debe administrar un solo archivo de proyecto. Cuando agrega o quita archivos de origen, las alternativas requieren que los sincronice manualmente con los otros proyectos.
  * Para generar fácilmente un paquete NuGet para consumo.
  * Le permite escribir código para una versión específica de .NET Framework en las bibliotecas a través del uso de directivas de compilador.

  *Escenarios no admitidos:*
  * Se necesita que los desarrolladores que usan Visual Studio 2017 abran los proyectos existentes. Para admitir versiones anteriores de Visual Studio, una opción mejor es [mantener los archivos de proyecto en distintas carpetas](#support-vs).

* <a name="support-vs"></a>[**Mantener separados los proyectos existentes y los proyectos de .NET Core nuevos**][option-csproj-folder]

  *Para qué se usa:*
  * Para mantener la compatibilidad con el desarrollo en proyectos existentes sin tener que hacer una actualización para los desarrolladores o colaboradores que posiblemente no tengan Visual Studio 2017.
  * Para disminuir la posibilidad de generar nuevos errores en proyectos existentes porque esos proyectos no requieren renovación de código.

## <a name="example"></a>Ejemplo

Considere el siguiente repositorio:

![Proyecto existente][example-initial-project]

[**Código fuente**][example-initial-project-code]

A continuación se describen varias formas de agregar compatibilidad para .NET Core para este repositorio en función de las restricciones y la complejidad de los proyectos existentes.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project"></a>Reemplazo de proyectos existentes por un proyecto .NET Core con compatibilidad con múltiples versiones

Reorganice el repositorio de manera que se quite cualquier archivo *\*.csproj* existente y se cree un archivo *\*.csproj* único que establezca varios marcos de trabajo como destino. Esta es una opción excelente, porque un proyecto único se puede compilar para distintos marcos de trabajo. También tiene la capacidad de controlar distintas dependencias y opciones de compilación por cada marco de trabajo de destino.

![Creación de un csproj con varios marcos de destino][example-csproj]

[**Código fuente**][example-csproj-code]

Los cambios que debe tener en cuenta son los siguientes:
* Reemplazo de *packages.config* y *\*.csproj* por un nuevo [.NET Core *\*.csproj*][example-csproj-netcore]. Los paquetes NuGet se especifican con `<PackageReference> ItemGroup`.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Mantenimiento de los proyectos existentes y creación de un proyecto .NET Core

Si hay proyectos existentes que tienen como destino marcos de trabajo anteriores, puede que desee dejarlos intactos y usar un proyecto .NET Core para establecer como destino marcos de trabajo futuros.

![Proyecto .NET Core con un proyecto existente en una carpeta distinta][example-csproj-different-folder]

[**Código fuente**][example-csproj-different-code]

Los cambios que debe tener en cuenta son los siguientes:
* .NET Core y los proyectos existentes se mantienen en carpetas independientes.
    * Mantener los proyectos en carpetas independientes evita que sea necesario tener Visual Studio 2017. Puede crear una solución independiente que solo abra los proyectos anteriores.

## <a name="see-also"></a>Vea también

Vea la [documentación sobre el traslado de .NET Core][porting-doc] para obtener más orientación sobre cómo migrar a .NET Core.

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Proyecto existente"
[example-initial-project-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library/

[example-csproj]: media/project-structure/project.csproj.png "Creación de un csproj con varios marcos de destino"
[example-csproj-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/
[example-csproj-netcore]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj/src/Car/Car.csproj

[example-csproj-different-folder]: media/project-structure/project.csproj.different.png "Proyecto .NET Core con PCL existente en una carpeta distinta"
[example-csproj-different-code]: https://github.com/dotnet/samples/tree/master/framework/libraries/migrate-library-csproj-keep-existing/

[option-csproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project
[option-csproj-folder]: #keep-existing-projects-and-create-a-net-core-project
