---
title: Procedimiento de instalación única para los ejemplos de Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
ms.openlocfilehash: 76cf2c7ec7edbfaaa186b45f4b810c7d4c0b1d47
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825188"
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Procedimiento de instalación única para los ejemplos de Windows Communication Foundation
La mayoría de los ejemplos de Windows Communication Foundation (WCF) se hospedan en Internet Information Services (IIS) y ejecutar desde un directorio virtual común. Este procedimiento de instalación única crea una carpeta en el disco; También agrega un directorio virtual en IIS denominado **ServiceModelSamples**.

 El **ServiceModelSamples** directorio virtual se utiliza para compilar y ejecutar todos los ejemplos que utilizan un servicio hospedado en IIS. Éste es el único directorio virtual que se exige para ejecutar los ejemplos. Al compilar un ejemplo, se reemplazará cualquier servicio implementado anteriormente en este directorio virtual; solo se implementará y estará disponible en este directorio virtual el ejemplo creado más recientemente.

> [!NOTE]
>  Debe ejecutar todos los comandos con una cuenta de administrador local. Si está utilizando Windows 7, [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)] o Windows Server 2008 R2, también debe ejecutar el símbolo del sistema con privilegios elevados. Para ello, haga clic en el icono de símbolo del sistema y, a continuación, haga clic en **ejecutar como administrador**. Todos los comandos de este tema se deben ejecutar en un símbolo del sistema que tenga la configuración de ruta de acceso adecuada.  La manera más fácil de asegurarse de esto es usar el símbolo del sistema de Visual Studio. Para abrir este símbolo del sistema, haga clic en **iniciar**, seleccione **todos los programas**, desplácese hacia abajo hasta **Visual Studio 2010**, seleccione **Visual Studio Tools**, Haga clic en **Visual Studio Command Prompt (2010)** y, a continuación, haga clic en **ejecutar como administrador**. Si tiene una de las ediciones de Visual Studio Express instalada, este símbolo del sistema no está disponible, y tendrá que agregar "C:\Windows\Microsoft.Net\Framework\v4.0" a la ruta de acceso del sistema.  
  
### <a name="one-time-setup-procedure-for-wcf-samples"></a>Procedimiento de instalación única para los ejemplos de WCF  
  
1.  Asegúrese de que [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] está instalado. Para obtener más información acerca de cómo configurar [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], consulte [instrucciones de hospedaje de Internet Information Services](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md).  
  
2.  Asegúrese de que [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] está instalado. Buscar el siguiente directorio v4.0 (o posterior): **\Windows\Microsoft.NET\Framework**  
  
