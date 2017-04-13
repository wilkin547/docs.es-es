---
title: "C&#243;mo: Establecer una confirmaci&#243;n de firma | Microsoft Docs"
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
  - "confirmación de firma"
  - "WCF, seguridad"
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# C&#243;mo: Establecer una confirmaci&#243;n de firma
La *confirmación de firma* es un mecanismo para que un iniciador de mensaje asegure que una respuesta recibida se generó en respuesta al mensaje original del remitente.La confirmación de la firma se define en la especificación WS\-Security 1.1.Si un extremo admite WS\-Security 1.0, no puede utilizar la confirmación de firma.  
  
 Los procedimientos siguientes especifican cómo habilitar la confirmación de firma mediante un <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.Puede utilizar el mismo procedimiento con <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.El procedimiento se basa en los pasos básicos de [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### Para habilitar la confirmación de firma en código  
  
1.  Cree una instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection>.  
  
2.  Cree una instancia de la clase <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3.  Establezca <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> en `true`.  
  
4.  Agregue el elemento de seguridad a la colección de enlaces.  
  
5.  Cree un enlace personalizado, como se especifica en [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### Para habilitar la confirmación de firma en configuración  
  
1.  Agregue un elemento `<customBinding>``<bindings> a la sección`  del archivo de configuración.  
  
2.  Agregue un elemento `<binding>` y establezca el atributo de nombre en un valor adecuado.  
  
3.  Agregue un elemento de codificación adecuado.El siguiente ejemplo agrega un elemento `<TextMessageEncoding>`.  
  
4.  Agregue un elemento secundario `<security>``requireSignatureConfirmation y establezca el atributo` `true en` .  
  
5.  Opcional.Para habilitar la confirmación de firma durante el arranque, agregue un elemento secundario [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) y establezca el atributo `equireSignatureConfirmation` en `true`.  
  
6.  Agregue un elemento de transporte adecuado.El siguiente ejemplo agrega un [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
    ```  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## Ejemplo  
 El siguiente código crea una instancia del <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y establece la propiedad <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> en `true`.Observe que este ejemplo no utiliza el elemento `<secureConversationBootstrap>` mostrado en el ejemplo anterior.Este ejemplo muestra la confirmación de firma al utilizar un token de Windows \(protocolo Kerberos\).En este caso, la firma del cliente se devuelve en todas las respuestas del servicio y es confirmada por el cliente.  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## Vea también  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>   
 [Cómo: Crear un enlace personalizado mediante SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)