---
title: "Cómo: Configurar un emisor local"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c24b039709a013f210a42d67c744c03489e4cf73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-a-local-issuer"></a><span data-ttu-id="9e1d6-102">Cómo: Configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="9e1d6-102">How to: Configure a Local Issuer</span></span>
<span data-ttu-id="9e1d6-103">En este tema se describe cómo configurar un cliente para utilizar un emisor local para los tokens emitidos.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-103">This topic describes how to configure a client to use a local issuer for issued tokens.</span></span>  
  
 <span data-ttu-id="9e1d6-104">A menudo, cuando un cliente se comunica con un servicio federado, el servicio especifica la dirección del servicio de token de seguridad que se espera que emita el token y que el cliente utilizará para autenticarse con el servicio federado.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-104">Often, when a client communicates with a federated service, the service specifies the address of the security token service that is expected to issue the token the client will use to authenticate itself to the federated service.</span></span> <span data-ttu-id="9e1d6-105">En determinadas situaciones, el cliente puede configurarse para utilizar un *emisor local*.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-105">In certain situations, the client may be configured to use a *local issuer*.</span></span>  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="9e1d6-106"> utiliza un emisor local en casos donde la dirección del emisor de un enlace federado sea http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous o `null`.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-106"> uses a local issuer in cases where the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`.</span></span> <span data-ttu-id="9e1d6-107">En casos como éste, debe configurar <xref:System.ServiceModel.Description.ClientCredentials> con la dirección del emisor local y el enlace que se va a utilizar para comunicarse con ese emisor.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-107">In such cases, you must configure the <xref:System.ServiceModel.Description.ClientCredentials> with the address of the local issuer and the binding to use to communicate with that issuer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e1d6-108">Si el <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> propiedad de la `ClientCredentials` clase se establece en `true`, no se especifica una dirección de emisor local y la dirección del emisor especificado por el [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) u otros http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self, el enlace federado es http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous, o es `null`, a continuación, las ventanas [!INCLUDE[infocard](../../../../includes/infocard-md.md)] emisor se utiliza.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-108">If the <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> property of the `ClientCredentials` class is set to `true`, a local issuer address is not specified, and the issuer address specified by the [\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) or other federated binding is http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self, http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous, or is `null`, then the Windows [!INCLUDE[infocard](../../../../includes/infocard-md.md)] issuer is used.</span></span>  
  
### <a name="to-configure-the-local-issuer-in-code"></a><span data-ttu-id="9e1d6-109">Para configurar el emisor local en código</span><span class="sxs-lookup"><span data-stu-id="9e1d6-109">To configure the local issuer in code</span></span>  
  
1.  <span data-ttu-id="9e1d6-110">Cree una variable de tipo <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span><span class="sxs-lookup"><span data-stu-id="9e1d6-110">Create a variable of type <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>  
  
