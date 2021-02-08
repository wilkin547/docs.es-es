---
description: 'Más información acerca de cómo: suplantar a un cliente en un servicio'
title: Procedimiento para suplantar a un cliente en un servicio
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
ms.openlocfilehash: 84d50b0c22161a829da66e42b4b3bbf004b68487
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779379"
---
# <a name="how-to-impersonate-a-client-on-a-service"></a>Procedimiento para suplantar a un cliente en un servicio

La suplantación de un cliente en un servicio de Windows Communication Foundation (WCF) permite al servicio realizar acciones en nombre del cliente. Para las acciones sujetas a las comprobaciones de la lista de control de acceso (ACL), como el acceso a los directorios y archivos de un equipo o el acceso a una base de datos de SQL Server, ACL realiza una comprobación frente a la cuenta de usuario del cliente. Este tema muestra los pasos básicos requeridos para permitir a un cliente de un dominio de Windows establecer un nivel de la suplantación del cliente. Para obtener un ejemplo ilustrativo, consulte [Impersonating the Client](./samples/impersonating-the-client.md). Para obtener más información sobre la suplantación de clientes, consulte [delegación y suplantación](./feature-details/delegation-and-impersonation-with-wcf.md).  
  
> [!NOTE]
> Cuando el cliente y el servicio se están ejecutando en el mismo equipo y el cliente se está ejecutando bajo una cuenta del sistema (por ejemplo, `Local System` o `Network Service`), no se puede suplantar el cliente cuando se establece una sesión segura con tokens de contexto de seguridad con estado. Un WinForms o una aplicación de consola se ejecuta normalmente con la cuenta con la que haya iniciado la sesión, de manera que la cuenta pueda suplantarse de manera predeterminada. Sin embargo, cuando el cliente es una página de ASP.NET y esa página se hospeda en IIS 6,0 o IIS 7,0, el cliente se ejecuta en la `Network Service` cuenta de forma predeterminada. Todos los enlaces proporcionados por el sistema que admiten sesiones seguras utilizan de forma predeterminada un token de contexto de seguridad sin estado. Sin embargo, si el cliente es una página de ASP.NET y se usan sesiones seguras con tokens de contexto de seguridad con estado, el cliente no se puede suplantar. Para obtener más información sobre el uso de tokens de contexto de seguridad con estado en una sesión segura, consulte [Cómo: crear un token de contexto de seguridad para una sesión segura](./feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a>Para habilitar la suplantación de un cliente desde un token de Windows almacenado en memoria caché en un servicio  
  
1. Cree el servicio. Para obtener un tutorial sobre este procedimiento básico, consulte [Getting Started Tutorial](getting-started-tutorial.md).  
  
2. Utilice un enlace que use autenticación de Windows y cree una sesión, como <xref:System.ServiceModel.NetTcpBinding> o <xref:System.ServiceModel.WSHttpBinding>.  
  
3. Al crear la implementación de la interfaz del servicio, aplique la clase <xref:System.ServiceModel.OperationBehaviorAttribute> al método que requiere la suplantación del cliente. Establezca la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> en <xref:System.ServiceModel.ImpersonationOption.Required>.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a>Para establecer el nivel de suplantación permitido en el cliente  
  
1. Cree el código de cliente del servicio mediante [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md). Para obtener más información, vea [obtener acceso a servicios mediante un cliente WCF](accessing-services-using-a-wcf-client.md).  
  
2. Después de crear el cliente de WCF, establezca la <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> propiedad de la <xref:System.ServiceModel.Security.WindowsClientCredential> clase en uno de los <xref:System.Security.Principal.TokenImpersonationLevel> valores de enumeración.  
  
    > [!NOTE]
    > Para usar <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, la autenticación de Kerberos negociada (a veces conocida como Kerberos *multibifurcación* o *multipaso* ) se ha de usar. Para obtener una descripción de cómo implementarlo, consulte [prácticas recomendadas para la seguridad](./feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.OperationBehaviorAttribute>
- <xref:System.Security.Principal.TokenImpersonationLevel>
- [Suplantar el cliente](./samples/impersonating-the-client.md)
- [Delegación y suplantación](./feature-details/delegation-and-impersonation-with-wcf.md)
