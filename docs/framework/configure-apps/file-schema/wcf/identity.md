---
title: '&lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fa6bfdf72bd292599867bf7a9571ecd6b408a2c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltidentitygt"></a><span data-ttu-id="bd7de-102">&lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="bd7de-102">&lt;identity&gt;</span></span>
<span data-ttu-id="bd7de-103">El elemento de identidad permite a un programador del cliente especificar en tiempo de diseño la identidad esperada del servicio.</span><span class="sxs-lookup"><span data-stu-id="bd7de-103">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="bd7de-104">En el proceso de protocolo de enlace entre el cliente y el servicio, la infraestructura de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] se asegurará de que la identidad del servicio esperado coincida con los valores de este elemento y, por tanto, pueda autenticarse.</span><span class="sxs-lookup"><span data-stu-id="bd7de-104">In the handshake process between the client and service, the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="bd7de-105">Para obtener más información, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="bd7de-105">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="bd7de-106">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bd7de-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="bd7de-107">\<cliente ></span><span class="sxs-lookup"><span data-stu-id="bd7de-107">\<client></span></span>  
<span data-ttu-id="bd7de-108">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="bd7de-108">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd7de-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd7de-109">Syntax</span></span>  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd7de-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bd7de-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bd7de-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bd7de-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd7de-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="bd7de-112">Attributes</span></span>  
 <span data-ttu-id="bd7de-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bd7de-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd7de-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bd7de-114">Child Elements</span></span>  
  
|<span data-ttu-id="bd7de-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd7de-115">Element</span></span>|<span data-ttu-id="bd7de-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd7de-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd7de-117">certificate</span><span class="sxs-lookup"><span data-stu-id="bd7de-117">certificate</span></span>|<span data-ttu-id="bd7de-118">Especifica los valores de un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="bd7de-118">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="bd7de-119">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="bd7de-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="bd7de-120">Contiene un atributo `encodedValue` que es una cadena, que especifica el valor codificado por este certificado.</span><span class="sxs-lookup"><span data-stu-id="bd7de-120">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="bd7de-121">certificateReference</span><span class="sxs-lookup"><span data-stu-id="bd7de-121">certificateReference</span></span>|<span data-ttu-id="bd7de-122">Especifica los valores para la validación del certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="bd7de-122">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="bd7de-123">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="bd7de-123">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="bd7de-124">dns</span><span class="sxs-lookup"><span data-stu-id="bd7de-124">dns</span></span>|<span data-ttu-id="bd7de-125">Especifica el DNS de un certificado X.509 usado para autenticar un servicio.</span><span class="sxs-lookup"><span data-stu-id="bd7de-125">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="bd7de-126">Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.</span><span class="sxs-lookup"><span data-stu-id="bd7de-126">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="bd7de-127">rsa</span><span class="sxs-lookup"><span data-stu-id="bd7de-127">rsa</span></span>|<span data-ttu-id="bd7de-128">Especifica el valor del campo RSA de un certificado X.509 usado para autenticar un servicio a un cliente.</span><span class="sxs-lookup"><span data-stu-id="bd7de-128">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="bd7de-129">Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.</span><span class="sxs-lookup"><span data-stu-id="bd7de-129">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="bd7de-130">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="bd7de-130">servicePrincipalName</span></span>|<span data-ttu-id="bd7de-131">Especifica una identidad del nombre de entidad de seguridad de servidor (SPN) que es el nombre de entidad de seguridad usado por un cliente para identificar de manera unívoca una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="bd7de-131">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="bd7de-132">Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real.</span><span class="sxs-lookup"><span data-stu-id="bd7de-132">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="bd7de-133">Este elemento es del tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="bd7de-133">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="bd7de-134">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="bd7de-134">userPrincipalName</span></span>|<span data-ttu-id="bd7de-135">Especifica una identidad del nombre principal del usuario (UPN), que es el tipo de nombre de inicio de sesión de un usuario en una red.</span><span class="sxs-lookup"><span data-stu-id="bd7de-135">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="bd7de-136">El nombre principal del usuario se compone del nombre de objeto del usuario usado en Active Directory, seguido por el símbolo (@) y a continuación, normalmente, el dominio primario del Sistema de nombres de dominio (DNS).</span><span class="sxs-lookup"><span data-stu-id="bd7de-136">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="bd7de-137">Por ejemplo, Jeff en el árbol de dominios de Fabrikam.com podría tener el nombre principal de usuario [ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com).  Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real.</span><span class="sxs-lookup"><span data-stu-id="bd7de-137">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).  This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="bd7de-138">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="bd7de-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd7de-139">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd7de-139">Parent Elements</span></span>  
  
|<span data-ttu-id="bd7de-140">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd7de-140">Element</span></span>|<span data-ttu-id="bd7de-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd7de-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd7de-142">\<personalizado ></span><span class="sxs-lookup"><span data-stu-id="bd7de-142">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="bd7de-143">Especifica la resolución del mismo nivel personalizado de un netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="bd7de-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="bd7de-144">\<punto de conexión ></span><span class="sxs-lookup"><span data-stu-id="bd7de-144">\<endpoint></span></span>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)|<span data-ttu-id="bd7de-145">Configura tipos diferentes de puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="bd7de-145">Configures different types of endpoints.</span></span>|  
|[<span data-ttu-id="bd7de-146">\<emisor ></span><span class="sxs-lookup"><span data-stu-id="bd7de-146">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="bd7de-147">Especifica el servicio de token de seguridad (STS) para el servicio aliado.</span><span class="sxs-lookup"><span data-stu-id="bd7de-147">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="bd7de-148">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="bd7de-148">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="bd7de-149">Especifica el punto de conexión de metadatos para el servicio de token de seguridad (STS) de un servicio aliado.</span><span class="sxs-lookup"><span data-stu-id="bd7de-149">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="bd7de-150">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="bd7de-150">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="bd7de-151">Define los parámetros para un token emitido en un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="bd7de-151">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="bd7de-152">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="bd7de-152">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="bd7de-153">Especifica un servicio de token de seguridad (STS) local.</span><span class="sxs-lookup"><span data-stu-id="bd7de-153">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd7de-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd7de-154">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [<span data-ttu-id="bd7de-155">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="bd7de-155">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="bd7de-156">Los puntos de conexión: Direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="bd7de-156">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
