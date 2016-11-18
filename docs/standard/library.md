---
title: "Biblioteca estándar de .NET"
description: "Biblioteca estándar de .NET"
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
translationtype: Human Translation
ms.sourcegitcommit: f9ffbb2e300df2080276096095a7269736260ba1
ms.openlocfilehash: d56ddc264d861081f0b808711cccd489a374c0b8

---

# <a name="net-standard-library"></a>Biblioteca estándar de .NET

La biblioteca estándar .NET es una especificación formal de las API de .NET que están pensadas para estar disponibles en todos los entornos de ejecución de .NET. La finalidad de la biblioteca estándar consiste en establecer una mayor uniformidad en el ecosistema de .NET. [ECMA 335](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) sigue estableciendo uniformidad en el comportamiento del tiempo de ejecución de .NET, pero no hay ninguna especificación parecida para las bibliotecas de clases base (BCL) de .NET para implementaciones de la biblioteca de .NET. 

La biblioteca estándar de .NET permite los escenarios clave siguientes: 

- Define un conjunto uniforme de API de BCL para todas las plataformas de .NET que se van a implementar, independientemente de la carga de trabajo.
- Permite a los desarrolladores generar bibliotecas portátiles que se pueden usar en los tiempos de ejecución de .NET con este mismo conjunto de API.
- Reduce y se espera que elimine la compilación condicional de código fuente compartido debido a las API de .NET, solo para API de sistema operativo.

Los diversos tiempos de ejecución de .NET implementan versiones específicas de la biblioteca estándar de .NET. Cada versión del tiempo de ejecución de .NET anuncia la última versión del estándar de .NET que admite, indicación de que también es compatible con versiones anteriores. Por ejemplo, .NET Framework 4.6 implementa la biblioteca estándar de .NET 1.3, lo que significa que expone todas las API definidas en las versiones de la biblioteca estándar de .NET de 1.0 a 1.3. De forma similar, .NET Framework 4.6.2 implementa la biblioteca estándar de .NET 1.5, mientras que .NET Core 1.0 implementa la biblioteca estándar de .NET 1.6.

## <a name="net-platforms-support"></a>Compatibilidad con plataformas de .NET

Puede ver el conjunto completo de tiempos de ejecución de .NET que admiten la biblioteca estándar de .NET.

| Nombre de la plataforma | Alias |  |  |  |  |  | | | |
| :---------- | :--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |:--------- |
|Estándar .NET | netstandard | 1.0 | 1.1 | 1.2 | 1.3 | 1.4 | 1.5 | 1.6 | 2.0 |
|Núcleo de .NET|netcoreapp|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|1.0|vNext|
|.NET Framework|net|&rarr;|4.5|4.5.1|4.6|4.6.1|4.6.2|vNext|4.6.1|
|Plataformas Mono/Xamarin||&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|&rarr;|vNext|
|Plataforma universal de Windows|uap|&rarr;|&rarr;|&rarr;|&rarr;|10.0|&rarr;|&rarr;|vNext|
|Windows|win|&rarr;|8.0|8.1||||||
|Windows Phone|wpa|&rarr;|&rarr;|8.1||||||
|Windows Phone Silverlight|wp|8.0||||||||

## <a name="comparison-to-portable-class-libraries"></a>Comparación con las bibliotecas de clases portátiles

