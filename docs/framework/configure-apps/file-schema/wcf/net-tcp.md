---
title: <net.tcp>
ms.date: 03/30/2017
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
ms.openlocfilehash: 4a3a17655f5469fe84c0b684ebdac9848bbfba84
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397693"
---
# \<net.tcp>
Especifica la configuración del servicio de uso compartido de puertos NET.TCP, que permite que varios procesos compartan el mismo puerto TCP.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<net.tcp>**  
  
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
|`listenBacklog`|Un entero que especifica las conexiones pendientes máximas que se aceptan desde la conexión compartida, pero que todavía no se envían a los servicios Windows Communication Foundation (WCF). El valor predeterminado es 10.|  
|`maxPendingAccepts`|Un entero que especifica el mayor número de subprocesos de aceptación simultáneos pendientes en el extremo de escucha para el servicio de uso compartido. El valor predeterminado es 2.|  
|`MaxPendingConnections`|Número máximo de conexiones que el agente de escucha puede tener en espera de aceptación por parte de la aplicación. Cuando se supera este valor de cuota, se pierden las nuevas conexiones entrantes en lugar de esperar a ser aceptadas. Características de conexión como la seguridad de mensaje pueden hacer que un cliente abra más de una conexión. Los administradores de servicio deberían tener en cuenta estas conexiones adicionales al establecer este valor de cuota. El valor predeterminado es 10.|  
|`receiveTimeout`|Un <xref:System.TimeSpan> que especifica el tiempo de espera para la lectura de datos de trama y para la conexión mediante el envío desde las conexiones subyacentes. El valor predeterminado es "00:00:10".|  
|`teredoEnabled`|Valor booleano que indica si el servicio de uso compartido de puertos utiliza el servicio Microsoft Teredo para realizar escuchas en puertos TCP en nombre de los servicios WCF. De manera predeterminada, es `false`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<allowAccounts>](allowaccounts.md)|Colección de elementos de configuración que contienen un `securityIdentifier` atributo para especificar las cuentas de usuario para los procesos que hospedan servicios WCF y tienen concedido acceso de conexión al servicio de uso compartido.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|Contiene la configuración para el proceso de agente de escucha SMSvcHost.exe.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre el uso compartido de puertos, consulte [uso compartido de puertos net. TCP](../../../wcf/feature-details/net-tcp-port-sharing.md). Para saber cómo configurar el servicio de uso compartido de puertos, vea [configurar el servicio de uso compartido de puertos net. TCP](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>
- [Uso compartido de puertos Net.TCP](../../../wcf/feature-details/net-tcp-port-sharing.md)
- [Configuración del servicio de uso compartido de puertos Net.TCP](../../../wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
