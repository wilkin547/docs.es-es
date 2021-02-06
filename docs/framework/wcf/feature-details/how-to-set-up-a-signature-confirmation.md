---
description: 'Más información acerca de cómo: configurar una confirmación de firma'
title: Procedimiento para establecer una confirmación de firma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 158ec2a5f74038f5c1ca1af847f57457a8881974
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643194"
---
# <a name="how-to-set-up-a-signature-confirmation"></a>Procedimiento para establecer una confirmación de firma

La confirmación de la *firma* es un mecanismo para que un iniciador del mensaje garantice que se generó una respuesta recibida como respuesta al mensaje original del remitente. La confirmación de la firma se define en la especificación WS-Security 1.1. Si un extremo admite WS-Security 1.0, no puede utilizar la confirmación de firma.

Los procedimientos siguientes especifican cómo habilitar la confirmación de firma mediante un <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Puede utilizar el mismo procedimiento con <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>. El procedimiento se basa en los pasos básicos que se encuentran en [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).

### <a name="to-enable-signature-confirmation-in-code"></a>Para habilitar la confirmación de firma en código

1. Cree una instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection>.

2. Cree una instancia de la  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> clase.

3. Establecer <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> en `true`.

4. Agregue el elemento de seguridad a la colección de enlaces.

5. Cree un enlace personalizado, como se especifica en [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).

### <a name="to-enable-signature-confirmation-in-configuration"></a>Para habilitar la confirmación de firma en configuración

1. Agregue un elemento `<customBinding>` del archivo de configuración.

2. Agregue un elemento `<binding>` y establezca el atributo de nombre en un valor adecuado.

3. Agregue un elemento de codificación adecuado. El siguiente ejemplo agrega un elemento `<TextMessageEncoding>`.

4. Agregue un elemento secundario `<security>``requireSignatureConfirmation`.

5. Opcional. Para habilitar la confirmación de la firma durante el arranque, agregue un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento secundario y establezca el `requireSignatureConfirmation` atributo en `true` .

6. Agregue un elemento de transporte adecuado. En el siguiente ejemplo se agrega un [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) :

    ```xml
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

## <a name="example"></a>Ejemplo

El siguiente código crea una instancia del <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y establece la propiedad <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> en `true`. Observe que este ejemplo no utiliza el elemento `<secureConversationBootstrap>` mostrado en el ejemplo anterior. Este ejemplo muestra la confirmación de firma al utilizar un token de Windows (protocolo Kerberos). En este caso, la firma del cliente se devuelve en todas las respuestas del servicio y es confirmada por el cliente.

[!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
[!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [Procedimiento para crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