3.  Si no está instalado Visual Studio 2012 y el sistema operativo no es Windows Server 2008 SP2 o posterior, instale [Hotfix 251798](https://go.microsoft.com/fwlink/?LinkId=184693).  
  
4.  Ejecute los siguientes comandos. Para obtener más información acerca de por qué se deben ejecutar estos comandos, consulte [error del servicio hospedado IIS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752252(v=vs.90)).  
  
    > [!WARNING]
    >  Si se reinstala IIS, los siguientes comandos deberán ejecutarse de nuevo.

    ```
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r
    ```

    > [!WARNING]
    >  Ejecute el comando `aspnet_regiis –i –enable` hará que el grupo de aplicaciones predeterminadas se ejecute con [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], lo que puede generar problemas de incompatibilidad para otras aplicaciones en el mismo equipo.  
  
5.  Siga el [instrucciones de Firewall](../../../../docs/framework/wcf/samples/firewall-instructions.md) para habilitar los puertos usados por los ejemplos.  
  
6.  Busque el siguiente directorio predeterminado: \<InstallDrive>:**\WF_WCF_Samples**. Si se instalaron los ejemplos con anterioridad, este es el directorio predeterminado.  
  
7.  Si los ejemplos no están instalados, instálelos desde la ubicación de descarga de ejemplos de [Visual C#](https://go.microsoft.com/fwlink/?LinkId=190939) o [Visual Basic](https://go.microsoft.com/fwlink/?LinkID=193373).  
  
8.  Después de instalar los ejemplos, vaya a: \<InstallDrive>:**\WF_WCF_Samples\WCF\Setup\\**  
  
9. Ejecute el **Setupvroot.bat** archivo por lotes. Se realizan estos pasos:  
  
    -   Se crea un directorio virtual en IIS denominado ServiceModelSamples.  
  
    -   Los nuevos directorios del disco se crean con los nombres %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples y %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin.  
  
     Si prefiere configurar estos directorios manualmente, consulte el [instrucciones de configuración del directorio Virtual](../../../../docs/framework/wcf/samples/virtual-directory-setup-instructions.md). Para revertir todos los cambios efectuados en este paso, ejecute cleanupvroot.bat después de que termine de utilizar los ejemplos.  
  
    > [!NOTE]
    >  Este procedimiento solo se debe realizar una vez en un equipo, a menos que se ejecute cleanupvroot.bat.

10. Debe conceder permiso para modificar %SystemDrive%\inetpub\wwwroot a la cuenta con la que se van a compilar los ejemplos y al usuario del Servicio de red. Mientras se compilan, algunos ejemplos hospedados en Web podrían intentar copiar los archivos binarios compilados en la ubicación mencionada previamente y, si no se han establecido los permisos adecuados, la compilación se interrumpirá. Como alternativa, puede dejar los permisos tal y como están y ejecutar el símbolo del sistema de SDK o el símbolo del sistema de Visual Studio (2012) como administrador o compilar los ejemplos de Visual Studio 2012, también se ejecutan como administrador.

    > [!NOTE]
    >  Si no se completa este paso, todos los ejemplos hospedados en IIS generarán errores al compilarse. Asegúrese de que ha establecido los permisos correctamente o ejecute el símbolo del sistema de SDK y Visual Studio (2012) como administrador.

11. Cree un directorio C:\logs en el equipo; en algunos ejemplos podría esperarse que exista. Asegúrese de que la cuenta adecuada tiene concedido acceso de escritura en esta carpeta. Para Windows 7, [!INCLUDE[wv](../../../../includes/wv-md.md)], y Windows Server 2008 R2, esta cuenta es **Network Service**. En [!INCLUDE[lserver](../../../../includes/lserver-md.md)], la cuenta es NT Authority\Network Service. En [!INCLUDE[wxp](../../../../includes/wxp-md.md)] y [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], la cuenta es ASPNET.

12. Ejecute el archivo Setupcerttool.bat. Este archivo se encuentra en la \<Rutadeinstalación > \WF_WCF_Samples\WCF\Setup\ carpeta.  Este script realizará las siguientes tareas:

    -   Compile La herramienta FindPrivateKey.

    -   Cree un directorio denominado %ProgramFiles%\ServiceModelSampleTools.

    -   Copie la nueva herramienta FindPrivateKey en este directorio.

     Esta herramienta se requiere en los ejemplos que utilizan certificados y se hospedan en IIS.

    > [!NOTE]
    >  Por motivos de seguridad, no olvide quitar la definición del directorio virtual y los permisos concedidos en los pasos de instalación anteriores cuando termine con los ejemplos; para ello ejecute el archivo por lotes denominado Cleanupvroot.bat.

13. Los ejemplos autohospedados (no se hospedan en IIS) requieren permiso para registrar las direcciones HTTP en el equipo a fin de realizar escuchas. El permiso para una reserva de espacio de nombres HTTP procede de la cuenta de usuario utilizada para ejecutar el ejemplo. De forma predeterminada, las cuentas de administrador tienen el permiso para registrar cualquier dirección HTTP. Las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP usados por los ejemplos. Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).

14. Algunos ejemplos requieren Message Queuing. Consulte [instalar Message Queuing (MSMQ)](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md) para obtener instrucciones de instalación.

    > [!NOTE]
    >  Asegúrese de iniciar el servicio de MSMQ antes de ejecutar cualquier ejemplo que requiera Message Queuing.

15. En algunos ejemplos se requieren los certificados. Consulte [de Internet Information Services (IIS) instrucciones de instalación de certificado de servidor](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).
