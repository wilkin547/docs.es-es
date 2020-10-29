---
title: 'Plataformas de destino en proyectos de estilo SDK: .NET'
description: Obtenga información sobre las plataformas de destino para las aplicaciones y bibliotecas de .NET.
ms.date: 09/08/2020
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: 85bc05f07cfcc5f59a8a27790ee3d78a497cecdc
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223461"
---
# <a name="target-frameworks-in-sdk-style-projects"></a>Plataformas de destino en proyectos de estilo SDK

Cuando se dirige a un marco en una aplicación o biblioteca, debe especificar el conjunto de API que quiere poner a disposición de la aplicación o biblioteca. La plataforma de destino se especifica en el archivo del proyecto, mediante monikers de la plataforma de destino (TFM).

Una aplicación o biblioteca puede tener como destino una versión de [.NET Standard](net-standard.md). Las versiones de .NET Standard representan conjuntos estandarizados de API en todas las implementaciones de .NET. Por ejemplo, una biblioteca puede tener como destino .NET Standard 1.6 y obtener acceso a las API que funcionan en .NET Core y .NET Framework con el mismo código base.

Una aplicación o biblioteca también puede tener como destino una implementación específica de .NET para obtener acceso a las API específicas de la implementación. Por ejemplo, una aplicación que tenga como destino Xamarin.iOS (por ejemplo, `Xamarin.iOS10`) tiene acceso a contenedores de API de iOS proporcionados por Xamarin para iOS 10, o una aplicación que tenga como destino la Plataforma universal de Windows (UWP, `uap10.0`) tiene acceso a las API que compilan para dispositivos que ejecutan Windows 10.

Para algunas plataformas de destino (por ejemplo, .NET Framework), las API se definen mediante los ensamblados que el marco instala en un sistema y pueden incluir las API del marco de trabajo de la aplicación (por ejemplo, ASP.NET).

Para plataformas de destino basadas en paquetes (por ejemplo, .NET Standard y .NET Core), las API se definen mediante los paquetes incluidos en la aplicación o biblioteca. Un *metapaquete* es un paquete de NuGet que no tiene contenido propio, pero que es una lista de dependencias (otros paquetes). Una plataforma de destino basada en paquetes de NuGet especifica implícitamente un metapaquete que hace referencia a todos los paquetes que forman el marco de trabajo.

## <a name="latest-versions"></a>Últimas versiones

En la tabla siguiente se definen las plataformas de destino más comunes, cómo se hace referencia a ellas y la versión de [.NET Standard](net-standard.md) que implementan. Estas versiones de plataformas de destino son las últimas versiones estables. No se muestran las versiones preliminares. Un moniker de la plataforma de destino (TFM) es un formato de token normalizado para especificar la plataforma de destino de una aplicación o biblioteca de .NET.

| Marco de destino      | Latest <br/> versión estable | Moniker de la plataforma de destino (TFM) | Implementado <br/> versión de .NET Standard |
| :-: | :-: | :-: | :-: |
| .NET Standard         | 2.1                         | netstandard2.1                 | N/D                                     |
| .NET Core             | 3.1                         | netcoreapp3.1                  | 2.1                                     |
| .NET Framework        | 4.8                         | net48                          | 2.0                                     |

## <a name="supported-target-frameworks"></a>Plataformas de destino admitidas

Normalmente, un TFM hace referencia a una plataforma de destino. En la tabla siguiente, se muestran las plataformas de destino compatibles con el SDK de .NET y el cliente de NuGet. Los equivalentes se muestran entre corchetes. Por ejemplo, `win81` es un TFM equivalente a `netcore451`.

| Versión de .NET Framework de destino           | TFM |
| -------------------------- | --- |
| .NET 5 (y .NET Core)     | netcoreapp1.0<br>netcoreapp1.1<br>netcoreapp2.0<br>netcoreapp2.1<br>netcoreapp2.2<br>netcoreapp3.0<br>netcoreapp3.1<br>net5.0* |
| .NET Standard              | netstandard1.0<br>netstandard1.1<br>netstandard1.2<br>netstandard1.3<br>netstandard1.4<br>netstandard1.5<br>netstandard1.6<br>netstandard2.0<br>netstandard2.1 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Tienda Windows              | netcore [netcore45]<br>netcore45 [win] [win8]<br>netcore451 [win81] |
| .NET Micro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | wp [wp7]<br>wp7<br>wp75<br>wp8<br>wp81<br>wpa81 |
| Plataforma universal de Windows | uap [uap10.0]<br>uap10.0 [win10] [netcore50] |

