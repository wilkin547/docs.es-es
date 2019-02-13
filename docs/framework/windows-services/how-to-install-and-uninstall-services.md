---
title: Filtrar Instalar y desinstalar servicios de Windows
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
ms.openlocfilehash: 43b5ad2f346406897e8bcbcce5660a6c9524f9af
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826278"
---
# <a name="how-to-install-and-uninstall-windows-services"></a>Filtrar Instalar y desinstalar servicios de Windows
Si desarrolla un servicio de Windows con .NET Framework, puede instalar rápidamente la aplicación de servicio mediante la utilidad de línea de comandos [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md). Los desarrolladores que quieran publicar un servicio de Windows que los usuarios puedan instalar y desinstalar deben usar InstallShield. Para más información, vea [Creación de un paquete de instalador (cliente de Windows)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).
  
> [!WARNING]
>  Si desea desinstalar un servicio del equipo, no siga los pasos descritos en este artículo. En su lugar, averigüe qué paquete de software o programa ha instalado el servicio y, después, haga clic en **Aplicaciones** en Configuración para desinstalar ese programa. Tenga en cuenta que muchos servicios forman parte de Windows; si los quita, podría causar inestabilidad en el sistema.  
  
 Para seguir los pasos de este artículo, primero debe agregar un instalador del servicio al servicio de Windows. Para obtener más información, vea [Tutorial: Creación de una aplicación de un servicio de Windows](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 Los proyectos de servicio de Windows no se pueden ejecutar directamente desde el entorno de desarrollo de Visual Studio presionando F5. Antes de poder ejecutar el proyecto, tendrá que instalar el servicio en el proyecto.  
  
> [!TIP]
>  Puede usar el **Explorador de servidores** para comprobar que el servicio se ha instalado o desinstalado. Para más información, vea [CÓMO: Utilizar el Explorador de servidores de Visual Studio .NET](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).
  
### <a name="install-your-service-manually"></a>Instalación manual del servicio  
  
1.  Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*versión*>** y, después **Símbolo del sistema para desarrolladores para VS \<*versión*>**.
  
     Aparecerá el símbolo del sistema para desarrolladores de Visual Studio. 
  
2.  Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.  
  
3.  Ejecute *InstallUtil.exe* desde la línea de comandos con el archivo ejecutable del proyecto como parámetro:  
  
    ```console
    installutil <yourproject>.exe  
    ```  

     Si usa el símbolo del sistema para desarrolladores de Visual Studio, *InstallUtil.exe* debe estar en la ruta de acceso del sistema. En caso contrario, puede agregarlo a la ruta de acceso o usar la ruta de acceso completa para invocarlo. Esta herramienta se instala con .NET Framework en *%WINDIR%\Microsoft.NET\Framework[64]\\<versión_de_la_plataforma>*.
     
     Por ejemplo:
     - Para la versión de 32 bits de .NET Framework 4 o 4.5 y versiones posteriores, si el directorio de instalación de Windows es *C:\Windows*, la ruta predeterminada es *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.
     - Para la versión de 64 bits de .NET Framework 4 o 4.5 y versiones posteriores, la ruta de acceso predeterminada es *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.
  
### <a name="uninstall-your-service-manually"></a>Desinstalación manual del servicio  
  
1. Desde el menú **Inicio**, seleccione el directorio **Visual Studio \<*versión*>** y, después **Símbolo del sistema para desarrolladores para VS \<*versión*>**.
  
     Aparecerá el símbolo del sistema para desarrolladores de Visual Studio.  
  
2.  Ejecute *InstallUtil.exe* desde la línea de comandos con la salida del proyecto como parámetro:  
  
    ```console  
    installutil /u <yourproject>.exe  
    ```  
  
3. Después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro. En ese caso, use el comando [sc delete](/windows-server/administration/windows-commands/sc-delete) para quitar la entrada del servicio del Registro.  
  
## <a name="see-also"></a>Vea también
- [Introducción a las aplicaciones de servicios de Windows](../windows-services/introduction-to-windows-service-applications.md)
- [Cómo: Crear servicios de Windows](../windows-services/how-to-create-windows-services.md)
- [Cómo: Agregar instaladores a una aplicación de servicio](../windows-services/how-to-add-installers-to-your-service-application.md)
- [Installutil.exe (Herramienta Installer)](../tools/installutil-exe-installer-tool.md)
