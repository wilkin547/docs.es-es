---
ms.openlocfilehash: 9e95db8a1530fabd30b5344c87728b9210c0ad69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74802840"
---
| .NET Standard              | [1.0]  | [1.1]  | [1.2] | [1.3] | [1.4] | [1.5]              | [1.6]              | [2.0]               | [2.1] |
|----------------------------|--------|--------|-------|-------|-------|--------------------|--------------------|---------------------|---------------------
| .NET Core                  | 1.0    | 1.0    | 1.0   | 1.0   | 1.0   | 1.0                | 1.0                | 2.0                 | 3.0 |
| .NET Framework <sup>1</sup>| 4.5    | 4.5    | 4.5.1 | 4.6   | 4.6.1 | 4.6.1 <sup>2</sup> | 4.6.1 <sup>2</sup> | 4.6.1 <sup>2</sup>  | N/A<sup>3</sup> |
| Mono                       | 4.6    | 4.6    | 4.6   | 4.6   | 4.6   | 4.6                | 4.6                | 5.4                 | 6.4 |
| Xamarin.iOS                | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0               | 10.0               | 10.14               | 12.16 |
| Xamarin.Mac                | 3.0    | 3.0    | 3.0   | 3.0   | 3.0   | 3.0                | 3.0                | 3.8                 | 5.16 |
| Xamarin.Android            | 7.0    | 7.0    | 7.0   | 7.0   | 7.0   | 7.0                | 7.0                | 8.0                 | 10.0 |
| Plataforma universal de Windows | 10.0   | 10.0   | 10.0  | 10.0  | 10.0  | 10.0.16299         | 10.0.16299         | 10.0.16299          | TBD |
| Unity                      | 2018.1 | 2018.1 | 2018.1| 2018.1| 2018.1| 2018.1             |  2018.1            | 2018.1              | TBD |

<sup>1 Las versiones que se muestran de .NET Framework se aplican al SDK de .NET Core 2.0 y versiones posteriores de la herramienta. Las versiones anteriores usaban una asignación diferente para .NET Standard 1.5 y versiones posteriores. Puede [descargar herramientas para .NET Core para Visual Studio 2015](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md) si no se puede actualizar a Visual Studio 2017 ni a una versión posterior.</sup>

<sup>2 Las versiones siguientes representan las reglas que usa NuGet para determinar si una determinada biblioteca de .NET Standard es aplicable. Aunque NuGet considera a .NET Framework 4.6.1 compatible con .NET Standard (versiones 1.5 a 2.0) hay varios problemas con el consumo de bibliotecas de .NET Standard que se compilaron para esas versiones desde proyectos de .NET Framework 4.6.1. Para los proyectos de .NET Framework que tengan que usar estas bibliotecas, se recomienda actualizar el proyecto para destinarlo a .NET Framework 4.7.2 o una versión posterior.</sup>

<sup>3 .NET Framework no admitirá .NET Standard 2.1 o versiones posteriores. Para más detalles, vea el [anuncio de .NET Standard 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-standard-2-1/).</sup>

- Las columnas representan las versiones de .NET Standard. Cada celda de encabezado es un vínculo a un documento que muestra qué API se han agregado en esa versión de .NET Standard.
- Las filas representan las diferentes implementaciones de .NET.
- El número de versión de cada celda indica la versión *mínima* de la implementación que necesitará para tener como destino dicha versión de .NET Standard.
- Para ver una tabla interactiva, consulte [Versiones de .NET Standard](https://dotnet.microsoft.com/platform/dotnet-standard#versions).

[1.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.0.md
[1.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.1.md
[1.2]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.2.md
[1.3]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.3.md
[1.4]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.4.md
[1.5]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.5.md
[1.6]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard1.6.md
[2.0]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.0.md
[2.1]: https://github.com/dotnet/standard/blob/master/docs/versions/netstandard2.1.md
