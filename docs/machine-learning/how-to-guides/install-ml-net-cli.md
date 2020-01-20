---
title: Cómo instalar la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET
description: Obtenga información sobre cómo instalar, cambiar a una versión anterior y desinstalar la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET.
ms.date: 12/18/2019
ms.openlocfilehash: 350122f2d2d2f03484ab6e272b482adf2094495c
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75739970"
---
# <a name="how-to-install-the-mlnet-command-line-interface-cli-tool"></a>Cómo instalar la herramienta de la interfaz de la línea de comandos (CLI) de ML.NET

Obtenga información sobre cómo instalar la CLI (interfaz de la línea de comandos) de ML.NET en Windows, Mac o Linux.

La CLI de ML.NET genera código fuente y modelos de ML.NET de buena calidad mediante el aprendizaje automático automatizado (AutoML) y un conjunto de datos de entrenamiento.

> [!NOTE]
> Este tema hace referencia a la CLI de ML.NET y AutoML de ML.NET, que se encuentran actualmente en versión preliminar, por lo que el material está sujeto a cambios.

## <a name="pre-requisites"></a>Requisitos previos

- [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2)

- (Opcional) [Visual Studio 2017 o 2019](https://visualstudio.microsoft.com/vs/)

Puede ejecutar los proyectos del código de C# generado con Visual Studio presionando la tecla `F5` o con `dotnet run` (CLI de .NET Core).

Nota: Si después de instalar el [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2) el comando `dotnet tool` no funciona, cierre la sesión de Windows y vuelva a iniciarla.

## <a name="install"></a>Instalar

La CLI de ML.NET se instala como cualquier otra herramienta global de dotnet. Use el comando de la CLI de .NET Core de `dotnet tool install`.

En el ejemplo siguiente se muestra cómo instalar la CLI de ML.NET en la ubicación de la fuente de NuGet predeterminada:

```dotnetcli
dotnet tool install -g mlnet
```

Si la herramienta no se puede instalar (es decir, si no está disponible con la fuente de NuGet predeterminada), se muestran mensajes de error. Verifique que se comprueban las fuentes que esperaba.

Si la instalación es correcta, se muestra un mensaje similar al siguiente con el comando que se usa para llamar a la herramienta y la versión instalada:

```console
You can invoke the tool using the following command: mlnet
Tool 'mlnet' (version 'X.X.X') was successfully installed.
```

Para confirmar que la instalación se realizó correctamente, escriba el comando siguiente:

```console
mlnet
```

Debería ver la Ayuda de los comandos disponibles para la herramienta de mlnet, como el comando "auto-train".

## <a name="install-a-specific-release-version"></a>Instalar una versión de lanzamiento específica

Si está intentando instalar una versión preliminar o una versión específica de la herramienta, puede especificar el [marco](../../standard/frameworks.md) con el formato siguiente:

```dotnetcli
dotnet tool install -g mlnet --framework <FRAMEWORK>
```

También puede comprobar si el paquete está instalado correctamente. Para ello, escriba el comando siguiente:

```dotnetcli
dotnet tool list -g
```

## <a name="uninstall-the-cli-package"></a>Desinstalar el paquete de la CLI

Escriba el siguiente comando para desinstalar el paquete de la máquina local:

```dotnetcli
dotnet tool uninstall mlnet -g
```

## <a name="update-the-cli-package"></a>Actualizar el paquete de la CLI

Escriba el siguiente comando para actualizar l paquete de la máquina local:

```dotnetcli
dotnet tool update -g mlnet
```

## <a name="set-up-cli-suggestions-tab-based-auto-completion"></a>Configure las sugerencias de la CLI (finalización automática basada en tabulación)

Puesto que la CLI de ML.NET se basa en `System.CommandLine`, tiene compatibilidad integrada para la finalización con tabulación.

En la siguiente animación se muestra un ejemplo de cómo funciona la finalización con tabulación automática:

![imagen](./media/cli-tab-completion.gif)

La "finalización automática basada en tabulación" (sugerencias de parámetro) funciona en *Windows PowerShell* y *bash de macOS/Linux*, pero no funcionará en *Windows CMD*.

Para habilitarla, en la versión preliminar actual, el usuario final debe realizar algunos pasos una vez por cada shell, los cuales se describen a continuación. Una vez que se realizó esta acción, las finalizaciones funcionarán para todas las aplicaciones escritas con `System.CommandLine`, como la CLI de ML.NET.

En el equipo donde desea habilitar la finalización, deberá hacer dos cosas.

1. Instale la herramienta global `dotnet-suggest` mediante la ejecución del comando siguiente:

    ```dotnetcli
    dotnet tool install dotnet-suggest -g
    ```

2. Agregue el script de correcciones de compatibilidad (shim) adecuado a su perfil de shell. Es posible que deba crear un archivo de perfil de shell. El script de correcciones de compatibilidad (shim) reenvía las solicitudes de finalización desde el shell a la herramienta `dotnet-suggest`, que delega a la aplicación basada en `System.CommandLine` adecuada.

    - Para bash, agregue el contenido de [dotnet-suggest-shim.bash](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.bash) a `~/.bash_profile`.

    - Para PowerShell, agregue el contenido del [dotnet-suggest-shim.ps1](https://github.com/dotnet/System.CommandLine/blob/master/src/System.CommandLine.Suggest/dotnet-suggest-shim.ps1) al perfil de PowerShell. Puede encontrar la ruta de acceso prevista para el perfil de PowerShell ejecutando el comando siguiente en la consola:

    ```console
    echo $profile
    ```

(Para otros shells, [busque](https://github.com/dotnet/System.CommandLine/issues?q=is%3Aissue+is%3Aopen+label%3A%22shell+suggestion%22) o abra una [incidencia](https://github.com/dotnet/System.CommandLine/issues).)

## <a name="installation-directory"></a>Directorio de instalación

La CLI de ML.NET puede instalarse en el directorio predeterminado o en una ubicación específica. Los directorios predeterminados son:

| SO          | Ruta de acceso                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Estas ubicaciones se agregan a la ruta de acceso del usuario cuando se ejecuta el SDK por primera vez, permitiendo así llamar directamente a las herramientas globales allí instaladas.

Nota: Las herramientas globales son específicas del usuario, no de la máquina. Específica del usuario significa que no se puede instalar una herramienta global que está disponible para todos los usuarios de la máquina. La herramienta solo está disponible para cada perfil de usuario en el que se instaló la herramienta.

Las herramientas globales también pueden instalarse en un directorio específico. Cuando se instalan en un directorio específico, el usuario debe incluir el directorio en la ruta de acceso a fin de asegurarse de que el comando está disponible. Hay dos maneras de hacerlo: llamar al comando con el directorio especificado, o llamar a la herramienta desde el directorio especificado.
En este caso, la CLI de .NET Core no agrega esta ubicación automáticamente a la variable de entorno PATH.

## <a name="see-also"></a>Vea también

- [Información general sobre la CLI de ML.NET](../automate-training-with-cli.md)
- [Tutorial: Análisis de opiniones mediante la CLI de ML.NET](../tutorials/sentiment-analysis-cli.md)
- [Guía de referencia de comandos de entrenamiento automático de la CLI de ML.NET](../reference/ml-net-cli-reference.md)
- [Telemetría en la CLI de ML.NET](../resources/ml-net-cli-telemetry.md)
