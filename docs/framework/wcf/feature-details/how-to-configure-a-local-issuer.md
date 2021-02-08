---
description: Más información acerca de cómo configurar un emisor local
title: Procedimiento para configurar un emisor local
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
ms.openlocfilehash: 1c950c2bbbb55954fc65e35632523ea14ee3ac00
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780172"
---
# <a name="how-to-configure-a-local-issuer"></a><span data-ttu-id="65ad0-103">Procedimiento para configurar un emisor local</span><span class="sxs-lookup"><span data-stu-id="65ad0-103">How to: Configure a Local Issuer</span></span>

<span data-ttu-id="65ad0-104">En este tema se describe cómo configurar un cliente para utilizar un emisor local para los tokens emitidos.</span><span class="sxs-lookup"><span data-stu-id="65ad0-104">This topic describes how to configure a client to use a local issuer for issued tokens.</span></span>

<span data-ttu-id="65ad0-105">A menudo, cuando un cliente se comunica con un servicio federado, el servicio especifica la dirección del servicio de token de seguridad que se espera que emita el token y que el cliente utilizará para autenticarse con el servicio federado.</span><span class="sxs-lookup"><span data-stu-id="65ad0-105">Often, when a client communicates with a federated service, the service specifies the address of the security token service that is expected to issue the token the client will use to authenticate itself to the federated service.</span></span> <span data-ttu-id="65ad0-106">En determinadas situaciones, el cliente se puede configurar para utilizar un *emisor local*.</span><span class="sxs-lookup"><span data-stu-id="65ad0-106">In certain situations, the client may be configured to use a *local issuer*.</span></span>

<span data-ttu-id="65ad0-107">Windows Communication Foundation (WCF) usa un emisor local en los casos en los que la dirección del emisor de un enlace federado es `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o `null` .</span><span class="sxs-lookup"><span data-stu-id="65ad0-107">Windows Communication Foundation (WCF) uses a local issuer in cases where the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`.</span></span> <span data-ttu-id="65ad0-108">En casos como éste, debe configurar <xref:System.ServiceModel.Description.ClientCredentials> con la dirección del emisor local y el enlace que se va a utilizar para comunicarse con ese emisor.</span><span class="sxs-lookup"><span data-stu-id="65ad0-108">In such cases, you must configure the <xref:System.ServiceModel.Description.ClientCredentials> with the address of the local issuer and the binding to use to communicate with that issuer.</span></span>

> [!NOTE]
> <span data-ttu-id="65ad0-109">Si la <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> propiedad de la `ClientCredentials` clase se establece en `true` , no se especifica una dirección del emisor local y la dirección del emisor especificada por [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) u otro enlace federado es `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self` , `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` o es `null` , se utiliza el emisor de Windows CardSpace.</span><span class="sxs-lookup"><span data-stu-id="65ad0-109">If the <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> property of the `ClientCredentials` class is set to `true`, a local issuer address is not specified, and the issuer address specified by the [\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md) or other federated binding is `http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self`, `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous`, or is `null`, then the Windows CardSpace issuer is used.</span></span>

## <a name="to-configure-the-local-issuer-in-code"></a><span data-ttu-id="65ad0-110">Para configurar el emisor local en código</span><span class="sxs-lookup"><span data-stu-id="65ad0-110">To configure the local issuer in code</span></span>

1. <span data-ttu-id="65ad0-111">Cree una variable de tipo <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span><span class="sxs-lookup"><span data-stu-id="65ad0-111">Create a variable of type <xref:System.ServiceModel.Security.IssuedTokenClientCredential></span></span>

