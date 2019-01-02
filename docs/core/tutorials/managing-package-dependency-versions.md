---
title: Cómo administrar las versiones de dependencias de paquete para .NET Core 1.0
description: Obtenga información sobre la administración de versiones de dependencias de paquete para aplicaciones y bibliotecas de .NET Core.
author: cartermp
ms.date: 06/20/2016
ms.custom: seodec18
ms.openlocfilehash: 7d7133ddb8717db1b830e531955454925c31a728
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168616"
---
# <a name="how-to-manage-package-dependency-versions-for-net-core-10"></a>Cómo administrar las versiones de dependencias de paquete para .NET Core 1.0

En este artículo se analiza lo que debe saber sobre las versiones de paquete para las bibliotecas y aplicaciones de .NET Core.

## <a name="glossary"></a>Glosario

**Corrección**: corregir las dependencias significa que usa la misma "familia" de paquetes lanzada en NuGet para .NET Core 1.0.

**Metapaquete**: un paquete NuGet que representa un conjunto de paquetes NuGet.

**Recorte**: acción de quitar de un metapaquete los paquetes de los cuales no depende.  Es importante para los creadores de paquetes NuGet.  Consulte [Reducción de dependencias de paquete con project.json](../deploying/reducing-dependencies.md) para más información. 

## <a name="fix-your-dependencies-to-net-core-10"></a>Corrección de las dependencias a .NET Core 1.0

Para restaurar de forma fiable los paquetes y escribir código confiable, es importante que corrija las dependencias a las versiones de los paquetes incluidos con .NET Core 1.0.  Esto significa que cada paquete debe tener una versión única sin calificadores adicionales.

**Ejemplos de paquetes corregidos a 1.0**

`"System.Collections":"4.0.11"`

`"NETStandard.Library":"1.6.0"`

`"Microsoft.NETCore.App":"1.0.0"`

**Ejemplos de paquetes NO corregidos a 1.0**

`"Microsoft.NETCore.App":"1.0.0-rc4-00454-00"`

`"System.Net.Http":"4.1.0-*"`

`"System.Text.RegularExpressions":"4.0.10-rc3-24021-00"`

### <a name="why-does-this-matter"></a>¿Por qué es importante?

Se garantiza que si se corrigen las dependencias del contenido que se distribuye con .NET Core 1.0, esos paquetes van a funcionar juntos. Dicha garantía no existe si usa paquetes no corregidos de esa manera.

### <a name="scenarios"></a>Escenarios

A pesar de que hay una gran lista de todos los paquetes y sus versiones lanzadas con .NET Core 1.0, puede que no sea necesario consultarla si el código que tiene se encuentra en ciertos escenarios.

**¿Depende solo de** `NETStandard.Library`**?**

Si es así, debe corregir el paquete `NETStandard.Library` a la versión `1.6`.  Como se trata de un metapaquete mantenido, la clausura de su paquete también se corrige a 1.0.

**¿Depende solo de** `Microsoft.NETCore.App`**?**

Si es así, debe corregir el paquete `Microsoft.NETCore.App` a la versión `1.0.0`.  Como se trata de un metapaquete mantenido, la clausura de su paquete también se corrige a 1.0.

**¿[Recorta](../deploying/reducing-dependencies.md) las dependencias del metapaquete** `NETStandard.Library` **o** `Microsoft.NETCore.App` **?**

Si es así, debe asegurarse de que el metapaquete con el que comienza esté corregido a 1.0.  Los paquetes individuales de los que depende después del recorte también se corrigen a 1.0.

**¿Depende de paquetes externos al metapaquete** `NETStandard.Library` **o** `Microsoft.NETCore.App` **?**

Si es así, debe corregir las otras dependencias a 1.0.  Consulte las versiones de paquete y los números de compilación correctos al final de este artículo.

### <a name="a-note-on-using-a-splat-string--when-versioning"></a>Nota sobre el uso de una cadena con asterisco (\*) cuando cree versiones

Puede que haya adoptado un patrón de creación de versiones que usa una cadena con asterisco (\*) como la siguiente: `"System.Collections":"4.0.11-*"`.

**No debe hacer esto**.  Si usa la cadena con asterisco podría restaurar paquetes de distintas compilaciones, algunas de las cuales podrían ir mucho más allá de .NET Core 1.0.  Esto podría hacer que algunos paquetes no sean compatibles.

## <a name="packages-and-version-numbers-organized-by-metapackage"></a>Número de versión y paquetes organizados por metapaquete

[Lista de todos los paquetes del estándar .NET y sus versiones para 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/corefx/release/1.0.0/Latest_Packages.txt).

[Lista de todos los paquetes de entorno de ejecución y sus versiones para 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/coreclr/release/1.0.0/LKG_Packages.txt).

[Lista de todos los paquetes de aplicaciones de .NET Core y sus versiones para 1.0](https://github.com/dotnet/versions/blob/master/build-info/dotnet/core-setup/release/1.0.0/Latest_Packages.txt).
