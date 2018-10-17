---
title: Entre plataformas de destino
description: Prácticas recomendadas para la creación de bibliotecas de .NET multiplataforma.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 72fa891d5b1054af485a98d89b4efb11d6b0018b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374909"
---
# <a name="cross-platform-targeting"></a>Entre plataformas de destino

.NET moderna es compatible con varios sistemas operativos y dispositivos. Es importante para las bibliotecas de código abierto de .NET admitir los desarrolladores tantos como sea posible, si está creando un sitio Web ASP.NET hospedado en Azure o un juego de .NET en Unity.

## <a name="net-standard"></a>.NET Standard

.NET standard es la mejor manera de agregar la compatibilidad multiplataforma a una biblioteca. NET. [.NET standard](../net-standard.md) es una especificación de API de .NET que están disponibles en todas las implementaciones. NET. Destinadas a .NET Standard le permite generar bibliotecas que están limitadas a usar las API que se encuentran en una versión concreta de .NET Standard, lo que significa que se puede usar con todas las plataformas que implementan esa versión de .NET Standard.

![.NET standard](./media/cross-platform-targeting/platforms-netstandard.png "estándar de .NET")

No garantizan la .NET Standard como destino y compilar correctamente el proyecto, que la biblioteca se ejecutará correctamente en todas las plataformas:

1. Las API específicas de plataforma se producirá un error en otras plataformas. Por ejemplo, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> se realizará correctamente en Windows e iniciar <xref:System.PlatformNotSupportedException> cuando se utiliza en cualquier otro sistema operativo.
2. Las API pueden comportarse de manera diferente. Por ejemplo, reflection API tienen diferentes características de rendimiento cuando una aplicación utiliza las compilación ahead of time en iOS o UWP.

> [!TIP]
> El equipo de .NET [ofrece un analizador Roslyn](../analyzers/api-analyzer.md) para ayudar a detectar posibles problemas.

**HACER ✔️** comenzar con incluyendo un `netstandard2.0` destino.

> Más bibliotecas de propósito generales no deberían necesitar las API fuera de .NET Standard 2.0. .NET standard 2.0 es compatible con todas las plataformas modernas y es la manera recomendada para admitir varias plataformas con un destino.

**Evite ❌** incluyendo un `netstandard1.x` destino.

> .NET standard 1.x se distribuye como un conjunto específico de paquetes de NuGet, que crea un gráfico de dependencias de paquete grande y da lugar a los desarrolladores descargando una gran cantidad de paquetes al compilar. Plataformas de .NET modernas, incluido .NET Framework 4.6.1, UWP y Xamarin, todos admiten .NET Standard 2.0. Solo debe destinarse a .NET Standard 1.x si tiene específicamente como destino una plataforma anterior.

**HACER ✔️** incluyen un `netstandard2.0` de destino si necesita un `netstandard1.x` destino.

> Todas las plataformas que admiten .NET Standard 2.0 usará el `netstandard2.0` de destino y beneficiarse de tener un gráfico de paquetes más pequeño, mientras que las plataformas anteriores todavía funcionarán y vuelven a usar el `netstandard1.x` destino.

**❌ NO** incluir un destino de .NET Standard si la biblioteca se basa en un modelo de aplicaciones específicas de la plataforma.

> Por ejemplo, una biblioteca de Kit de herramientas de controles UWP depende de un modelo de aplicación que solo está disponible en UWP. Aplicación específicos del modelo de API no estará disponibles en .NET Standard.

## <a name="multi-targeting"></a>Compatibilidad con múltiples versiones

En ocasiones necesitará tener acceso a las API específicas del marco de las bibliotecas. La mejor manera de llamar a las API específicas del marco utiliza múltiples, que compila el proyecto para muchos [plataformas de destino de .NET](../frameworks.md) en lugar de solo uno.

Para proteger a los consumidores de tener que crear para los marcos individuales, debe procurar que tiene una salida de .NET Standard además de una o más salidas específicas del marco. Con múltiples versiones, todos los ensamblados se empaquetan dentro de un único paquete de NuGet. Los consumidores, a continuación, pueden hacer referencia el mismo paquete y NuGet seleccionará la implementación apropiada. La biblioteca estándar de .NET actúa como la biblioteca de reserva que usa en todas partes, salvo en los casos donde el paquete NuGet ofrece una implementación específica del marco. Múltiples le permite usar la compilación condicional en el código y llamar a las API específicas del marco.

![Paquete de NuGet con varios ensamblados](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "paquete de NuGet con varios ensamblados")

**Considere la posibilidad de ✔️** destinadas a las implementaciones de .NET además de .NET Standard.

> Destinatarios de las implementaciones de .NET le permite llamar a las API específicas de la plataforma que se encuentran fuera de .NET Standard.
>
> No eliminar la compatibilidad con .NET Standard al hacer esto. En su lugar, iniciar desde la implementación y ofrecen funcionalidad de API. De este modo, la biblioteca se puede usar en cualquier lugar y admite luminosas en tiempo de ejecución de funciones.

**Evite ❌** utilizando múltiples con .NET Standard si el código fuente es el mismo para todos los destinos.

> Se usará automáticamente el ensamblado de .NET Standard mediante NuGet. Destinatarios de las implementaciones de .NET individuales aumenta la `*.nupkg` tamaño sin obtener ventaja alguna.

**✔️, considere la posibilidad de** agregar un destino para `net461` cuando le está ofreciendo un `netstandard2.0` destino. 

> Uso de .NET Standard 2.0 de .NET Framework tiene algunos problemas que se han solucionado en .NET Framework 4.7.2. Puede mejorar la experiencia para los desarrolladores que siguen en .NET Framework 4.6.1 - 4.7.1, ya que les ofrece un archivo binario que se ha creado para .NET Framework 4.6.1.

**HACER ✔️** distribuir su biblioteca usando un paquete de NuGet.

> NuGet se selecciona el mejor destino para el desarrollador y protegerlos de tener que elegir la implementación apropiada.

**HACER ✔️** usar un archivo de proyecto `TargetFrameworks` propiedad cuando múltiples.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

**Considere la posibilidad de ✔️** mediante [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) cuando múltiples versiones de UWP y Xamarin, pues simplifica en gran medida el archivo de proyecto.

## <a name="older-targets"></a>Destinos anteriores

.NET es compatible con las versiones de .NET Framework destinatarios largos fuera del soporte técnico, así como las plataformas que ya no suelen usarse. Aunque no hay valor para realizar su trabajo de biblioteca en ya pueden agregar muchos destinos como sea posible, tener que solucionar la falta de API importante sobrecarga. Creemos que ciertos marcos dejan que vale la pena como destino, teniendo en cuenta su alcance y las limitaciones.

**❌ NO** incluir un destino de la biblioteca de clases portables (PCL). Por ejemplo: `portable-net45+win8+wpa81+wp8`.

> .NET standard es la forma moderna para admitir las bibliotecas de .NET multiplataforma y reemplaza los PCL.

**❌ NO** incluyen destinos para las plataformas de .NET que ya no se admiten. Por ejemplo: `SL4`, `WP`.

>[!div class="step-by-step"]
[Anterior](./get-started.md)
[Siguiente](./strong-naming.md)
