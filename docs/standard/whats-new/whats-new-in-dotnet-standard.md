---
title: Novedades de .NET Standard
description: En este artículo, se resumen las nuevas características y mejoras que se encuentran en cada nueva versión de .NET Standard.
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
ms.openlocfilehash: 28d6a3546e08bbc3a7d4a26f08ba9cc5e16a901b
ms.sourcegitcommit: 2ff49dcf9ddf107d139b4055534681052febad62
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2020
ms.locfileid: "80438200"
---
# <a name="whats-new-in-net-standard"></a>Novedades de .NET Standard

.NET Standard es una especificación formal que define un conjunto de API con control de versiones que debe estar disponible en las implementaciones de .NET que cumplen con esa versión del estándar. .NET Standard está dirigido a los desarrolladores de bibliotecas. Una biblioteca que tenga como destino una versión estándar de .NET Standard se puede usar en cualquier implementación de .NET Framework, .NET Core o Xamarin que admita esa versión del estándar.

.NET Standard se incluye con el SDK de .NET Core, así como con Visual Studio cuando se selecciona la carga de trabajo de .NET Core.

## <a name="supported-net-implementations"></a>Implementaciones de .NET compatibles

.NET Standard 2.0 es compatible con las implementaciones siguientes de .NET:

- .NET Core 2.0 o versiones posteriores
- .NET Framework 4.6.1 o versiones posteriores
- Mono 5.4 o versiones posteriores
- Xamarin.iOS 10.14 o versiones posteriores
- Xamarin.Mac 3.8 o versiones posteriores
- Xamarin.Android 8.0 o versiones posteriores
- Plataforma universal de Windows 10.0.16299 o versiones posteriores

## <a name="whats-new-in-net-standard-20"></a>Novedades de .NET Standard 2.0

.NET Standard 2.0 incluye las siguientes características nuevas:

### <a name="a-vastly-expanded-set-of-apis"></a>Un conjunto de API ampliamente expandido

Con la versión 1.6, .NET Standard incluía un subconjunto relativamente pequeño de API. Entre las excluidas estaban muchas API utilizadas habitualmente en .NET Framework o Xamarin. Esto complica el desarrollo, ya que los desarrolladores tienen que encontrar sustitutas adecuadas para API familiares para desarrollar aplicaciones y bibliotecas destinadas a varias implementaciones de .NET. .NET Standard 2.0 soluciona esta limitación con la incorporación de más de 20 000 API más de las que estaban disponibles en .NET Standard 1.6, la versión anterior del estándar. Si quiere obtener una lista de las API agregadas a .NET Standard 2.0, vea [comparación entre .NET Standard 2.0 y 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).

Alguna de las adiciones al espacio de nombres <xref:System> de .NET Standard 2.0 incluyen:

- Compatibilidad con la clase <xref:System.AppDomain>.
- Mayor compatibilidad para trabajar con matrices de miembros adicionales en la clase <xref:System.Array>.
- Mayor compatibilidad para trabajar con atributos de miembros adicionales en la clase <xref:System.Attribute>.
- Mayor compatibilidad del calendario y opciones de formato adicionales para los valores <xref:System.DateTime>.
- Funcionalidad de redondeo <xref:System.Decimal> adicional.
- Funcionalidad adicional en la clase <xref:System.Environment>.
- Control mejorado sobre el recolector de elementos no utilizados en la clase <xref:System.GC>.
- Compatibilidad mejorada para la comparación de cadenas, la enumeración y la normalización en la clase <xref:System.String>.
- Compatibilidad para los tiempos de transición y los ajustes del horario de verano en las clases <xref:System.TimeZoneInfo.AdjustmentRule> y <xref:System.TimeZoneInfo.TransitionTime>.
- Funcionalidad mejorada significativamente en la clase <xref:System.Type>.
- Mejor compatibilidad para la deserialización de objetos de excepción mediante la adición de un constructor de excepción con los parámetros <xref:System.Runtime.Serialization.SerializationInfo> y <xref:System.Runtime.Serialization.StreamingContext>.

### <a name="support-for-net-framework-libraries"></a>Compatibilidad con las bibliotecas .NET Framework

La gran mayoría de las bibliotecas tienen como destino .NET Framework en lugar de .NET Standard. Sin embargo, la mayoría de las llamadas de esas bibliotecas se realizan a las API incluidas en .NET Standard 2.0. A partir de .NET Standard 2.0, puede acceder a las bibliotecas de .NET Framework desde una biblioteca de .NET Standard usando una [corrección de compatibilidad](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification). Este nivel de compatibilidad es transparente para los desarrolladores; no tiene que hacer nada para aprovechar las ventajas de las bibliotecas de .NET Framework.

El único requisito es que las API a las que llaman las bibliotecas de clases .NET Framework estén incluidas en .NET Standard 2.0.

### <a name="support-for-visual-basic"></a>Compatibilidad con Visual Basic

Ahora puede desarrollar bibliotecas de .NET Standard en Visual Basic. Visual Studio 2019 y Visual Studio 2017, versión 15.3 o una posterior con la carga de trabajo de .NET Core instalada, incluyen una plantilla de la biblioteca de clases .NET Standard. Para los desarrolladores de Visual Basic que usan otras herramientas y entornos de desarrollo, puede usar el comando [dotnet new](../../core/tools/dotnet-new.md) para crear un proyecto de biblioteca de .NET Standard. Para más información, vea [Compatibilidad con herramientas de bibliotecas estándar de .NET](#tooling-support-for-net-standard-libraries).

### <a name="tooling-support-for-net-standard-libraries"></a>Compatibilidad con herramientas de bibliotecas de .NET Standard

Con la versión de .NET Core 2.0 y .NET Standard 2.0, Visual Studio 2017 y la [CLI de .NET Core](../../core/tools/index.md) incluyen compatibilidad con herramientas para crear bibliotecas de .NET Standard.

Si instala Visual Studio con la carga de trabajo de **desarrollo multiplataforma de .NET Core**, puede crear un proyecto de biblioteca de .NET Standard 2.0 al usar una plantilla de proyecto, como se muestra en la ilustración siguiente:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

![Agregar un proyecto de biblioteca nuevo de .NET Standard](./media/std-project-cs.png)

Si usa la CLI de .NET Core, el comando [dotnet new](../../core/tools/dotnet-new.md) siguiente crea un proyecto de biblioteca de clases que tiene como destino .NET Standard 2.0:

```dotnetcli
dotnet new classlib
```

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

![Agregar un proyecto de biblioteca nuevo de .NET Standard](./media/std-project-vb.png)

Si usa la CLI de .NET Core, el comando [dotnet new](../../core/tools/dotnet-new.md) siguiente crea un proyecto de biblioteca de clases que tiene como destino .NET Standard 2.0:

```dotnetcli
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a>Vea también

- [.NET Standard](../net-standard.md)
- [Introducing .NET Standard](https://devblogs.microsoft.com/dotnet/introducing-net-standard/) (Introducción a .NET Standard)
