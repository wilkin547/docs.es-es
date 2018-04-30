---
title: Utilización del instrumental de administración de Windows (WMI) para diagnósticos
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e01418844db4197cea2f9292f72b9089e77a596
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="using-windows-management-instrumentation-for-diagnostics"></a>Utilización del instrumental de administración de Windows (WMI) para diagnósticos
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] expone datos de la inspección de un servicio en el tiempo de ejecución a través de un proveedor del Instrumental de administración de Windows (WMI) [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].  
  
## <a name="enabling-wmi"></a>Habilitar WMI  
 WMI es la implementación de Microsoft del estándar Web-Based Enterprise Management (WBEM). Para obtener más información sobre el SDK de WMI, consulte [Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx). WBEM es un estándar de la industria para saber cómo exponen las aplicaciones la instrumentación de administración a las herramientas de administración externas.  
  
 Un proveedor de WMI es un componente que expone la instrumentación en el tiempo de ejecución a través de una interfaz compatible con WBEM. Está compuesto de un conjunto de objetos WMI con pares atributo/valor. Los pares pueden ser de varios tipos simples. Las herramientas de administración pueden conectarse a los servicios a través de la interfaz en tiempo de ejecución. [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] expone atributos de servicios como direcciones, enlaces, comportamientos y agentes de escucha.  
  
 El proveedor de WMI integrado puede activarse en el archivo de configuración de la aplicación. Esto se realiza a través de la `wmiProviderEnabled` atributo de la [ \<diagnóstico >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) en el [ \<system.serviceModel >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sección, como se muestra en el ejemplo siguiente configuración.  
  
```xml  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
```  
  
 Esta entrada de configuración expone una interfaz WMI. Ahora, las aplicaciones de administración pueden establecer la conexión a través de esta interfaz y obtener acceso a la instrumentación de administración de la aplicación.  
  
## <a name="accessing-wmi-data"></a>Obtener acceso a datos WMI  
 Puede obtenerse acceso a los datos WMI de maneras muy distintas. Microsoft proporciona las API de WMI para scripts, aplicaciones de Visual Basic, aplicaciones de C++ y la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. Para obtener más información, consulte [mediante WMI](http://go.microsoft.com/fwlink/?LinkId=95183).  
  
> [!CAUTION]
>  Si utiliza los métodos proporcionados por .NET Framework para tener acceso mediante programación a los datos de WMI, debe tener en cuenta que tales métodos pueden iniciar excepciones una vez establecida la conexión. La conexión no se establece durante la construcción de la instancia <xref:System.Management.ManagementObject>, sino con la primera solicitud que implique el intercambio real de datos. Por lo tanto, utilice un bloque `try..catch` para detectar las posibles excepciones.  
  
 Puede cambiar la traza y el nivel de registro de mensajes, así como las opciones de registro de mensajes para el origen de traza de la traza `System.ServiceModel` en WMI. Esto puede hacerse mediante el acceso a la [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md) instancia, que expone las siguientes propiedades booleanas: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages`, y `TraceLevel`. Por consiguiente, si configura un agente de escucha de traza para el registro de mensajes, pero define estas opciones en `false`, en la configuración, puede cambiarlas después a `true`, una vez se esté ejecutando la aplicación. Esto habilitará de manera efectiva el registro de mensajes en el tiempo de ejecución. De igual forma, si habilita el registro de mensajes en su archivo de configuración, puede deshabilitarlo en el tiempo de ejecución mediante WMI.  
  
 Debe tener en cuenta que si en el archivo de configuración no se especifica ningún agente de escucha de traza de registro de mensajes para el registro de mensajes, o no se especifica ningún agente de escucha de traza de `System.ServiceModel`, no se aplica ninguno de sus cambios, aunque WMI los acepte. Para obtener más información sobre cómo establecer correctamente los agentes de escucha respectivos, consulte [configuración de registro de mensajes](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) y [configurar el seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md). El nivel de seguimiento de traza, del resto de los orígenes de traza de traza, especificado por la configuración es efectivo cuando se inicia la aplicación, y no se puede cambiar.  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] expone un método `GetOperationCounterInstanceName` para scripting. Este método devuelve un nombre de instancia del contador de rendimiento si le proporciona un nombre de operación. Sin embargo, no valida la entrada. Por lo tanto, si proporciona un nombre de operación incorrecto, se devuelve un nombre de contador incorrecto.  
  
 La propiedad `OutgoingChannel` de la instancia `Service` no cuenta los canales abiertos por un servicio para establecer la conexión con otro servicio, si no se crea el cliente [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] del servicio de destino en el método `Service`.  
  
 **Precaución** WMI solo admite un <xref:System.TimeSpan> valor hasta 3 separadores decimales. Por ejemplo, si su servicio establece una de sus propiedades en <xref:System.TimeSpan.MaxValue>, su valor se trunca pasados los 3 separadores decimales cuando se ve mediante WMI.  
  
## <a name="security"></a>Seguridad  
 Dado que el proveedor WMI [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] permite la detección de servicios en un entorno, debería tener una precaución extrema al permitir el acceso a él. Si suaviza el acceso predeterminado exclusivo a los administradores, puede permitir el acceso de partes menos fiables a los datos confidenciales de su entorno. En concreto, si suaviza los permisos de acceso remoto a WMI, pueden producirse ataques por inundación. Si un proceso se inunda por un exceso de solicitudes de WMI, su rendimiento puede degradarse.  
  
 Además, si suaviza los permisos de acceso para el archivo MOF, partes menos fiables pueden manipular el comportamiento de WMI y modificar los objetos que se cargan en el esquema de WMI. Por ejemplo, pueden quitarse campos de modo que se oculten datos críticos al administrador, que no se puedan rellenar campos, o provocar que se agreguen excepciones al archivo.  
  
 De manera predeterminada, el proveedor de WMI [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] otorga permisos "ejecutar métodos", "escritura del proveedor", y "habilitar cuentas" para el administrador, y el permiso "habilitar cuentas" para ASP.NET, el servicio local y el servicio de red. En concreto, en plataformas no [!INCLUDE[wv](../../../../../includes/wv-md.md)], la cuenta de ASP.NET posee acceso de lectura al espacio de nombres ServiceModel de WMI. Si no desea conceder estos privilegios a un grupo de usuarios determinado, debe desactivar el proveedor de WMI (deshabilitado de manera predeterminada), o deshabilitar el acceso para el grupo de usuarios concreto.  
  
 Además, al intentar habilitar WMI a través de la configuración, WMI puede no estar habilitada debido a un privilegio de usuario insuficiente. No obstante, no se escribe ningún evento en el registro de eventos que registre este error.  
  
 Para modificar los niveles de privilegio del usuario, siga los pasos siguientes.  
  
1.  Haga clic en Inicio y, a continuación, ejecutar y escriba **compmgmt.msc**.  
  
2.  Haga clic en **servicios y los controles de aplicación/WMI** para seleccionar **propiedades**.  
  
3.  Seleccione el **seguridad** ficha y navegue hasta la **Root/ServiceModel** espacio de nombres. Haga clic en el **seguridad** botón.  
  
4.  Seleccione el grupo o usuario específico que se desea controlar el acceso y utilizar el **permitir** o **Deny** casilla de verificación para configurar los permisos.  
  
## <a name="granting-wcf-wmi-registration-permissions-to-additional-users"></a>Conceder permisos de registro de WCF WMI a usuarios adicionales  
 WCF expone datos de administración a WMI. Lo consigue hospedando un proveedor WMI en curso, a veces denominado "proveedor desacoplado". La cuenta que registra este proveedor debe tener los permisos apropiados para poder exponer los datos de administración. En Windows, solo un pequeño conjunto de cuentas privilegiadas pueden registrar proveedores desacoplados de forma predeterminada. Esto supone un problema, ya que los usuarios normalmente desean exponer los datos WMI de un servicio WCF que se está ejecutando bajo una cuenta que no se encuentra en el conjunto predeterminado.  
  
 Para proporcionar este acceso, el administrador debe conceder los permisos siguientes a la cuenta adicional en el orden siguiente:  
  
1.  Permiso para tener acceso al espacio de nombres de WMI de WCF.  
  
2.  Permiso para registrar el proveedor desacoplado WMI de WCF.  
  
#### <a name="to-grant-wmi-namespace-access-permission"></a>Para conceder permiso de acceso al espacio de nombres WMI  
  
1.  Ejecute el siguiente script de PowerShell.  
  
    ```powershell  
    write-host ""  
    write-host "Granting Access to root/servicemodel WMI namespace to built in users group"  
    write-host ""  
  
    # Create the binary representation of the permissions to grant in SDDL  
    $newPermissions = "O:BAG:BAD:P(A;CI;CCDCLCSWRPWPRCWD;;;BA)(A;CI;CC;;;NS)(A;CI;CC;;;LS)(A;CI;CC;;;BU)"  
    $converter = new-object system.management.ManagementClass Win32_SecurityDescriptorHelper  
    $binarySD = $converter.SDDLToBinarySD($newPermissions)  
    $convertedPermissions = ,$binarySD.BinarySD  
  
    # Get the object used to set the permissions  
    $security = gwmi -namespace root/servicemodel -class __SystemSecurity  
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "Previous ACL: "$outsddl.SDDL  
  
    # Change the Access Control List (ACL) using SDDL  
    $result = $security.PsBase.InvokeMethod("SetSD",$convertedPermissions)   
  
    # Get and output the current settings  
    $binarySD = @($null)  
    $result = $security.PsBase.InvokeMethod("GetSD",$binarySD)  
  
    $outsddl = $converter.BinarySDToSDDL($binarySD[0])  
    write-host "New ACL:      "$outsddl.SDDL  
    write-host ""  
    ```  
  
     Este script de PowerShell usa el lenguaje de definición de descriptores de seguridad (SDDL) para conceder acceso al grupo de usuarios integrado en el espacio de nombres WMI "root/servicemodel". Especifica las ACL siguientes:  
  
    -   Cuenta predefinida Administrador (BA) - Ya tenía acceso.  
  
    -   Servicio de red (NS) - Ya tenía acceso.  
  
    -   Sistema local (LS) - Ya tenía acceso.  
  
    -   Usuarios integrado - El grupo al que se va a conceder acceso.  
  
#### <a name="to-grant-provider-registration-access"></a>Para conceder acceso de registro de proveedores  
  
1.  Ejecute el siguiente script de PowerShell.  
  
    ```powershell  
    write-host ""  
    write-host "Granting WCF provider registration access to built in users group"  
    write-host ""  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host ""  
    ```  
  
### <a name="granting-access-to-arbitrary-users-or-groups"></a>Conceder acceso a usuarios o grupos arbitrarios  
 En el ejemplo de esta sección se conceden privilegios de registro de proveedores WMI a todos los usuarios locales. Si desea conceder acceso a un usuario o grupo no integrado, debe obtener el identificador de seguridad (SID) de dicho usuario o grupo. No hay ninguna forma sencilla de obtener el SID de un usuario arbitrario. Un método consiste en iniciar sesión como el usuario deseado y, a continuación, usar el comando shell siguiente.  
  
```  
Whoami /user  
```  
  
 Esto proporciona el SID del usuario actual, pero este método no se puede usar para obtener el SID de un usuario arbitrario. Otro método para obtener el SID es usar el [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) herramienta desde el [herramientas del Kit de recursos de Windows 2000 para las tareas administrativas](http://go.microsoft.com/fwlink/?LinkId=178660). Esta herramienta compara el SID de dos usuarios (locales o del dominio), y como efecto secundario imprime ambos SID en la línea de comandos. Para obtener más información, consulte [Well Known SID](http://go.microsoft.com/fwlink/?LinkId=186468).  
  
## <a name="accessing-remote-wmi-object-instances"></a>Acceso a las instancias de objeto de WMI remotas  
 Si necesita tener acceso a las instancias WMI [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en un equipo remoto, debe habilitar la privacidad de paquete en las herramientas que utilice para el acceso. La siguiente sección describe cómo conseguirlo mediante CIM Studio de WMI, la Herramienta de comprobación del instrumental de administración de Windows, y .NET SDK 2.0.  
  
### <a name="wmi-cim-studio"></a>CIM Studio de WMI  
 Si ha instalado [herramientas administrativas de WMI](http://go.microsoft.com/fwlink/?LinkId=95185), puede usar CIM Studio de WMI para acceder a instancias WMI. Las herramientas se encuentran en la carpeta siguiente  
  
 **Herramientas de Files\WMI %Windir%\Program\\**  
  
1.  En el **conectar al espacio de nombres:** ventana, escriba **root\ServiceModel** y haga clic en **Aceptar.**  
  
2.  En el **el inicio de sesión de WMI CIM Studio** ventana, haga clic en el **Opciones >>** botón para expandir la ventana. Seleccione **privacidad de paquete** para **nivel de autenticación**y haga clic en **Aceptar**.  
  
### <a name="windows-management-instrumentation-tester"></a>Herramienta de comprobación del instrumental de administración de Windows  
 Windows instala esta herramienta. Para ejecutarlo, inicie una consola de comandos escribiendo **cmd.exe** en el **inicio/ejecutar** cuadro de diálogo y haga clic en **Aceptar**. A continuación, escriba **wbemtest.exe** en la ventana de comandos. Se inicia la Herramienta de comprobación del instrumental de administración de Windows.  
  
1.  Haga clic en el **conectar** botón en la esquina superior derecha de la ventana.  
  
2.  En la ventana nueva, escriba **root\ServiceModel** para el **Namespace** campo y, a continuación, seleccione **privacidad de paquete** para **nivel de autenticación**. Haga clic en **conectar**.  
  
### <a name="using-managed-code"></a>Utilización del código administrado  
 También puede obtener acceso a instancias WMI remotas mediante programación utilizando las clases proporcionadas por el espacio de nombres <xref:System.Management>. En el ejemplo de código siguiente se muestra cómo utilizar este recurso.  
  
```  
String wcfNamespace = String.Format(@"\\{0}\Root\ServiceModel",      
   this.serviceMachineName);  
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```
