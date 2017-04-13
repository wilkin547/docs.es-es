---
title: "Utilizaci&#243;n del instrumental de administraci&#243;n de Windows (WMI) para diagn&#243;sticos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe48738d-e31b-454d-b5ec-24c85c6bf79a
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Utilizaci&#243;n del instrumental de administraci&#243;n de Windows (WMI) para diagn&#243;sticos
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] expone datos de la inspección de un servicio en el tiempo de ejecución a través de un proveedor del Instrumental de administración de Windows \(WMI\) [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].  
  
## Habilitar WMI  
 WMI es la implementación de Microsoft del estándar Web\-Based Enterprise Management \(WBEM\).  [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] el SDK de WMI, vea MSDN Library.  \(http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/wmisdk\/wmi\/wmi\_start\_page.asp\).  WBEM es un estándar de la industria para saber cómo exponen las aplicaciones la instrumentación de administración a las herramientas de administración externas.  
  
 Un proveedor de WMI es un componente que expone la instrumentación en el tiempo de ejecución a través de una interfaz compatible con WBEM.  Está compuesto de un conjunto de objetos WMI con pares atributo\/valor.  Los pares pueden ser de varios tipos simples.  Las herramientas de administración pueden conectarse a los servicios a través de la interfaz en tiempo de ejecución.  [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] expone atributos de servicios como direcciones, enlaces, comportamientos y agentes de escucha.  
  
 El proveedor de WMI integrado puede activarse en el archivo de configuración de la aplicación.  Esto se consigue a través del atributo `wmiProviderEnabled` del elemento [\<diagnóstico\>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) en la sección del elemento [\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md), como se muestra en la configuración del ejemplo siguiente.  
  
```  
<system.serviceModel>  
    …  
    <diagnostics wmiProviderEnabled="true" />  
    …  
</system.serviceModel>  
  
```  
  
 Esta entrada de configuración expone una interfaz WMI.  Ahora, las aplicaciones de administración pueden establecer la conexión a través de esta interfaz y obtener acceso a la instrumentación de administración de la aplicación.  
  
