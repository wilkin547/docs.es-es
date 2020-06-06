---
title: <serviceSecurityAudit>
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
ms.openlocfilehash: 10888f26053014ffb1fec49d1dfe87c7fd09ab54
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399578"
---
# \<serviceSecurityAudit>
Especifica valores que habilitan la auditoría de eventos de seguridad durante las operaciones del servicio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceSecurityAudit>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<serviceSecurityAudit auditLogLocation="Default/Application/Security"
                      messageAuthenticationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"
                      suppressAuditFailure="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|auditLogLocation|Especifica la ubicación del registro de auditoría. Los valores válidos incluyen los siguientes:<br /><br /> -Default: los eventos de seguridad se escriben en el registro de la aplicación en Windows XP y en el registro de eventos en Windows Server 2003 y Windows Vista.<br />-Application: los eventos de auditoría se escriben en el registro de eventos de la aplicación.<br />-Security: los eventos de auditoría se escriben en el registro de eventos de seguridad.<br /><br /> El valor predeterminado es Default. Para obtener más información, vea <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.<br /><br /> Se debería notificar a las aplicaciones de los errores de escritura en el registro de auditoría. Si su aplicación no está diseñada para administrar errores de auditoría, debería usar este atributo para suprimir errores de escritura en el registro de auditoría.<br /><br /> Si este atributo es `true`, el sistema administra excepciones distintas de OutOfMemoryException, StackOverFlowException, ThreadAbortException y ArgumentException que son el resultado de los intentos de escribir los eventos de auditoría y no se propagan a la aplicación. Si este atributo es `false`, todas las excepciones que son el resultado de los intentos por escribir los eventos de auditoría se pasan a la aplicación.<br /><br /> De manera predeterminada, es `true`.|  
|serviceAuthorizationAuditLevel|Especifica los tipos de eventos de autorización que se graban en el registro de auditoría. Los valores válidos incluyen los siguientes:<br /><br /> -None: no se realiza ninguna auditoría de eventos de autorización de servicio.<br />-Success: solo se auditan los eventos de autorización de servicio correctos.<br />-Error: solo se auditan los eventos de autorización de servicio con errores.<br />-SuccessOrFailure: se auditan los eventos de autorización de servicio correctos y erróneos.<br /><br /> El valor predeterminado es Ninguno. Para obtener más información, vea <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Especifica el tipo de eventos de auditoría de autenticación de mensajes registrados. Los valores válidos incluyen los siguientes:<br /><br /> -None: no se generan eventos de auditoría.<br />-Success: solo se registran los eventos de seguridad correcta (validación completa, incluidos la validación de la firma del mensaje, el cifrado y la validación del token).<br />-Error: solo se registran los eventos de error.<br />-SuccessOrFailure: se registran los eventos correctos y los errores.<br /><br /> El valor predeterminado es Ninguno. Para obtener más información, vea <xref:System.ServiceModel.AuditLevel>.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Este elemento de configuración se utiliza para auditar eventos de autenticación Windows Communication Foundation (WCF). Cuando la auditoría está habilitada, se pueden auditar intentos de autenticación correctos (o ambos) o fallidos. Los eventos se escriben en uno de tres registros de eventos: aplicación, seguridad o registro predeterminado para la versión de sistema operativo. Los registros de eventos  se pueden ver utilizando el Visor de eventos de Windows.  
  
 Para obtener un ejemplo detallado del uso de este elemento de configuración, vea comportamiento de la [Auditoría del servicio](../../../wcf/samples/service-auditing-behavior.md).  
  
 De forma predeterminada, en Windows XP los eventos de auditoría se pueden ver en el registro de aplicaciones, mientras que en Windows Server 2003 y Windows Vista, los eventos de auditoría se pueden ver en el registro de seguridad. Se puede especificar la ubicación de los eventos de auditoría estableciendo el atributo `auditLogLocation` en 'Aplicación' o 'Seguridad'. Para obtener más información, consulte [Cómo: auditar eventos de seguridad](../../../wcf/feature-details/how-to-audit-wcf-security-events.md). Si los eventos se escriben en el registro de seguridad, se debe establecer el valor de LocalSecurityPolicy-> habilitar el acceso a objetos para "Success" y "Failure".  
  
 Al examinar el registro de eventos, el origen de los eventos de auditoría es "ServiceModel Audit 3.0.0.0". Los registros de auditoría de autenticación de mensajes tienen una categoría de "MessageAuthentication" mientras que los registros de auditoría de autorización tienen una categoría de 'ServiceAuthorization'.  
  
 Los eventos de auditoría de autenticación de mensajes incluyen si el mensaje se manipuló, si el mensaje ha expirado y si el cliente puede autenticar el servicio. Proporcionan información sobre si la autenticación fue correcta o no con la identidad del cliente y el punto de conexión al que se envió el mensaje, junto con la acción asociada al mensaje.  
  
 Los eventos de auditoría de autorización de servicio incluyen la decisión de la autorización realizada por un administrador de autorización del servicio. Proporcionan información sobre si la autorización tuvo éxito o no, así como la identidad del cliente, el extremo al que se envió el mensaje, la acción asociada al mensaje, el identificador del contexto de autorización que se generó a partir del mensaje entrante y el tipo de administrador de autorización que tomó la decisión de acceso.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<system.serviceModel>
  <behaviors>
    <serviceBehaviors>
      <behavior name="NewBehavior">
        <serviceSecurityAudit auditLogLocation="Application"
                              suppressAuditFailure="true"
                              serviceAuthorizationAuditLevel="Success"
                              messageAuthenticationAuditLevel="Success" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- [Comportamientos de seguridad](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [Auditoría](../../../wcf/feature-details/auditing-security-events.md)
- [Procedimiento para auditar eventos de seguridad](../../../wcf/feature-details/how-to-audit-wcf-security-events.md)
- [Comportamiento de auditoría de servicio](../../../wcf/samples/service-auditing-behavior.md)
