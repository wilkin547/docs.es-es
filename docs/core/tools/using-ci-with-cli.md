---
title: Integración continua (CI) con el SDK de .NET Core y herramientas
description: Aprenda a usar el SDK de .NET Core y sus herramientas en el servidor de compilación con la integración continua.
ms.date: 05/18/2017
ms.openlocfilehash: 724cc639a2588b085b31ff4590acce34d2380655
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537722"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a>Uso de .NET Core SDK y herramientas de integración continua (CI)

En este documento se describe el uso del SDK de .NET Core y sus herramientas en un servidor de compilación. El conjunto de herramientas de .NET Core funciona tanto de forma interactiva, donde un desarrollador escribe comandos en un símbolo del sistema, como de manera automática, donde un servidor de integración continua (CI) ejecuta un script de compilación. Los comandos, las opciones, las entradas y las salidas son los mismos, y solo lo que el usuario especifica sirve para adquirir las herramientas y un sistema para compilar la aplicación. Este documento se centra en escenarios de adquisición de herramientas de integración continua, donde además se ofrecen recomendaciones sobre cómo diseñar y estructurar los scripts de compilación.

## <a name="installation-options-for-ci-build-servers"></a>Opciones de instalación para los servidores de compilación de CI

### <a name="using-the-native-installers"></a>Uso de instaladores nativos

Los instaladores nativos están disponibles para macOS, Linux y Windows. Los instaladores requieren acceso de administrador (sudo) para el servidor de compilación. El instalador nativo ofrece la ventaja de que instala todas las dependencias nativas necesarias para la ejecución de las herramientas. Además, los instaladores nativos instalan el SDK en todo el sistema.

Los usuarios de macOS deben usar los instaladores PKG. En Linux, se ofrece la posibilidad de usar un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS, o de usar los mismos paquetes (DEB o RPM). En Windows, utilice el instalador MSI.

