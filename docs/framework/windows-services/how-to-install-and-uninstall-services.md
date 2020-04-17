---
title: 'Cómo: Instalar y desinstalar servicios de Windows'
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
author: ghogen
ms.openlocfilehash: 8937ef8b4007253b06444e59b292395084e4df2f
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607924"
---
# <a name="how-to-install-and-uninstall-windows-services"></a>Cómo: Instalar y desinstalar servicios de Windows

Si está desarrollando un servicio de Windows con .NET Framework, puede instalar rápidamente la aplicación de servicio mediante la utilidad de línea de comandos [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) o [PowerShell](/powershell/scripting/overview). Los desarrolladores que quieran publicar un servicio de Windows que los usuarios puedan instalar y desinstalar deben usar InstallShield. Para obtener más información, consulte [Crear un paquete de instalación (escritorio](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)de Windows).

> [!WARNING]
> Si desea desinstalar un servicio del equipo, no siga los pasos descritos en este artículo. En su lugar, averigüe qué paquete de software o programa ha instalado el servicio y, después, haga clic en **Aplicaciones** en Configuración para desinstalar ese programa. Tenga en cuenta que muchos servicios forman parte de Windows; si los quita, podría causar inestabilidad en el sistema.

Para seguir los pasos de este artículo, primero debe agregar un instalador del servicio al servicio de Windows. Para obtener más información, vea [Tutorial: Crear una aplicación](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)de servicio de Windows .

Los proyectos de servicio de Windows no se pueden ejecutar directamente desde el entorno de desarrollo de Visual Studio presionando F5. Antes de poder ejecutar el proyecto, tendrá que instalar el servicio en el proyecto.

> [!TIP]
> Puede usar el **Explorador de servidores** para comprobar que el servicio se ha instalado o desinstalado. Para más información, vea [CÓMO: Utilizar el Explorador de servidores de Visual Studio .NET](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).

### <a name="install-your-service-manually-using-installutilexe-utility"></a>Instale el servicio manualmente con la utilidad InstallUtil.exe

1. Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*versión*>** y, después **Símbolo del sistema para desarrolladores para VS \<*versión*>**.

     Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.

2. Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.

3. Ejecute *InstallUtil.exe* desde la línea de comandos con el archivo ejecutable del proyecto como parámetro:

    ```console
    installutil <yourproject>.exe
    ```

     Si usa el símbolo del sistema para desarrolladores de Visual Studio, *InstallUtil.exe* debe estar en la ruta de acceso del sistema. En caso contrario, puede agregarlo a la ruta de acceso o usar la ruta de acceso completa para invocarlo. Esta herramienta se instala con .NET Framework en *%WINDIR%-Microsoft.NET-Framework[64]\\<framework_version\>*.

     Por ejemplo:
     - Para la versión de 32 bits de .NET Framework 4 o 4.5 y versiones posteriores, si el directorio de instalación de Windows es *C:\Windows*, la ruta predeterminada es *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.
     - Para la versión de 64 bits de .NET Framework 4 o 4.5 y versiones posteriores, la ruta de acceso predeterminada es *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.

### <a name="uninstall-your-service-manually-using-installutilexe-utility"></a>Desinstale el servicio manualmente con la utilidad InstallUtil.exe

1. Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*versión*>** y, después **Símbolo del sistema para desarrolladores para VS \<*versión*>**.

     Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.

2. Ejecute *InstallUtil.exe* desde la línea de comandos con la salida del proyecto como parámetro:

    ```console
    installutil /u <yourproject>.exe
    ```

3. Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro. En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.

### <a name="install-your-service-manually-using-powershell"></a>Instale el servicio manualmente con PowerShell

1. En el menú **Inicio,** seleccione el directorio de **Windows PowerShell** y, a continuación, seleccione **Windows PowerShell**.

2. Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.

3. Ejecute el cmdlet [**New-Service**](/powershell/module/microsoft.powershell.management/new-service) con la salida del proyecto y un nombre de servicio como parámetros:

    ```powershell
    New-Service -Name "YourServiceName" -BinaryPathName <yourproject>.exe
    ```

### <a name="uninstall-your-service-manually-using-powershell"></a>Desinstale el servicio manualmente con PowerShell

1. En el menú **Inicio,** seleccione el directorio de **Windows PowerShell** y, a continuación, seleccione **Windows PowerShell**.

2. Ejecute el cmdlet [**Remove-Service**](/powershell/module/microsoft.powershell.management/remove-service) con el nombre del servicio como parámetro:

    ```powershell
    Remove-Service -Name "YourServiceName"
    ```

3. Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro. En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.

    ```powershell
    sc.exe delete "YourServiceName"
    ```

## <a name="see-also"></a>Vea también

- [Introducción a las aplicaciones de servicio de Windows](../windows-services/introduction-to-windows-service-applications.md)
- [Cómo: Crear servicios de Windows](../windows-services/how-to-create-windows-services.md)
- [Cómo: Agregar instaladores a la aplicación de servicio](../windows-services/how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (Herramienta Installer)](../tools/installutil-exe-installer-tool.md)
