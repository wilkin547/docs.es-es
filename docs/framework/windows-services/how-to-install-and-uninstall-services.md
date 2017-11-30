---
title: "Cómo: Instalar y desinstalar servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: d52512ef98596e1e3d5f0acb3b1bbc0eebffe867
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-install-and-uninstall-services"></a>Cómo: Instalar y desinstalar servicios
Si desarrolla un servicio de Windows mediante .NET Framework, puede instalar rápidamente la aplicación de servicio mediante una utilidad de línea de comandos denominada InstallUtil.exe. Si es desarrollador y desea publicar un servicio de Windows que los usuarios puedan instalar y desinstalar, debe usar InstallShield. Vea [implementación de Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
> [!WARNING]
>  Si desea desinstalar un servicio del equipo, no siga los pasos descritos en este artículo. En su lugar, averigüe qué paquete de software o programa instaló el servicio y, a continuación, elija **agregar o quitar programas** en el Panel de Control para desinstalar el programa. Tenga en cuenta que muchos servicios forman parte de Windows; si los quita, podría causar inestabilidad en el sistema.  
  
 Para poder seguir los pasos de este artículo, primero debe agregar un instalador del servicio al servicio de Windows. Vea [Tutorial: crear una ventana de la aplicación en el Diseñador de componentes de servicio](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).  
  
 Los proyectos de servicio de Windows no se pueden ejecutar directamente desde el entorno de desarrollo de Visual Studio presionando F5. Esto es porque el servicio del proyecto debe estar instalado para poder ejecutar el proyecto.  
  
> [!TIP]
>  Puede iniciar **Explorador de servidores** y compruebe que el servicio se ha instalado o desinstalado. Para obtener más información, vea Cómo: acceso e inicializar el Explorador de explorador de bases de datos de servidor.  
  
### <a name="to-install-your-service-manually"></a>Para instalar el servicio manualmente  
  
1.  En las ventanas **iniciar** menú o **iniciar** , elija **Visual Studio** , **Visual Studio Tools**, **para desarrolladores Símbolo del sistema**.  
  
     Aparece un símbolo del sistema de Visual Studio.  
  
2.  Obtenga acceso al directorio donde se encuentra el archivo ejecutable compilado del proyecto.  
  
3.  Ejecute InstallUtil.exe desde la línea de comandos con el archivo ejecutable del proyecto como parámetro:  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     Si usa el símbolo del sistema de Visual Studio, InstallUtil.exe debe estar en la ruta de acceso del sistema. Si no es así, puede agregarlo a la ruta de acceso o usar la ruta de acceso completa para invocarlo. Esta herramienta se instala con .NET Framework y su ruta de acceso es `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`. Por ejemplo, para la versión de 32 bits de .NET Framework 4 o 4.5*, si el directorio de instalación de Windows es C:\Windows, la ruta de acceso es `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`. Para la versión de 64 bits de .NET Framework 4 o 4.5. \*, la ruta predeterminada es `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.  
  
### <a name="to-uninstall-your-service-manually"></a>Para desinstalar el servicio manualmente  
  
1.  En las ventanas **iniciar** menú o **iniciar** , elija **Visual Studio**, **Visual Studio Tools**, **para desarrolladores Símbolo del sistema**.  
  
     Aparece un símbolo del sistema de Visual Studio.  
  
2.  Ejecute InstallUtil.exe desde la línea de comandos con la salida del proyecto como parámetro:  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  A veces, después de eliminar el archivo ejecutable de un servicio, es posible que el servicio permanezca en el Registro. En ese caso, use el comando [sc delete](http://technet.microsoft.com/library/cc742045.aspx) para quitar la entrada para el servicio del registro.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las aplicaciones de servicio de Windows](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Cómo: crear servicios de Windows](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [Cómo: agregar instaladores a la aplicación de servicio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Installutil.exe (Herramienta Installer)](../../../docs/framework/tools/installutil-exe-installer-tool.md)