## Obtener acceso a datos WMI  
 Puede obtenerse acceso a los datos WMI de maneras muy distintas.  Microsoft proporciona API de WMI para los scripts, aplicaciones [!INCLUDE[vbprvb](../../../../../includes/vbprvb-md.md)], aplicaciones C\+\+ y [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].  Para obtener más información, vea el tema sobre [cómo usar WMI](http://go.microsoft.com/fwlink/?LinkId=95183).  
  
> [!CAUTION]
>  Si utiliza los métodos proporcionados por .NET Framework para tener acceso mediante programación a los datos de WMI, debe tener en cuenta que tales métodos pueden iniciar excepciones una vez establecida la conexión.  La conexión no se establece durante la construcción de la instancia <xref:System.Management.ManagementObject>, sino con la primera solicitud que implique el intercambio real de datos.  Por lo tanto, utilice un bloque `try..catch` para detectar las posibles excepciones.  
  
 Puede cambiar la traza y el nivel de registro de mensajes, así como las opciones de registro de mensajes para el origen de traza de la traza `System.ServiceModel` en WMI.  Puede hacerlo accediendo a la instancia [AppDomainInfo](../../../../../docs/framework/wcf/diagnostics/wmi/appdomaininfo.md), que expone las siguientes propiedades booleanas: `LogMessagesAtServiceLevel`, `LogMessagesAtTransportLevel`, `LogMalformedMessages` y `TraceLevel`.  Por consiguiente, si configura un agente de escucha de traza para el registro de mensajes, pero define estas opciones en `false`, en la configuración, puede cambiarlas después a `true`, una vez se esté ejecutando la aplicación.  Esto habilitará de manera efectiva el registro de mensajes en el tiempo de ejecución.  De igual forma, si habilita el registro de mensajes en su archivo de configuración, puede deshabilitarlo en el tiempo de ejecución mediante WMI.  
  
 Debe tener en cuenta que si en el archivo de configuración no se especifica ningún agente de escucha de traza de registro de mensajes para el registro de mensajes, o no se especifica ningún agente de escucha de traza de `System.ServiceModel`, no se aplica ninguno de sus cambios, aunque WMI los acepte.  Para obtener más información acerca de cómo establecer correctamente los agentes de escucha respectivos, consulte [Configuración del registro de mensajes](../../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) y [Configurar seguimiento](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  El nivel de seguimiento de traza, del resto de los orígenes de traza de traza, especificado por la configuración es efectivo cuando se inicia la aplicación, y no se puede cambiar.  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] expone un método `GetOperationCounterInstanceName` para scripting.  Este método devuelve un nombre de instancia del contador de rendimiento si le proporciona un nombre de operación.  Sin embargo, no valida la entrada.  Por lo tanto, si proporciona un nombre de operación incorrecto, se devuelve un nombre de contador incorrecto.  
  
 La propiedad `OutgoingChannel` de la instancia `Service` no cuenta los canales abiertos por un servicio para establecer la conexión con otro servicio, si no se crea el cliente [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] del servicio de destino en el método `Service`.  
  
 **Precaución** WMI solo admite un valor <xref:System.TimeSpan> con un máximo de 3 separadores decimales.  Por ejemplo, si su servicio establece una de sus propiedades en <xref:System.TimeSpan.MaxValue>, su valor se trunca pasados los 3 separadores decimales cuando se ve mediante WMI.  
  
## Seguridad  
 Dado que el proveedor WMI [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] permite la detección de servicios en un entorno, debería tener una precaución extrema al permitir el acceso a él.  Si suaviza el acceso predeterminado exclusivo a los administradores, puede permitir el acceso de partes menos fiables a los datos confidenciales de su entorno.  En concreto, si suaviza los permisos de acceso remoto a WMI, pueden producirse ataques por inundación.  Si un proceso se inunda por un exceso de solicitudes de WMI, su rendimiento puede degradarse.  
  
 Además, si suaviza los permisos de acceso para el archivo MOF, partes menos fiables pueden manipular el comportamiento de WMI y modificar los objetos que se cargan en el esquema de WMI.  Por ejemplo, pueden quitarse campos de modo que se oculten datos críticos al administrador, que no se puedan rellenar campos, o provocar que se agreguen excepciones al archivo.  
  
 De manera predeterminada, el proveedor de WMI [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] otorga permisos "ejecutar métodos", "escritura del proveedor", y "habilitar cuentas" para el administrador, y el permiso "habilitar cuentas" para ASP.NET, el servicio local y el servicio de red.  En concreto, en plataformas no [!INCLUDE[wv](../../../../../includes/wv-md.md)], la cuenta de ASP.NET posee acceso de lectura al espacio de nombres ServiceModel de WMI.  Si no desea conceder estos privilegios a un grupo de usuarios determinado, debe desactivar el proveedor de WMI \(deshabilitado de manera predeterminada\), o deshabilitar el acceso para el grupo de usuarios concreto.  
  
 Además, al intentar habilitar WMI a través de la configuración, WMI puede no estar habilitada debido a un privilegio de usuario insuficiente.  No obstante, no se escribe ningún evento en el registro de eventos que registre este error.  
  
 Para modificar los niveles de privilegio del usuario, siga los pasos siguientes.  
  
1.  Haga clic en Inicio y, a continuación, en Ejecutar y escriba **compmgmt.msc**.  
  
2.  Haga clic con el botón secundario en **Servicios y Controles de Aplicación\/WMI** para seleccionar **Propiedades**.  
  
3.  Seleccione la pestaña **Seguridad**, y vaya al espacio de nombres **Root\/ServiceModel** .  Haga clic en el botón **Seguridad**.  
  
4.  Seleccione el grupo o usuario específico para el que desea controlar el acceso, y utilice la casilla **Permitir** o **Denegar** para configurar los permisos.  
  
## Conceder permisos de registro de WCF WMI a usuarios adicionales  
 WCF expone datos de administración a WMI.  Lo consigue hospedando un proveedor en proceso WMI, denominado a veces un “proveedor desacoplado”.  La cuenta que registra este proveedor debe tener los permisos apropiados para poder exponer los datos de administración.  En Windows, solo un pequeño conjunto de cuentas privilegiadas pueden registrar proveedores desacoplados de forma predeterminada. Esto supone un problema, ya que los usuarios normalmente desean exponer los datos WMI de un servicio WCF que se está ejecutando bajo una cuenta que no se encuentra en el conjunto predeterminado.  
  
 Para proporcionar este acceso, el administrador debe conceder los permisos siguientes a la cuenta adicional en el orden siguiente:  
  
1.  Permiso para tener acceso al espacio de nombres de WMI de WCF.  
  
2.  Permiso para registrar el proveedor desacoplado WMI de WCF.  
  
#### Para conceder permiso de acceso al espacio de nombres WMI  
  
1.  Ejecute el siguiente script de PowerShell.  
  
    ```powershell  
    write-host “”  
    write-host “Granting Access to root/servicemodel WMI namespace to built in users group”  
    write-host “”  
  
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
    write-host “”  
  
    ```  
  
     Este script de PowerShell usa el lenguaje de definición de descriptor de seguridad \(SDDL\) para conceder al grupo Usuarios integrado acceso al espacio de nombres WMI “root\/servicemodel”.  Especifica las ACL siguientes:  
  
    -   Cuenta predefinida Administrador \(BA\) \- Ya tenía acceso.  
  
    -   Servicio de red \(NS\) \- Ya tenía acceso.  
  
    -   Sistema local \(LS\) \- Ya tenía acceso.  
  
    -   Usuarios integrado \- El grupo al que se va a conceder acceso.  
  
#### Para conceder acceso de registro de proveedores  
  
1.  Ejecute el siguiente script de PowerShell.  
  
    ```powershell  
    write-host “”  
    write-host “Granting WCF provider registration access to built in users group”  
    write-host “”  
    # Set security on ServiceModel provider  
    $provider = get-WmiObject -namespace "root\servicemodel" __Win32Provider  
  
    write-host "Previous ACL: "$provider.SecurityDescriptor  
    $result = $provider.SecurityDescriptor = "O:BUG:BUD:(A;;0x1;;;BA)(A;;0x1;;;NS)(A;;0x1;;;LS)(A;;0x1;;;BU)"  
  
    # Commit the changes and display it to the console  
    $result = $provider.Put()  
    write-host "New ACL:      "$provider.SecurityDescriptor  
    write-host “”  
  
    ```  
  
### Conceder acceso a usuarios o grupos arbitrarios  
 En el ejemplo de esta sección se conceden privilegios de registro de proveedores WMI a todos los usuarios locales.  Si desea conceder acceso a un usuario o grupo no integrado, debe obtener el identificador de seguridad \(SID\) de dicho usuario o grupo.  No hay ninguna forma sencilla de obtener el SID de un usuario arbitrario.  Un método consiste en iniciar sesión como el usuario deseado y, a continuación, usar el comando shell siguiente.  
  
```  
Whoami /user  
```  
  
 Esto proporciona el SID del usuario actual, pero este método no se puede usar para obtener el SID de un usuario arbitrario.  Otro método para obtener el SID es usar la herramienta [getsid.exe](http://go.microsoft.com/fwlink/?LinkId=186467) en las [Herramientas del Kit de recursos de Windows 2000 para las tareas administrativas](http://go.microsoft.com/fwlink/?LinkId=178660).  Esta herramienta compara el SID de dos usuarios \(locales o del dominio\), y como efecto secundario imprime ambos SID en la línea de comandos.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][Identificadores de seguridad conocidos en los sistemas operativos Windows](http://go.microsoft.com/fwlink/?LinkId=186468).  
  
## Acceso a las instancias de objeto de WMI remotas  
 Si necesita tener acceso a las instancias WMI [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en un equipo remoto, debe habilitar la privacidad de paquete en las herramientas que utilice para el acceso.  La siguiente sección describe cómo conseguirlo mediante CIM Studio de WMI, la Herramienta de comprobación del instrumental de administración de Windows, y .NET SDK 2.0.  
  
### CIM Studio de WMI  
 Si ha instalado las [herramientas administrativas de WMI](http://go.microsoft.com/fwlink/?LinkId=95185), puede usar CIM Studio de WMI para obtener acceso a las instancias de WMI.  Las herramientas se encuentran en la carpeta siguiente  
  
 **%windir%\\Program Files\\WMI Tools\\**  
  
1.  En la ventana **Conectarse al espacio de nombres:**, escriba **root\\ServiceModel**, y haga clic en Aceptar.  
  
2.  En la ventana **Inicio de sesión de CIM Studio de WMI**, haga clic en el botón **Opciones \>\>** para expandir la ventana.  Seleccione **Privacidad de paquete** para el **Nivel de autenticación**, y haga clic en **Aceptar**.  
  
### Herramienta de comprobación del instrumental de administración de Windows  
 Windows instala esta herramienta.  Para ejecutarlo, inicie una consola de comandos escribiendo cmd.exe en el cuadro de diálogo **Iniciar\/Ejecutar**, y haga clic en **Aceptar**.  A continuación, escriba wbemtest.exe en la ventana de comandos.  Se inicia la Herramienta de comprobación del instrumental de administración de Windows.  
  
1.  Haga clic en el botón **Conectar** situado en la esquina superior derecha de la ventana.  
  
2.  En la nueva ventana, escriba **root\\ServiceModel** en el campo **Espacio de nombres**, y seleccione **Privacidad de paquete** para el Nivel de autenticación.  Haga clic en **Conectar**.  
  
### Utilización del código administrado  
 También puede obtener acceso a instancias WMI remotas mediante programación utilizando las clases proporcionadas por el espacio de nombres <xref:System.Management>.  En el ejemplo de código siguiente se muestra cómo utilizar este recurso.  
  
```  
String wcfNamespace = String.Format(@"\\{0}\Root\ServiceModel",      
   this.serviceMachineName);  
  
ConnectionOptions connection = new ConnectionOptions();  
connection.Authentication = AuthenticationLevel.PacketPrivacy;  
ManagementScope scope = new ManagementScope(this.wcfNamespace, connection);  
```