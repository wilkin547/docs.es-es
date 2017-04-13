---
title: "&lt;serviceSecurityAudit&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
caps.latest.revision: 17
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 17
---
# &lt;serviceSecurityAudit&gt;
Especifica valores que habilitan la auditoría de eventos de seguridad durante las operaciones del servicio.  
  
## Sintaxis  
  
```  
  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessAndFailure"  
   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessAndFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|auditLogLocation|Especifica la ubicación del registro de auditoría.  Los valores válidos son los siguientes:<br /><br /> -   Default: los eventos Security se escriben en el registro de aplicaciones en Windows XP y en el Registro de eventos de Windows Server 2003 y Windows Vista.<br />-   Application: los eventos de auditoría se escriben en el Application Event Log.<br />-   Security: los eventos de auditoría se escriben en el Security Event Log.<br /><br /> El valor predeterminado es Default.  Para obtener más información, consulta <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Un valor booleano que especifica el comportamiento para suprimir errores al escribir en el registro de auditoría.<br /><br /> Se debería notificar a las aplicaciones de los errores de escritura en el registro de auditoría.  Si su aplicación no está diseñada para administrar errores de auditoría, debería usar este atributo para suprimir errores de escritura en el registro de auditoría.<br /><br /> Si este atributo es `true`, el sistema administra excepciones distintas de OutOfMemoryException, StackOverFlowException, ThreadAbortException y ArgumentException que son el resultado de los intentos de escribir los eventos de auditoría y no se propagan a la aplicación.  Si este atributo es `false`, todas las excepciones que son el resultado de los intentos por escribir los eventos de auditoría se pasan a la aplicación.<br /><br /> De manera predeterminada, es `true`.|  
|serviceAuthorizationAuditLevel|Especifica los tipos de eventos de autorización que se graban en el registro de auditoría.  Los valores válidos son los siguientes:<br /><br /> -   None: no se realiza ninguna auditoría de eventos de autorización de servicio.<br />-   Success: sólo se auditan los eventos de autorización de servicio correctos.<br />-   Failure: sólo se auditan los eventos de autorización de servicio erróneos.<br />-   SuccessAndFailure: se auditan los eventos de autorización de servicio correctos y erróneos.<br /><br /> El valor predeterminado es None.  Para obtener más información, consulta <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Especifica el tipo de eventos de auditoría de autenticación de mensajes registrados.  Los valores válidos son los siguientes:<br /><br /> -   None: no se genera ningún evento de auditoría.<br />-   Success: sólo los eventos de seguridad \(validación completa incluida la validación de la firma del mensaje, cero y validación del token\) correctos están registrados.<br />-   Failure: sólo los eventos de error están registrados.<br />-   SuccessAndFailure: los eventos correctos y erróneos están registrados.<br /><br /> El valor predeterminado es None.  Para obtener más información, consulta <xref:System.ServiceModel.AuditLevel>.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## Comentarios  
 Este elemento de configuración se utiliza para auditar los eventos de autenticación de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  Cuando la auditoría está habilitada, se pueden auditar intentos de autenticación correctos \(o ambos\) o fallidos.  Los eventos se escriben en uno de tres registros de eventos: aplicación, seguridad o registro predeterminado para la versión de sistema operativo.  Los registros de eventos  se pueden ver utilizando el Visor de eventos de Windows.  
  
 Para obtener un ejemplo detallado de utilizar este elemento de configuración, vea [Comportamiento de auditoría de servicio](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).  
  
 De forma predeterminada, en Windows XP los eventos de auditoría se pueden ver en el registro de aplicaciones, mientras que en Windows Server 2003 y Windows Vista, los eventos de auditoría se pueden ver en el registro de seguridad.  Se puede especificar la ubicación de los eventos de auditoría estableciendo el atributo `auditLogLocation` en 'Aplicación' o 'Seguridad'.  Para obtener más información, consulta [Cómo: Auditar eventos de seguridad.](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).  Si los eventos se escriben el registro de seguridad, LocalSecurityPolicy \-\> Habilitar el acceso de objetos debería estar configurado en "Éxito" y "Error."  
  
 Al examinar el registro de eventos, el origen de los eventos de auditoría es "ServiceModel Audit 3.0.0.0".  Los registros de auditoría de autenticación de mensajes tienen una categoría de "MessageAuthentication" mientras que los registros de auditoría de autorización tienen una categoría de 'ServiceAuthorization'.  
  
 Los eventos de auditoría de autenticación de mensajes incluyen si el mensaje se manipuló, si el mensaje ha expirado y si el cliente puede autenticar el servicio.  Proporcionan información sobre si la autenticación fue correcta o no con la identidad del cliente y el extremo al que se envió el mensaje, junto con la acción asociada al mensaje.  
  
 Los eventos de auditoría de autorización de servicio incluyen la decisión de la autorización realizada por un administrador de autorización del servicio.  Proporcionan información sobre si la autorización fue correcta o no con la identidad del cliente, el extremo al que se envió el mensaje, la acción asociada al mensaje, el identificador del contexto de autorización que generó el mensaje entrante y el tipo del administrador de autorización que tomó la decisión de acceso.  
  
## Ejemplo  
  
```  
<system.serviceModel>  
   <serviceBehaviors>  
      <behavior name="NewBehavior">  
         <serviceSecurityAudit auditLogLocation="Application"   
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"   
             messageAuthenticationAuditLevel="Success" />  
      </behavior>  
   </serviceBehaviors>  
</behaviors>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>   
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>   
 [Comportamientos de seguridad](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Auditoría](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)   
 [Cómo: Auditar eventos de seguridad.](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)   
 [Comportamiento de auditoría de servicio](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)