---
title: "Uso de .NET Core SDK y herramientas de integración continua (CI) | Microsoft Docs"
description: "Información sobre el uso del SDK de .NET Core y sus herramientas en el servidor de compilación."
keywords: .NET, .NET Core, continuous integration, ci, build, automation, Travis CI, AppVeyor, Visual Studio Team Services, vsts
author: guardrex
ms.author: mairaw
ms.date: 05/18/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0d6e1e34-277c-4aaf-9880-3ebf81023857
ms.translationtype: Human Translation
ms.sourcegitcommit: 5af11b469f906b7c074f127704eb338a78a62b34
ms.openlocfilehash: a13f6b80248a659bda23baece3638e33a166b5df
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---

# Uso de .NET Core SDK y herramientas de integración continua (CI)
<a id="using-net-core-sdk-and-tools-in-continuous-integration-ci" class="xliff"></a>

## Información general
<a id="overview" class="xliff"></a>

En este documento se describe el uso del SDK de .NET Core y sus herramientas en un servidor de compilación. El conjunto de herramientas de .NET Core funciona tanto de forma interactiva, donde un desarrollador escribe comandos en un símbolo del sistema, como de manera automática, donde un servidor de integración continua (CI) ejecuta un script de compilación. Los comandos, las opciones, las entradas y las salidas son los mismos, y solo lo que el usuario especifica sirve para adquirir las herramientas y un sistema para compilar la aplicación. Este documento se centra en escenarios de adquisición de herramientas de integración continua, donde además se ofrecen recomendaciones sobre cómo diseñar y estructurar los scripts de compilación.

## Opciones de instalación para los servidores de compilación de CI
<a id="installation-options-for-ci-build-servers" class="xliff"></a>

### Uso de instaladores nativos
<a id="using-the-native-installers" class="xliff"></a>

Los instaladores nativos están disponibles para macOS, Linux y Windows. Los instaladores requieren acceso de administrador (sudo) para el servidor de compilación. El instalador nativo ofrece la ventaja de que instala todas las dependencias nativas necesarias para la ejecución de las herramientas. Además, los instaladores nativos instalan el SDK en todo el sistema.

Los usuarios de macOS deben usar los instaladores PKG. En Linux, se ofrece la posibilidad de usar un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS, o de usar los mismos paquetes (DEB o RPM). En Windows, utilice el instalador MSI.

