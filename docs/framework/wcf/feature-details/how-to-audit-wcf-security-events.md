---
title: Procedimiento Auditar eventos de seguridad de Windows Communication Foundation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 634489ced9b437d7b273eb5fa1092165cc6a935f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047976"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a>Procedimiento Auditar eventos de seguridad de Windows Communication Foundation
Windows Communication Foundation (WCF) le permite registrar eventos de seguridad en el registro de eventos de Windows, que se pueden ver mediante el Visor de eventos de Windows. Este tema explica cómo configurar una aplicación para que registre los eventos de seguridad. Para obtener más información acerca de la auditoría de WCF, vea [auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
### <a name="to-audit-security-events-in-code"></a>Para auditar los eventos de seguridad en el código  
  
1. Especifique la ubicación del registro de auditoría. Para ello, establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> de la clase <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> en uno de los valores de enumeración <xref:System.ServiceModel.AuditLogLocation>, como se muestra en el código siguiente.  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     El <xref:System.ServiceModel.AuditLogLocation> enumeración tiene tres valores: `Application`, `Security`, o `Default`. El valor especifica uno de los registros visibles en el visor de eventos, el registro de seguridad o de aplicaciones. Si utiliza el valor `Default`, el registro real dependerá del sistema operativo en el que se está ejecutando la aplicación. Si se habilita la auditoría y no se especifica la ubicación del registro, el valor predeterminado es el registro de `Security` en las plataformas que admiten escribir en el registro de seguridad; de lo contrario, se escribirá en el registro `Application`. Solo [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wv](../../../../includes/wv-md.md)] permiten escribir de forma predeterminada en el registro de seguridad.  
  
2. Establezca los tipos de eventos que se van a auditar. Puede auditar, simultáneamente, eventos de nivel de servicio o eventos de nivel de autorización. Establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> o la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> en uno de los valores de enumeración <xref:System.ServiceModel.AuditLevel>, como muestra el siguiente código.  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. Especifique si suprimir o exponer los errores a la aplicación relacionados con los eventos de auditoría del registro. Establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> en `true` o `false`, como muestra el siguiente código.  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     La propiedad `SuppressAuditFailure` predeterminada es `true`, de modo que el error que se audita no afecta a la aplicación. De lo contrario, se inicia una excepción. Para cualquier auditoría realizada correctamente, se escribe con detalle el seguimiento de la traza. Para cualquier error que se audita, se escribe el seguimiento de la traza en el nivel del error.  
  
4. Elimine el <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> existente de la colección de comportamientos encontrada en la descripción de <xref:System.ServiceModel.ServiceHost>. A la colección de comportamiento tiene acceso la propiedad <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, a la que a su vez tiene acceso la propiedad <xref:System.ServiceModel.ServiceHostBase.Description%2A>. A continuación, agregue el nuevo <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> a la misma colección, como se muestra en el código siguiente.  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a>Para establecer la auditoría en la configuración  
  
1. Para configurar la auditoría en la configuración, agregue un [ \<comportamiento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento a la [ \<comportamientos >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) sección del archivo web.config. A continuación, agregue un [ \<serviceSecurityAudit >](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) y establezca los distintos atributos, como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"   
                serviceAuthorizationAuditLevel="None"   
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2. Debe especificarse el comportamiento del servicio, como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"   
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"   
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a>Ejemplo  
 El siguiente código crea una instancia de la clase <xref:System.ServiceModel.ServiceHost> y agrega un nuevo <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> a la colección de comportamientos.  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Cuando se establece la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> como `true`, se suprime cualquier error que genere auditorías de seguridad (si se establece como `false`, se inicia una excepción). Sin embargo, si habilita el siguiente Windows **configuración de seguridad Local** propiedad, un error al generar eventos de auditoría hará que Windows cierre inmediato:  
  
 **Auditoría: Apagar el sistema inmediatamente si no se puede registrar las auditorías de seguridad**  
  
 Para establecer la propiedad, abra el **configuración de seguridad Local** cuadro de diálogo. En **configuración de seguridad**, haga clic en **directivas locales**. A continuación, haga clic en **las opciones de seguridad**.  
  
 Si el <xref:System.ServiceModel.AuditLogLocation> propiedad está establecida en <xref:System.ServiceModel.AuditLogLocation.Security> y **auditar el acceso a objetos** no está establecido en el **directiva de seguridad Local**, eventos de auditoría no se escribirán en el registro de seguridad. Tenga en cuenta que no se devuelve ningún error, aunque las entradas de auditoría no se escriben en el registro de seguridad.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
