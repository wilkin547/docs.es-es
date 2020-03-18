---
title: 'Paquetes, metapaquetes y marcos de trabajo: .NET Core'
description: Aprenda la terminología sobre paquetes, metapaquetes y marcos de trabajo.
author: richlander
ms.date: 06/20/2016
ms.openlocfilehash: 657519edf1c0860ee3222c71ce85723e19029a9d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397936"
---
# <a name="packages-metapackages-and-frameworks"></a>Paquetes, metapaquetes y marcos

.NET Core es una plataforma conformada por paquetes NuGet. Algunas experiencias del producto se benefician de la definición específica de los paquetes, mientras que otras lo hacen de la definición general de las mismas. Para dar cabida a esta dualidad, .NET Core se distribuye como un conjunto específico de paquetes y en fragmentos más generales con un tipo de paquete que recibe informalmente el nombre de [metapaquete](#metapackages).

Cada uno de los paquetes de .NET Core admite su ejecución en varias implementaciones .NET, que se representan como marcos. Algunos de estos son marcos tradicionales, como `net46`, que representa a .NET Framework. Otro conjunto son marcos de trabajo nuevos que se pueden considerar "marcos de trabajo basados en paquete", que establecen un modelo nuevo para definir los marcos de trabajo. Estos marcos basados en paquete están completamente creados y definidos como paquetes, lo que establece una fuerte relación entre los paquetes y los marcos.

## <a name="packages"></a>Paquetes

.NET Core se divide en un conjunto de paquetes que proporcionan primitivas, tipos de datos de nivel superior, tipos de composición de aplicaciones y utilidades comunes. Cada uno de estos paquetes representa un solo ensamblado del mismo nombre. Por ejemplo, el [paquete System.Runtime](https://www.nuget.org/packages/System.Runtime) contiene System.Runtime.dll.

Hay ventajas si los paquetes se definen de manera específica:

- Los paquetes específicos se pueden enviar según su propia programación con una prueba relativamente limitada de los otros paquetes.
- Los paquetes específicos pueden brindar compatibilidad con distintos SO y CPU.
- Los paquetes específicos pueden tener dependencias específicas solo para una biblioteca.
- Las aplicaciones son más pequeñas, porque los paquetes a los que no se hace referencia no forman parte de la distribución de aplicaciones.

Algunas de estas ventajas solo se usan bajo ciertas circunstancias. Por ejemplo, los paquetes de .NET Core normalmente se envían en la misma programación con la misma compatibilidad de plataforma. En el caso del mantenimiento, las correcciones se pueden distribuir e instalar como pequeñas actualizaciones de paquetes únicos. Debido al alcance limitado del cambio, la validación y el tiempo para que una corrección esté disponible están limitados a las necesidades de una biblioteca única.

A continuación se muestra una lista de los paquetes NuGet clave para .NET Core:

- [System.Runtime](https://www.nuget.org/packages/System.Runtime): el paquete más fundamental de .NET Core, que incluye <xref:System.Object>, <xref:System.String>, <xref:System.Array>, <xref:System.Action> y <xref:System.Collections.Generic.IList%601>.
- [System.Collections](https://www.nuget.org/packages/System.Collections): un conjunto de colecciones genéricas (principalmente), que incluye <xref:System.Collections.Generic.List%601> y <xref:System.Collections.Generic.Dictionary%602>.
- [System.Net.Http](https://www.nuget.org/packages/System.Net.Http): un conjunto de tipos de comunicación de red HTTP, que incluye <xref:System.Net.Http.HttpClient> y <xref:System.Net.Http.HttpResponseMessage>.
- [System.IO.FileSystem](https://www.nuget.org/packages/System.IO.FileSystem): un conjunto de tipos de lectura y escritura en un almacenamiento basado en disco local o en red, y que incluye <xref:System.IO.File> y <xref:System.IO.Directory>.
- [System.Linq](https://www.nuget.org/packages/System.Linq): un conjunto de tipos para consultar objetos, que incluye `Enumerable` y <xref:System.Linq.ILookup%602>.
- [System.Reflection](https://www.nuget.org/packages/System.Reflection): un conjunto de tipos para cargar, inspeccionar y activar tipos, que incluye <xref:System.Reflection.Assembly>, <xref:System.Reflection.TypeInfo> y <xref:System.Reflection.MethodInfo>.

Normalmente, en lugar de incluir cada paquete, es más fácil y más sólido incluir un [metapaquete](#metapackages). En cambio, cuando necesite un solo paquete, puede incluirlo como en el ejemplo siguiente, que hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.6</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

## <a name="metapackages"></a>Metapaquetes

Un metapaquete es una conversión de paquetes NuGet que se usa para describir un conjunto de paquetes que tienen sentido de forma conjunta. Para representar este conjunto de paquetes, lo transforma en dependencias. De manera opcional, el metapaquete puede especificar un marco a fin de establecer uno para este conjunto de paquetes.

De manera predeterminada, las versiones anteriores de las herramientas de .NET Core (las herramientas basadas en project.json y csproj) especificaban un marco y un metapaquete. Pero, actualmente, el marco de destino hace referencia implícitamente al metapaquete, de manera que cada uno está asociado a un marco de destino. Por ejemplo, el marco `netstandard1.6` hace referencia al metapaquete de la versión 1.6.0 de NetStandard.Library. De manera similar, el marco `netcoreapp2.1` hace referencia al metapaquete de la versión 2.1.0 de Microsoft.NETCore.App. Para obtener más información, vea [Implicit metapackage package reference in the .NET Core SDK](https://github.com/dotnet/core/blob/master/release-notes/1.0/sdk/1.0-rc3-implicit-package-refs.md) (Referencia del paquete implícita del metapaquete en el SDK de .NET Core).

Dirigirse a un marco y hacer referencia implícitamente a un metapaquete significa que, realmente, se está agregando una referencia a cada uno de sus paquetes dependientes como un gesto único. Esto hace que todas las bibliotecas de esos paquetes estén disponibles para IntelliSense (o una experiencia similar) y para publicar la aplicación.

Usar metapaquetes tiene ventajas:

- Proporciona una experiencia del usuario adecuada para hacer referencia a un gran conjunto de paquetes específicos.
- Define un conjunto de paquetes (incluidas las versiones específicas) que se prueban y trabajan correctamente en conjunto.

El metapaquete del estándar .NET es:

- [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library): describe las bibliotecas que forman parte de .NET Standard. Se aplica a todas las implementaciones .NET (por ejemplo, .NET Framework, .NET Core y Mono) que admiten .NET Standard. Establece el marco de `netstandard`.

Los metapaquetes principales de .NET Core son:

- [Microsoft.NETCore.App](https://www.nuget.org/packages/Microsoft.NETCore.App): describe las bibliotecas que forman parte de la distribución de .NET Core. Establece el marco de `.NETCoreApp`. Depende del `NETStandard.Library` más pequeño.
- [Microsoft.AspNetCore.All](https://www.nuget.org/packages/Microsoft.AspNetCore.App): incluye todos los paquetes admitidos de ASP.NET Core y Entity Framework Core, excepto aquellos que contienen dependencias de terceros. Vea [Metapaquete Microsoft.AspNetCore.All para ASP.NET Core](/aspnet/core/fundamentals/metapackage-app) para más información.
- [Microsoft.AspNetCore.All](https://www.nuget.org/packages/Microsoft.AspNetCore.All): incluye todos los paquetes admitidos de ASP.NET Core, Entity Framework Core y las dependencias internas y de terceros que usan ASP.NET Core y Entity Framework Core. Consulte [Microsoft.AspNetCore.All metapackage for ASP.NET Core 2.x](/aspnet/core/fundamentals/metapackage) (Metapaquete Microsoft.AspNetCore.All para ASP.NET Core 2.x) para obtener más información.
- [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility): un conjunto de fachadas de compatibilidad que permite que las Bibliotecas de clases portables (PCL) basadas en mscorlib se ejecuten en .NET Core.

## <a name="frameworks"></a>Marcos de trabajo

Cada paquete de .NET Core admite un conjunto de marcos en tiempo de ejecución. Los marcos de trabajo describen un conjunto de API disponible (y posiblemente también otras características) en que puede basarse cuando tiene como destino un marco de trabajo determinado. Se crean versiones suyas cada vez que se agregan API nuevas.

Por ejemplo, [System.IO.FileSystem](https://www.nuget.org/packages/System.IO.FileSystem) admite los siguientes marcos de trabajo:

- .NETFramework,Version=4.6
- .NETStandard,Version=1.3
- 6 plataformas Xamarin (por ejemplo, xamarinios10)

Es útil contrastar los dos primeros de estos marcos, ya que son ejemplos de las dos formas distintas en las que estos se definen:

- El marco de `.NETFramework,Version=4.6` representa las API disponibles en .NET Framework 4.6. Se pueden generar bibliotecas compiladas con los ensamblados de referencia de .NET Framework 4.6 y, luego, distribuir esas bibliotecas en paquetes NuGet en una carpeta net46 lib. Se usará para las aplicaciones que tienen como destino .NET Framework 4.6 o que son compatibles con esa plataforma. Esta es la forma de trabajar tradicional de todos los marcos de trabajo.

- El marco de trabajo `.NETStandard,Version=1.3` está basado en paquete. Se basa en paquetes que tienen como destino el marco de trabajo para definir y exponer las API en términos del marco de trabajo.

## <a name="package-based-frameworks"></a>Marcos de trabajo basados en paquete

Existe una relación recíproca entre los marcos de trabajo y los paquetes. La primera parte es definir las API disponibles para un marco de trabajo determinado, por ejemplo, `netstandard1.3`. Los paquetes que tienen como destino `netstandard1.3` (o marcos de trabajo compatibles, como `netstandard1.0`) definen las API disponibles para `netstandard1.3`. Esto puede parecer una definición circular, pero no lo es. En virtud de estar "basada en paquete", la definición de API del marco de trabajo proviene de los paquetes. El marco de trabajo mismo no define a ninguna API.

La segunda parte de la relación es la selección de recursos. Los paquetes pueden incluir recursos para varios marcos de trabajo. Dada una referencia a un conjunto de paquetes o metapaquetes, el marco de trabajo es necesario para determinar el recurso que se debe seleccionar, por ejemplo `net46` o `netstandard1.3`. Es importante seleccionar el recurso correcto. Por ejemplo, es poco probable que un recurso de `net46` sea compatible con .NET Framework 4.0 o .NET Core 1.0.

Puede ver esta relación en la imagen siguiente. La *API* tiene como destino el *marco de trabajo* y lo define. El *marco de trabajo* se usa para la *selección de recursos*. El *recurso* le brinda la API.

![Composición del marco de trabajo basado en paquete](./media/packages/package-framework.png)

Los dos principales marcos de trabajo basados en paquete que se usan con .NET Core son los siguientes:

- `netstandard`
- `netcoreapp`

### <a name="net-standard"></a>.NET Standard

El marco .NET Standard ([moniker de la plataforma de destino](../standard/frameworks.md): `netstandard`) representa las API definidas por [.NET Standard](../standard/net-standard.md) y que se basan en esta especificación. Las bibliotecas diseñadas para ejecutarse en varios entornos de ejecución deben tener como destino este marco de trabajo. Se admiten en cualquier runtime compatible con .NET Standard, como .NET Core, .NET Framework y Mono/Xamarin. Cada uno de estos entornos de ejecución admite un conjunto de versiones del estándar .NET, en función de las API que implementan.

El marco `netstandard` hace referencia implícitamente al metapaquete [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library). Por ejemplo, el siguiente archivo del proyecto de MSBuild indica que el proyecto tiene como destino `netstandard1.6`, que hace referencia al metapaquete de la [versión 1.6 de `NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library/1.6.0).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.6</TargetFramework>
  </PropertyGroup>
</Project>
```

En cambio, las referencias del metapaquete y el marco en el archivo del proyecto no necesitan coincidir, y puede usar el elemento `<NetStandardImplicitPackageVersion>` en su archivo del proyecto para especificar una versión de marco que sea anterior a la del metapaquete. Por ejemplo, el siguiente archivo del proyecto es válido.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

Puede parecer extraño establecer `netstandard1.3` como destino pero usa la versión 1.6.0 de `NETStandard.Library`. Se trata de un caso de uso válido, debido a que el metapaquete mantiene la compatibilidad con versiones anteriores de `netstandard`. Podría ser el caso que estandarizó en la versión 1.6.0 del metapaquete y úselo para todas las bibliotecas, que establecen como destino distintas versiones de `netstandard`. Con este enfoque, solo necesita restaurar `NETStandard.Library` 1.6.0 y no las versiones anteriores.

Lo contrario no sería válido: establecer `netstandard1.6` como destino con la versión 1.3.0 de `NETStandard.Library`. No puede establecer como destino un marco de trabajo superior con un metapaquete inferior, debido a que el metapaquete de una versión inferior no expondrá ningún recurso para ese marco de trabajo superior. El esquema de control de versiones para los metapaquetes afirma que estos coinciden con la versión más reciente del marco de trabajo que describen. En virtud del esquema de control de versiones, la primera versión de `NETStandard.Library` es v1.6.0, siempre que contenga recursos de `netstandard1.6`. (A efectos de simetría con el ejemplo anterior, aquí se usa v1.3.0, pero en realidad no existe).

### <a name="net-core-application"></a>Aplicación .NET Core

El marco .NET Core ([moniker de la plataforma de destino](../standard/frameworks.md): `netcoreapp`) representa los paquetes y las API asociadas que se incluyen en la distribución de .NET Core y el modelo de aplicación de consola que proporciona. Las aplicaciones .NET Core deben usar este marco de trabajo, debido a que intentan establecer el modelo de aplicación de consola como destino, al igual que las bibliotecas que se pretende ejecutar solo en .NET Core. Usar este marco de trabajo restringe a las aplicaciones y bibliotecas solo a su ejecución en .NET Core.

El metapaquete `Microsoft.NETCore.App` tiene como destino el marco de trabajo `netcoreapp`. Proporciona acceso aproximadamente a 60 bibliotecas, de las cuales el paquete `NETStandard.Library` proporciona unas 40, además de otras 20. Puede hacer referencia a bibliotecas adicionales que establecen como destino a `netcoreapp` o marcos de trabajo compatibles, como `netstandard`, para obtener acceso a API adicionales.

La mayoría de las bibliotecas adicionales que `Microsoft.NETCore.App` proporciona también establecen como destino a `netstandard`, dado que otras bibliotecas `netstandard` satisfacen sus dependencias. Esto significa que las bibliotecas `netstandard` también pueden hacer referencia a esos paquetes como dependencias.
