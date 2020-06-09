---
title: Procedimientos recomendados acerca de seguridad en WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- best practices [WCF], security
ms.assetid: 3639de41-1fa7-4875-a1d7-f393e4c8bd69
ms.openlocfilehash: c99ab5e1e72aefc688df1692091e60caf930d5e4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597623"
---
# <a name="best-practices-for-security-in-wcf"></a>Procedimientos recomendados acerca de seguridad en WCF
En las secciones siguientes se enumeran los procedimientos recomendados que tener en cuenta a la hora de crear aplicaciones seguras mediante Windows Communication Foundation (WCF). Para obtener más información sobre la seguridad, vea [Consideraciones de seguridad](security-considerations-in-wcf.md), [Consideraciones de seguridad para datos](security-considerations-for-data.md) y [Consideraciones de seguridad con metadatos](security-considerations-with-metadata.md).  
  
## <a name="identify-services-performing-windows-authentication-with-spns"></a>Identificación de los servicios que utilizan la autenticación de Windows con SPN  
 Los servicios se pueden identificar con nombres principales del usuario (UPN) o nombres de entidad de seguridad de servicio (SPN). Los servicios que se ejecutan con cuentas de equipo tales como servicio de red tienen una identidad de SPN que corresponde al equipo en que se ejecutan. Los servicios que se ejecutan con cuentas de usuario tienen una identidad de UPN que corresponde al usuario en nombre del que se ejecutan, aunque se puede usar la herramienta `setspn` para asignar un SPN a la cuenta de usuario. Configurar un servicio de modo que se pueda identificar a través del SPN y configurar los clientes que se conectan al servicio de manera que utilicen ese SPN puede dificultar ciertos ataques. Esta guía se aplica a los enlaces que utilizan la negociación Kerberos o SSPI.  Los clientes todavía deberían especificar el SPN si SSPI retrocede a NTLM.  
  
## <a name="verify-service-identities-in-wsdl"></a>Comprobación de las identidades de servicio en WSDL  
 WS-SecurityPolicy permite a los servicios publicar información sobre sus propias identidades en los metadatos. Cuando se recupera a través de `svcutil` u otros métodos como <xref:System.ServiceModel.Description.WsdlImporter>, esta información de identidad se convierte en las propiedades de identidad de las direcciones de punto de conexión del servicio WCF. Los clientes que no comprueban que estas identidades de servicio son correctas y válidas, omiten la autenticación del servicio. Un servicio malintencionado se puede aprovechar de estos clientes para ejecutar ataques de reenvío de credenciales y otros ataques de tipo "Man in the middle" cambiando la identidad alegada en su WSDL.  
  
## <a name="use-x509-certificates-instead-of-ntlm"></a>Uso de certificados X509 en lugar de NTLM  
 WCF proporciona dos mecanismos para la autenticación punto a punto: los certificados X509 (usados por el canal del mismo nivel) y la autenticación de Windows, donde la negociación SSPI disminuye de Kerberos a NTLM.  Se prefiere la autenticación basada en certificado con tamaños de clave de 1024 bits o más antes que NTLM por varias razones:  
  
- la disponibilidad de la autenticación mutua  
  
- el uso de algoritmos criptográficos más seguros y  
  
- la mayor dificultad de usar credenciales X509 reenviadas.  

## <a name="always-revert-after-impersonation"></a>Siempre revierta tras la suplantación  
 Al utilizar API que permiten la suplantación de un cliente, asegúrese de revertir a la identidad original. Por ejemplo, al usar <xref:System.Security.Principal.WindowsIdentity> y <xref:System.Security.Principal.WindowsImpersonationContext>, use la instrucción `using` de C# o la instrucción `Using` de Visual Basic, como se muestra en el código siguiente. La clase <xref:System.Security.Principal.WindowsImpersonationContext> implementa la interfaz <xref:System.IDisposable> y, por consiguiente, Common Language Runtime (CLR) revierte automáticamente a la identidad original una vez que el código deja el bloque `using`.  
  
 [!code-csharp[c_SecurityBestPractices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securitybestpractices/cs/source.cs#1)]
 [!code-vb[c_SecurityBestPractices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securitybestpractices/vb/source.vb#1)]  
  
## <a name="impersonate-only-as-needed"></a>Suplante solo cuando sea necesario  
 Con el método <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> de la clase <xref:System.Security.Principal.WindowsIdentity>, es posible utilizar la suplantación en un ámbito muy controlado. Esto se opone al uso de la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> del <xref:System.ServiceModel.OperationBehaviorAttribute>, que permite la suplantación en toda la operación. Siempre que sea posible, controle el ámbito de suplantación utilizando el método <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> más preciso.  
  
## <a name="obtain-metadata-from-trusted-sources"></a>Obtención de los metadatos desde fuentes de confianza  
 Asegúrese de que confía en el origen de sus metadatos y de que nadie ha manipulado los metadatos. Los metadatos recuperados utilizando el protocolo HTTP se envían en texto no cifrado y se pueden manipular. Si el servicio utiliza la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> y <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>, utilice la URL proporcionada por el creador del servicio para descargar los datos mediante el protocolo HTTPS.  
  
## <a name="publish-metadata-using-security"></a>Publicación de metadatos utilizando la seguridad  
 Para evitar la modificación de los metadatos publicados de un servicio, proteja el punto de conexión de intercambio de metadatos mediante seguridad de mensajes o de transporte. Para obtener más información, vea [Publicación de puntos de conexión de metadatos](../publishing-metadata-endpoints.md) y [Publicación de metadatos para un servicio mediante código](how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="ensure-use-of-local-issuer"></a>Asegure el uso de un emisor local  
 Si se especifica una dirección y un enlace del emisor para un enlace determinado, el emisor local no se utiliza para los extremos que utilizan ese enlace. Los clientes que esperan utilizar siempre el emisor local deberían asegurarse de que no utilizan dicho enlace o de que modifican el enlace de manera que la dirección del emisor sea null.  
  
## <a name="saml-token-size-quotas"></a>Cuotas de tamaño de tokens de SAML  
 Cuando los tokens de Security Assertions Markup Language (SAML) se serializan en mensajes, cuando los emite un servicio de tokens de seguridad (STS) o cuando son presentados por clientes a servicios como parte de la autenticación, la cuota de tamaño máximo del mensaje debe ser suficientemente grande para alojar el token SAML y las otras partes del mensaje. En casos normales, las cuotas de tamaño del mensaje predeterminadas son suficientes. Sin embargo, en los casos en los que un token de SAML sea grande porque contiene cientos de notificaciones, se deberían incrementar las cuotas para alojar al token serializado. Para obtener más información sobre las cuotas, vea [Consideraciones de seguridad para datos](security-considerations-for-data.md).  
  
## <a name="set-securitybindingelementincludetimestamp-to-true-on-custom-bindings"></a>Establecer SecurityBindingElement.IncludeTimestamp en True en enlaces personalizados  
 Al crear un enlace personalizado, debe establecer <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> en `true`. De lo contrario, si <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> se establece en `false` y el cliente usa un token basado en clave asimétrica, como un certificado X509, el mensaje no se firmará.  
  
## <a name="see-also"></a>Vea también

- [Consideraciones sobre la seguridad](security-considerations-in-wcf.md)
- [Consideraciones de seguridad para datos](security-considerations-for-data.md)
- [Consideraciones de seguridad con metadatos](security-considerations-with-metadata.md)
