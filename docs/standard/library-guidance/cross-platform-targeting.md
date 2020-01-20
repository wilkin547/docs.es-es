---
title: Destino multiplataforma para bibliotecas de .NET
description: Procedimientos recomendados para la creación de bibliotecas de .NET multiplataforma.
ms.date: 08/12/2019
ms.openlocfilehash: 45eb67837c924558ec51381dd924abf9fd0fa315
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706522"
---
# <a name="cross-platform-targeting"></a>Destinatarios multiplataforma

La plataforma .NET moderna es compatible con varios sistemas operativos y dispositivos. Es importante para las bibliotecas de código abierto de .NET admitir tantos desarrolladores como sea posible, ya sea que esté creando un sitio web ASP.NET hospedado en Azure o un juego de .NET en Unity.

## <a name="net-standard"></a>.NET Standard

.NET Standard es la mejor manera de agregar compatibilidad multiplataforma a una biblioteca de .NET. [.NET Standard](../net-standard.md) es una especificación de API de .NET que se prevé que esté disponible en todas las implementaciones de .NET. El destino .NET Standard le permite generar bibliotecas que están limitadas a usar las API que se encuentran en una versión concreta de .NET Standard, lo que significa que la pueden usar todas las plataformas que implementan esa versión de .NET Standard.

