---
title: Procedimiento de instalación única para los ejemplos de Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: a5848ffd-3eb5-432d-812e-bd948ccb6bca
ms.openlocfilehash: 954ec04d2ef1ca7667b4f75a8a6652010b5dbd33
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121627"
---
# <a name="one-time-setup-procedure-for-the-windows-communication-foundation-samples"></a>Procedimiento de instalación única para los ejemplos de Windows Communication Foundation

La mayoría de los ejemplos de Windows Communication Foundation (WCF) se hospedan en Internet Information Services (IIS) y se ejecutan desde un directorio virtual común. Este procedimiento de configuración de una sola vez crea una carpeta en el disco; también agrega un directorio virtual a IIS denominado **ServiceModelSamples**.

El directorio virtual **ServiceModelSamples** se usa para compilar y ejecutar todos los ejemplos que usan un servicio hospedado en IIS. Éste es el único directorio virtual que se exige para ejecutar los ejemplos. Al compilar un ejemplo, se reemplazará cualquier servicio implementado anteriormente en este directorio virtual; solo se implementará y estará disponible en este directorio virtual el ejemplo creado más recientemente.

> [!NOTE]
> Debe ejecutar todos los comandos con una cuenta de administrador local. Si usa Windows 7, Windows Vista o Windows Server 2008 R2, también debe ejecutar el símbolo del sistema con privilegios elevados. Para ello, haga clic con el botón derecho en el icono del símbolo del sistema y, a continuación, haga clic en **Ejecutar como administrador**. Todos los comandos de este tema se deben ejecutar en un símbolo del sistema que tenga la configuración de ruta de acceso adecuada.  La manera más fácil de asegurarse de esto es usar el símbolo del sistema de Visual Studio. Para abrir este símbolo del sistema, haga clic en **Inicio**, seleccione **Todos los programas**, desplácese hacia abajo hasta Visual Studio **2010**, seleccione **Visual Studio Tools**, haga clic con el botón secundario en Símbolo del sistema de Visual Studio **(2010)** y, a continuación, haga clic en **Ejecutar como administrador**. Si tiene una de las ediciones de Visual Studio Express instalada, este símbolo del sistema no está disponible, y tendrá que agregar "C:\Windows\Microsoft.Net\Framework\v4.0" a la ruta de acceso del sistema.

### <a name="one-time-setup-procedure-for-wcf-samples"></a>Procedimiento de instalación única para los ejemplos de WCF

1. Asegúrese de que ASP.NET esté configurado. Para obtener más información acerca de cómo configurar ASP.NET, consulte Instrucciones de hospedaje de servicios de [Internet Information.](internet-information-service-hosting-instructions.md)

2. Asegúrese de que .NET Framework 4 está instalado. Busque en el directorio siguiente la versión v4.0 (o **posterior):**

3. Asegúrese de que tiene Visual Studio 2012 o posterior instalado, o que el sistema operativo sea Windows Server 2008 SP2 o posterior.

4. Ejecute los comandos siguientes: Para obtener más información acerca de por qué se deben ejecutar estos comandos, vea Error en el servicio hospedado de [IIS](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752252(v=vs.90)).

    > [!WARNING]
    > Si se reinstala IIS, los siguientes comandos deberán ejecutarse de nuevo.

    ```console
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\aspnet_regiis" –i –enable
    "%WINDIR%\Microsoft.Net\Framework\v4.0.30319\ServiceModelReg.exe" -r
    ```

    > [!WARNING]
    > La ejecución `aspnet_regiis –i –enable` del comando hará que el grupo de aplicaciones predeterminado se ejecute con .NET Framework 4, lo que puede producir problemas de incompatibilidad para otras aplicaciones en el mismo equipo.

5. Siga las instrucciones del [cortafuegos](firewall-instructions.md) para habilitar los puertos utilizados por los ejemplos.

6. Busque el siguiente directorio \<predeterminado: InstallDrive>:**.WF_WCF_Samples**. Si se instalaron los ejemplos con anterioridad, este es el directorio predeterminado.

7. Si los ejemplos no están instalados, instálelos desde ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

