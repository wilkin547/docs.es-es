---
title: Comportamiento de auditoría de servicio
ms.date: 03/30/2017
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
ms.openlocfilehash: ae190be48a20af5c108e56c6b0fd7965e39f8b66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="service-auditing-behavior"></a>Comportamiento de auditoría de servicio
Este ejemplo muestra cómo utilizar <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> para habilitar la auditoría de eventos de seguridad durante las operaciones de servicio. En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md). El servicio y el cliente se ha configurado mediante el [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). El `mode` atributo de la [ \<seguridad >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) se ha establecido en `Message` y `clientCredentialType` se ha establecido en `Windows`. En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 El archivo de configuración de servicio utiliza el elemento `serviceSecurityAudit` para configurar la auditoría.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      ...  
<!-- serviceSecurityAudit allows specification of audit location   
     and whether to audit success, failure or both. This service   
     logs success and failure of messageAuthentication   
     to the default location -->  
     <serviceSecurityAudit auditLogLocation ="Default" messageAuthenticationAuditLevel = "SuccessOrFailure" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente. Presione ENTRAR en la ventana de la consola para cerrar el cliente.  
  
 Los registros de auditoría resultantes se pueden ver al ejecutar el Visor de eventos. De forma predeterminada, en Windows XP los eventos de auditoría se pueden ver en el registro de aplicaciones, mientras que en Windows Server 2003 y Windows Vista, los eventos de auditoría se pueden ver en el registro de seguridad. En Windows Server 2008 y Windows 7, los eventos de auditoría se pueden ver en los registros de aplicaciones y servicios. Puede especificar la ubicación de los eventos de auditoría estableciendo el `auditLogLocation` atributo "Application" o "Seguridad". Para obtener más información, consulte [Cómo: eventos de auditoría de seguridad](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md). Si los eventos se escriben en el registro de seguridad, LocalSecurityPolicy-> Habilitar el acceso de objetos debería configurarse como "Success" y "Failure".  
  
 Al examinar el registro de eventos, el origen de los eventos de auditoría es "ServiceModel Audit 3.0.0.0". Registros de auditoría de autenticación de mensajes tienen una categoría de "MessageAuthentication" mientras registros de auditoría de autorización tienen una categoría de "ServiceAuthorization".  
  
 Los eventos de auditoría de autenticación de mensajes incluyen si el mensaje se manipuló, si el mensaje ha expirado y si el cliente se puede autenticar en el servicio. Proporcionan información sobre si la autenticación fue correcta o no, así como la identidad del cliente, y el extremo al que se envió el mensaje, junto con la acción asociada al mensaje.  
  
 Los eventos de auditoría de autorización de servicio incluyen la decisión de la autorización realizada por un administrador de autorización del servicio. Proporcionan información sobre si la autorización tuvo éxito o no, así como la identidad del cliente, el punto de conexión al que se envió el mensaje, la acción asociada al mensaje, el identificador del contexto de autorización que generó el mensaje entrante y el tipo del administrador de autorización que tomó la decisión sobre el acceso.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Vea también  
 [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [Auditoría de eventos de seguridad](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
