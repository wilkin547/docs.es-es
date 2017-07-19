---
title: "C&#243;mo auditar los eventos de seguridad de Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "seguridad [WCF], auditar eventos"
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# C&#243;mo auditar los eventos de seguridad de Windows Communication Foundation
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] permite registrar los eventos de seguridad en el registro de eventos de Windows, que puede consultarse utilizando el visor de eventos de Windows.  Este tema explica cómo configurar una aplicación para que registre los eventos de seguridad.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] la auditoría de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], vea [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
### Para auditar los eventos de seguridad en el código  
  
1.  Especifique la ubicación del registro de auditoría.  Para ello, establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> de la clase <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> en uno de los valores de enumeración <xref:System.ServiceModel.AuditLogLocation>, como se muestra en el código siguiente.  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     La enumeración <xref:System.ServiceModel.AuditLogLocation> tiene tres valores: `Application`, `Security`, o `Default`.  El valor especifica uno de los registros visibles en el visor de eventos, el registro de seguridad o de aplicaciones.  Si utiliza el valor `Default`, el registro real dependerá del sistema operativo en el que se está ejecutando la aplicación.  Si se habilita la auditoría y no se especifica la ubicación del registro, el valor predeterminado es el registro de `Security` en las plataformas que admiten escribir en el registro de seguridad; de lo contrario, se escribirá en el registro `Application`.  Solo [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wv](../../../../includes/wv-md.md)] permiten escribir de forma predeterminada en el registro de seguridad.  
  
2.  Establezca los tipos de eventos que se van a auditar.  Puede auditar, simultáneamente, eventos de nivel de servicio o eventos de nivel de autorización.  Establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> o la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> en uno de los valores de enumeración <xref:System.ServiceModel.AuditLevel>, como muestra el siguiente código.  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3.  Especifique si suprimir o exponer los errores a la aplicación relacionados con los eventos de auditoría del registro.  Establezca la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> en `true` o `false`, como muestra el siguiente código.  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     La propiedad `SuppressAuditFailure` predeterminada es `true`, de modo que el error que se audita no afecta a la aplicación.  De lo contrario, se inicia una excepción.  Para cualquier auditoría realizada correctamente, se escribe con detalle el seguimiento de la traza.  Para cualquier error que se audita, se escribe el seguimiento de la traza en el nivel del error.  
  
4.  Elimine el <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> existente de la colección de comportamientos encontrada en la descripción de <xref:System.ServiceModel.ServiceHost>.  A la colección de comportamiento tiene acceso la propiedad <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, a la que a su vez tiene acceso la propiedad <xref:System.ServiceModel.ServiceHostBase.Description%2A>.  A continuación, agregue el nuevo <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> a la misma colección, como se muestra en el código siguiente.  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### Para establecer la auditoría en la configuración  
  
1.  Para establecer la auditoría en la configuración, agregue un elemento [\<comportamiento\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) a la sección [\<comportamientos\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) del archivo web.config.  Después, agregue un elemento [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) y establezca los distintos atributos, como se muestra en el ejemplo siguiente.  
  
    ```  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"   
                serviceAuthorizationAuditLevel="None"   
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2.  Debe especificarse el comportamiento del servicio, como se muestra en el ejemplo siguiente.  
  
    ```  
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
  
## Ejemplo  
 El siguiente código crea una instancia de la clase <xref:System.ServiceModel.ServiceHost> y agrega un nuevo <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> a la colección de comportamientos.  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## Seguridad de .NET Framework  
 Cuando se establece la propiedad <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> como `true`, se suprime cualquier error que genere auditorías de seguridad \(si se establece como `false`, se inicia una excepción\).  Sin embargo, si habilita la siguiente propiedad **Local Security Setting** de Windows, un error que genere eventos de auditoría provocará el cierre inmediato de Windows:  
  
 **Auditoría: cierre el sistema inmediatamente si no se pueden registrar las auditorías de seguridad**  
  
 Para establecer la propiedad, abra el cuadro de diálogo **Configuración de seguridad local**.  En **Configuración de seguridad**, haga clic en **Directivas locales**.  A continuación, haga clic en **Opciones de seguridad**.  
  
 Si la propiedad <xref:System.ServiceModel.AuditLogLocation> está establecida como <xref:System.ServiceModel.AuditLogLocation> y **Auditar el acceso a objetos** no está definido en **Directiva de seguridad local**, los eventos de auditoría no se escribirán en el registro de seguridad.  Tenga en cuenta que no se devuelve ningún error, aunque las entradas de auditoría no se escriben en el registro de seguridad.  
  
## Vea también  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>   
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>   
 <xref:System.ServiceModel.AuditLogLocation>   
 [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)