![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")

El destino .NET Standard, así como la compilación correcta del proyecto, no garantiza que la biblioteca se ejecutará correctamente en todas las plataformas:

1. Las API específicas de plataforma producirán un error en otras plataformas. Por ejemplo, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> se llevará a cabo correctamente en Windows y generará <xref:System.PlatformNotSupportedException> cuando se utilice en cualquier otro sistema operativo.
2. Las API pueden comportarse de manera diferente. Por ejemplo, las API de reflexión tienen diferentes características de rendimiento cuando una aplicación utiliza una compilación anticipada en iOS o UWP.

> [!TIP]
> El equipo de .NET [ofrece un analizador Roslyn](../analyzers/api-analyzer.md) para ayudar a detectar posibles problemas.

**✔️ DEBE** empezar incluyendo un destino `netstandard2.0`.

> La mayoría de bibliotecas de uso general no deberían necesitar API fuera de .NET Standard 2.0. Todas las plataformas modernas admiten .NET Standard 2.0 y es la manera recomendada para admitir varias plataformas con un destino.

**❌ EVITE** incluir un destino `netstandard1.x`.

> .NET Standard 1.x se distribuye como un conjunto pormenorizado de paquetes NuGet, que crea un gráfico de dependencias de paquete grande y da lugar a que los desarrolladores descarguen una gran cantidad de paquetes al compilar. Las plataformas .NET modernas, incluidas .NET Framework 4.6.1, UWP y Xamarin, admiten .NET Standard 2.0. Solo debe utilizar .NET Standard 1.x como destino si necesita específicamente una plataforma anterior como destino.

**✔️ DEBE** incluir un destino `netstandard2.0` si necesita un destino `netstandard1.x`.

> Todas las plataformas que admiten .NET Standard 2.0 usarán el destino `netstandard2.0` y se aprovecharán del hecho de tener un gráfico de paquetes más pequeño, mientras que las plataformas anteriores seguirán funcionando y pasarán a usar el destino `netstandard1.x`.

**❌ NO** incluya un destino de .NET Standard si la biblioteca se basa en un modelo de aplicación específico de la plataforma.

> Por ejemplo, una biblioteca de Kit de herramientas de control UWP depende de un modelo de aplicación que solo está disponible en UWP. Las API específicas del modelo de aplicación no estarán disponibles en .NET Standard.

## <a name="multi-targeting"></a>Compatibilidad con múltiples versiones

En ocasiones necesitará tener acceso a las API específicas del marco de las bibliotecas. La mejor manera de llamar a las API específicas del marco es usar varios destinos, que crea el proyecto para muchos [marcos de destino de .NET](../frameworks.md) en lugar de solo para uno.

Para evitar que los consumidores tengan que crear para marcos individuales, debe procurar tener una salida de .NET Standard además de una o más salidas específicas del marco. Con varias versiones, todos los ensamblados se empaquetan dentro de un único paquete NuGet. Después, los consumidores pueden hacer referencia al mismo paquete y NuGet seleccionará la implementación apropiada. La biblioteca de .NET Standard actúa como la biblioteca de reserva que se usa en todas partes, salvo en los casos donde el paquete NuGet ofrece una implementación específica del marco. Varios destinos le permiten usar la compilación condicional en el código y llamar a las API específicas del marco.

![Paquete NuGet con varios ensamblados](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "Paquete NuGet con varios ensamblados")

**✔️ ES RECOMENDABLE** usar las implementaciones de .NET como destino además de .NET Standard.

> El uso de las implementaciones de .NET como destino le permite llamar a las API específicas de la plataforma que se encuentran fuera de .NET Standard.
>
> No elimine la compatibilidad con .NET Standard al hacer esto. En su lugar, empiece desde la implementación y ofrezca API de funcionalidad. De este modo, la biblioteca se puede usar en cualquier lugar y admite la carga ligera de características en tiempo de ejecución.

```csharp
public static class GpsLocation
{
    // This project uses multi-targeting to expose device-specific APIs to .NET Standard.
    public static async Task<(double latitude, double longitude)> GetCoordinatesAsync()
    {
#if NET461
        return CallDotNetFramworkApi();
#elif WINDOWS_UWP
        return CallUwpApi();
#else
        throw new PlatformNotSupportedException();
#endif
    }

    // Allows callers to check without having to catch PlatformNotSupportedException
    // or replicating the OS check.
    public static bool IsSupported
    {
        get
        {
#if NET461 || WINDOWS_UWP
            return true;
#else
            return false;
#endif
        }
    }
}
```

**❌ EVITE** varios destinos así como destinar a .NET Standard si el código fuente es el mismo para todos los destinos.

> NuGet usará automáticamente el ensamblado de .NET Standard. El uso de las implementaciones de .NET individuales como destino aumenta el tamaño de `*.nupkg` sin obtener ventaja alguna.

**✔️ ES RECOMENDABLE** agregar un destino para `net461` cuando se ofrece un destino `netstandard2.0`.

> El uso de .NET Standard 2.0 de .NET Framework tiene algunos problemas que se han solucionado en .NET Framework 4.7.2. Puede mejorar la experiencia para los desarrolladores que siguen usando .NET Framework 4.6.1 - 4.7.1 ofreciéndoles un archivo binario que se ha creado para .NET Framework 4.6.1.

**✔️ DEBE** distribuir las bibliotecas mediante un paquete NuGet.

> NuGet seleccionará el mejor destino para el desarrollador y evitará que tenga de tener que elegir la implementación apropiada.

**✔️ DEBE** usar una propiedad `TargetFrameworks` del archivo de proyecto cuando haya varios destinos.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

**✔️ ES RECOMENDABLE** usar [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) cuando se usan varios destinos para UWP y Xamarin, ya que simplifica considerablemente el archivo de proyecto.

## <a name="older-targets"></a>Destinos antiguos

.NET admite las versiones de destino de .NET Framework que llevan mucho tiempo sin soporte técnico, así como las plataformas que ya no se suelen utilizar. Si bien es valioso hacer que la biblioteca funcione en tantos destinos como sea posible, tener que trabajar con API ausentes puede agregar una sobrecarga significativa. Creemos que ciertos marcos ya no valen la pena como destino, considerando su alcance y limitaciones.

**❌ NO** incluya un destino de Biblioteca de clases portable (PCL). Por ejemplo: `portable-net45+win8+wpa81+wp8`.

> .NET standard es la forma moderna de admitir las bibliotecas de .NET multiplataforma y reemplaza a las PCL.

**❌ NO** incluya destinos para las plataformas de .NET que ya no se admiten. Por ejemplo: `SL4`, `WP`.

>[!div class="step-by-step"]
>[Anterior](get-started.md)
>[Siguiente](strong-naming.md)
