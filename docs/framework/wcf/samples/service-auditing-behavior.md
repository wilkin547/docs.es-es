---
title: Comportamiento de auditoría de servicio
ms.date: 03/30/2017
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
ms.openlocfilehash: bfe13146a7f7cdec648a82a34c34077ec5466809
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599937"
---
# <a name="service-auditing-behavior"></a>Comportamiento de auditoría de servicio
Este ejemplo muestra cómo utilizar <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> para habilitar la auditoría de eventos de seguridad durante las operaciones de servicio. Este ejemplo se basa en el [Introducción](getting-started-sample.md). El servicio y el cliente se han configurado con [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) . El `mode` atributo de [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) se ha establecido en `Message` y se ha `clientCredentialType` establecido en `Windows` . En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
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
  
 Los registros de auditoría resultantes se pueden ver al ejecutar el Visor de eventos. De forma predeterminada, en Windows XP los eventos de auditoría se pueden ver en el registro de aplicaciones, mientras que en Windows Server 2003 y Windows Vista, los eventos de auditoría se pueden ver en el registro de seguridad. En Windows Server 2008 y Windows 7, los eventos de auditoría se pueden ver en los registros de aplicaciones y servicios. La ubicación de los eventos de auditoría se puede especificar estableciendo el `auditLogLocation` atributo en "Application" o "Security". Para obtener más información, consulte [Cómo: auditar eventos de seguridad](../feature-details/how-to-audit-wcf-security-events.md). Si los eventos se escriben en el registro de seguridad, se debe establecer LocalSecurityPolicy-> habilitar el acceso a objetos para "Success" y "Failure".  
  
 Al examinar el registro de eventos, el origen de los eventos de auditoría es "ServiceModel Audit 3.0.0.0". Los registros de auditoría de autenticación de mensajes tienen una categoría de "MessageAuthentication", mientras que los registros de auditoría de autorización de servicio tienen una categoría de "ServiceAuthorization".  
  
 Los eventos de auditoría de autenticación de mensajes incluyen si el mensaje se manipuló, si el mensaje ha expirado y si el cliente se puede autenticar en el servicio. Proporcionan información sobre si la autenticación fue correcta o no, así como la identidad del cliente, y el extremo al que se envió el mensaje, junto con la acción asociada al mensaje.  
  
 Los eventos de auditoría de autorización de servicio incluyen la decisión de la autorización realizada por un administrador de autorización del servicio. Proporcionan información sobre si la autorización tuvo éxito o no, así como la identidad del cliente, el extremo al que se envió el mensaje, la acción asociada al mensaje, el identificador del contexto de autorización que generó el mensaje entrante y el tipo del administrador de autorización que tomó la decisión sobre el acceso.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
## <a name="see-also"></a>Vea también

- [Auditoría](../feature-details/auditing-security-events.md)
- [Procedimiento para auditar eventos de seguridad](../feature-details/how-to-audit-wcf-security-events.md)
