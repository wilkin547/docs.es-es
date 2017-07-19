---
title: "Configuraci&#243;n del servicio de uso compartido de puertos Net.TCP | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b6dd81fa-68b7-4e1b-868e-88e5901b7ea0
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Configuraci&#243;n del servicio de uso compartido de puertos Net.TCP
Los servicios autohospedados que utilizan el transporte Net.TCP pueden controlar varios ajustes avanzados, como `ListenBacklog` y `MaxPendingAccepts`, que rigen el comportamiento del socket de TCP subyacente utilizado para la comunicación por red.  Sin embargo, esta configuración para cada socket solo se aplica en el nivel de enlace si el enlace de transporte ha deshabilitado el uso compartido de puertos, que está habilitado de forma predeterminada.  
  
 Cuando un enlace net.tcp habilita el uso compartido de puertos \(estableciendo `portSharingEnabled =true` en el elemento de enlace de transporte\), permite implícitamente a un proceso externo \(concretamente SMSvcHost.exe, que hospeda el servicio de uso compartido de puertos Net.TCP\) que administre el socket TCP en su nombre.  Por ejemplo, al utilizar TCP, especifique:  
  
```  
    <tcpTransport   
        portSharingEnabled="true"  
/>  
```  
  
 Cuando se configura de esta manera, los valores de socket especificados en el elemento de enlace de transporte del servicio se omiten a favor de los valores de socket especificados por SMSvcHost.exe.  
  
 Para configurar SMSvcHost.exe, cree un archivo de configuración XML denominado SmSvcHost.exe.config y colóquelo en el mismo directorio físico que el archivo ejecutable SMSvcHost.exe \(por ejemplo, C:\\Windows\\Microsoft.NET\\Framework\\v4.5\).  
  
 El siguiente ejemplo muestra un SMSvcHost.exe.config de ejemplo, con la configuración predeterminada de todos los valores configurables declarados explícitamente.  
  
```  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="16" <!—16 * # of processors -->  
          maxPendingAccepts="4"<!— 4 * # of processors -->  
          maxPendingConnections="100"  
          receiveTimeout="00:00:30" <!—30 seconds -->  
          teredoEnabled="false">  
          <allowAccounts>  
             <!-- LocalSystem account -->  
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->  
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->  
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->  
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only) -->  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
</configuration>  
```  
  
## Cuándo modificar SMSvcHost.exe.config  
 En general, se debería tener cuidado al modificar el contenido del archivo SMSvcHost.exe.config, porque cualquier configuración especificada en este archivo afecta a todos los servicios de un equipo que utiliza el servicio de uso compartido de puertos de Net.TCP.  Esto incluye a las aplicaciones en [!INCLUDE[wv](../../../../includes/wv-md.md)] que utilizan las características de activación TCP de Windows Process Activation Service \(WAS\).  
  
 Sin embargo, a veces puede necesitar cambiar la configuración predeterminada del servicio de uso compartido de puertos de Net.TCP.  Por ejemplo, el valor predeterminado de `maxPendingAccepts` es 4 \* número de procesadores.  Los servidores que hospedan un gran número de servicios que usan el uso compartido de puertos pueden aumentar este valor para lograr un rendimiento máximo.  El valor predeterminado para `maxPendingConnections` es 100.  Considere aumentar este valor también si hay clientes varios simultáneos que llaman al servicio y el servicio está quitando conexiones de cliente.  
  
 SMSvcHost.exe.config también contiene información sobre las identidades de proceso que pueden utilizar el servicio de uso compartido de puertos.  Cuando un proceso se conecta al servicio de uso compartido de puertos para utilizar un puerto TCP compartido, la identidad del proceso de conexión se compara frente a una lista de identidades a las que se permite el uso del servicio de uso compartido de puertos.  Estas identidades se especifican como identificadores de seguridad \(SID\) en la sección \<allowAccounts\> del archivo SMSvcHost.exe.config.  De forma predeterminada, el permiso de uso del servicio de uso compartido de puertos se concede a las cuentas del sistema \(LocalService, LocalSystem y NetworkService\) así como a los miembros del grupo Administradores.  Las aplicaciones que permiten a un proceso se ejecuta como otra identidad \(por ejemplo, una identidad de usuario\) que se conecten al servicio de uso compartido de puertos deben agregar explícitamente el SID adecuado a SMSvcHost.exe.config \(estos cambios no se aplican hasta que se reinicie el proceso de SMSvc.exe\).  
  
> [!NOTE]
>  En los sistemas [!INCLUDE[wv](../../../../includes/wv-md.md)] con el Control de cuentas de usuario \(UAC\) habilitado, los usuarios locales necesitan permisos elevados aun cuando su cuenta sea miembro del grupo Administradores.  Para permitir a estos usuarios utilizar el servicio de uso compartido de puertos sin elevación, debe agregarse el SID del usuario \(o el SID de un grupo del que el usuario sea miembro\) explícitamente a la sección \<allowAccounts\> de SMSvcHost.exe.config.  
  
> [!WARNING]
>  El archivo SMSvcHost.exe.config predeterminado especifica un valor `etwProviderId` personalizado para evitar que el seguimiento de SMSvcHost.exe interfiera con los seguimientos del servicio.  
  
## Vea también  
 [\<net.tcp\>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)