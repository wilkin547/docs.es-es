---
title: Limitaciones de Xamarin
ms.date: 12/13/2019
description: Se describen algunas de las limitaciones que encontrará al usar Xamarin.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450409"
---
# <a name="xamarin-limitations"></a>Limitaciones de Xamarin

Microsoft.Data.SQLite tiene como destino .NET Standard 2.0 y es compatible con Xamarin. En la tabla siguiente se muestran las plataformas para las que la agrupación SQLitePCLRaw predeterminada proporciona archivos binarios nativos de SQLite. Vea [Versiones personalizadas de SQLite](custom-versions.md) para obtener más información sobre el uso de otra agrupación o cómo suministrar archivos binarios nativos de SQLite propios.

| Plataforma | Archivos binarios de SQLite |
| --- | --- |
| **Xamarin.Android** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | ✔ |
| **Xamarin.iOS** | ✔ |
| **Xamarin.Mac** | ✔ |
| **Xamarin.TVOS** | ✔ |
| **UWP** | — |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | ✔ |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | ✔ |

## <a name="ios"></a>iOS

Microsoft.Data.SQLite intenta inicializar automáticamente las agrupaciones SQLitePCLRaw. Desafortunadamente, debido a las limitaciones de la compilación Ahead Of Time (AOT) de Xamarin.iOS, no se puede realizar el intento y se obtiene el siguiente error.

> Debe llamar a `SQLitePCL.raw.SetProvider()`. Si usa un paquete de agrupaciones, debe llamar a `SQLitePCL.Batteries.Init()`.

Para inicializar la agrupación, agregue la línea de código siguiente a la aplicación antes de usar Microsoft.Data.SQLite.

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a>Vea también

* [Limitaciones de Async](async.md)
* [Versiones personalizadas de SQLite](custom-versions.md)
