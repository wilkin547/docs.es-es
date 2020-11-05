---
title: Dependencias y bibliotecas de .NET
description: Procedimientos recomendados para administrar las dependencias de NuGet en las bibliotecas de. NET.
ms.date: 10/02/2018
ms.openlocfilehash: d189a3364b501272e29de72b6018844877bf2128
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93189308"
---
# <a name="dependencies"></a>Dependencias

La principal manera de agregar dependencias a una biblioteca de .NET es hacer referencia a paquetes NuGet. Las referencias de los paquetes NuGet permiten reutilizar y aprovechar rápidamente la funcionalidad ya escrita, pero son una fuente común de problemas para los desarrolladores. NET. La administración correcta de las dependencias es importante para evitar que los cambios en otras bibliotecas de .NET interrumpan la biblioteca de .NET y viceversa.

## <a name="diamond-dependencies"></a>Dependencias de rombo

Es una situación común para un proyecto de .NET tener varias versiones de un paquete en el árbol de dependencias. Por ejemplo, una aplicación depende de dos paquetes NuGet, cada uno de los cuales depende de las diferentes versiones del mismo paquete. Ahora existe una dependencia de rombo en el gráfico de dependencias de la aplicación.

![Dependencias de rombo](./media/dependencies/diamond-dependency.png "Dependencias de rombo")

En el momento de la compilación, NuGet analiza todos los paquetes de los que depende un proyecto, incluidas las dependencias de dependencias. Cuando se detectan varias versiones de un paquete, se evalúan las reglas para elegir una. La unificación de paquetes es necesaria porque la ejecutan de versiones en paralelo de un ensamblado en la misma aplicación es problemática en. NET.

La mayoría de las dependencias de rombo se resuelven con facilidad; sin embargo, pueden crear problemas en determinadas circunstancias:

- **Las referencias de paquetes NuGet en conflicto** impiden que una versión se resuelva durante la restauración de paquetes.
- **Los cambios importantes entre las versiones** provocan errores y excepciones en tiempo de ejecución.
- **El ensamblado del paquete tiene un nombre seguro** , la versión del ensamblado ha cambiado y la aplicación se ejecuta en .NET Framework. Se necesitan redirecciones de enlace de ensamblados.

No es posible saber qué paquetes se utilizarán junto con los suyos. Una buena forma de reducir la probabilidad de que una dependencia de rombo interrumpa la biblioteca es minimizar el número de paquetes de los que usted depende.

✔️ REVISE la biblioteca de .NET en busca de dependencias innecesarias.

## <a name="nuget-dependency-version-ranges"></a>Intervalos de versiones de dependencia de NuGet

Una referencia de paquete especifica el intervalo de paquetes válidos que permite. Normalmente, la versión de referencia de paquete del archivo de proyecto es la versión mínima y no hay una máxima.

```xml
<!-- Accepts any version 1.0 and above. -->
<PackageReference Include="ExamplePackage" Version="1.0" />
```

