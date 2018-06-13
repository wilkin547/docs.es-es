---
title: 'Cómo: Establecer una confirmación de firma'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
ms.openlocfilehash: d7076917e48124b2501826ecb0ac7599c663ba7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491994"
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="43304-102">Cómo: Establecer una confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="43304-102">How to: Set Up a Signature Confirmation</span></span>
<span data-ttu-id="43304-103">*Confirmación de firma* es un mecanismo para que un iniciador de mensaje para asegurarse de que se generó una respuesta recibida en respuesta al mensaje original del remitente.</span><span class="sxs-lookup"><span data-stu-id="43304-103">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="43304-104">La confirmación de la firma se define en la especificación WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="43304-104">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="43304-105">Si un punto de conexión admite WS-Security 1.0, no puede utilizar la confirmación de firma.</span><span class="sxs-lookup"><span data-stu-id="43304-105">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>  
  
 <span data-ttu-id="43304-106">Los procedimientos siguientes especifican cómo habilitar la confirmación de firma mediante un <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="43304-106">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="43304-107">Puede utilizar el mismo procedimiento con <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="43304-107">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="43304-108">El procedimiento se basa en los pasos básicos que se encuentra en [Cómo: crear un personalizado de enlace con SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="43304-108">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="43304-109">Para habilitar la confirmación de firma en código</span><span class="sxs-lookup"><span data-stu-id="43304-109">To enable signature confirmation in code</span></span>  
  
1.  <span data-ttu-id="43304-110">Cree una instancia de la clase <xref:System.ServiceModel.Channels.BindingElementCollection>.</span><span class="sxs-lookup"><span data-stu-id="43304-110">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>  
  
2.  <span data-ttu-id="43304-111">Cree una instancia de la <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> clase.</span><span class="sxs-lookup"><span data-stu-id="43304-111">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>  
  
3.  <span data-ttu-id="43304-112">Establezca <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="43304-112">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="43304-113">Agregue el elemento de seguridad a la colección de enlaces.</span><span class="sxs-lookup"><span data-stu-id="43304-113">Add the security element to the binding collection.</span></span>  
  
5.  <span data-ttu-id="43304-114">Crear un enlace personalizado, como se especifica en [Cómo: crear un enlace personalizado con SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="43304-114">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="43304-115">Para habilitar la confirmación de firma en configuración</span><span class="sxs-lookup"><span data-stu-id="43304-115">To enable signature confirmation in configuration</span></span>  
  
1.  <span data-ttu-id="43304-116">Agregue un elemento `<customBinding>` a la sección`<bindings>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="43304-116">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>  
  
2.  <span data-ttu-id="43304-117">Agregue un elemento `<binding>` y establezca el atributo de nombre en un valor adecuado.</span><span class="sxs-lookup"><span data-stu-id="43304-117">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="43304-118">Agregue un elemento de codificación adecuado.</span><span class="sxs-lookup"><span data-stu-id="43304-118">Add an appropriate encoding element.</span></span> <span data-ttu-id="43304-119">El siguiente ejemplo agrega un elemento `<TextMessageEncoding>`.</span><span class="sxs-lookup"><span data-stu-id="43304-119">The following example adds a `<TextMessageEncoding>` element.</span></span>  
  
4.  <span data-ttu-id="43304-120">Agregue un elemento secundario `<security>` y establezca el atributo`requireSignatureConfirmation` en`true`.</span><span class="sxs-lookup"><span data-stu-id="43304-120">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>  
  
5.  <span data-ttu-id="43304-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="43304-121">Optional.</span></span> <span data-ttu-id="43304-122">Para habilitar la confirmación de firma durante el arranque, agregar un [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento secundario y establezca la `equireSignatureConfirmation` atribuir a `true`.</span><span class="sxs-lookup"><span data-stu-id="43304-122">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `equireSignatureConfirmation` attribute to `true`.</span></span>  
  
6.  <span data-ttu-id="43304-123">Agregue un elemento de transporte adecuado.</span><span class="sxs-lookup"><span data-stu-id="43304-123">Add an appropriate transport element.</span></span> <span data-ttu-id="43304-124">En el ejemplo siguiente se agrega un [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):</span><span class="sxs-lookup"><span data-stu-id="43304-124">The following example adds an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="43304-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43304-125">Example</span></span>  
 <span data-ttu-id="43304-126">El siguiente código crea una instancia del <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> y establece la propiedad <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="43304-126">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="43304-127">Observe que este ejemplo no utiliza el elemento `<secureConversationBootstrap>` mostrado en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="43304-127">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="43304-128">Este ejemplo muestra la confirmación de firma al utilizar un token de Windows (protocolo Kerberos).</span><span class="sxs-lookup"><span data-stu-id="43304-128">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="43304-129">En este caso, la firma del cliente se devuelve en todas las respuestas del servicio y es confirmada por el cliente.</span><span class="sxs-lookup"><span data-stu-id="43304-129">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="43304-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="43304-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>  
 [<span data-ttu-id="43304-131">Creación de un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="43304-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="43304-132">Creación de un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="43304-132">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
