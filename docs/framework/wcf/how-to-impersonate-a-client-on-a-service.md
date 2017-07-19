---
title: "C&#243;mo suplantar a un cliente en un servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, suplantación"
  - "representación"
  - "WCF, seguridad"
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: 33
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 33
---
# C&#243;mo suplantar a un cliente en un servicio
Suplantar un cliente en un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] permite al servicio realizar acciones en nombre del cliente. Para las acciones sujetas a las comprobaciones de la lista de control de acceso \(ACL\), como el acceso a los directorios y archivos de un equipo o el acceso a una base de datos de SQL Server, ACL realiza una comprobación frente a la cuenta de usuario del cliente. Este tema muestra los pasos básicos requeridos para permitir a un cliente de un dominio de Windows establecer un nivel de la suplantación del cliente. Para obtener un ejemplo ilustrativo, consulte [Suplantar el cliente](../../../docs/framework/wcf/samples/impersonating-the-client.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] la suplantación de clientes, consulte [Delegación y suplantación](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
> [!NOTE]
>  Cuando el cliente y el servicio se están ejecutando en el mismo equipo y el cliente se está ejecutando bajo una cuenta del sistema \(por ejemplo, `Local System` o `Network Service`\), no se puede suplantar el cliente cuando se establece una sesión segura con tokens de contexto de seguridad con estado. Un WinForms o una aplicación de consola se ejecuta normalmente con la cuenta con la que haya iniciado la sesión, de manera que la cuenta pueda suplantarse de manera predeterminada. No obstante, cuando el cliente es una página [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] que se hospeda en [!INCLUDE[iis601](../../../includes/iis601-md.md)] o ISS 7.0, el cliente se ejecuta, de manera predeterminada, en la cuenta `Network Service`. Todos los enlaces proporcionados por el sistema que admiten sesiones seguras utilizan de forma predeterminada un token de contexto de seguridad sin estado. Sin embargo, si el cliente es una página de [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] y se usan sesiones seguras con tokens de contexto de seguridad con estado, no se puede suplantar al cliente.[!INCLUDE[crabout](../../../includes/crabout-md.md)] el uso de tokens de contexto de seguridad con estado en una sesión segura, consulte [Cómo: Crear un token de contexto de seguridad para una sesión segura](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### Para habilitar la suplantación de un cliente desde un token de Windows almacenado en memoria caché en un servicio  
  
1.  Cree el servicio. Para obtener un tutorial sobre este procedimiento básico, consulte [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
2.  Utilice un enlace que use autenticación de Windows y cree una sesión, como <xref:System.ServiceModel.NetTcpBinding> o <xref:System.ServiceModel.WSHttpBinding>.  
  
3.  Al crear la implementación de la interfaz del servicio, aplique la clase <xref:System.ServiceModel.OperationBehaviorAttribute> al método que requiere la suplantación del cliente. Establezca la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> en <xref:System.ServiceModel.ImpersonationOption>.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### Para establecer el nivel de suplantación permitido en el cliente  
  
1.  Cree el código de cliente del servicio mediante [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Acceso a los servicios mediante un cliente WCF](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).  
  
2.  Después de crear el cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], establezca la propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> de la clase <xref:System.ServiceModel.Security.WindowsClientCredential> en uno de los valores de enumeración <xref:System.Security.Principal.TokenImpersonationLevel>.  
  
    > [!NOTE]
    >  Para usar <xref:System.Security.Principal.TokenImpersonationLevel>, la autenticación de Kerberos negociada \(a veces conocida como Kerberos *multibifurcación* o *multipaso*\) se ha de usar. Para obtener una descripción sobre cómo realizar la implementación, consulte [Procedimientos recomendados de seguridad](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## Vea también  
 <xref:System.ServiceModel.OperationBehaviorAttribute>   
 <xref:System.Security.Principal.TokenImpersonationLevel>   
 [Suplantar el cliente](../../../docs/framework/wcf/samples/impersonating-the-client.md)   
 [Delegación y suplantación](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)