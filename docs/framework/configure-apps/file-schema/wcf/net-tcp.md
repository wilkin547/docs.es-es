---
title: '&lt;NET.TCP&gt;'
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: ae6837bf6dc8167e165a3adcd1fca8abc3dcd396
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43500816"
---
# <a name="ltnettcpgt"></a>&lt;NET.TCP&gt;
Especifica la configuración del servicio de uso compartido de puertos NET.TCP, que permite que varios procesos compartan el mismo puerto TCP.  
  
 \<system.serviceModel.activation >  
\<NET.TCP >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
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
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`listenBacklog`|Un entero que especifica las conexiones pendientes máximas que se aceptan desde la conexión compartida, pero todavía no se envían a los servicios de Windows Communication Foundation (WCF). El valor predeterminado es 10.|  
|`maxPendingAccepts`|Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido. El valor predeterminado es 2.|  
|`MaxPendingConnections`|Número máximo de conexiones que el agente de escucha puede tener en espera de aceptación por parte de la aplicación. Cuando se supera este valor de cuota, se pierden las nuevas conexiones entrantes en lugar de esperar a ser aceptadas. Características de conexión como la seguridad de mensaje pueden hacer que un cliente abra más de una conexión. Los administradores de servicio deberían tener en cuenta estas conexiones adicionales al establecer este valor de cuota. El valor predeterminado es 10.|  
|`receiveTimeout`|Un `TimeSpan` que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes. El valor predeterminado es "00:00:10".|  
|`teredoEnabled`|Un valor booleano que indica si el servicio de uso compartido de puerto utiliza el servicio Microsoft Teredo para realizar escuchas en puertos TCP en nombre de los servicios de WCF. De manera predeterminada, es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<allowAccounts >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Una colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedidos acceso de conexión al servicio de uso compartido.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre el uso compartido de puertos, consulte [uso compartido de puertos Net.TCP](https://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded). Para comprender cómo configurar el puerto de servicio de uso compartido, consulte [configurar el servicio de uso compartido de puertos Net.TCP](https://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [Uso compartido de puertos Net.TCP](https://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [Configuración del servicio de uso compartido de puertos Net.TCP](https://msdn.microsoft.com/library/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
