---
title: '&lt;certificate&gt; para &lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 28a1b992a70986652030ad42d4d4a5738350ae1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676164"
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="97ab7-102">&lt;certificate&gt; para &lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="97ab7-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="97ab7-103">Especifica un certificado X.509 usado para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="97ab7-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="97ab7-104">Para obtener más información acerca de cómo establecer el valor del elemento, vea [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="97ab7-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="97ab7-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="97ab7-105">\<identity></span></span>  
<span data-ttu-id="97ab7-106">\<certificate></span><span class="sxs-lookup"><span data-stu-id="97ab7-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ab7-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97ab7-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97ab7-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97ab7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="97ab7-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97ab7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97ab7-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="97ab7-110">Attributes</span></span>  
  
|<span data-ttu-id="97ab7-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="97ab7-111">Attribute</span></span>|<span data-ttu-id="97ab7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ab7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97ab7-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="97ab7-113">encodedValue</span></span>|<span data-ttu-id="97ab7-114">Una codificación Base64 del certificado.</span><span class="sxs-lookup"><span data-stu-id="97ab7-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97ab7-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97ab7-115">Child Elements</span></span>  
 <span data-ttu-id="97ab7-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97ab7-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97ab7-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97ab7-117">Parent Elements</span></span>  
  
|<span data-ttu-id="97ab7-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="97ab7-118">Element</span></span>|<span data-ttu-id="97ab7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="97ab7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97ab7-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="97ab7-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="97ab7-121">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="97ab7-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="97ab7-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97ab7-122">Example</span></span>  
 <span data-ttu-id="97ab7-123">El código siguiente especifica la representación codificada de un certificado usada para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="97ab7-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="97ab7-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ab7-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="97ab7-125">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="97ab7-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="97ab7-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="97ab7-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
