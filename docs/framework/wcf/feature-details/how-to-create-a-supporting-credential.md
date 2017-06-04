---
title: "C&#243;mo: Crear una credencial de apoyo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0952919-8bb4-4978-926c-9cc108f89806
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# C&#243;mo: Crear una credencial de apoyo
Es posible tener un esquema de seguridad personalizado que requiera más de una credencial.  Por ejemplo, un servicio puede solicitar del cliente un nombre de usuario y contraseña, pero también una credencial que demuestre que el cliente tiene más de 18 años.  La segunda credencial es una *credencial de apoyo*.  En este tema, se explica cómo implementar dichos credenciales en un cliente [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
> [!NOTE]
>  La especificación para admitir las credenciales forma parte de la especificación WS\-SecurityPolicy.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Especificaciones de Seguridad de Servicios web](http://go.microsoft.com/fwlink/?LinkId=88537).  
  
## Tokens auxiliares  
 En resumen, al usar el modo de seguridad, una *credencial primaria* siempre se usa para proteger el mensaje \(por ejemplo, un certificado X.509 o un vale Kerberos\).  
  
 Como ha definido la especificación, un enlace de seguridad utiliza *tokens* para proteger el intercambio de mensajes.  Un *token* es una representación de una credencial de seguridad.  
  
 El enlace de seguridad utiliza un token primario identificado en la directiva de enlace de seguridad para crear una firma.  Esta firma se conoce como la *firma del mensaje*.  
  
 Los tokens adicionales se pueden especificar para aumentar las notificaciones proporcionadas por el token asociado a la firma del mensaje.  
  
## Endosar, firmar y cifrar  
 Una credencial de aprobación produce como resultado un *token de aprobación* transmitido dentro del mensaje.  La especificación de WS\-SecurityPolicy define cuatro maneras de adjuntar un token de aprobación al mensaje, tal y como se describe en la tabla siguiente.  
  
|Finalidad|Descripción|  
|---------------|-----------------|  
|Firmado|El token de aprobación está incluido en el encabezado de seguridad y es firmado por la firma del mensaje.|  
|Endosar|Un *token endosado* firma la firma del mensaje.|  
|Firmar y endosar|Los tokens firmados y endosados firman el elemento `ds:Signature` completo generado a partir de la firma del mensaje y están firmados por esa firma del mensaje; es decir, ambos tokens \(el token utilizado para la firma del mensaje y el token endosado y firmado\) se firman entre sí.|  
|Firmar y cifrar|Los tokens de aprobación firmados y cifrados son tokens de aprobación firmados que también se cifran cuando aparecen en `wsse:SecurityHeader`.|  
  
## Programar credenciales de aprobación  
 Para crear un servicio que utiliza los tokens de aprobación, usted debe crear [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  \([!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).\)  
  
 El primer paso cuando se crea un enlace personalizado es crear un elemento de enlace de seguridad, que puede ser uno de tres tipos:  
  
-   <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 Todas las clases heredan del <xref:System.ServiceModel.Channels.SecurityBindingElement>, que incluye cuatro propiedades pertinentes:  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.EndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OperationSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalEndpointSupportingTokenParameters%2A>  
  
-   <xref:System.ServiceModel.Channels.SecurityBindingElement.OptionalOperationSupportingTokenParameters%2A>  
  
#### Ámbitos  
 Existen dos ámbitos para admitir las credenciales:  
  
-   *Los tokens de aprobación de extremo* admiten todas las operaciones de un extremo.  Es decir, se puede utilizar la credencial que el token de aprobación representa siempre que se invoca una operación de extremo.  
  
-   *Los tokens de aprobación de la operación* admiten solo una operación de extremo concreta.  
  
 Tal y como han indicado los nombres de la propiedad, se puede requerir las credenciales de aprobación o estas pueden ser opcionales.  Es decir, si la credencial de aprobación se utiliza si está presente, aunque no es necesario, pero no se producirá un error en la autenticación si no está presente.  
  
## Procedimientos  
  
#### Para crear un enlace personalizado que incluye credenciales de aprobación  
  
1.  Crear un elemento de enlace de seguridad.  El ejemplo siguiente crea <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> con el modo de autenticación `UserNameForCertificate`.  Utilice el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>.  
  
2.  Agregue el parámetro de aprobación a la colección de tipos devuelta por la propiedad adecuada \(`Endorsing`, `Signed`, `SignedEncrypted`o `SignedEndorsed`\).  Los tipos en el espacio de nombres <xref:System.ServiceModel.Security.Tokens> incluyen tipos utilizados normalmente, como <xref:System.ServiceModel.Security.Tokens.X509SecurityTokenParameters>.  
  
## Ejemplo  
  
### Descripción  
 En el ejemplo siguiente se crea una instancia de<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y agrega una instancia de la clase <xref:System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters> a la colección que ha devuelto la propiedad endosada.  
  
### Código  
 [!code-csharp[c_SupportingCredential#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_supportingcredential/cs/source.cs#1)]  
  
## Vea también  
 [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)