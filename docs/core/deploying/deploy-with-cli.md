---
title: Publicación de aplicaciones con la CLI de .NET
description: Aprenda a publicar una aplicación .NET mediante los comandos de la CLI de .NET.
author: adegeo
ms.author: adegeo
ms.date: 02/05/2021
dev_langs:
- csharp
- vb
ms.openlocfilehash: d2695b1f271e57bb44ed3f94acbbe17b830fdd60
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255701"
---
# <a name="publish-net-apps-with-the-net-cli"></a>Publicación de aplicaciones de .NET con la CLI de .NET

En este artículo se muestra cómo se puede publicar la aplicación .NET desde la línea de comandos. .NET proporciona tres maneras de publicar las aplicaciones. La implementación dependiente de la plataforma genera un archivo .dll multiplataforma que usa el entorno de ejecución de .NET instalado localmente. La implementación dependiente de la plataforma genera un archivo ejecutable específico de la plataforma que usa el entorno de ejecución de .NET instalado localmente. El archivo ejecutable independiente genera un archivo ejecutable específico de la plataforma e incluye una copia local del entorno de ejecución de .NET.

Para obtener información general sobre estos modos de publicación, consulte [Implementación de aplicaciones .NET](index.md).

¿Busca ayuda rápida sobre el uso de la CLI? En la tabla siguiente se muestran algunos ejemplos de cómo publicar la aplicación. La plataforma de destino se puede especificar con el parámetro `-f <TFM>` o si edita el archivo de proyecto. Para más información, vea [Conceptos básicos de publicación](#publishing-basics).

| Modo de publicación                   | Versión del SDK | Comando                                                     |
|--------------------------------|-------------|-------------------------------------------------------------|
| [Implementación dependiente de marco de trabajo](#framework-dependent-deployment) | 2.1         | `dotnet publish -c Release`                                 |
|                                | 3.1         | `dotnet publish -c Release -p:UseAppHost=false`             |
|                                | 5.0         | `dotnet publish -c Release -p:UseAppHost=false`             |
| [Archivo ejecutable dependiente de la plataforma](#framework-dependent-executable) | 3.1         | `dotnet publish -c Release -r <RID> --self-contained false`<br>`dotnet publish -c Release` |
|                                | 5.0         | `dotnet publish -c Release -r <RID> --self-contained false`<br>`dotnet publish -c Release` |
| [Implementación autocontenida](#self-contained-deployment)      | 2.1         | `dotnet publish -c Release -r <RID> --self-contained true`  |
|                                | 3.1         | `dotnet publish -c Release -r <RID> --self-contained true`  |
|                                | 5.0         | `dotnet publish -c Release -r <RID> --self-contained true`  |

\* Si se usa el **SDK versión 3.1** o superiores, el archivo ejecutable dependiente de la plataforma es el modo de publicación predeterminado cuando se ejecuta el comando `dotnet publish` básico.

> [!NOTE]
> El parámetro `-c Release` no es necesario. Se le proporciona como recordatorio para publicar la compilación de la **versión** de la aplicación.

## <a name="publishing-basics"></a>Conceptos básicos de publicación

El valor `<TargetFramework>` del archivo de proyecto especifica la plataforma de destino predeterminada al publicar la aplicación. Se puede cambiar la plataforma de destino a cualquier [moniker de la plataforma de destino (TFM)](../../standard/frameworks.md). Por ejemplo, si en el proyecto se usa `<TargetFramework>netcoreapp2.1</TargetFramework>`, se crea un archivo binario que tiene como destino .NET Core 2.1. El TFM especificado en esta configuración es el destino predeterminado que usa el comando [`dotnet publish`](../tools/dotnet-publish.md).

Si quiere tener como destino más de una plataforma, puede establecer el valor `<TargetFrameworks>` en varios valores de TFM separados por punto y coma. Al crear la aplicación, se genera una compilación para cada plataforma de destino. Sin embargo, al publicar la aplicación, debe especificar la versión de la plataforma de destino con el comando `dotnet publish -f <TFM>`.

A menos que se establezca otro, el directorio de salida del comando [`dotnet publish`](../tools/dotnet-publish.md) es `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`. El modo **BUILD-CONFIGURATION** predeterminado es **Depurar** a menos que se cambie con el parámetro `-c`. Por ejemplo, `dotnet publish -c Release -f netcoreapp2.1` publica en `./bin/Release/netcoreapp2.1/publish/`.

Si usa SDK de .NET Core 3.1 o una versión posterior, el modo de publicación predeterminado es un _ejecutable_ dependiente de la plataforma.

Si utiliza SDK de .NET Core 2,1, el modo de publicación predeterminado es de la _implementación_ dependiente de la plataforma.

### <a name="native-dependencies"></a>Dependencias nativas

Si la aplicación tiene dependencias nativas, es posible que no funcione en otro sistema operativo. Por ejemplo, si en la aplicación se usa la API Windows nativa, no se ejecutará en macOS o Linux. Tendrá que proporcionar código específico de la plataforma y compilar un archivo ejecutable para cada plataforma.

Tenga en cuenta también que, si una biblioteca a la que se hace referencia tiene una dependencia nativa, es posible que la aplicación no se ejecute en todas las plataformas. Pero es posible que un paquete NuGet al que se hace referencia incluya versiones específicas de la plataforma para controlar de forma automática las dependencias nativas necesarias.

Al distribuir una aplicación con dependencias nativas, es posible que tenga que usar el modificador `dotnet publish -r <RID>` para especificar la plataforma de destino para la que se quiere publicar. Para obtener una lista de identificadores de tiempo de ejecución, vea [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md).

En las secciones [Archivo ejecutable dependiente de la plataforma](#framework-dependent-executable) e [Implementación autocontenida](#self-contained-deployment) se ofrece más información sobre los archivos binarios específicos de la plataforma.

## <a name="sample-app"></a>Aplicación de ejemplo

Puede usar la siguiente aplicación para explorar los comandos de publicación. La aplicación se crea mediante la ejecución de los comandos siguientes en el terminal:

```dotnetcli
mkdir apptest1
cd apptest1
dotnet new console
dotnet add package Figgle
```

Es necesario cambiar el archivo `Program.cs` o `Program.vb` que genera la plantilla de consola por lo siguiente:

```csharp
using System;

namespace apptest1
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"));
        }
    }
}
```

```vb
Module Program
    Sub Main(args As String())
        Console.WriteLine(Figgle.FiggleFonts.Standard.Render("Hello, World!"))
    End Sub
End Module
```

Al ejecutar la aplicación ([`dotnet run`](../tools/dotnet-run.md)), se muestra el resultado siguiente:

```terminal
  _   _      _ _         __        __         _     _ _
 | | | | ___| | | ___    \ \      / /__  _ __| | __| | |
 | |_| |/ _ \ | |/ _ \    \ \ /\ / / _ \| '__| |/ _` | |
 |  _  |  __/ | | (_) |    \ V  V / (_) | |  | | (_| |_|
 |_| |_|\___|_|_|\___( )    \_/\_/ \___/|_|  |_|\__,_(_)
                     |/
```

## <a name="framework-dependent-deployment"></a>Implementación dependiente de marco de trabajo

Para la CLI del SDK de .NET 2.1, la implementación dependiente de la plataforma (FDD) es el modo predeterminado para el comando `dotnet publish` básico. En los SDK más recientes, el [archivo ejecutable dependiente de la plataforma](#framework-dependent-executable) es el valor predeterminado.

Cuando la aplicación se publica como una FDD, se crea un archivo `<PROJECT-NAME>.dll` en la carpeta `./bin/<BUILD-CONFIGURATION>/<TFM>/publish/`. Para ejecutar la aplicación, vaya a la carpeta de salida y use el comando `dotnet <PROJECT-NAME>.dll`.

La aplicación está configurada para tener como destino una versión específica de .NET. Es obligatorio que ese entorno de ejecución de .NET de destino esté en cualquier equipo donde se ejecute la aplicación. Por ejemplo, si la aplicación tiene como destino .NET Core 3.1, todas las máquinas en las que se ejecute la aplicación deben tener instalado el entorno de ejecución de .NET Core 3.1. Como se indica en la sección [Conceptos básicos de publicación](#publishing-basics), se puede editar el archivo de proyecto para cambiar la plataforma de destino predeterminada o seleccionar más de una como destino.

Al publicar una FDD se crea una aplicación que realiza la puesta al día automática a la revisión de seguridad de .NET más reciente disponible en el sistema en el que se ejecuta la aplicación. Para más información sobre el enlace de versión en tiempo de compilación, consulte [Selección de la versión de .NET que se va a usar](../versions/selection.md#framework-dependent-apps-roll-forward).

| Modo de publicación                   | Versión del SDK | Comando                                                     |
|--------------------------------|-------------|-------------------------------------------------------------|
| Implementación dependiente de marco de trabajo | 2.1         | `dotnet publish -c Release`                                 |
|                                | 3.1         | `dotnet publish -c Release -p:UseAppHost=false`             |
|                                | 5.0         | `dotnet publish -c Release -p:UseAppHost=false`             |

## <a name="framework-dependent-executable"></a>Archivo ejecutable dependiente de la plataforma

Para la CLI del SDK de .NET 5 (y .NET Core 3.1), el archivo ejecutable dependiente de la plataforma (FDE) es el modo predeterminado para el comando `dotnet publish` básico. No es necesario especificar ningún otro parámetro, siempre que se quiera establecer como destino el sistema operativo actual.

En este modo, se crea un host ejecutable específico de la plataforma para hospedar la aplicación multiplataforma. Este modo es similar a FDD, ya que requiere un host en forma del comando `dotnet`. El nombre de archivo ejecutable de host varía según la plataforma y es similar a `<PROJECT-FILE>.exe`. Este archivo ejecutable se puede ejecutar directamente en lugar de llamar a `dotnet <PROJECT-FILE>.dll`, que sigue siendo una forma aceptable de ejecutar la aplicación.

La aplicación está configurada para tener como destino una versión específica de .NET. Es obligatorio que ese entorno de ejecución de .NET de destino esté en cualquier equipo donde se ejecute la aplicación. Por ejemplo, si la aplicación tiene como destino .NET Core 3.1, todas las máquinas en las que se ejecute la aplicación deben tener instalado el entorno de ejecución de .NET Core 3.1. Como se indica en la sección [Conceptos básicos de publicación](#publishing-basics), se puede editar el archivo de proyecto para cambiar la plataforma de destino predeterminada o seleccionar más de una como destino.

Al publicar un FDE se crea una aplicación que realiza la puesta al día automática a la revisión de seguridad de .NET más reciente disponible en el sistema en el que se ejecuta la aplicación. Para más información sobre el enlace de versión en tiempo de compilación, consulte [Selección de la versión de .NET que se va a usar](../versions/selection.md#framework-dependent-apps-roll-forward).

Para .NET 2.1, debe usar los modificadores siguientes con el comando `dotnet publish` para publicar un FDE:

- `-r <RID>` Este modificador usa un identificador (RID) para especificar la plataforma de destino. Para obtener una lista de identificadores de tiempo de ejecución, vea [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md).

- `--self-contained false` Este modificador deshabilita el comportamiento predeterminado del modificador `-r`, que consiste en crear una implementación autocontenida (SCD). Este modificador crea un FDE.

| Modo de publicación                   | Versión del SDK | Comando                                                     |
|--------------------------------|-------------|-------------------------------------------------------------|
| Archivo ejecutable dependiente de la plataforma | 3.1         | `dotnet publish -c Release -r <RID> --self-contained false`<br>`dotnet publish -c Release` |
|                                | 5.0         | `dotnet publish -c Release -r <RID> --self-contained false`<br>`dotnet publish -c Release` |

Siempre que se usa el modificador `-r`, la ruta de acceso de la carpeta de salida cambia a: `./bin/<BUILD-CONFIGURATION>/<TFM>/<RID>/publish/`

Si usa la [aplicación de ejemplo](#sample-app), ejecute `dotnet publish -f net5.0 -r win10-x64 --self-contained false`. Este comando crea el archivo ejecutable siguiente: `./bin/Debug/net5.0/win10-x64/publish/apptest1.exe`

> [!NOTE]
> Puede reducir el tamaño total de la implementación si habilita el **modo de globalización invariable**. Este modo es útil para las aplicaciones que no son globales y que pueden usar las convenciones de formato, las de mayúsculas y minúsculas, y el criterio de ordenación y la comparación de cadenas de la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture). Para más información sobre el **modo de globalización invariable** y cómo habilitarlo, consulte [Modo de globalización invariable de .NET](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

## <a name="self-contained-deployment"></a>Implementación autocontenida

Cuando se publica una implementación autocontenida (SCD), el SDK de .NET crea un archivo ejecutable específico de la plataforma. La publicación de una SCD incluye todos los archivos de .NET necesarios para ejecutar la aplicación, pero no incluye las [dependencias nativas de .NET](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md). Estas dependencias deben estar presentes en el sistema antes de ejecutar la aplicación.

Al publicar una SCD, se crea una aplicación que no se pone al día a la revisión de seguridad de .NET más reciente disponible. Para más información sobre el enlace de versión en tiempo de compilación, consulte [Selección de la versión de .NET que se va a usar](../versions/selection.md#self-contained-deployments-include-the-selected-runtime).

Debe usar los modificadores siguientes con el comando `dotnet publish` para publicar una SCD:

- `-r <RID>` Este modificador usa un identificador (RID) para especificar la plataforma de destino. Para obtener una lista de identificadores de tiempo de ejecución, vea [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md).

- `--self-contained true` Este modificador indica al SDK de .NET Core que cree un archivo ejecutable como una SCD.

| Modo de publicación                   | Versión del SDK | Comando                                                     |
|--------------------------------|-------------|-------------------------------------------------------------|
| Implementación autocontenida      | 2.1         | `dotnet publish -c Release -r <RID> --self-contained true`  |
|                                | 3.1         | `dotnet publish -c Release -r <RID> --self-contained true`  |
|                                | 5.0         | `dotnet publish -c Release -r <RID> --self-contained true`  |

> [!NOTE]
> Puede reducir el tamaño total de la implementación si habilita el **modo de globalización invariable**. Este modo es útil para las aplicaciones que no son globales y que pueden usar las convenciones de formato, las de mayúsculas y minúsculas, y el criterio de ordenación y la comparación de cadenas de la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture). Para más información sobre el **modo de globalización invariable** y cómo habilitarlo, vea [Modo de globalización invariable de .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).

## <a name="see-also"></a>Vea también

- [Introducción a la implementación de aplicaciones .NET](index.md)
- [Catálogo de identificadores de entorno de ejecución (RID) de .NET](../rid-catalog.md)