La biblioteca estándar de .NET puede considerarse la próxima generación de [bibliotecas de clases portátiles (PCL)](https://msdn.microsoft.com/library/gg597391.aspx). La biblioteca estándar de .NET mejora la experiencia de creación de bibliotecas portátiles, ya que mantiene una BCL estándar y establece como resultado una mayor uniformidad en los tiempos de ejecución de .NET. Una biblioteca que tiene como destino la biblioteca estándar de .NET es una PCL o "PCL basada en .NET Standard". Las PCL existentes son "PCL basadas en perfiles".

La biblioteca estándar de .NET y los perfiles de PCL se crearon con propósitos parecidos, pero también presentan algunas diferencias clave.

Similitudes:

- Definen las API que se pueden usar para compartir código binario.

Diferencias:

- La biblioteca estándar de .NET es un conjunto mantenido de API, mientras que los perfiles de PCL se definen por las intersecciones de las plataformas existentes.
- La biblioteca estándar de .NET tiene versiones lineales, al contrario de los perfiles de PCL.
- Los perfiles de PCL representan plataformas de Microsoft, mientras que la biblioteca estándar de .NET es independiente de la plataforma.

## <a name="specification"></a>Especificación

La especificación de la biblioteca estándar de .NET es un conjunto estandarizado de API. La especificación se mantiene mediante implementadores de tiempo de ejecución de .NET, específicamente Microsoft (que incluye .NET Framework, .NET Core y Mono) y Unity. Se usa un proceso de comentarios públicos como parte del establecimiento de las versiones nuevas de la biblioteca estándar de .NET.

### <a name="official-artifacts"></a>Artefactos oficiales

La especificación oficial es un conjunto de archivos .cs que definen las API que forman parte del estándar. El [directorio de referencia](https://github.com/dotnet/corefx/tree/master/src/System.Runtime/ref) de cada [componente](https://github.com/dotnet/corefx/tree/master/src) define las API de la biblioteca estándar de .NET. Aunque los artefactos de referencia residen en el [repositorio de CoreFX](https://github.com/dotnet/corefx), no son específicos de .NET Core.

El metapaquete [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) ([código fuente](https://github.com/dotnet/corefx/blob/master/pkg/NETStandard.Library/NETStandard.Library.packages.targets)) describe el conjunto de bibliotecas que definen (en parte) una o varias versiones de la biblioteca estándar de .NET.

Un componente determinado, como System.Runtime, describe lo siguiente:

- Parte de la biblioteca estándar de .NET (solo su ámbito).
- Varias versiones de la biblioteca estándar de .NET para ese ámbito.

Se proporcionan artefactos derivados para permitir una lectura más cómoda y habilitar ciertos escenarios de desarrollo (por ejemplo, el uso de un compilador).

- Lista de API en Markdown (por determinar)
- Ensamblados de referencia, distribuidos como [paquetes NuGet](../core/packages.md) y a los que hace referencia el metapaquete [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/).

### <a name="package-representation"></a>Representación de paquetes

El principal vehículo de distribución de los ensamblados de referencia de la biblioteca estándar de .NET son los [paquetes NuGet](../core/packages.md). Las implementaciones se entregarán de diversas formas, adecuadas para cada tiempo de ejecución de .NET.

Los paquetes NuGet tienen como destino uno o varios [marcos](frameworks.md). Los paquetes de la biblioteca estándar de .NET tienen como destino el marco ".NET Standard". Puede establecer como destino el marco de .NET Standard mediante el [TFM compacto](frameworks.md) `netstandard` (por ejemplo, `netstandard1.4`). Las bibliotecas diseñadas para ejecutarse en varios tiempos de ejecución deben tener como destino este marco. 

El metapaquete `NETStandard.Library` hace referencia al conjunto completo de paquetes NuGet que definen la biblioteca estándar de .NET.  La manera más común de establecer como destino `netstandard` consiste en hacer referencia a este metapaquete. Describe y proporciona acceso a las aproximadamente 40 bibliotecas de .NET y las API asociadas que definen la Biblioteca estándar de .NET. Puede hacer referencia a paquetes adicionales que tienen como destino `netstandard` para obtener acceso a otras API. 

### <a name="versioning"></a>Control de versiones

La especificación no es única, sino que se trata de un conjunto de API con versiones lineales y con un crecimiento incremental. La primera versión del estándar establece un conjunto básico de API. Las versiones posteriores agregan API y heredan las API definidas por las versiones anteriores. No se ha establecido ninguna disposición para quitar API del estándar.

La biblioteca estándar de .NET no es específica de ningún tiempo de ejecución de .NET ni coincide con el esquema de control de versiones de ningún tiempo de ejecución.

Las API agregadas a cualquier tiempo de ejecución (por ejemplo, .NET Framework, .NET Core y Mono) pueden considerarse candidatas para agregarse a la especificación, sobre todo si se consideran fundamentales por su naturaleza. Las nuevas [versiones de la biblioteca estándar de .NET](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/net-platform-standard.md#list-of-net-corefx-apis-and-their-associated-net-platform-standard-version) se crean basadas en las versiones del tiempo de ejecución de .NET, lo que permite establecer como destino nuevas API desde una PCL de .NET Standard. Los mecanismos de control de versiones se describen con más detalle en [.NET Core Versioning](../core/versions/index.md) (Control de versiones de .NET Core).

El control de versiones de la biblioteca estándar de .NET es importante para su uso. Dada una versión de la biblioteca estándar de .NET, puede usar bibliotecas que tengan como destino esa misma versión o una versión inferior. En el enfoque siguiente se describe el flujo de trabajo para el uso de PCL de la biblioteca estándar de .NET específicas para tener como destino la biblioteca estándar de .NET.

- Seleccione una versión de la biblioteca estándar de .NET que se usará para la PCL.
- Use bibliotecas que dependan de la misma versión de la biblioteca estándar de .NET o de una versión inferior.
- Si encuentra una biblioteca que depende de una versión superior de la biblioteca estándar de .NET, deberá adoptar la misma versión o bien decidir no usar dicha biblioteca.

### <a name="pcl-compatibility"></a>Compatibilidad con PCL

La biblioteca estándar de .NET es compatible con un subconjunto de perfiles de PCL. Las bibliotecas estándar de .NET 1.0, 1.1 y 1.2 se superponen con un conjunto de perfiles de PCL. Esta superposición se ha creado por dos motivos:

- Habilitar las PCL basadas en .NET Standard para hacer referencia a PCL basadas en perfiles.
- Habilitar las PCL basadas en perfiles para empaquetarlas como PCL basadas en .NET Standard.

Se proporciona compatibilidad con PCL basada en perfiles mediante el paquete NuGet [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility). Esta dependencia es necesaria cuando se hace referencia a paquetes NuGet que contienen PCL basadas en perfiles.

Las PCL basadas en perfiles empaquetadas como `netstandard` son más fáciles de consumir que las PCL basadas en perfiles empaquetadas normalmente en project.json. El empaquetado de `netstandard` es compatible con los usuarios existentes.

Puede ver el conjunto de perfiles de PCL que son compatibles con .NET Standard: 

| Perfil | Versión estándar de la plataforma .NET |
| ---------| --------------- |
| Subconjunto portátil de .NET Profile7 (.NET Framework 4.5, Windows 8) | 1.1 |
| Subconjunto portátil de .NET Profile31 (Windows 8.1, Windows Phone Silverlight 8.1)| 1.0 |
| Subconjunto portátil de .NET Profile32 (Windows 8.1, Windows Phone 8.1) | 1.2 |
| Subconjunto portátil de .NET Profile44 (.NET Framework 4.5.1, Windows 8.1) | 1.2 |
| Subconjunto portátil de .NET Profile49 (.NET Framework 4.5, Windows Phone Silverlight 8) | 1.0 |
| Subconjunto portátil de .NET Profile78 (.NET Framework 4.5, Windows 8, Windows Phone Silverlight 8) | 1.0 |
| Subconjunto portátil de .NET Profile84 (Windows Phone 8.1, Windows Phone Silverlight 8.1) | 1.0 |
| Subconjunto portátil de .NET Profile111 (.NET Framework 4.5, Windows 8, Windows Phone 8.1) | 1.1 |
| Subconjunto portátil de .NET Profile151 (.NET Framework 4.5.1, Windows 8.1, Windows Phone 8.1) | 1.2 |
| Subconjunto portátil de .NET Profile157 (Windows 8.1, Windows Phone 8.1, Windows Phone Silverlight 8.1) | 1.0 |
| Subconjunto portátil de .NET Profile259 (.NET Framework 4.5, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8) | 1.0 |

## <a name="targeting-net-standard-library"></a>Establecer como destino la biblioteca estándar de .NET

Puede [compilar bibliotecas estándar de .NET](../core/tutorials/libraries.md) mediante una combinación del marco `netstandard` y el metapaquete NETStandard.Library. Puede ver ejemplos de cómo [establecer como destino la biblioteca estándar de .NET con herramientas de .NET Core](../core/packages.md).



<!--HONumber=Nov16_HO3-->


