---
description: 'Más información acerca de: <identity>'
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: ceb4dc0e7efa6cd01204253001432ed1ef2c048e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802260"
---
# \<identity>

<span data-ttu-id="fdf59-102">El elemento de identidad permite a un programador del cliente especificar en tiempo de diseño la identidad esperada del servicio.</span><span class="sxs-lookup"><span data-stu-id="fdf59-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="fdf59-103">En el proceso de protocolo de enlace entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento y, por tanto, se puede autenticar.</span><span class="sxs-lookup"><span data-stu-id="fdf59-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="fdf59-104">Para obtener más información, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="fdf59-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a><span data-ttu-id="fdf59-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdf59-105">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdf59-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fdf59-106">Attributes and Elements</span></span>  

 <span data-ttu-id="fdf59-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fdf59-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdf59-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="fdf59-108">Attributes</span></span>  

 <span data-ttu-id="fdf59-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fdf59-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fdf59-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fdf59-110">Child Elements</span></span>  
  
|<span data-ttu-id="fdf59-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdf59-111">Element</span></span>|<span data-ttu-id="fdf59-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdf59-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fdf59-113">certificado</span><span class="sxs-lookup"><span data-stu-id="fdf59-113">certificate</span></span>|<span data-ttu-id="fdf59-114">Especifica los valores de un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="fdf59-114">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="fdf59-115">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="fdf59-115">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="fdf59-116">Contiene un atributo `encodedValue` que es una cadena, que especifica el valor codificado por este certificado.</span><span class="sxs-lookup"><span data-stu-id="fdf59-116">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="fdf59-117">certificateReference</span><span class="sxs-lookup"><span data-stu-id="fdf59-117">certificateReference</span></span>|<span data-ttu-id="fdf59-118">Especifica los valores para la validación del certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="fdf59-118">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="fdf59-119">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="fdf59-119">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="fdf59-120">dns</span><span class="sxs-lookup"><span data-stu-id="fdf59-120">dns</span></span>|<span data-ttu-id="fdf59-121">Especifica el DNS de un certificado X.509 usado para autenticar un servicio.</span><span class="sxs-lookup"><span data-stu-id="fdf59-121">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="fdf59-122">Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.</span><span class="sxs-lookup"><span data-stu-id="fdf59-122">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="fdf59-123">rsa</span><span class="sxs-lookup"><span data-stu-id="fdf59-123">rsa</span></span>|<span data-ttu-id="fdf59-124">Especifica el valor del campo RSA de un certificado X.509 usado para autenticar un servicio a un cliente.</span><span class="sxs-lookup"><span data-stu-id="fdf59-124">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="fdf59-125">Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.</span><span class="sxs-lookup"><span data-stu-id="fdf59-125">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="fdf59-126">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="fdf59-126">servicePrincipalName</span></span>|<span data-ttu-id="fdf59-127">Especifica una identidad del nombre de entidad de seguridad de servidor (SPN) que es el nombre de entidad de seguridad usado por un cliente para identificar de manera unívoca una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="fdf59-127">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="fdf59-128">Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real.</span><span class="sxs-lookup"><span data-stu-id="fdf59-128">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="fdf59-129">Este elemento es del tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="fdf59-129">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="fdf59-130">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="fdf59-130">userPrincipalName</span></span>|<span data-ttu-id="fdf59-131">Especifica una identidad del nombre principal del usuario (UPN), que es el tipo de nombre de inicio de sesión de un usuario en una red.</span><span class="sxs-lookup"><span data-stu-id="fdf59-131">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="fdf59-132">El nombre principal de usuario se compone del nombre de objeto de usuario que se usa en Active Directory, seguido del símbolo de arroba ( \@ ) y, a continuación, normalmente, el dominio primario del sistema de nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="fdf59-132">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="fdf59-133">Por ejemplo, Jeff en el árbol de dominio de Fabrikam.com podría tener el nombre principal de usuario [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) .</span><span class="sxs-lookup"><span data-stu-id="fdf59-133">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="fdf59-134">Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real.</span><span class="sxs-lookup"><span data-stu-id="fdf59-134">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="fdf59-135">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="fdf59-135">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fdf59-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fdf59-136">Parent Elements</span></span>  
  
|<span data-ttu-id="fdf59-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="fdf59-137">Element</span></span>|<span data-ttu-id="fdf59-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdf59-138">Description</span></span>|  
|-------------|-----------------|  
|[\<custom>](custom.md)|<span data-ttu-id="fdf59-139">Especifica la resolución del mismo nivel personalizado de un netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="fdf59-139">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="fdf59-140">Configura puntos de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="fdf59-140">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="fdf59-141">\<endpoint> de \<client></span><span class="sxs-lookup"><span data-stu-id="fdf59-141">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="fdf59-142">Configura los extremos del canal.</span><span class="sxs-lookup"><span data-stu-id="fdf59-142">Configures channel endpoints.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="fdf59-143">Especifica el servicio de token de seguridad (STS) para el servicio aliado.</span><span class="sxs-lookup"><span data-stu-id="fdf59-143">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="fdf59-144">Especifica el punto de conexión de metadatos para el servicio de token de seguridad (STS) de un servicio aliado.</span><span class="sxs-lookup"><span data-stu-id="fdf59-144">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="fdf59-145">Define los parámetros para un token emitido en un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="fdf59-145">Defines parameters for an issued token in a custom binding.</span></span>|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="fdf59-146">Especifica un servicio de token de seguridad (STS) local.</span><span class="sxs-lookup"><span data-stu-id="fdf59-146">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fdf59-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdf59-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="fdf59-148">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="fdf59-148">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fdf59-149">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="fdf59-149">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