2. <span data-ttu-id="65ad0-112">Establezca la variable en la instancia devuelta de la propiedad <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> de la clase `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="65ad0-112">Set the variable to the instance returned from the <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> property of the `ClientCredentials` class.</span></span> <span data-ttu-id="65ad0-113">Esa instancia es devuelta por la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> del cliente (heredada de <xref:System.ServiceModel.ClientBase%601>) o la propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A> de <xref:System.ServiceModel.ChannelFactory>:</span><span class="sxs-lookup"><span data-stu-id="65ad0-113">That instance is returned by the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the client (inherited from <xref:System.ServiceModel.ClientBase%601>) or the <xref:System.ServiceModel.ChannelFactory.Credentials%2A> property of the <xref:System.ServiceModel.ChannelFactory>:</span></span>

     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]

3. <span data-ttu-id="65ad0-114">Establezca la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> en una nueva instancia de <xref:System.ServiceModel.EndpointAddress>, con la dirección del emisor local como un argumento para el constructor.</span><span class="sxs-lookup"><span data-stu-id="65ad0-114">Set the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> property to a new instance of the <xref:System.ServiceModel.EndpointAddress>, with the address of the local issuer as an argument to the constructor.</span></span>

     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]

     <span data-ttu-id="65ad0-115">De manera alternativa, cree una nueva instancia <xref:System.Uri> como un argumento para el constructor.</span><span class="sxs-lookup"><span data-stu-id="65ad0-115">Alternatively, create a new <xref:System.Uri> instance as an argument to the constructor.</span></span>

     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]

     <span data-ttu-id="65ad0-116">El `addressHeaders` parámetro es una matriz de <xref:System.ServiceModel.Channels.AddressHeader> instancias, como se muestra.</span><span class="sxs-lookup"><span data-stu-id="65ad0-116">The `addressHeaders` parameter is an array of <xref:System.ServiceModel.Channels.AddressHeader> instances, as shown.</span></span>

     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]

4. <span data-ttu-id="65ad0-117">Establezca el enlace del emisor local mediante la <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="65ad0-117">Set the binding for the local issuer using the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> property.</span></span>

     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]

5. <span data-ttu-id="65ad0-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="65ad0-118">Optional.</span></span> <span data-ttu-id="65ad0-119">Agregue los comportamientos del punto de conexión configurados para el emisor local agregando tales comportamientos a la colección devuelta por la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.</span><span class="sxs-lookup"><span data-stu-id="65ad0-119">Add configured endpoint behaviors for the local issuer by adding such behaviors to the collection returned by the <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A> property.</span></span>

     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]

## <a name="to-configure-the-local-issuer-in-configuration"></a><span data-ttu-id="65ad0-120">Para configurar el emisor local en la configuración</span><span class="sxs-lookup"><span data-stu-id="65ad0-120">To configure the local issuer in configuration</span></span>

1. <span data-ttu-id="65ad0-121">Cree un [\<localIssuer>](../../configure-apps/file-schema/wcf/localissuer.md) elemento como elemento secundario del [\<issuedToken>](../../configure-apps/file-schema/wcf/issuedtoken.md) elemento que es en sí mismo un elemento secundario del [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) elemento en un comportamiento del extremo.</span><span class="sxs-lookup"><span data-stu-id="65ad0-121">Create a [\<localIssuer>](../../configure-apps/file-schema/wcf/localissuer.md) element as a child of the [\<issuedToken>](../../configure-apps/file-schema/wcf/issuedtoken.md) element that is itself a child of the [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element in an endpoint behavior.</span></span>

2. <span data-ttu-id="65ad0-122">Establezca el atributo `address` en la dirección del emisor local que aceptará las solicitudes del token.</span><span class="sxs-lookup"><span data-stu-id="65ad0-122">Set the `address` attribute to the address of the local issuer that will accept token requests.</span></span>

3. <span data-ttu-id="65ad0-123">Establezca los atributos `binding` y `bindingConfiguration` en valores que hacen referencia al enlace adecuado que se debe usar cuando se comunica con el extremo del emisor local.</span><span class="sxs-lookup"><span data-stu-id="65ad0-123">Set the `binding` and `bindingConfiguration` attributes to values that reference the appropriate binding to use when communicating with the local issuer endpoint.</span></span>

4. <span data-ttu-id="65ad0-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="65ad0-124">Optional.</span></span> <span data-ttu-id="65ad0-125">Establezca el [\<identity>](../../configure-apps/file-schema/wcf/identity.md) elemento como un elemento secundario del `localIssuer` elemento <> y especifique la información de identidad del emisor local.</span><span class="sxs-lookup"><span data-stu-id="65ad0-125">Set the [\<identity>](../../configure-apps/file-schema/wcf/identity.md) element as a child of the <`localIssuer`> element and specify identity information for the local issuer.</span></span>

5. <span data-ttu-id="65ad0-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="65ad0-126">Optional.</span></span> <span data-ttu-id="65ad0-127">Establezca el [\<headers>](../../configure-apps/file-schema/wcf/headers.md) elemento como un elemento secundario del `localIssuer` elemento <> y especifique encabezados adicionales que sean necesarios para solucionar correctamente el emisor local.</span><span class="sxs-lookup"><span data-stu-id="65ad0-127">Set the [\<headers>](../../configure-apps/file-schema/wcf/headers.md) element as a child of the <`localIssuer`> element and specify additional headers that are required in order to correctly address the local issuer.</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="65ad0-128">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="65ad0-128">.NET Framework Security</span></span>

<span data-ttu-id="65ad0-129">Tenga en cuenta que si se especifica una dirección y un enlace del emisor para un enlace determinado, el emisor local no se utiliza para los puntos de conexión que utilizan ese enlace.</span><span class="sxs-lookup"><span data-stu-id="65ad0-129">Note that if an issuer address and binding are specified for a given binding, the local issuer is not used for endpoints that use that binding.</span></span> <span data-ttu-id="65ad0-130">Los clientes que siempre esperan utilizar el emisor local deberían asegurarse de que no utilizan este enlace o que modifican el enlace de manera que la dirección del emisor sea `null`.</span><span class="sxs-lookup"><span data-stu-id="65ad0-130">Clients who expect to always use the local issuer should ensure that they do not use such a binding or that they modify the binding so that the issuer address is `null`.</span></span>

## <a name="see-also"></a><span data-ttu-id="65ad0-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="65ad0-131">See also</span></span>

- [<span data-ttu-id="65ad0-132">Procedimiento para configurar las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="65ad0-132">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="65ad0-133">Procedimiento para crear un cliente federado</span><span class="sxs-lookup"><span data-stu-id="65ad0-133">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)
- [<span data-ttu-id="65ad0-134">Procedimiento para crear un WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="65ad0-134">How to: Create a WSFederationHttpBinding</span></span>](how-to-create-a-wsfederationhttpbinding.md)