\* Los TFM de.NET 5.0 y versiones posteriores incluyen variaciones específicas del sistema operativo. Para obtener más información, consulte la sección [TFM específicos del sistema operativo de .NET 5](#net-5-os-specific-tfms).

### <a name="net-5-os-specific-tfms"></a>TFM específicos del sistema operativo de .NET 5

Para cada TFM de.NET 5.0 y versiones posteriores, por ejemplo, `net5.0`, hay variaciones de TFM que incluyen enlaces específicos del sistema operativo. Estas variaciones se muestran en la tabla siguiente:

| Formato específico del sistema operativo | Ejemplo        |
|--------------------|----------------|
| \<base-tfm>-android | net5.0-android |
| \<base-tfm>-ios     | net5.0-ios     |
| \<base-tfm>-macos   | net5.0-macos   |
| \<base-tfm>-tvos    | net5.0-tvos    |
| \<base-tfm>-watchos | net5.0-watchos |
| \<base-tfm>-windows | net5.0-windows |

También puede especificar una versión opcional del sistema operativo, por ejemplo, `net5.0-ios12.0`.

Para obtener más información sobre los TFM de .NET 5, vea la página [Nombres de plataformas de destino en .NET 5](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md).

## <a name="how-to-specify-a-target-framework"></a>Procedimiento para especificar una plataforma de destino

Las plataformas de destino se especifican en un archivo del proyecto. Cuando especifique una única plataforma de destino, use el elemento **TargetFramework** . En el siguiente archivo de proyecto de aplicación de consola se muestra cómo elegir como destino .NET 5.0:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Al especificar varias plataformas de destino, puede hacer referencia de forma condicional a ensamblados para cada plataforma de destino. En el código, puede compilar de forma condicional en esos ensamblados utilizando símbolos de preprocesador con lógica *if-then-else* .

El siguiente proyecto de biblioteca tiene como destino las API de .NET Standard (`netstandard1.4`) y de .NET Framework (`net40` y `net45`). Use el elemento **TargetFrameworks** plural con varias plataformas de destino. Los atributos `Condition` incluyen paquetes específicos de la implementación cuando se compila la biblioteca para los dos TFM de .NET Framework:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

Dentro de su aplicación o biblioteca, puede escribir código condicional mediante [directivas de preprocesador](../csharp/language-reference/preprocessor-directives/preprocessor-if.md) para compilar para cada plataforma de destino:

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

El sistema de compilación es consciente de los símbolos de preprocesador que representan las plataformas de destino que se muestran en la tabla [Versiones compatibles de las plataformas de destino](#supported-target-frameworks) cuando se usan proyectos de estilo SDK. Cuando use un símbolo que representa un TFM de .NET Standard, .NET Core o .NET 5, reemplace los puntos y guiones por un carácter de subrayado y cambie las letras minúsculas por mayúsculas (por ejemplo, el símbolo de `netstandard1.4` es `NETSTANDARD1_4`).

La lista completa de símbolos de preprocesador para plataformas de destino de .NET es la siguiente:

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>Plataformas de destino en desuso

Las siguientes plataformas de destino están en desuso. Los paquetes que tienen como destino estas plataformas deben migrarse a los reemplazos indicados.

| TFM en desuso                                                                             | Replacement |
| ------------------------------------------------------------------------------------------ | ----------- |
| aspnet50<br>aspnetcore50<br>dnxcore50<br>dnx<br>dnx45<br>dnx451<br>dnx452                  | netcoreapp  |
| dotnet<br>dotnet50<br>dotnet51<br>dotnet52<br>dotnet53<br>dotnet54<br>dotnet55<br>dotnet56 | netstandard |
| netcore50                                                                                  | uap10.0     |
| win                                                                                        | netcore45   |
| win8                                                                                       | netcore45   |
| win81                                                                                      | netcore451  |
| win10                                                                                      | uap10.0     |
| winrt                                                                                      | netcore45   |

## <a name="see-also"></a>Vea también

- [Desarrollo de bibliotecas con herramientas multiplataforma](../core/tutorials/libraries.md)
- [.NET Standard](net-standard.md)
- [Control de versiones de .NET Core](../core/versions/index.md)
- [Repositorio de GitHub dotnet/standard](https://github.com/dotnet/standard)
- [Repositorio de GitHub de herramientas de NuGet](https://github.com/joelverhagen/NuGetTools)
- [Framework Profiles in .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html) (Perfiles de marco de trabajo en .NET)
