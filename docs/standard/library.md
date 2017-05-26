---
title: .NET Standard | Microsoft Docs
description: "Aprenda qué es .NET Standard, sus versiones y las plataformas de .NET compatibles."
keywords: .NET Standard, PCL, .NET
author: richlander
ms.author: mairaw
ms.date: 03/17/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.translationtype: Machine Translation
ms.sourcegitcommit: a580e33f756bfb5eb96daeb9decb4acfe3ef2f52
ms.openlocfilehash: 970c70af2d8e5524e022f38d1ad93697a62985f8
ms.contentlocale: es-es
ms.lasthandoff: 05/11/2017

---

# <a name="net-standard"></a>Estándar .NET

[.NET Standard](https://github.com/dotnet/standard) es una especificación formal de las API de .NET que se prevé que estén disponibles en todos los entornos de tiempo de ejecución .NET. La finalidad de .NET Standard es establecer una mayor uniformidad en el ecosistema de .NET. [ECMA 335](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) sigue estableciendo uniformidad en el comportamiento del tiempo de ejecución de .NET, pero no hay ninguna especificación parecida para las bibliotecas de clases base (BCL) de .NET para implementaciones de la biblioteca de .NET. 

.NET Standard habilita los escenarios clave siguientes: 

- Define un conjunto uniforme de API de BCL para todas las plataformas de .NET que se van a implementar, independientemente de la carga de trabajo.
- Permite a los desarrolladores generar bibliotecas portátiles que se pueden usar en los tiempos de ejecución de .NET con este mismo conjunto de API.
- Reduce y se espera que elimine la compilación condicional de código fuente compartido debido a las API de .NET, solo para API de sistema operativo.

Los diversos entornos de tiempo de ejecución .NET implementan versiones concretas de .NET Standard. Cada versión del tiempo de ejecución de .NET anuncia la última versión del estándar de .NET que admite, indicación de que también es compatible con versiones anteriores. Por ejemplo, .NET Framework 4.6 implementa .NET Standard 1.3, lo que significa que expone todas las API definidas en las versiones de .NET Standard de 1.0 a 1.3. De forma similar, .NET Framework 4.6.1 implementa .NET Standard 1.5, mientras que .NET Core 1.0 implementa .NET Standard 1.6.

## <a name="net-platforms-support"></a>Compatibilidad con plataformas de .NET

En la tabla siguiente se enumeran todas las versiones de .NET Standard y las plataformas compatibles:

[!INCLUDE [net-standard-table](~/includes/net-standard-table.md)]

Para buscar la versión superior de .NET Standard que puede usar como destino, haga lo siguiente:
1. Busque la fila que indica la plataforma de .NET en la que quiere ejecutar.
2. Busque la columna de esa fila que indica la versión de derecha a izquierda.
3. El encabezado de columna indica la versión de .NET Standard que admite el destino (y las versiones de .NET Standard inferiores también lo admitirán).
4. Repita este proceso para cada plataforma a la que quiera dirigirse. Si tiene más de una plataforma de destino, debe elegir la versión más baja. Por ejemplo, si quiere ejecutar en .NET Framework 4.5 y .NET Core 1.0, la versión de .NET Standard más alta que puede usar es .NET Standard 1.1.

### <a name="which-net-standard-version-to-target"></a>Versión de .NET Standard de destino

Al elegir una versión de .NET Standard, debe tener en cuenta lo siguiente:

- Cuanto mayor sea la versión, más API tendrá disponibles.
- Cuanto menor sea la versión, más plataformas la implementarán.

En general, se recomienda elegir como destino la versión *menor* de .NET Standard posible. Así, después de buscar la versión de .NET Standard superior que puede elegir como destino, siga estos pasos:
1. Diríjase a la siguiente versión menor de .NET Standard y cree el proyecto.
2. Si el proyecto se crea correctamente, repita el paso 1. De lo contrario, vuelva a dirigirse a la siguiente versión mayor, que es la que debe usar.

### <a name="net-standard-versioning-rules"></a>Reglas de control de versiones de .NET Standard

Hay dos reglas de control de versiones principales:

- Adición: las versiones de .NET Standard son círculos lógicamente concéntricos: las versiones superiores incorporan todas las API de las versiones anteriores. No hay ningún cambio importante entre versiones.
- Inmutabilidad. Una vez publicadas, las versiones de .NET Standard se congelan. Las nuevas API primero están disponibles en plataformas de .NET concretas, como .NET Core. Si el consejo de revisión de .NET Standard cree que las nuevas API deben estar disponibles en todas las plataformas, se agregan en una nueva versión de .NET Standard.

## <a name="comparison-to-portable-class-libraries"></a>Comparación con las bibliotecas de clases portátiles

.NET Standard puede considerarse la siguiente generación de [bibliotecas de clases portables (PCL)](https://msdn.microsoft.com/library/gg597391.aspx). .NET Standard mejora la experiencia de creación de bibliotecas portátiles, ya que mantiene una BCL estándar y establece como resultado una mayor uniformidad en los entornos de tiempo de ejecución .NET. Una biblioteca que tiene como destino .NET Standard es una PCL o "PCL basada en .NET Standard". Las PCL existentes son "PCL basadas en perfiles".

.NET Standard y los perfiles de PCL se crearon con propósitos parecidos, pero también presentan algunas diferencias clave.

Similitudes:

- Definen las API que se pueden usar para compartir código binario.

Diferencias:

- .NET Standard es un conjunto mantenido de API, mientras que los perfiles de PCL se definen por las intersecciones de las plataformas existentes.
- .NET Standard tiene versiones lineales, al contrario de los perfiles de PCL.
- Los perfiles de PCL representan plataformas de Microsoft, mientras que .NET Standard es independiente de la plataforma.

## <a name="specification"></a>Especificación

La especificación de .NET Standard es un conjunto estandarizado de API. La especificación se mantiene mediante implementadores de tiempo de ejecución de .NET, específicamente Microsoft (que incluye .NET Framework, .NET Core y Mono) y Unity. Se usa un proceso de comentarios públicos como parte del establecimiento de las versiones nuevas de .NET Standard a través de [GitHub](https://github.com/dotnet/standard).

### <a name="official-artifacts"></a>Artefactos oficiales

La especificación oficial es un conjunto de archivos .cs que definen las API que forman parte del estándar. El [directorio de referencia](https://github.com/dotnet/corefx/tree/master/src/System.Runtime/ref) de cada [componente](https://github.com/dotnet/corefx/tree/master/src) define las API de .NET Standard. Aunque los artefactos de referencia residen en el [repositorio de CoreFX](https://github.com/dotnet/corefx), no son específicos de .NET Core.

El metapaquete [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) ([código fuente](https://github.com/dotnet/standard/blob/master/netstandard/pkg/NETStandard.Library.dependencies.props)) describe el conjunto de bibliotecas que definen (en parte) una o varias versiones de la biblioteca estándar de .NET.

Un componente determinado, como System.Runtime, describe lo siguiente:

- Parte de .NET Standard (solo su ámbito).
- Varias versiones de .NET Standard para ese ámbito.

Se proporcionan artefactos derivados para permitir una lectura más cómoda y habilitar ciertos escenarios de desarrollo (por ejemplo, el uso de un compilador).

- [Lista de API en Markdown](https://github.com/dotnet/standard/tree/master/docs/versions)
- Ensamblados de referencia, distribuidos como [paquetes NuGet](../core/packages.md) y a los que hace referencia el metapaquete [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/).

### <a name="package-representation"></a>Representación de paquetes

El principal vehículo de distribución de los ensamblados de referencia de .NET Standard son los [paquetes NuGet](../core/packages.md). Las implementaciones se entregarán de diversas formas, adecuadas para cada tiempo de ejecución de .NET.

Los paquetes NuGet tienen como destino uno o varios [marcos](frameworks.md). Los paquetes de .NET Standard tienen como destino el marco de trabajo ".NET Standard". Puede establecer como destino el marco de .NET Standard mediante el [TFM compacto](frameworks.md) `netstandard` (por ejemplo, `netstandard1.4`). Las bibliotecas diseñadas para ejecutarse en varios tiempos de ejecución deben tener como destino este marco. 

El metapaquete `NETStandard.Library` hace referencia al conjunto completo de paquetes NuGet que definen .NET Standard.  La manera más común de establecer como destino `netstandard` consiste en hacer referencia a este metapaquete. Describe y proporciona acceso a las aproximadamente 40 bibliotecas de .NET y las API asociadas que definen .NET Standard. Puede hacer referencia a paquetes adicionales que tienen como destino `netstandard` para obtener acceso a otras API. 

### <a name="versioning"></a>Control de versiones

La especificación no es única, sino que se trata de un conjunto de API con versiones lineales y con un crecimiento incremental. La primera versión del estándar establece un conjunto básico de API. Las versiones posteriores agregan API y heredan las API definidas por las versiones anteriores. No se ha establecido ninguna disposición para quitar API del estándar.

.NET Standard no es específico de ningún entorno de tiempo de ejecución .NET ni coincide con el esquema de control de versiones de ningún entorno de tiempo de ejecución.

Las API agregadas a cualquier tiempo de ejecución (por ejemplo, .NET Framework, .NET Core y Mono) pueden considerarse candidatas para agregarse a la especificación, sobre todo si se consideran fundamentales por su naturaleza. Las nuevas [versiones de .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md) se crean en función de las versiones del entorno de tiempo de ejecución .NET, lo que permite establecer como destino nuevas API desde una PCL de .NET Standard. Los mecanismos de control de versiones se describen con más detalle en [.NET Core Versioning](../core/versions/index.md) (Control de versiones de .NET Core).

El control de versiones de .NET Standard es importante para su uso. Dada una versión de .NET Standard, puede usar bibliotecas que tengan como destino esa misma versión o una inferior. En el enfoque siguiente se describe el flujo de trabajo para el uso de PCL de .NET Standard específicas para tener como destino .NET Standard.

- Seleccione una versión de .NET Standard para usarla para la PCL.
- Use bibliotecas que dependan de la misma versión de .NET Standard o de una inferior.
- Si encuentra una biblioteca que depende de una versión superior de .NET Standard, deberá adoptar la misma versión o bien optar por no usar esa biblioteca.

### <a name="pcl-compatibility"></a>Compatibilidad con PCL

.NET Standard es compatible con un subconjunto de perfiles de PCL. .NET Standard 1.0, 1.1 y 1.2 se superponen con un conjunto de perfiles de PCL. Esta superposición se ha creado por dos motivos:

- Habilitar las PCL basadas en .NET Standard para hacer referencia a PCL basadas en perfiles.
- Habilitar las PCL basadas en perfiles para empaquetarlas como PCL basadas en .NET Standard.

Se proporciona compatibilidad con PCL basada en perfiles mediante el paquete NuGet [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility). Esta dependencia es necesaria cuando se hace referencia a paquetes NuGet que contienen PCL basadas en perfiles.

Las PCL basadas en perfiles empaquetadas como `netstandard` son más fáciles de consumir que las PCL basadas en perfiles empaquetadas normalmente. El empaquetado de `netstandard` es compatible con los usuarios existentes.

Puede ver el conjunto de perfiles de PCL que son compatibles con .NET Standard: 

| Perfil de PCL | Estándar .NET | Plataformas de PCL
|:-----------:|:-------------:|------------------------------------------------------------------------------
| Profile7    | 1.1           | .NET Framework 4.5, Windows 8
| Profile31   | 1.0           | Windows 8.1, Windows Phone Silverlight 8.1
| Profile32   | 1.2           | Windows 8.1, Windows Phone 8.1
| Profile44   | 1.2           | .NET Framework 4.5.1, Windows 8.1
| Profile49   | 1.0           | .NET Framework 4.5, Windows Phone Silverlight 8
| Profile78   | 1.0           | .NET Framework 4.5, Windows 8, Windows Phone Silverlight 8
| Profile84   | 1.0           | Windows Phone 8.1, Windows Phone Silverlight 8.1
| Profile111  | 1.1           | .NET Framework 4.5, Windows 8, Windows Phone 8.1
| Profile151  | 1.2           | .NET Framework 4.5.1, Windows 8.1, Windows Phone 8.1
| Profile157  | 1.0           | Windows 8.1, Windows Phone 8.1, Windows Phone Silverlight 8.1
| Profile259  | 1.0           | .NET Framework 4.5, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8


## <a name="targeting-net-standard"></a>.NET Standard como destino

Puede [compilar bibliotecas estándar de .NET](../core/tutorials/libraries.md) mediante una combinación del marco `netstandard` y el metapaquete NETStandard.Library. Puede ver ejemplos de [.NET Standard como destino con herramientas de .NET Core](../core/packages.md).

## <a name="see-also"></a>Vea también
[Versiones de .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md)

