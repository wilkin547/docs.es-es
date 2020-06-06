---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855155"
---
# \<identity>
<span data-ttu-id="982c8-101">El elemento de identidad permite a un programador del cliente especificar en tiempo de diseño la identidad esperada del servicio.</span><span class="sxs-lookup"><span data-stu-id="982c8-101">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="982c8-102">En el proceso de protocolo de enlace entre el cliente y el servicio, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento y, por tanto, se puede autenticar.</span><span class="sxs-lookup"><span data-stu-id="982c8-102">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="982c8-103">Para obtener más información, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="982c8-103">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a><span data-ttu-id="982c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="982c8-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="982c8-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="982c8-105">Attributes and Elements</span></span>  
 <span data-ttu-id="982c8-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="982c8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="982c8-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="982c8-107">Attributes</span></span>  
 <span data-ttu-id="982c8-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="982c8-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="982c8-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="982c8-109">Child Elements</span></span>  
  
|<span data-ttu-id="982c8-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="982c8-110">Element</span></span>|<span data-ttu-id="982c8-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="982c8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="982c8-112">certificado</span><span class="sxs-lookup"><span data-stu-id="982c8-112">certificate</span></span>|<span data-ttu-id="982c8-113">Especifica los valores de un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="982c8-113">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="982c8-114">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateElement>.</span><span class="sxs-lookup"><span data-stu-id="982c8-114">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="982c8-115">Contiene un atributo `encodedValue` que es una cadena, que especifica el valor codificado por este certificado.</span><span class="sxs-lookup"><span data-stu-id="982c8-115">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="982c8-116">certificateReference</span><span class="sxs-lookup"><span data-stu-id="982c8-116">certificateReference</span></span>|<span data-ttu-id="982c8-117">Especifica los valores para la validación del certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="982c8-117">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="982c8-118">Este elemento es del tipo <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span><span class="sxs-lookup"><span data-stu-id="982c8-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="982c8-119">dns</span><span class="sxs-lookup"><span data-stu-id="982c8-119">dns</span></span>|<span data-ttu-id="982c8-120">Especifica el DNS de un certificado X.509 usado para autenticar un servicio.</span><span class="sxs-lookup"><span data-stu-id="982c8-120">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="982c8-121">Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.</span><span class="sxs-lookup"><span data-stu-id="982c8-121">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="982c8-122">rsa</span><span class="sxs-lookup"><span data-stu-id="982c8-122">rsa</span></span>|<span data-ttu-id="982c8-123">Especifica el valor del campo RSA de un certificado X.509 usado para autenticar un servicio a un cliente.</span><span class="sxs-lookup"><span data-stu-id="982c8-123">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="982c8-124">Este elemento contiene un atributo `value` que es una cadena y contiene la identidad real.</span><span class="sxs-lookup"><span data-stu-id="982c8-124">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="982c8-125">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="982c8-125">servicePrincipalName</span></span>|<span data-ttu-id="982c8-126">Especifica una identidad del nombre de entidad de seguridad de servidor (SPN) que es el nombre de entidad de seguridad usado por un cliente para identificar de manera unívoca una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="982c8-126">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="982c8-127">Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real.</span><span class="sxs-lookup"><span data-stu-id="982c8-127">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="982c8-128">Este elemento es del tipo <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="982c8-128">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="982c8-129">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="982c8-129">userPrincipalName</span></span>|<span data-ttu-id="982c8-130">Especifica una identidad del nombre principal del usuario (UPN), que es el tipo de nombre de inicio de sesión de un usuario en una red.</span><span class="sxs-lookup"><span data-stu-id="982c8-130">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="982c8-131">El nombre principal de usuario se compone del nombre de objeto de usuario que se usa en Active Directory, seguido del símbolo de arroba ( \@ ) y, a continuación, normalmente, el dominio primario del sistema de nombres de dominio.</span><span class="sxs-lookup"><span data-stu-id="982c8-131">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="982c8-132">Por ejemplo, Jeff en el árbol de dominio de Fabrikam.com podría tener el nombre principal de usuario [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) .</span><span class="sxs-lookup"><span data-stu-id="982c8-132">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="982c8-133">Este elemento contiene un atributo `value` que es una cadena y contiene el nombre de entidad de seguridad real.</span><span class="sxs-lookup"><span data-stu-id="982c8-133">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="982c8-134">Este elemento es del tipo <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span><span class="sxs-lookup"><span data-stu-id="982c8-134">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="982c8-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="982c8-135">Parent Elements</span></span>  
  
|<span data-ttu-id="982c8-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="982c8-136">Element</span></span>|<span data-ttu-id="982c8-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="982c8-137">Description</span></span>|  
|-------------|-----------------|  
|[\<custom>](custom.md)|<span data-ttu-id="982c8-138">Especifica la resolución del mismo nivel personalizado de un netPeerTcpBinding.</span><span class="sxs-lookup"><span data-stu-id="982c8-138">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="982c8-139">Configura puntos de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="982c8-139">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="982c8-140">\<endpoint>de\<client></span><span class="sxs-lookup"><span data-stu-id="982c8-140">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="982c8-141">Configura los extremos del canal.</span><span class="sxs-lookup"><span data-stu-id="982c8-141">Configures channel endpoints.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="982c8-142">Especifica el servicio de token de seguridad (STS) para el servicio aliado.</span><span class="sxs-lookup"><span data-stu-id="982c8-142">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="982c8-143">Especifica el punto de conexión de metadatos para el servicio de token de seguridad (STS) de un servicio aliado.</span><span class="sxs-lookup"><span data-stu-id="982c8-143">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="982c8-144">Define los parámetros para un token emitido en un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="982c8-144">Defines parameters for an issued token in a custom binding.</span></span>|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="982c8-145">Especifica un servicio de token de seguridad (STS) local.</span><span class="sxs-lookup"><span data-stu-id="982c8-145">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="982c8-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="982c8-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="982c8-147">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="982c8-147">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="982c8-148">Puntos de conexión: direcciones, enlaces y contratos</span><span class="sxs-lookup"><span data-stu-id="982c8-148">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
