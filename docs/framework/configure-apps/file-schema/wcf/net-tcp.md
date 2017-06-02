---
title: "&lt;net.tcp&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# &lt;net.tcp&gt;
Especifica la configuración del servicio de uso compartido de puertos NET.TCP, que permite que varios procesos compartan el mismo puerto TCP.  
  
## Sintaxis  
  
```  
  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`listenBacklog`|Un entero que especifica las conexiones pendientes máximas que se aceptan desde la conexión compartida, pero todavía no se envían a los servicios [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  El valor predeterminado es 10.|  
|`maxPendingAccepts`|Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido.  El valor predeterminado es 2.|  
|`MaxPendingConnections`|Número máximo de conexiones que el agente de escucha puede tener en espera de aceptación por parte de la aplicación.  Cuando se supera este valor de cuota, se pierden las nuevas conexiones entrantes en lugar de esperar a ser aceptadas.  Características de conexión como la seguridad de mensaje pueden hacer que un cliente abra más de una conexión.  Los administradores de servicio deberían tener en cuenta estas conexiones adicionales al establecer este valor de cuota.  El valor predeterminado es 10.|  
|`receiveTimeout`|Un <xref:System.Timespan> que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes.  El valor predeterminado es "00:00:10".|  
|`teredoEnabled`|Un valor booleano que indica si el servicio de uso compartido de puerto utiliza el servicio Microsoft Teredo para realizar escuchas en puertos TCP en nombre de los servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].  De manera predeterminada, es `false`.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<allowAccounts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Una colección de elementos de configuración que contiene un atributo `securityIdentifier` que especifica cuentas de usuario para los procesos que hospedan servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y se concede el acceso de conexión al servicio de uso compartido.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.serviceModel.activation\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.|  
  
## Comentarios  
 Para obtener más información sobre el uso compartido de puertos, vea [Net.TCP Port Sharing](http://msdn.microsoft.com/es-es/f13692ee-a179-4439-ae72-50db9534eded).  Para entender cómo configurar el servicio de uso compartido de puertos, vea [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/es-es/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).  
  
## Vea también  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>   
 [Net.TCP Port Sharing](http://msdn.microsoft.com/es-es/f13692ee-a179-4439-ae72-50db9534eded)   
 [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/es-es/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)