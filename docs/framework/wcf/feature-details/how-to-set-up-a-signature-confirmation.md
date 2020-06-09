---
title: Procedimiento para establecer una confirmación de firma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: 9423922753efee7aac32e430f97307c715e43464
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586928"
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="35fd2-102">Procedimiento para establecer una confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="35fd2-102">How to: Set Up a Signature Confirmation</span></span>

<span data-ttu-id="35fd2-103">La confirmación de la *firma* es un mecanismo para que un iniciador del mensaje garantice que se generó una respuesta recibida como respuesta al mensaje original del remitente.</span><span class="sxs-lookup"><span data-stu-id="35fd2-103">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="35fd2-104">La confirmación de la firma se define en la especificación WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="35fd2-104">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="35fd2-105">Si un extremo admite WS-Security 1.0, no puede utilizar la confirmación de firma.</span><span class="sxs-lookup"><span data-stu-id="35fd2-105">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>

<span data-ttu-id="35fd2-106">Los procedimientos siguientes especifican cómo habilitar la confirmación de firma mediante un <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="35fd2-106">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="35fd2-107">Puede utilizar el mismo procedimiento con <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="35fd2-107">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="35fd2-108">El procedimiento se basa en los pasos básicos que se encuentran en [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="35fd2-108">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="35fd2-109">Para habilitar la confirmación de firma en código</span><span class="sxs-lookup"><span data-stu-id="35fd2-109">To enable signature confirmation in code</span></span>

1. <span data-ttu-id="35fd2-110">Cree una instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection>.</span><span class="sxs-lookup"><span data-stu-id="35fd2-110">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>

2. <span data-ttu-id="35fd2-111">Cree una instancia de la <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> clase.</span><span class="sxs-lookup"><span data-stu-id="35fd2-111">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>

3. <span data-ttu-id="35fd2-112">Establecer <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="35fd2-112">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>

4. <span data-ttu-id="35fd2-113">Agregue el elemento de seguridad a la colección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="35fd2-113">Add the security element to the binding collection.</span></span>

5. <span data-ttu-id="35fd2-114">Cree un enlace personalizado, como se especifica en [Cómo: crear un enlace personalizado mediante SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="35fd2-114">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>

### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="35fd2-115">Para habilitar la confirmación de firma en configuración</span><span class="sxs-lookup"><span data-stu-id="35fd2-115">To enable signature confirmation in configuration</span></span>

1. <span data-ttu-id="35fd2-116">Agregue un elemento `<customBinding>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="35fd2-116">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>

2. <span data-ttu-id="35fd2-117">Agregue un elemento `<binding>` y establezca el atributo de nombre en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="35fd2-117">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>

3. <span data-ttu-id="35fd2-118">Agregue un elemento de codificación adecuado.</span><span class="sxs-lookup"><span data-stu-id="35fd2-118">Add an appropriate encoding element.</span></span> <span data-ttu-id="35fd2-119">El siguiente ejemplo agrega un elemento `<TextMessageEncoding>`.</span><span class="sxs-lookup"><span data-stu-id="35fd2-119">The following example adds a `<TextMessageEncoding>` element.</span></span>

4. <span data-ttu-id="35fd2-120">Agregue un elemento secundario `<security>``requireSignatureConfirmation`.</span><span class="sxs-lookup"><span data-stu-id="35fd2-120">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

5. <span data-ttu-id="35fd2-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="35fd2-121">Optional.</span></span> <span data-ttu-id="35fd2-122">Para habilitar la confirmación de la firma durante el arranque, agregue un [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento secundario y establezca el `requireSignatureConfirmation` atributo en `true` .</span><span class="sxs-lookup"><span data-stu-id="35fd2-122">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>

6. <span data-ttu-id="35fd2-123">Agregue un elemento de transporte adecuado.</span><span class="sxs-lookup"><span data-stu-id="35fd2-123">Add an appropriate transport element.</span></span> <span data-ttu-id="35fd2-124">En el siguiente ejemplo se agrega un [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) :</span><span class="sxs-lookup"><span data-stu-id="35fd2-124">The following example adds an [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md):</span></span>

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

## <a name="example"></a><span data-ttu-id="35fd2-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35fd2-125">Example</span></span>

<span data-ttu-id="35fd2-126">El siguiente código crea una instancia del <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y establece la propiedad <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="35fd2-126">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="35fd2-127">Observe que este ejemplo no utiliza el elemento `<secureConversationBootstrap>` mostrado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="35fd2-127">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="35fd2-128">Este ejemplo muestra la confirmación de firma al utilizar un token de Windows (protocolo Kerberos).</span><span class="sxs-lookup"><span data-stu-id="35fd2-128">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="35fd2-129">En este caso, la firma del cliente se devuelve en todas las respuestas del servicio y es confirmada por el cliente.</span><span class="sxs-lookup"><span data-stu-id="35fd2-129">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>

[!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
[!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="35fd2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="35fd2-130">See also</span></span>

- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>
- [<span data-ttu-id="35fd2-131">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="35fd2-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="35fd2-132">Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="35fd2-132">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
