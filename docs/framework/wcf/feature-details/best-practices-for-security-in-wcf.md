---
title: Procedimientos recomendados acerca de seguridad en WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- best practices [WCF], security
ms.assetid: 3639de41-1fa7-4875-a1d7-f393e4c8bd69
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: ad5e459e7dc070b9412de860048c840f677421f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-security-in-wcf"></a>Procedimientos recomendados acerca de seguridad en WCF
Las siguientes secciones enumeran los procedimientos recomendados que hay que tener en cuenta a la hora de crear aplicaciones seguras mediante [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]seguridad, consulte [consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md), [consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md), y [consideraciones de seguridad con metadatos](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md).  
  
## <a name="identify-services-performing-windows-authentication-with-spns"></a>Identificación de los servicios que utilizan la autenticación de Windows con SPN  
 Los servicios se pueden identificar con nombres principales del usuario (UPN) o nombres de entidad de seguridad de servicio (SPN). Los servicios que se ejecutan con cuentas de equipo tales como servicio de red tienen una identidad de SPN que corresponde al equipo en que se ejecutan. Los servicios que se ejecutan con cuentas de usuario tienen una identidad de UPN que corresponde al usuario en nombre del que se ejecutan, aunque se puede usar la herramienta `setspn` para asignar un SPN a la cuenta de usuario. Configurar un servicio de modo que se pueda identificar a través del SPN y configurar los clientes que se conectan al servicio de manera que utilicen ese SPN puede dificultar ciertos ataques. Esta guía se aplica a los enlaces que utilizan la negociación Kerberos o SSPI.  Los clientes todavía deberían especificar el SPN si SSPI retrocede a NTLM.  
  
## <a name="verify-service-identities-in-wsdl"></a>Comprobación de las identidades de servicio en WSDL  
 WS-SecurityPolicy permite a los servicios publicar información sobre sus propias identidades en los metadatos. Cuando se recupera a través de `svcutil` u otros métodos como <xref:System.ServiceModel.Description.WsdlImporter>, esta información de identidad se convierte en las propiedades de identidad de las direcciones de extremo del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Los clientes que no comprueban que estas identidades de servicio son correctas y válidas, omiten la autenticación del servicio. Un servicio malintencionado se puede aprovechar de estos clientes para ejecutar ataques de reenvío de credenciales y otros ataques de tipo "Man in the middle" cambiando la identidad alegada en su WSDL.  
  
## <a name="use-x509-certificates-instead-of-ntlm"></a>Uso de certificados X509 en lugar de NTLM  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona dos mecanismos para la autenticación punto a punto: los certificados X509 (utilizados por el canal del mismo nivel) y la autenticación de Windows, donde la negociación SSPI disminuye de Kerberos a NTLM.  Se prefiere la autenticación basada en certificado con tamaños de clave de 1024 bits o más antes que NTLM por varias razones:  
  
-   la disponibilidad de la autenticación mutua  
  
-   el uso de algoritmos criptográficos más seguros y  
  
-   la mayor dificultad de usar credenciales X509 reenviadas.  
  
 Para obtener información general de NTLM ataques de reenvío, vaya a [http://msdn.microsoft.com/msdnmag/issues/06/09/SecureByDesign/default.aspx](http://go.microsoft.com/fwlink/?LinkId=109571).  
  
## <a name="always-revert-after-impersonation"></a>Siempre revierta tras la suplantación  
 Al utilizar API que permiten la suplantación de un cliente, asegúrese de revertir a la identidad original. Por ejemplo, al utilizar el <xref:System.Security.Principal.WindowsIdentity> y <xref:System.Security.Principal.WindowsImpersonationContext>, usar C# `using` instrucción o [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] `Using` instrucción, como se muestra en el código siguiente. La clase <xref:System.Security.Principal.WindowsImpersonationContext> implementa la interfaz <xref:System.IDisposable> y, por consiguiente, Common Language Runtime (CLR) revierte automáticamente a la identidad original una vez que el código deja el bloque `using`.  
  
 [!code-csharp[c_SecurityBestPractices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securitybestpractices/cs/source.cs#1)]
 [!code-vb[c_SecurityBestPractices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securitybestpractices/vb/source.vb#1)]  
  
## <a name="impersonate-only-as-needed"></a>Suplante solo cuando sea necesario  
 Con el método <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> de la clase <xref:System.Security.Principal.WindowsIdentity>, es posible utilizar la suplantación en un ámbito muy controlado. Esto se opone al uso de la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> del <xref:System.ServiceModel.OperationBehaviorAttribute>, que permite la suplantación en toda la operación. Siempre que sea posible, controle el ámbito de suplantación utilizando el método <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> más preciso.  
  
## <a name="obtain-metadata-from-trusted-sources"></a>Obtención de los metadatos desde fuentes de confianza  
 Asegúrese de que confía en el origen de sus metadatos y de que nadie ha manipulado los metadatos. Los metadatos recuperados utilizando el protocolo HTTP se envían en texto no cifrado y se pueden manipular. Si el servicio utiliza la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> y <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>, utilice la URL proporcionada por el creador del servicio para descargar los datos mediante el protocolo HTTPS.  
  
## <a name="publish-metadata-using-security"></a>Publicación de metadatos utilizando la seguridad  
 Para evitar la modificación de los metadatos publicados de un servicio, proteja el punto de conexión de intercambio de metadatos mediante seguridad de mensajes o de transporte. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Extremos de metadatos de publicación](../../../../docs/framework/wcf/publishing-metadata-endpoints.md) y [Cómo: publicar los metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="ensure-use-of-local-issuer"></a>Asegure el uso de un emisor local  
 Si se especifica una dirección y un enlace del emisor para un enlace determinado, el emisor local no se utiliza para los puntos de conexión que utilizan ese enlace. Los clientes que esperan utilizar siempre el emisor local deberían asegurarse de que no utilizan dicho enlace o de que modifican el enlace de manera que la dirección del emisor sea null.  
  
## <a name="saml-token-size-quotas"></a>Cuotas de tamaño de tokens de SAML  
 Cuando los tokens de Security Assertions Markup Language (SAML) se serializan en mensajes, cuando los emite un servicio de tokens de seguridad (STS) o cuando son presentados por clientes a servicios como parte de la autenticación, la cuota de tamaño máximo del mensaje debe ser suficientemente grande para alojar el token SAML y las otras partes del mensaje. En casos normales, las cuotas de tamaño del mensaje predeterminadas son suficientes. Sin embargo, en los casos en los que un token de SAML sea grande porque contiene cientos de notificaciones, se deberían incrementar las cuotas para alojar al token serializado. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]las cuotas, consulte [consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).  
  
## <a name="set-securitybindingelementincludetimestamp-to-true-on-custom-bindings"></a>Establecer SecurityBindingElement.IncludeTimestamp en True en enlaces personalizados  
 Al crear un enlace personalizado, debe establecer <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> en `true`. De lo contrario, si <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> se establece en `false` y el cliente usa un token basado en clave asimétrica, como un certificado X509, el mensaje no se firmará.  
  
## <a name="see-also"></a>Vea también  
 [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md)  
 [Consideraciones de seguridad con metadatos](../../../../docs/framework/wcf/feature-details/security-considerations-with-metadata.md)
