---
title: .NET Standard
description: Obtenga información sobre .NET Standard, sus versiones y las implementaciones de .NET que lo admiten.
ms.date: 10/05/2020
ms.technology: dotnet-standard
ms.custom: updateeachrelease
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: a4736e46eb7c25b64278bed8f2c2457002936b81
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224160"
---
# <a name="net-standard"></a>.NET Standard

[.NET Standard](https://github.com/dotnet/standard) es una especificación formal de las API de .NET que están disponibles en varias implementaciones de .NET. La finalidad de .NET Standard ha sido establecer una mayor uniformidad en el ecosistema de .NET. Pero en .NET 5 se adopta otro enfoque para establecer la uniformidad, en el que se elimina la necesidad de .NET Standard en muchos escenarios. Para obtener más información, vea [.NET 5 y .NET Standard](#net-5-and-net-standard) más adelante en este artículo.

## <a name="net-implementation-support"></a>Compatibilidad con implementaciones de .NET

Las diversas implementaciones de .NET tienen como destino versiones concretas de .NET Standard. Cada implementación de .NET anuncia la última versión más alta de .NET Standard que admite, indicación de que también es compatible con versiones anteriores. Por ejemplo, .NET Framework 4.6 implementa .NET Standard 1.3, lo que significa que expone todas las API definidas en las versiones de .NET Standard de 1.0 a 1.3. De forma similar, .NET Framework 4.6.1 implementa .NET Standard 1.4, mientras que .NET 5.0 implementa .NET Standard 2.1.

En la tabla siguiente se enumeran las versiones de implementación **mínimas** compatibles con cada versión de .NET Standard. Esto significa que las versiones posteriores de una implementación de la lista también son compatibles con la versión correspondiente de .NET Standard. Por ejemplo, .NET Core 2.1 y versiones posteriores admiten .NET Standard 2.0 y versiones anteriores.

[!INCLUDE [net-standard-table](../../includes/net-standard-table.md)]

Para encontrar la versión más reciente de .NET Standard que puede usar como destino, haga lo siguiente:

1. Busque la fila en la que se indica la implementación de .NET en la que quiere realizar la ejecución.
1. Busque la columna de esa fila que indica la versión de derecha a izquierda.
1. El encabezado de columna indica la versión de .NET Standard que admite el destino. También se puede seleccionar como destino cualquier versión anterior de .NET Standard. Las versiones superiores de .NET Standard también serán compatibles con la implementación.
1. Repita este proceso para cada plataforma a la que quiera dirigirse. Si tiene más de una plataforma de destino, debe elegir la versión más baja. Por ejemplo, si quiere ejecutar en .NET Framework 4.8 y .NET 5.0, la versión de .NET Standard más alta que puede usar es .NET Standard 2.0.

### <a name="which-net-standard-version-to-target"></a>Versión de .NET Standard de destino

Al elegir una versión de .NET Standard como destino, debe tener en cuenta lo siguiente:

- Cuanto mayor sea la versión, más API estarán disponibles para el código de la biblioteca.
- Cuanto menor sea la versión, más aplicaciones y bibliotecas podrá usar la biblioteca.

Se recomienda elegir como destino la versión *más baja* posible de .NET Standard. Así, después de buscar la versión de .NET Standard superior que puede elegir como destino, siga estos pasos:

1. Diríjase a la siguiente versión menor de .NET Standard y cree el proyecto.
2. Si el proyecto se crea correctamente, repita el paso 1. De lo contrario, vuelva a dirigirse a la siguiente versión mayor, que es la que debe usar.

Sin embargo, el establecimiento como destino de las versiones inferiores de .NET Standard introduce diferentes dependencias de compatibilidad. Si el proyecto establece como destino .NET Standard 1.x, le recomendamos que *también* establezca .NET Standard 2.0 como destino. Esto simplifica el gráfico de dependencias para los usuarios de la biblioteca que se ejecutan en implementaciones compatibles de .NET Standard 2.0 y reduce el número de paquetes que necesitan descargar.

### <a name="net-standard-versioning-rules"></a>Reglas de control de versiones de .NET Standard

Hay dos reglas de control de versiones principales:

- Adición: las versiones de .NET Standard son círculos lógicamente concéntricos: las versiones superiores incorporan todas las API de las versiones anteriores. No hay ningún cambio importante entre versiones.
- Inmutable: Una vez publicadas, las versiones de .NET Standard se congelan.

No habrá nuevas versiones de .NET Standard después de la versión 2.1. Para obtener más información, vea [.NET 5 y .NET Standard](#net-5-and-net-standard) más adelante en este artículo.

## <a name="specification"></a>Especificación

La especificación de .NET Standard es un conjunto estandarizado de API. La especificación se mantiene mediante implementadores de .NET, específicamente Microsoft (que incluye .NET Framework, .NET Core y Mono) y Unity.

### <a name="official-artifacts"></a>Artefactos oficiales

La especificación oficial es un conjunto de archivos *.cs* que definen las API que forman parte del estándar. El [directorio ref](https://github.com/dotnet/standard/tree/master/src/netstandard/ref) en el [repositorio dotnet/standard](https://github.com/dotnet/standard) define las API de .NET Standard.

El metapaquete [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) ([código fuente](https://github.com/dotnet/standard/blob/master/src/netstandard/pkg/NETStandard.Library.dependencies.props)) describe el conjunto de bibliotecas que definen (en parte) una o varias versiones de .NET Standard.

Un componente determinado, como `System.Runtime`, describe lo siguiente:

- Parte de .NET Standard (solo su ámbito).
- Varias versiones de .NET Standard para ese ámbito.

Se proporcionan artefactos derivados para permitir una lectura más cómoda y habilitar ciertos escenarios de desarrollo (por ejemplo, el uso de un compilador).

- [Lista de API en Markdown](https://github.com/dotnet/standard/tree/master/docs/versions)
- Ensamblados de referencia, distribuidos como paquetes NuGet y a los que hace referencia el metapaquete [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/).

### <a name="package-representation"></a>Representación de paquetes

El principal vehículo de distribución de los ensamblados de referencia de .NET Standard son los paquetes NuGet. Las implementaciones se entregarán de diversas formas, adecuadas para cada implementación de .NET.

Los paquetes NuGet tienen como destino uno o varios [marcos](frameworks.md). Los paquetes de .NET Standard tienen como destino el marco ".NET Standard". Puede establecer como destino el marco de .NET Standard mediante el [TFM compacto](frameworks.md)`netstandard` (por ejemplo, `netstandard1.4`). Las bibliotecas diseñadas para ejecutarse en varias implementaciones de .NET deben tener como destino este marco. Para obtener el conjunto más amplio de API, indique `netstandard2.0` como destino, puesto que el número de API disponibles se ha doblado entre .NET Standard 1.6 y 2.0.

El metapaquete [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library/) hace referencia al conjunto completo de paquetes NuGet que definen .NET Standard.  La manera más común de establecer como destino `netstandard` consiste en hacer referencia a este metapaquete. Describe y proporciona acceso a las aproximadamente 40 bibliotecas de .NET y las API asociadas que definen .NET Standard. Puede hacer referencia a paquetes adicionales que tienen como destino `netstandard` para obtener acceso a otras API.

### <a name="versioning"></a>Control de versiones

La especificación no es única, sino que se trata de un conjunto de API con versiones lineales. La primera versión del estándar establece un conjunto básico de API. Las versiones posteriores agregan API y heredan las API definidas por las versiones anteriores. No se ha establecido ninguna disposición para quitar API del estándar.

.NET Standard no es específico de ninguna implementación de .NET, ni coincide con el sistema de control de versiones de ninguna de esas implementaciones.

Como se ha mencionado antes, no habrá nuevas versiones de .NET Standard después de la versión 2.1.

## <a name="target-net-standard"></a>.NET Standard como destino

Puede [compilar bibliotecas de .NET Standard](../core/tutorials/libraries.md) mediante una combinación del marco `netstandard` y el metapaquete `NETStandard.Library`.

## <a name="net-framework-compatibility-mode"></a>Modo de compatibilidad de .NET Framework

A partir de .NET Standard 2.0 se ha introducido el modo de compatibilidad de .NET Framework. Este modo de compatibilidad permite que los proyectos de .NET Standard hagan referencia a bibliotecas de .NET Framework como si estuviesen compiladas para .NET Standard. Las referencias a bibliotecas de .NET Framework no funcionan para todos los proyectos, por ejemplo, en bibliotecas que usan API de Windows Presentation Foundation (WPF).

Para obtener más información, consulte [Modo de compatibilidad de .NET Framework](../core/porting/third-party-deps.md#net-framework-compatibility-mode).

## <a name="net-standard-libraries-and-visual-studio"></a>Bibliotecas de .NET standard y Visual Studio

Para crear bibliotecas de .NET Standard en Visual Studio, asegúrese de tener [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o la versión 15.3 de Visual Studio 2017 o posterior instalada en Windows, o bien la [versión 7.1 de Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) o posterior instalada en macOS.

Si solo necesita consumir bibliotecas de .NET Standard 2.0 en sus proyectos, también puede hacerlo en Visual Studio 2015. Sin embargo, necesitará tener el cliente 3.6 de NuGet o uno posterior instalado. Puede descargar el cliente de NuGet para Visual Studio 2015 desde la página de [descargas de NuGet](https://www.nuget.org/downloads).

## <a name="net-5-and-net-standard"></a>.NET 5 y .NET Standard

.NET 5 es la implementación de .NET que Microsoft desarrolla de forma activa. Se trata de un único producto con un conjunto uniforme de funcionalidades y API que se pueden usar para aplicaciones de escritorio de Windows y aplicaciones de consola multiplataforma, servicios en la nube y sitios web. Los [moniker de la plataforma de destino](frameworks.md) de .NET 5.0 reflejan esta amplia gama de escenarios:

* `net5.0`

  Este TFM es para el código que se ejecuta en todas partes. Con algunas excepciones, solo incluye tecnologías que funcionan entre plataformas. En el código de .NET 5, `net5.0` reemplaza los TFM `netcoreapp` y `netstandard`.

* `net5.0-windows`

  Este es un ejemplo de [TFM específicos del sistema operativo](frameworks.md#net-5-os-specific-tfms) que agregan funcionalidad específica del sistema operativo a todo a lo que `net5.0` hace referencia.

### <a name="when-to-target-net50-vs-netstandard"></a>Diferencias entre elegir .NET 5.0 y .NET Standard como destino

Para el código existente que tiene como destino `netstandard`, no es necesario cambiar el TFM por `net5.0`. .NET 5.0 implementa .NET Standard 2.1 y versiones anteriores. La única razón para cambiar el destino de .NET Standard a .NET 5.0 sería para obtener acceso a más características de tiempo de ejecución, del lenguaje o API. Por ejemplo, para usar C# 9, debe tener como destino .NET 5.0. Puede tener como destino .NET 5.0 y .NET Standard para obtener acceso a las características más recientes y seguir teniendo la biblioteca disponible para otras implementaciones de .NET.

Estas son algunas instrucciones para el código nuevo de .NET 5:

* Componentes de la aplicación

  Si usa bibliotecas para dividir una aplicación en varios componentes, se recomienda seleccionar como destino `net5.x`, donde `5.x` es la versión más antigua de .NET 5 que la aplicación puede tener como destino. Para simplificar, es mejor mantener todos los proyectos que componen la aplicación en la misma versión de .NET. Después, puede suponer las mismas características de BCL en todas partes.

* Bibliotecas reutilizables

  Si va a compilar bibliotecas reutilizables que planea enviar en NuGet, tenga en cuenta el equilibrio entre el alcance y el conjunto de características disponibles. .NET Standard 2.0 es la última versión admitida por .NET Framework, por lo que ofrece un buen alcance con un conjunto de características bastante amplio. No se recomienda establecer .NET Standard 1.x como destino, ya que se limitaría el conjunto de características disponibles a cambio de un mínimo aumento del alcance.

  Si no necesita admitir .NET Framework, puede usar .NET Standard 2.1 o .NET 5. Se recomienda omitir .NET Standard 2.1 y pasar directamente a .NET 5. En última instancia,. las bibliotecas más utilizadas tendrán como destino tanto .NET Standard 2.0 como .NET 5. Al admitir .NET Standard 2.0 se obtiene el máximo alcance, mientras que al admitir .NET 5 se garantiza el aprovechamiento de las características más recientes de la plataforma para los clientes que ya usan .NET 5.

### <a name="net-standard-problems"></a>Problemas con .NET Standard

Estos son algunos problemas con .NET Standard que ayudan a explicar por qué .NET 5 es la mejor manera de compartir código entre plataformas y cargas de trabajo:

- Lentitud para agregar API nuevas

  .NET Standard se creó como un conjunto de API que todas las implementaciones de .NET debían admitir, por lo que hubo un proceso de revisión de las propuestas para agregar API nuevas. El objetivo era normalizar solo las API que se pudieran implementar en todas las plataformas .NET, actuales y futuras. Como resultado, si faltaba una característica en una versión concreta, es posible que tuviera que esperar un par de años antes de que se agregara a una versión de Standard. Después, tendría que esperar incluso más a que la nueva versión de .NET Standard tuviera compatibilidad suficiente.

  **Solución en .NET 5:** Cuando se implementa una característica, ya está disponible para cada aplicación y biblioteca de .NET 5, porque la base de código está compartida. Y como no hay ninguna diferencia entre la especificación de la API y su implementación, puede aprovechar las ventajas de las nuevas características mucho más rápido que con .NET Standard.

- Complejidad del control de versiones

  La separación de la especificación de la API de sus implementaciones da lugar a una asignación compleja entre las versiones de especificación de la API y las de implementación. Esta complejidad es evidente en la tabla que se ha mostrado antes en este artículo y en las instrucciones sobre cómo interpretarla.

  **Solución en .NET 5:** No existe separación entre la especificación de una API de .NET 5.x y su implementación. El resultado es un esquema de TFM simplificado. Hay un prefijo de TFM para todas las cargas de trabajo: se usa `net5.0` para bibliotecas, aplicaciones de consola y aplicaciones web. La única variante es un [sufijo que especifica las API específicas de la plataforma](frameworks.md#net-5-os-specific-tfms) para una plataforma concreta, como `net5.0-windows`. Gracias a esta convención de nomenclatura de TFM, puede saber con facilidad si una aplicación concreta puede usar una biblioteca determinada. No se necesita una tabla de números de versión equivalentes como la de .NET Standard.

- Excepciones no admitidas por la plataforma en tiempo de ejecución

  .NET Standard expone API específicas de la plataforma. El código se podría compilar sin errores y parecer ser portable a cualquier plataforma aunque lo no sea. Cuando se ejecuta en una plataforma que no tiene una implementación de una API determinada, se obtienen errores en tiempo de ejecución.

  **Solución en .NET 5:** El SDK de .NET 5 incluye analizadores de código que están habilitados de forma predeterminada. El analizador de compatibilidad de plataformas detecta el uso involuntario de las API que no se admiten en las plataformas en las se que pretenden ejecutar. Para obtener más información, vea [Analizador de compatibilidad de plataformas](analyzers/platform-compat-analyzer.md).

### <a name="net-standard-not-deprecated"></a>.NET Standard no está en desuso

.NET Standard sigue siendo necesario para las bibliotecas que se pueden usar en varias implementaciones de .NET. Se recomienda seleccionar .NET Standard como destino en los escenarios siguientes:

* Use `netstandard2.0` para compartir código entre .NET Framework y todas las demás implementaciones de .NET.
* Use `netstandard2.1` para compartir código entre Mono, Xamarin y .NET Core 3.x.

## <a name="see-also"></a>Consulte también

- [Versiones de .NET Standard (código fuente)](https://github.com/dotnet/standard/blob/master/docs/versions.md)
- [Versiones de .NET Standard (IU interactiva)](https://dotnet.microsoft.com/platform/dotnet-standard#versions)
- [Compilación de una biblioteca de .NET Standard](../core/tutorials/library-with-visual-studio.md)
- [Destinatarios multiplataforma](./library-guidance/cross-platform-targeting.md)