Las reglas que NuGet usa al resolver dependencias son [complejas](/nuget/consume-packages/dependency-resolution), pero NuGet busca [de forma predeterminada](/nuget/consume-packages/install-use-packages-visual-studio#install-and-update-options) la versión aplicable más baja. NuGet prefiere la versión más baja aplicable en lugar de usar la más alta disponible porque la más baja tendrá los menores problemas de compatibilidad.

Debido a la regla de versión más baja aplicable de NuGet, no es necesario colocar una versión superior o un intervalo exacto en referencias de paquete para evitar la obtención de la versión más reciente. NuGet ya intenta encontrar la versión más compatible y más baja automáticamente.

```xml
<!-- Accepts 1.0 up to 1.x, but not 2.0 and higher. -->
<PackageReference Include="ExamplePackage" Version="[1.0,2.0)" />

<!-- Accepts exactly 1.0. -->
<PackageReference Include="ExamplePackage" Version="[1.0]" />
```

Los límites de versión superiores provocarán que NuGet genere un error si hay un conflicto. Por ejemplo, una biblioteca acepta exactamente la versión 1.0 mientras otra biblioteca requiere la versión 2.0 o una superior. Aunque se pueden haber introducido cambios importantes en la versión 2.0, una dependencia de versión con límite superior o estricta garantiza un error.

![Conflicto de dependencias de rombo](./media/dependencies/diamond-dependency-conflict.png "Conflicto de dependencias de rombo")

❌ NO tenga referencias de paquetes NuGet sin versión mínima.

❌ EVITE las referencias de paquetes NuGet que exijan una versión exacta.

❌ EVITE las referencias de paquetes NuGet con un límite superior de versión.

## <a name="nuget-shared-source-packages"></a>Paquetes NuGet de código fuente compartido

Una forma de reducir las dependencias externas de los paquetes NuGet es hacer referencia a paquetes de código fuente compartido. Un paquete de código fuente compartido contiene [archivos de código fuente](/nuget/reference/nuspec#including-content-files) que se incluyen en un proyecto al que hace referencia. Dado que solo se incluyen los archivos de código fuente que se compilan con el resto del proyecto, no hay ninguna dependencia externa ni posibilidad de conflicto.

Los paquetes de código fuente compartido son excelentes para incluir pequeños fragmentos de funcionalidad. Por ejemplo, un paquete de código fuente compartido de los métodos auxiliares para llamadas HTTP.

![Paquete de código fuente compartido](./media/dependencies/shared-source-package.png "Paquete de código fuente compartido")

```xml
<PackageReference Include="Microsoft.Extensions.Buffers.Testing.Sources" PrivateAssets="All" Version="1.0" />
```

![Proyecto de código fuente compartido](./media/dependencies/shared-source-project.png "Proyecto de código fuente compartido")

Los paquetes de código fuente compartido tienen algunas limitaciones. Solo `PackageReference` puede hacer referencia a ellos, por lo que los proyectos `packages.config` más antiguos se excluyen. Asimismo, los paquetes de código fuente compartido solo resultan útiles para los proyectos con el mismo tipo de lenguaje. Debido a estas limitaciones, los paquetes de código fuente compartido son útiles para compartir la funcionalidad dentro de un proyecto de código abierto.

✔️ ES RECOMENDABLE hacer referencia a paquetes de código fuente compartido para partes internas pequeñas de funcionalidad.

✔️ ES RECOMENDABLE convertir el paquete en un paquete de código fuente compartido si proporciona partes internas pequeñas de funcionalidad.

✔️ HAGA REFERENCIA a paquetes de código fuente compartido con `PrivateAssets="All"`.

> Esta opción indica a NuGet que el paquete solamente se debe usar en tiempo de desarrollo y no se debe exponer como una dependencia pública.

❌ NO tenga tipos de paquete de código fuente compartido en la API pública.

> Los tipos de código fuente compartido se compilan en el ensamblado de referencia y no se pueden intercambiar entre límites de ensamblado. Por ejemplo, un tipo `IRepository` de código fuente compartido en un proyecto es un tipo independiente del mismo `IRepository` de código fuente compartido en otro proyecto. Los tipos de paquetes de código fuente compartido deben tener una visibilidad `internal`.

❌ NO publique paquetes de código fuente compartido en NuGet.org.

> Los paquetes de código fuente compartido contienen código fuente y solo los pueden usar los proyectos con el mismo tipo de lenguaje. Por ejemplo, una aplicación de F# no puede usar el paquete de código fuente compartido de C#.
>
> Publique paquetes de código fuente compartido en una [fuente local o MyGet](./publish-nuget-package.md) para usarlos de forma interna en el proyecto.

>[!div class="step-by-step"]
>[Anterior](nuget.md)
>[Siguiente](sourcelink.md)