8. Después de instalar los \<ejemplos, vaya a : InstallDrive>:**WF_WCF_Samples .\\ **

9. Ejecute el archivo por lotes **Setupvroot.bat.** Hay que seguir estos pasos:

    - Se crea un directorio virtual en IIS denominado ServiceModelSamples.

    - Los nuevos directorios del disco se crean con los nombres %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples y %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples\bin.

    Si prefiere configurar estos directorios manualmente, consulte las Instrucciones de [instalación del directorio](virtual-directory-setup-instructions.md)virtual. Para revertir todos los cambios efectuados en este paso, ejecute cleanupvroot.bat después de que termine de utilizar los ejemplos.

    > [!NOTE]
    > Este procedimiento solo se debe realizar una vez en un equipo, a menos que se ejecute cleanupvroot.bat.

10. Debe conceder permiso para modificar %SystemDrive%\inetpub\wwwroot a la cuenta con la que se van a compilar los ejemplos y al usuario del Servicio de red. Mientras se compilan, algunos ejemplos hospedados en Web podrían intentar copiar los archivos binarios compilados en la ubicación mencionada previamente y, si no se han establecido los permisos adecuados, la compilación se interrumpirá. Como alternativa, puede dejar los permisos tal como están y ejecutar el símbolo del sistema del SDK o el símbolo del sistema de Visual Studio (2012) como administrador, o compilar los ejemplos en Visual Studio 2012, también se ejecutan como administrador.

    > [!NOTE]
    > Si no se completa este paso, todos los ejemplos hospedados en IIS generarán errores al compilarse. Asegúrese de que ha establecido los permisos correctamente o ejecute el símbolo del sistema de SDK y Visual Studio (2012) como administrador.

11. Cree un directorio C:\logs en el equipo; en algunos ejemplos podría esperarse que exista. Asegúrese de que la cuenta adecuada tiene concedido acceso de escritura en esta carpeta. Para Windows 7, Windows Vista y Windows Server 2008 R2, esta cuenta es **Servicio**de red . Para Windows Server 2008, la cuenta es NT Authority-Network Service. Para Windows XP y Windows Server 2003, la cuenta es ASPNET.

12. Ejecute el archivo Setupcerttool.bat. Este archivo se \<encuentra en la carpeta InstallPath>, WF_WCF_Samples, WCF, Setup.  Este script realizará las siguientes tareas:

    - Compile La herramienta FindPrivateKey.

    - Cree un directorio denominado %ProgramFiles%\ServiceModelSampleTools.

    - Copie la nueva herramienta FindPrivateKey en este directorio.

    Esta herramienta se requiere en los ejemplos que utilizan certificados y se hospedan en IIS.

    > [!NOTE]
    > Por motivos de seguridad, no olvide quitar la definición del directorio virtual y los permisos concedidos en los pasos de instalación anteriores cuando termine con los ejemplos; para ello ejecute el archivo por lotes denominado Cleanupvroot.bat.

13. Los ejemplos autohospedados (no se hospedan en IIS) requieren permiso para registrar las direcciones HTTP en el equipo a fin de realizar escuchas. El permiso para una reserva de espacio de nombres HTTP procede de la cuenta de usuario utilizada para ejecutar el ejemplo. De forma predeterminada, las cuentas de administrador tienen el permiso para registrar cualquier dirección HTTP. Las cuentas de usuario no administrador deben tener concedido permiso para los espacios de nombres HTTP usados por los ejemplos. Para obtener más información sobre cómo configurar las reservas de espacio de nombres, vea [Configuración de HTTP y HTTPS](../feature-details/configuring-http-and-https.md).

14. Algunos ejemplos requieren Message Queuing. Consulte [Instalación de Message Queue Server (MSMQ)](installing-message-queuing-msmq.md) para obtener instrucciones de instalación.

    > [!NOTE]
    > Asegúrese de iniciar el servicio de MSMQ antes de ejecutar cualquier ejemplo que requiera Message Queuing.

15. En algunos ejemplos se requieren los certificados. Vea [Instrucciones de instalación del certificado de servidor de Internet Information Services (IIS)](iis-server-certificate-installation-instructions.md).
