---
title: Procedimiento Instalar y desinstalar servicios de Windows
description: Vea cómo instalar y desinstalar servicios de Windows. Si va a desarrollar un servicio de Windows con .NET, puede usar InstallUtil.exe o PowerShell.
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
ms.openlocfilehash: 0803d9908a9b92df0d17537ee4db2d798a2a07cc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433426"
---
# <a name="how-to-install-and-uninstall-windows-services"></a>Procedimiento Instalar y desinstalar servicios de Windows

Si va a desarrollar un servicio de Windows con .NET Framework, puede instalar rápidamente la aplicación de servicio mediante la utilidad de línea de comandos [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) o [PowerShell](/powershell/scripting/overview). Los desarrolladores que quieran publicar un servicio de Windows que los usuarios puedan instalar y desinstalar pueden utilizar el [conjunto de herramientas WiX](https://wixtoolset.org/) gratuito u otras herramientas comerciales como [Advanced Installer](https://www.advancedinstaller.com/), [InstallShield](https://www.revenera.com/install/products/installshield.html), etc. Para más información, consulte [Creación de un paquete de instalador (escritorio de Windows)](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).

> [!WARNING]
> Si quiere desinstalar un servicio del equipo, no siga los pasos descritos en este artículo. En su lugar, averigüe qué paquete de software o programa ha instalado el servicio y, después, haga clic en **Aplicaciones** en Configuración para desinstalar ese programa. Tenga en cuenta que muchos servicios forman parte de Windows; si los quita, podría causar inestabilidad en el sistema.

Para seguir los pasos de este artículo, primero debe agregar un instalador del servicio al servicio de Windows. Para obtener más información, vea [Tutorial: Creación de una aplicación de un servicio de Windows](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).

Los proyectos de servicio de Windows no se pueden ejecutar directamente desde el entorno de desarrollo de Visual Studio presionando F5. Antes de poder ejecutar el proyecto, tendrá que instalar el servicio en el proyecto.

> [!TIP]
> Puede usar el **Explorador de servidores** para comprobar que el servicio se ha instalado o desinstalado.

## <a name="install-using-installutilexe-utility"></a>Instalación mediante la utilidad InstallUtil.exe

1. Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*version*>** y luego **Símbolo del sistema para desarrolladores para VS\<*version*>** .

     Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.

2. Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.

3. Ejecute *InstallUtil.exe* desde la línea de comandos con el archivo ejecutable del proyecto como parámetro:

    ```console
    installutil <yourproject>.exe
    ```

     Si usa el símbolo del sistema para desarrolladores de Visual Studio, *InstallUtil.exe* debe estar en la ruta de acceso del sistema. En caso contrario, puede agregarlo a la ruta de acceso o usar la ruta de acceso completa para invocarlo. Esta herramienta se instala con .NET Framework en *%WINDIR%\Microsoft.NET\Framework[64]\\<versión_de_la_plataforma>\>* .

     Por ejemplo:
     - Para la versión de 32 bits de .NET Framework 4 o 4.5 y versiones posteriores, si el directorio de instalación de Windows es *C:\Windows*, la ruta predeterminada es *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.
     - Para la versión de 64 bits de .NET Framework 4 o 4.5 y versiones posteriores, la ruta de acceso predeterminada es *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.

## <a name="uninstall-using-installutilexe-utility"></a>Desinstalación mediante la utilidad InstallUtil.exe

1. Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*version*>** y luego **Símbolo del sistema para desarrolladores para VS\<*version*>** .

     Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.

2. Ejecute *InstallUtil.exe* desde la línea de comandos con la salida del proyecto como parámetro:

    ```console
    installutil /u <yourproject>.exe
    ```

3. Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro. En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.

## <a name="install-using-powershell"></a>Instalación mediante PowerShell

1. En el menú **Inicio**, seleccione el directorio **Windows PowerShell** y elija **Windows PowerShell**.

2. Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.

3. Ejecute el cmdlet [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) con la salida del proyecto y un nombre de servicio como parámetros:

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

## <a name="uninstall-using-powershell"></a>Desinstalación mediante PowerShell

1. En el menú **Inicio**, seleccione el directorio **Windows PowerShell** y elija **Windows PowerShell**.

2. Ejecute el cmdlet [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) con el nombre del servicio como parámetro:

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro. En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicios de Windows](introduction-to-windows-service-applications.md)
- [Cómo: Crear servicios de Windows](how-to-create-windows-services.md)
- [Cómo: Agregar instaladores a una aplicación de servicio](how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (Herramienta Installer)](../tools/installutil-exe-installer-tool.md)