2.  <span data-ttu-id="9e1d6-111">Establezca la variable en la instancia devuelta de la propiedad <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> de la clase `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-111">Set the variable to the instance returned from the <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> property of the `ClientCredentials` class.</span></span> <span data-ttu-id="9e1d6-112">Esa instancia es devuelta por la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> del cliente (heredada de <xref:System.ServiceModel.ClientBase%601>) o la propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A> de <xref:System.ServiceModel.ChannelFactory>:</span><span class="sxs-lookup"><span data-stu-id="9e1d6-112">That instance is returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the client (inherited from <xref:System.ServiceModel.ClientBase%601>) or the <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property of the <xref:System.ServiceModel.ChannelFactory>:</span></span>  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
3.  <span data-ttu-id="9e1d6-113">Establezca la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> en una nueva instancia de <xref:System.ServiceModel.EndpointAddress>, con la dirección del emisor local como un argumento para el constructor.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-113">Set the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> property to a new instance of the <xref:System.ServiceModel.EndpointAddress>, with the address of the local issuer as an argument to the constructor.</span></span>  
  
     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]  
  
     <span data-ttu-id="9e1d6-114">De manera alternativa, cree una nueva instancia <xref:System.Uri> como un argumento para el constructor.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-114">Alternatively, create a new <xref:System.Uri> instance as an argument to the constructor.</span></span>  
  
     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]  
  
     <span data-ttu-id="9e1d6-115">El `addressHeaders` parámetro es una matriz de <xref:System.ServiceModel.Channels.AddressHeader> instancias, tal como se muestra.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-115">The `addressHeaders` parameter is an array of <xref:System.ServiceModel.Channels.AddressHeader> instances, as shown.</span></span>  
  
     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]  
  
4.  <span data-ttu-id="9e1d6-116">Establezca el enlace para el emisor local utilizando la <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-116">Set the binding for the local issuer using the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> property.</span></span>  
  
     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]  
  
5.  <span data-ttu-id="9e1d6-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-117">Optional.</span></span> <span data-ttu-id="9e1d6-118">Agregue los comportamientos del extremo configurados para el emisor local agregando tales comportamientos a la colección devuelta por la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-118">Add configured endpoint behaviors for the local issuer by adding such behaviors to the collection returned by the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> property.</span></span>  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-local-issuer-in-configuration"></a><span data-ttu-id="9e1d6-119">Para configurar el emisor local en la configuración</span><span class="sxs-lookup"><span data-stu-id="9e1d6-119">To configure the local issuer in configuration</span></span>  
  
1.  <span data-ttu-id="9e1d6-120">Crear un [ \<localIssuer >](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) elemento como elemento secundario de la [ \<issuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) elemento que es un elemento secundario de la [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento en un comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-120">Create a [\<localIssuer>](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) element as a child of the [\<issuedToken>](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) element that is itself a child of the [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element in an endpoint behavior.</span></span>  
  
2.  <span data-ttu-id="9e1d6-121">Establezca el atributo `address` en la dirección del emisor local que aceptará las solicitudes del token.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-121">Set the `address` attribute to the address of the local issuer that will accept token requests.</span></span>  
  
3.  <span data-ttu-id="9e1d6-122">Establezca los atributos `binding` y `bindingConfiguration` en valores que hacen referencia al enlace adecuado que se debe usar cuando se comunica con el extremo del emisor local.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-122">Set the `binding` and `bindingConfiguration` attributes to values that reference the appropriate binding to use when communicating with the local issuer endpoint.</span></span>  
  
4.  <span data-ttu-id="9e1d6-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-123">Optional.</span></span> <span data-ttu-id="9e1d6-124">Establecer el [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elemento como elemento secundario de la <`localIssuer`> elemento y especifique la información de identidad para el emisor local.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-124">Set the [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) element as a child of the <`localIssuer`> element and specify identity information for the local issuer.</span></span>  
  
5.  <span data-ttu-id="9e1d6-125">Opcional.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-125">Optional.</span></span> <span data-ttu-id="9e1d6-126">Establecer el [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) elemento como elemento secundario de la <`localIssuer`> elemento y especifique los encabezados adicionales que son necesarios para poder direccionar el emisor local correctamente.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-126">Set the [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) element as a child of the <`localIssuer`> element and specify additional headers that are required in order to correctly address the local issuer.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9e1d6-127">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9e1d6-127">.NET Framework Security</span></span>  
 <span data-ttu-id="9e1d6-128">Tenga en cuenta que si se especifica una dirección y un enlace del emisor para un enlace determinado, el emisor local no se utiliza para los puntos de conexión que utilizan ese enlace.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-128">Note that if an issuer address and binding are specified for a given binding, the local issuer is not used for endpoints that use that binding.</span></span> <span data-ttu-id="9e1d6-129">Los clientes que siempre esperan utilizar el emisor local deberían asegurarse de que no utilizan este enlace o que modifican el enlace de manera que la dirección del emisor sea `null`.</span><span class="sxs-lookup"><span data-stu-id="9e1d6-129">Clients who expect to always use the local issuer should ensure that they do not use such a binding or that they modify the binding so that the issuer address is `null`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e1d6-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e1d6-130">See Also</span></span>  
 [<span data-ttu-id="9e1d6-131">Configuración de las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="9e1d6-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="9e1d6-132">Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="9e1d6-132">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="9e1d6-133">Creación de un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="9e1d6-133">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