Los últimos archivos binarios estables se encuentran en [Get Started with .NET Core](https://aka.ms/dotnetcoregs) (Introducción a .NET Core). Si desea utilizar las herramientas de la última versión preliminar, que posiblemente sean inestables, use los vínculos proporcionados en el [repositorio de GitHub sobre la CLI de dotnet](https://github.com/dotnet/cli#installers-and-binaries). Para las distribuciones de Linux, se encuentran disponibles los archivos `tar.gz` (conocidos también como `tarballs`); use los scripts de instalación dentro de los archivos para instalar .NET Core.

### Uso del script del instalador
<a id="using-the-installer-script" class="xliff"></a>

El uso del script del instalador permite la instalación sin derechos administrativos en el servidor de compilación y una sencilla automatización para obtener las herramientas. El script se encarga de descargar las herramientas y extraerlas en una ubicación predeterminada o especificada para su uso. También puede especificar la versión de las herramientas que desea instalar y si prefiere instalar el SDK completo o solo el runtime compartido.

El script del instalador se puede automatizar para que se ejecute al principio de la compilación, a fin de obtener e instalar la versión deseada del SDK. La *versión deseada* se corresponde con cualquier versión del SKD que los proyectos necesitan para la compilación. El script permite instalar el SDK en un directorio local del servidor, ejecutar las herramientas desde la ubicación de instalación y limpiar después de la compilación, o bien dejar que el servicio de CI realice dicha limpieza. Esto permite encapsular y aislar todo el proceso de compilación. La referencia del script de instalación se encuentra en el tema [dotnet-install](dotnet-install-script.md).

> [!NOTE]
> Cuando se utiliza el script del instalador, las dependencias nativas no se instalan automáticamente. Debe instalarlas en caso de el sistema operativo no las incluya. Vea la lista de requisitos previos en el tema [.NET Core native prerequisites](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) (Requisitos previos nativos de .NET Core).

## Ejemplos de configuración de CI
<a id="ci-setup-examples" class="xliff"></a>

En esta sección se explica un procedimiento de instalación manual con un script de PowerShell o de Bash, además de incluir una descripción de varias soluciones de CI de software como servicio (SaaS). Las soluciones de CI de SaaS tratadas son [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) y [compilación de Visual Studio Team Services](https://www.visualstudio.com/docs/build/overview).

### Instalación manual
<a id="manual-setup" class="xliff"></a>

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
    -Uri "https://raw.githubusercontent.com/dotnet/cli/rel/1.0.1/scripts/obtain/dotnet-install.ps1" `
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
# Do not use an INSTALLDIR path containing spaces:
#   https://github.com/dotnet/cli/issues/5281
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://raw.githubusercontent.com/dotnet/cli/rel/1.0.1/scripts/obtain/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
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

### Travis CI
<a id="travis-ci" class="xliff"></a>

Puede configurar [Travis CI](https://travis-ci.org/) para instalar el SDK de .NET Core con el lenguaje `csharp` y la clave `dotnet`. Vea los documentos oficiales de Travis CI en [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/) (Compilación de un proyecto de C#, F# o Visual Basic) para obtener más información. Al acceder a la información de Travis CI, observará que el identificador de lenguaje `language: csharp` de cuyo mantenimiento se encarga la comunidad funciona con todos los lenguajes de .NET, incluidos F# y Mono.

Travis CI se ejecuta tanto en trabajos de macOS (OS X 10.11, OS X 10.12) como de Linux (Ubuntu 14.04) en una *matriz de compilación*, donde debe especificar una combinación de runtime, entorno y exclusiones/inclusiones para aceptar las combinaciones de compilación de la aplicación. Vea el archivo de [ejemplo .travis.yml](https://github.com/dotnet/docs/blob/master/.travis.yml) y [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) (Personalización de la compilación) en los documentos de Travis CI para obtener más información. Las herramientas basadas en MSBuild incluyen los runtimes LTS (1.0.x) y Current (1.1.x) en el paquete; por tanto, cuando instala el SDK, recibe todo lo que necesita para la compilación.

### AppVeyor
<a id="appveyor" class="xliff"></a>

[AppVeyor](https://www.appveyor.com/) instala el SDK de .NET Core 1.0.1 con la imagen de trabajo de compilación de `Visual Studio 2017`. Se encuentran disponibles otras imágenes de compilación con diferentes versiones del SDK de .NET Core; vea el [ejemplo de appveyor.yml](https://github.com/dotnet/docs/blob/master/appveyor.yml) y el tema [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) (Imágenes de trabajo de compilación) de los documentos de AppVeyor para obtener más información.

Los archivos binarios del SDK de .NET Core se descargan y descomprimen en un subdirectorio con la utilización del script de instalación y, después, se agregan a la variable de entorno `PATH`. Agregue una matriz de compilación para ejecutar las pruebas de integración con varias versiones del SDK de .NET Core:

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### Visual Studio Team Services (VSTS)
<a id="visual-studio-team-services-vsts" class="xliff"></a>

Configure Visual Studio Team Services (VSTS) para compilar proyectos de .NET Core con alguno de estos enfoques:

1. Ejecute el script del [paso de instalación manual](#manual-setup) con sus comandos.
1. Cree una compilación compuesta de varias tareas de compilación integradas en VSTS que están configuradas para usar herramientas de .NET Core.

Ambas soluciones son válidas. Con la utilización de un script de instalación manual, puede controlar la versión de las herramientas que recibe, ya que las descarga como parte de la compilación. La compilación se ejecuta desde un script que debe crear. En este tema solo se trata la opción manual. Para obtener más información sobre la composición de una compilación con tareas de compilación de VSTS, consulte el tema [Continuous integration and deployment](https://www.visualstudio.com/docs/build/overview) (Implementación e integración continuas) de VSTS.

Para usar un script de instalación manual en VSTS, cree una definición de compilación y especifique el script que va a ejecutar para el paso de compilación. Esto se realiza en la interfaz de usuario de VSTS:

1. Empiece por crear una definición de compilación. Cuando llegue a la pantalla en la que se ofrece la opción de definir el tipo de compilación que desea crear, seleccione la opción **Vacío**.

   ![Selección de una definición de compilación vacía](./media/using-ci-with-cli/screen1.png)

1. Después de configurar el repositorio que va a compilar, se le remite a las definiciones de compilación. Seleccione **Agregar paso de compilación**:

   ![Agregar un paso de compilación](./media/using-ci-with-cli/screen2.png)

1. Se abre el **Catálogo de tareas**. El catálogo contiene tareas que se utilizan en la compilación. Como ya tiene un script, seleccione el botón **Agregar** en **PowerShell: Ejecute un script de PowerShell**.

   ![Paso para agregar un script de PowerShell](./media/using-ci-with-cli/screen3.png)

1. Configure el paso de compilación. Agregue el script desde el repositorio que se va a compilar:

   ![Especificar el script de PowerShell que va a ejecutar](./media/using-ci-with-cli/screen4.png)

## Orquestación de la compilación
<a id="orchestrating-the-build" class="xliff"></a>

En la mayor parte de este documento se describe cómo adquirir las herramientas de .NET Core y configurar varios servicios de CI sin ofrecer información sobre cómo orquestar o *compilar realmente* el código con .NET Core. Las opciones para estructurar el proceso de compilación dependen de muchos factores que no se pueden tratar aquí en términos generales. Explore los recursos y ejemplos proporcionados en las series de documentos de [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) y [VSTS](https://www.visualstudio.com/docs/build/overview) para obtener más información sobre cómo orquestar las compilaciones con cada tecnología.

Dos enfoques generales que se aplican para estructurar el proceso de compilación del código de .NET Core con herramientas de .NET Core consisten en utilizar directamente MSBuild o en usar los comandos de la línea de comandos de .NET Core. El enfoque que debe adoptar depende de lo cómo que se sienta con cada uno de ellos y de los inconvenientes que presente su complejidad. MSBuild ofrece la posibilidad de expresar el proceso de compilación como tareas y objetivos, pero presenta la complejidad añadida de tener que aprender la sintaxis del archivo de proyecto de MSBuild. Quizá sea más sencillo usar las herramientas de línea de comandos de .NET Core, pero, en este caso, es necesario escribir la lógica de orquestación en un lenguaje de scripting como `bash` o PowerShell.

## Vea también
<a id="see-also" class="xliff"></a>

[Pasos de adquisición de Ubuntu](https://www.microsoft.com/net/core#linuxubuntu)   

