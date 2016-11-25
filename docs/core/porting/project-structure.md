---
title: "Organización del proyecto para admitir .NET Framework y .NET Core"
description: "Organización del proyecto para admitir .NET Framework y .NET Core"
keywords: .NET, .NET Core
author: conniey
manager: wpickett
ms.date: 07/18/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3af62252-1dfa-4336-8d2f-5cfdb57d7724
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 7a3f972debee1e90deda57e5604214ff4756da4a

---

# <a name="organizing-your-project-to-support-net-framework-and-net-core"></a>Organización del proyecto para admitir .NET Framework y .NET Core

Este artículo pretende ayudar a los propietarios del proyecto que desean compilar su solución en .NET Framework y en .NET Core, en paralelo.  Se proporcionan varias opciones para organizar los proyectos a fin de permitir que los desarrolladores alcancen este objetivo.  Los siguientes son algunos escenarios típicos que debe considerar cuando decida cómo va a configurar el diseño del proyecto con .NET Core.  Es posible que no abarquen todos los aspectos que desea, pero debe darles prioridad en función de las necesidades del proyecto.

* [**Combinar los proyectos existentes y los proyectos de .NET Core en proyectos únicos**][option-xproj]
  
  *Para qué se usa:*
  * Para simplificar el proceso de compilación mediante la compilación de un proyecto único en lugar de compilar varios proyectos, donde cada uno de ellos tiene como destino una plataforma o versión distinta de .NET Framework.
  * Para simplificar la administración de archivos de origen en proyectos con compatibilidad con múltiples versiones, porque debe administrar un solo archivo de proyecto.  Cuando agrega o quita archivos de origen, las alternativas requieren que los sincronice manualmente con los otros proyectos.
  * Para generar fácilmente un paquete NuGet para consumo.
  * Le permite escribir código para una versión específica de .NET Framework en las bibliotecas a través del uso de directivas de compilador.
  
  *Escenarios no admitidos:*
  * No se permite que los desarrolladores que no tienen Visual Studio 2015 abran los proyectos existentes. Para admitir versiones anteriores de Visual Studio, una opción mejor es [mantener los archivos de proyecto en distintas carpetas](#support-vs).
  * No se le permite compartir la biblioteca .NET Core en distintos tipos de proyecto dentro del mismo archivo de solución. Para admitir esto, una opción mejor es [crear una Biblioteca de clases portable](#support-pcl).
  * No se permite la compilación de proyecto o cargar modificaciones admitidas por tareas y destinos de MSBuild. Para admitir esto, una opción mejor es [crear una Biblioteca de clases portable](#support-pcl).

* <a name="support-vs"></a>[**Mantener separados los proyectos existentes y los proyectos de .NET Core nuevos**][option-xproj-folder]
  
  *Para qué se usa:*
  * Para mantener la compatibilidad con el desarrollo en proyectos existentes sin tener que hacer una actualización para los desarrolladores o colaboradores que posiblemente no tengan Visual Studio 2015.
  * Para disminuir la posibilidad de generar nuevos errores en proyectos existentes porque esos proyectos no requieren renovación de código.

* <a name="support-pcl"></a>[**Mantener los proyectos existentes y crear Bibliotecas de clases portables (PCL) que tienen a .NET Core como destino**][option-pcl]

  *Para qué se usa:*
  * Para hacer referencia a las bibliotecas .NET Core en proyectos web o de escritorio que tienen como destino la plataforma completa de .NET Framework en la misma solución.
  * Para admitir modificaciones en el proceso de carga o la compilación del proyecto. Estas modificaciones podrían ser la inclusión de tareas y destinos de MSBuild en el archivo `*.csproj`.

  *Escenarios no admitidos:*
  * No se le permite escribir código para una versión específica de .NET Framework, porque no se admiten los [símbolos predefinidos del preprocesador][how-to-multitarget].

## <a name="example"></a>Ejemplo

Considere el siguiente repositorio:

![Proyecto existente][example-initial-project]

[**Código fuente**][example-initial-project-code]

Hay varias formas distintas de agregar compatibilidad para .NET Core para este repositorio en función de las restricciones y la complejidad de los proyectos existentes, que se describen a continuación.

## <a name="replace-existing-projects-with-a-multi-targeted-net-core-project-xproj"></a>Reemplazo de proyectos existentes por un proyecto .NET Core con compatibilidad con múltiples versiones (xproj)

El repositorio se puede reorganizar de manera tal que se quita cualquier archivo `*.csproj` existente y se crea un archivo `*.xproj` único que establece varios marcos de trabajo como destino.  Esta es una opción excelente, porque un proyecto único se puede compilar para distintos marcos de trabajo.  También tiene la capacidad de controlar distintas dependencias, opciones de compilación, etc. por marco de trabajo de destino.

![Creación de un xproj con varios marcos de trabajo de destino][example-xproj]

[**Código fuente**][example-xproj-code]

Los cambios que debe tener en cuenta son los siguientes:
* Se agrega `global.json`
* `packages.config` y `*.csproj` se reemplazan por `project.json` y `*.xproj`
* Los cambios en el [archivo project.json de Car][example-xproj-projectjson] y su [proyecto de prueba][example-xproj-projectjson-test] para admitir la compilación del marco de trabajo .NET Framework existente, al igual que otros

## <a name="create-a-portable-class-library-pcl-to-target-net-core"></a>Creación de una Biblioteca de clases portable (PCL) con .NET Core como destino

Si los proyectos existentes contienen propiedades u operaciones de compilación complejas en el archivo `*.csproj`, puede resultar más fácil crear una PCL.

![][example-pcl]

[**Código fuente**][example-pcl-code]

Los cambios que debe tener en cuenta son los siguientes:
*  Cambiar el nombre de `project.json` a `{project-name}.project.json`
    * Esto evita cualquier conflicto potencial en Visual Studio cuando se intenta restaurar paquetes para las bibliotecas que se encuentran en el mismo directorio. Para más información, consulte las [preguntas más frecuentes sobre NuGet](https://docs.nuget.org/consume/nuget-faq#working-with-packages) en "_I have multiple projects in the same folder, how can I use separate packages.config or project.json files for each project?_" ("Tengo varios proyectos en la misma carpeta. ¿Cómo puedo usar archivos packages.config o project.json independientes para cada proyecto?").
    *  **Opción alternativa**. Para evitar este problema, puede crear la PCL en otra carpeta y hacer referencia al código fuente original.  Colocar la PCL en otra carpeta tiene una ventaja adicional: los usuarios que no tienen Visual Studio 2015 pueden seguir trabajando en los proyectos anteriores sin tener que cargar la solución nueva.
*  Para establecer el estándar .NET como destino después de crear la PCL, en Visual Studio, abra las **propiedades del proyecto**. En la sección de **destinos**, haga clic en el vínculo **"Usar como destino la plataforma del estándar .NET"**.  Puede revertir este cambio si repite los mismos pasos.

## <a name="keep-existing-projects-and-create-a-net-core-project"></a>Mantenimiento de los proyectos existentes y creación de un proyecto .NET Core

Si hay proyectos existentes que tienen como destino marcos de trabajo anteriores, puede que desee dejarlos intactos y usar un proyecto .NET Core para establecer como destino marcos de trabajo futuros.

![Proyecto .NET Core con PCL existente en una carpeta distinta][example-xproj-different-folder]

[**Código fuente**][example-xproj-different-code]

Los cambios que debe tener en cuenta son los siguientes:
* .NET Core y los proyectos existentes se mantienen en carpetas independientes.
    * Esto permite evitar el problema con la restauración de los paquetes que se mencionó anteriormente debido a que varios archivos project.json o package.config se encuentran en la misma carpeta.
    * Mantener los proyectos en carpetas independientes evita que sea necesario tener Visual Studio 2015 (debido al archivo project.json).  Puede crear una solución independiente que solo abra los proyectos anteriores.

## <a name="see-also"></a>Vea también

Consulte la [documentación sobre el traslado de .NET Core][porting-doc] para más orientación sobre cómo migrar los archivos project.json y xproj.

[porting-doc]: index.md
[example-initial-project]: media/project-structure/project.png "Proyecto existente"
[example-initial-project-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library/

[example-xproj]: media/project-structure/project.xproj.png "Creación de un xproj con varios marcos de trabajo de destino"
[example-xproj-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/
[example-xproj-projectjson]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/src/Car/project.json
[example-xproj-projectjson-test]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj/tests/Car.Tests/project.json

[example-xproj-different-folder]: media/project-structure/project.xproj.different.png "Proyecto .NET Core con PCL existente en una carpeta distinta"
[example-xproj-different-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-xproj-keep-csproj/

[example-pcl]: media/project-structure/project.pcl.png "PCL con .NET Core como destino"
[example-pcl-code]: https://github.com/dotnet/docs/tree/master/samples/framework/libraries/migrate-library-pcl

[option-xproj]: #replace-existing-projects-with-a-multi-targeted-net-core-project-xproj
[option-pcl]: #create-a-portable-class-library-pcl-to-target-net-core
[option-xproj-folder]: #keep-existing-projects-and-create-a-net-core-project

[how-to-multitarget]: ../tutorials/libraries.md#how-to-multitarget



<!--HONumber=Nov16_HO3-->