Los archivos binarios estables más recientes se encuentran en [Descargas de .NET](https://dotnet.microsoft.com/download). Si desea utilizar las herramientas de la última versión preliminar, que posiblemente sean inestables, use los vínculos proporcionados en el [repositorio de GitHub dotnet/core-sdk](https://github.com/dotnet/core-sdk#installers-and-binaries). Para las distribuciones de Linux, se encuentran disponibles los archivos `tar.gz` (conocidos también como `tarballs`); use los scripts de instalación dentro de los archivos para instalar .NET Core.

### <a name="using-the-installer-script"></a>Uso del script del instalador

El uso del script del instalador permite la instalación sin derechos administrativos en el servidor de compilación y una sencilla automatización para obtener las herramientas. El script se encarga de descargar las herramientas y extraerlas en una ubicación predeterminada o especificada para su uso. También puede especificar la versión de las herramientas que desea instalar y si prefiere instalar el SDK completo o solo el runtime compartido.

El script del instalador se puede automatizar para que se ejecute al principio de la compilación, a fin de obtener e instalar la versión deseada del SDK. La *versión deseada* se corresponde con cualquier versión del SKD que los proyectos necesitan para la compilación. El script permite instalar el SDK en un directorio local del servidor, ejecutar las herramientas desde la ubicación de instalación y limpiar después de la compilación, o bien dejar que el servicio de CI realice dicha limpieza. Esto permite encapsular y aislar todo el proceso de compilación. La referencia del script de instalación se encuentra en el artículo [dotnet-install](dotnet-install-script.md).

> [!NOTE]
> **Azure DevOps Services**
>
> Cuando se utiliza el script del instalador, las dependencias nativas no se instalan automáticamente. Debe instalarlas en caso de el sistema operativo no las incluya. Para obtener más información, vea [Dependencias y requisitos de .NET Core](../install/windows.md#dependencies).

## <a name="ci-setup-examples"></a>Ejemplos de configuración de CI

En esta sección se explica un procedimiento de instalación manual con un script de PowerShell o de Bash, además de incluir una descripción de varias soluciones de CI de software como servicio (SaaS). Las soluciones de CI de SaaS tratadas son [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) y [ Azure Pipelines](/azure/devops/pipelines/index).

### <a name="manual-setup"></a>Instalación manual

Cada servicio de SaaS tiene sus propios métodos para crear y configurar un proceso de compilación. Si usa una solución de SaaS distinta a las que indican o necesita realizar alguna personalización aparte de la compatibilidad preconfigurada, debe realizar al menos alguna configuración manual.

En general, para realizar una instalación manual, es necesario que adquiera una versión de las herramientas o las últimas compilaciones nocturnas de las herramientas y que, después, ejecute el script de compilación. Puede usar un script de PowerShell o de Bash para orquestar los comandos de .NET Core o utilizar un archivo del proyecto en el que se describa el proceso de compilación. En la [sección de orquestación](#orchestrating-the-build) se ofrece más información sobre estas opciones.

Después de crear un script que realiza una instalación manual del servidor de compilación de CI, úselo en el equipo de desarrollo para compilar el código de forma local con fines de pruebas. Cuando confirme que el script se ejecuta de forma correcta en el entorno local, impleméntelo en el servidor de compilación de CI. Un script de PowerShell relativamente sencillo demuestra cómo obtener el SDK de NET Core e instalarlo en un servidor de compilación de Windows:

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it
#   does, it's removed. This is not strictly required, but it's a
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

Debe proporcionar la implementación para el proceso de compilación al final del script. El script adquiere las herramientas y, después, ejecuta el proceso de compilación. En los equipos UNIX, el siguiente script de Bash realiza las acciones descritas en el script de PowerShell de forma similar:

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a>Travis CI

Puede configurar [Travis CI](https://travis-ci.org/) para instalar el SDK de .NET Core con el lenguaje `csharp` y la clave `dotnet`. Para más información, consulte los documentos oficiales de Travis CI en [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) (Compilación de un proyecto de C#, F# o Visual Basic). Al acceder a la información de Travis CI, observará que el identificador de lenguaje `language: csharp` de cuyo mantenimiento se encarga la comunidad funciona con todos los lenguajes de .NET, incluidos F# y Mono.

Travis CI se ejecuta tanto en trabajos de macOS como de Linux en una *matriz de compilación*, donde debe especificar una combinación de runtime, entorno y exclusiones/inclusiones para aceptar las combinaciones de compilación de la aplicación. Para más información, vea el artículo [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) (Personalización de la compilación) en la documentación de Travis CI. Las herramientas basadas en MSBuild incluyen los runtimes LTS (1.0.x) y Current (1.1.x) en el paquete; por tanto, cuando instala el SDK, recibe todo lo que necesita para la compilación.

### <a name="appveyor"></a>AppVeyor

[AppVeyor](https://www.appveyor.com/) instala el SDK de .NET Core 1.0.1 con la imagen de trabajo de compilación de `Visual Studio 2017`. Hay disponibles otras imágenes de compilación con distintas versiones del SDK de .NET Core. Para más información, consulte el [ejemplo appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) y el artículo [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) (Imágenes de trabajo de compilación) en los documentos de AppVeyor.

Los archivos binarios del SDK de .NET Core se descargan y descomprimen en un subdirectorio con la utilización del script de instalación y, después, se agregan a la variable de entorno `PATH`. Agregue una matriz de compilación para ejecutar las pruebas de integración con varias versiones del SDK de .NET Core:

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="azure-devops-services"></a>Azure DevOps Services

Configure Azure DevOps Services para compilar proyectos de .NET Core con alguno de estos enfoques:

1. Ejecute el script del [paso de instalación manual](#manual-setup) con sus comandos.
1. Cree una compilación compuesta de varias tareas de compilación integradas en Azure DevOps Services que están configuradas para usar herramientas de .NET Core.

Ambas soluciones son válidas. Con la utilización de un script de instalación manual, puede controlar la versión de las herramientas que recibe, ya que las descarga como parte de la compilación. La compilación se ejecuta desde un script que debe crear. En este artículo solo se trata la opción manual. Para más información sobre cómo elaborar una compilación con las tareas de compilación de Azure DevOps Services, consulte la documentación de [Azure Pipelines](/azure/devops/pipelines/index).

Para usar un script de instalación manual en Azure DevOps Services, cree una definición de compilación y especifique el script que va a ejecutar para el paso de compilación. Esto se realiza en la interfaz de usuario de Azure DevOps Services:

1. Empiece por crear una definición de compilación. Cuando llegue a la pantalla en la que se ofrece la opción de definir el tipo de compilación que desea crear, seleccione la opción **Vacío**.

   ![Selección de una definición de compilación vacía](./media/using-ci-with-cli/select-empty-build-definition.png)

1. Después de configurar el repositorio que va a compilar, se le remite a las definiciones de compilación. Seleccione **Agregar paso de compilación**:

   ![Agregar un paso de compilación](./media/using-ci-with-cli/add-build-step.png)

1. Se abre el **Catálogo de tareas**. El catálogo contiene tareas que se utilizan en la compilación. Como ya tiene un script, seleccione el botón **Agregar** en **PowerShell: Ejecute un script de PowerShell**.

   ![Paso para agregar un script de PowerShell](./media/using-ci-with-cli/add-powershell-script.png)

1. Configure el paso de compilación. Agregue el script desde el repositorio que se va a compilar:

   ![Especificar el script de PowerShell que va a ejecutar](./media/using-ci-with-cli/powershell-script-path.png)

## <a name="orchestrating-the-build"></a>Orquestación de la compilación

En la mayor parte de este documento se describe cómo adquirir las herramientas de .NET Core y configurar varios servicios de CI sin ofrecer información sobre cómo orquestar o *compilar realmente* el código con .NET Core. Las opciones para estructurar el proceso de compilación dependen de muchos factores que no se pueden tratar aquí en términos generales. Para más información sobre cómo orquestar las compilaciones con cada tecnología, explore los recursos y los ejemplos que se proporciona en los conjuntos de documentación de [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) y [Azure Pipelines](/azure/devops/pipelines/index).

Dos enfoques generales que se aplican para estructurar el proceso de compilación del código de .NET Core con herramientas de .NET Core consisten en utilizar directamente MSBuild o en usar los comandos de la línea de comandos de .NET Core. El enfoque que debe adoptar depende de lo cómo que se sienta con cada uno de ellos y de los inconvenientes que presente su complejidad. MSBuild ofrece la posibilidad de expresar el proceso de compilación como tareas y objetivos, pero presenta la complejidad añadida de tener que aprender la sintaxis del archivo de proyecto de MSBuild. Quizá sea más sencillo usar las herramientas de línea de comandos de .NET Core, pero, en este caso, es necesario escribir la lógica de orquestación en un lenguaje de scripting como `bash` o PowerShell.

## <a name="see-also"></a>Vea también

- [Descargas de .NET: Linux](https://dotnet.microsoft.com/download?initial-os=linux)
