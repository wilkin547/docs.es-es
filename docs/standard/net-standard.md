---
title: .NET Standard
description: Obtenga información sobre .NET Standard, sus versiones y las implementaciones de .NET que lo admiten.
ms.date: 02/13/2020
ms.technology: dotnet-standard
ms.custom: updateeachrelease
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: e96a03ca55682d3e30bc13fb20a8e443105301fc
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359316"
---
# <a name="net-standard"></a>.NET Standard

[.NET Standard](https://github.com/dotnet/standard) es una especificación formal de las API de .NET que se prevé que estén disponibles en todas las implementaciones de .NET. La finalidad de .NET Standard es establecer una mayor uniformidad en el ecosistema de .NET. [ECMA 335](https://github.com/dotnet/runtime/blob/master/docs/project/dotnet-standards.md) sigue estableciendo uniformidad para el comportamiento de la implementación de .NET y, aunque ECMA 335 especifica un pequeño conjunto de bibliotecas estándar, la especificación de .NET Standard abarca una gama más amplia de API de .NET.

.NET Standard habilita los escenarios clave siguientes:

- Define un conjunto uniforme de API de BCL para todas las implementaciones de .NET que se van a implementar, independientemente de la carga de trabajo.
- Permite a los desarrolladores generar bibliotecas portátiles que se pueden usar en las implementaciones de .NET con este mismo conjunto de API.
- Reduce o incluso elimina la compilación condicional de código fuente compartido debido a las API de .NET, solo para API de sistema operativo.

Las diversas implementaciones de .NET tienen como destino versiones concretas de .NET Standard. Cada implementación de .NET anuncia la última versión más alta de .NET Standard que admite, indicación de que también es compatible con versiones anteriores. Por ejemplo, .NET Framework 4.6 implementa .NET Standard 1.3, lo que significa que expone todas las API definidas en las versiones de .NET Standard de 1.0 a 1.3. De forma similar, .NET Framework 4.6.1 implementa .NET Standard 1.4, mientras que .NET Core 1.0 implementa .NET Standard 1.6.

## <a name="net-implementation-support"></a>Compatibilidad con implementaciones de .NET

En la tabla siguiente se indican las versiones **mínimas** de la plataforma compatibles con cada versión de .NET Standard. Esto significa que las versiones posteriores de una plataforma de la lista también son compatibles con la versión correspondiente de .NET Standard. Por ejemplo, .NET Core 2.2 es compatible con .NET Standard 2.0 y versiones anteriores.

[!INCLUDE [net-standard-table](../../includes/net-standard-table.md)]

Para encontrar la versión más reciente de .NET Standard que puede usar como destino, haga lo siguiente:

1. Busque la fila en la que se indica la implementación de .NET en la que quiere realizar la ejecución.
2. Busque la columna de esa fila que indica la versión de derecha a izquierda.
3. El encabezado de columna indica la versión de .NET Standard que admite el destino. También se puede seleccionar como destino cualquier versión anterior de .NET Standard. Las versiones superiores de .NET Standard también serán compatibles con la implementación.
4. Repita este proceso para cada plataforma a la que quiera dirigirse. Si tiene más de una plataforma de destino, debe elegir la versión más baja. Por ejemplo, si quiere ejecutar en .NET Framework 4.5 y .NET Core 1.0, la versión de .NET Standard más alta que puede usar es .NET Standard 1.1.

### <a name="which-net-standard-version-to-target"></a>Versión de .NET Standard de destino

Al elegir una versión de .NET Standard, debe tener en cuenta lo siguiente:

- Cuanto mayor sea la versión, más API tendrá disponibles.
- Cuanto menor sea la versión, más plataformas la implementarán.

En general, se recomienda elegir como destino la versión *menor* de .NET Standard posible. Así, después de buscar la versión de .NET Standard superior que puede elegir como destino, siga estos pasos:

1. Diríjase a la siguiente versión menor de .NET Standard y cree el proyecto.
2. Si el proyecto se crea correctamente, repita el paso 1. De lo contrario, vuelva a dirigirse a la siguiente versión mayor, que es la que debe usar.

Sin embargo, el establecimiento como destino de las versiones inferiores de .NET Standard introduce diferentes dependencias de compatibilidad. Si el proyecto establece como destino .NET Standard 1.x, le recomendamos que *también* establezca .NET Standard 2.0 como destino. Esto simplifica el gráfico de dependencias para los usuarios de la biblioteca que se ejecutan en los marcos compatibles de .NET Standard 2.0 y reduce el número de paquetes que necesitan descargar.

### <a name="net-standard-versioning-rules"></a>Reglas de control de versiones de .NET Standard

Hay dos reglas de control de versiones principales:

- Adición: las versiones de .NET Standard son círculos lógicamente concéntricos: las versiones superiores incorporan todas las API de las versiones anteriores. No hay ningún cambio importante entre versiones.
- Inmutable: Una vez publicadas, las versiones de .NET Standard se congelan. Las nuevas API primero están disponibles en implementaciones de .NET concretas, como .NET Core. Si el consejo de revisión de .NET Standard cree que las nuevas API deben estar disponibles para todas las implementaciones de .NET, se agregan en una nueva versión de .NET Standard.

## <a name="specification"></a>Especificación

La especificación de .NET Standard es un conjunto estandarizado de API. La especificación se mantiene mediante implementadores de .NET, específicamente Microsoft (que incluye .NET Framework, .NET Core y Mono) y Unity. Se usa un proceso de comentarios públicos como parte del establecimiento de las versiones nuevas de .NET Standard a través de [GitHub](https://github.com/dotnet/standard).

### <a name="official-artifacts"></a>Artefactos oficiales

La especificación oficial es un conjunto de archivos .cs que definen las API que forman parte del estándar. El [directorio ref](https://github.com/dotnet/standard/tree/master/src/netstandard/ref) en el [repositorio dotnet/standard](https://github.com/dotnet/standard) define las API de .NET Standard.

El metapaquete [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) ([código fuente](https://github.com/dotnet/standard/blob/master/src/netstandard/pkg/NETStandard.Library.dependencies.props)) describe el conjunto de bibliotecas que definen (en parte) una o varias versiones de .NET Standard.

Un componente determinado, como `System.Runtime`, describe lo siguiente:

- Parte de .NET Standard (solo su ámbito).
- Varias versiones de .NET Standard para ese ámbito.

Se proporcionan artefactos derivados para permitir una lectura más cómoda y habilitar ciertos escenarios de desarrollo (por ejemplo, el uso de un compilador).

- [Lista de API en Markdown](https://github.com/dotnet/standard/tree/master/docs/versions)
- Ensamblados de referencia, distribuidos como paquetes NuGet y a los que hace referencia el metapaquete [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/).

### <a name="package-representation"></a>Representación de paquetes

El principal vehículo de distribución de los ensamblados de referencia de .NET Standard son los paquetes NuGet. Las implementaciones se entregarán de diversas formas, adecuadas para cada implementación de .NET.

Los paquetes NuGet tienen como destino uno o varios [marcos](frameworks.md). Los paquetes de .NET Standard tienen como destino el marco de trabajo ".NET Standard". Puede establecer como destino el marco de .NET Standard mediante el [TFM compacto](frameworks.md)`netstandard` (por ejemplo, `netstandard1.4`). Las bibliotecas diseñadas para ejecutarse en varios entornos de ejecución deben tener como destino este marco de trabajo. Para obtener el conjunto más amplio de API, indique `netstandard2.0` como destino, puesto que el número de API disponibles se ha doblado entre .NET Standard 1.6 y 2.0.

El metapaquete [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library/) hace referencia al conjunto completo de paquetes NuGet que definen .NET Standard.  La manera más común de establecer como destino `netstandard` consiste en hacer referencia a este metapaquete. Describe y proporciona acceso a las aproximadamente 40 bibliotecas de .NET y las API asociadas que definen .NET Standard. Puede hacer referencia a paquetes adicionales que tienen como destino `netstandard` para obtener acceso a otras API.

### <a name="versioning"></a>Control de versiones

La especificación no es única, sino que se trata de un conjunto de API con versiones lineales y con un crecimiento incremental. La primera versión del estándar establece un conjunto básico de API. Las versiones posteriores agregan API y heredan las API definidas por las versiones anteriores. No se ha establecido ninguna disposición para quitar API del estándar.

.NET Standard no es específico de ninguna implementación de .NET ni coincide con el esquema de control de versiones de ningún entorno de ejecución.

Las API agregadas a cualquier implementación de .NET (por ejemplo, .NET Framework, .NET Core y Mono) pueden considerarse candidatas para agregarse a la especificación, sobre todo si se consideran fundamentales por su naturaleza. Las nuevas [versiones de .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md) se crean en función de las versiones de la implementación de .NET, lo que permite establecer como destino nuevas API desde una Biblioteca de clases portable (PLC) de .NET Standard. Los mecanismos de control de versiones se describen con más detalle en [Control de versiones de .NET Core](../core/versions/index.md).

El control de versiones de .NET Standard es importante para su uso. Dada una versión de .NET Standard, puede usar bibliotecas que tengan como destino esa misma versión o una inferior. En el enfoque siguiente se describe el flujo de trabajo para el uso de PCL de .NET Standard específicas para tener como destino .NET Standard.

- Seleccione una versión de .NET Standard para usarla para la PCL.
- Use bibliotecas que dependan de la misma versión de .NET Standard o de una inferior.
- Si encuentra una biblioteca que depende de una versión superior de .NET Standard, deberá adoptar la misma versión o bien optar por no usar esa biblioteca.

## <a name="target-net-standard"></a>.NET Standard como destino

Puede [compilar bibliotecas estándar de .NET](../core/tutorials/libraries.md) mediante una combinación del marco `netstandard` y el metapaquete NETStandard.Library.

## <a name="net-framework-compatibility-mode"></a>Modo de compatibilidad de .NET Framework

A partir de .NET Standard 2.0 se ha introducido el modo de compatibilidad de .NET Framework. Este modo de compatibilidad permite que los proyectos de .NET Standard hagan referencia a bibliotecas de .NET Framework como si estuviesen compiladas para .NET Standard. Las referencias a bibliotecas de .NET Framework no funcionan para todos los proyectos, por ejemplo, en bibliotecas que usan API de Windows Presentation Foundation (WPF).

Para obtener más información, consulte [Modo de compatibilidad de .NET Framework](../core/porting/third-party-deps.md#net-framework-compatibility-mode).

## <a name="net-standard-libraries-and-visual-studio"></a>Bibliotecas de .NET standard y Visual Studio

Para crear bibliotecas de .NET Standard en Visual Studio, asegúrese de tener [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o la versión 15.3 de Visual Studio 2017 o posterior instalada en Windows, o bien la [versión 7.1 de Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) o posterior instalada en macOS.

Si solo necesita consumir bibliotecas de .NET Standard 2.0 en sus proyectos, también puede hacerlo en Visual Studio 2015. Sin embargo, necesitará tener el cliente 3.6 de NuGet o uno posterior instalado. Puede descargar el cliente de NuGet para Visual Studio 2015 desde la página de [descargas de NuGet](https://www.nuget.org/downloads).

## <a name="comparison-to-portable-class-libraries"></a>Comparación con las bibliotecas de clases portátiles

.NET Standard es el reemplazo de las [bibliotecas de clases portátiles (PCL)](./cross-platform/cross-platform-development-with-the-portable-class-library.md). .NET Standard mejora la experiencia de creación de bibliotecas portátiles, ya que mantiene una BCL estándar y establece como resultado una mayor uniformidad en las implementaciones de .NET. Una biblioteca que tiene como destino .NET Standard es una PCL o "PCL basada en .NET Standard". Las PCL existentes son "PCL basadas en perfiles".

.NET Standard y los perfiles de PCL se crearon con propósitos parecidos, pero también presentan algunas diferencias clave.

Similitudes:

- Definen las API que se pueden usar para compartir código binario.

Diferencias:

- .NET Standard es un conjunto mantenido de API, mientras que los perfiles de PCL se definen por las intersecciones de las plataformas existentes.
- .NET Standard tiene versiones lineales, al contrario de los perfiles de PCL.
- Los perfiles de PCL representan plataformas de Microsoft, mientras que .NET Standard es independiente de la plataforma.

### <a name="pcl-compatibility"></a>Compatibilidad con PCL

.NET Standard es compatible con un subconjunto de perfiles de PCL. .NET Standard 1.0, 1.1 y 1.2 se superponen con un conjunto de perfiles de PCL. Esta superposición se ha creado por dos motivos:

- Habilitar las PCL basadas en .NET Standard para hacer referencia a PCL basadas en perfiles.
- Habilitar las PCL basadas en perfiles para empaquetarlas como PCL basadas en .NET Standard.

Se proporciona compatibilidad con PCL basada en perfiles mediante el paquete NuGet [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility). Esta dependencia es necesaria cuando se hace referencia a paquetes NuGet que contienen PCL basadas en perfiles.

Las PCL basadas en perfiles empaquetadas como `netstandard` son más fáciles de consumir que las PCL basadas en perfiles empaquetadas normalmente. El empaquetado de `netstandard` es compatible con los usuarios existentes.

Puede ver el conjunto de perfiles de PCL que son compatibles con .NET Standard:

| Perfil de PCL | .NET Standard | Plataformas de PCL
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

## <a name="see-also"></a>Vea también

- [Versiones de .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md)
- [Compilación de una biblioteca de .NET Standard](../core/tutorials/library-with-visual-studio.md)
- [Destinatarios multiplataforma](./library-guidance/cross-platform-targeting.md)
