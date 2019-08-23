---
title: <certificate> para <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 52d1fa31cebd949c91809464976739ef1334af29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919614"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="02521-102">\<> de certificado \<para > de identidad</span><span class="sxs-lookup"><span data-stu-id="02521-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="02521-103">Especifica un certificado X.509 usado para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="02521-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="02521-104">Para obtener más información sobre cómo establecer el valor del elemento, vea [identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="02521-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="02521-105">\<> de identidad</span><span class="sxs-lookup"><span data-stu-id="02521-105">\<identity></span></span>  
<span data-ttu-id="02521-106">\<certificate></span><span class="sxs-lookup"><span data-stu-id="02521-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02521-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02521-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02521-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02521-108">Attributes and Elements</span></span>  
 <span data-ttu-id="02521-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02521-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02521-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="02521-110">Attributes</span></span>  
  
|<span data-ttu-id="02521-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="02521-111">Attribute</span></span>|<span data-ttu-id="02521-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="02521-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02521-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="02521-113">encodedValue</span></span>|<span data-ttu-id="02521-114">Una codificación Base64 del certificado.</span><span class="sxs-lookup"><span data-stu-id="02521-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02521-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02521-115">Child Elements</span></span>  
 <span data-ttu-id="02521-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02521-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02521-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02521-117">Parent Elements</span></span>  
  
|<span data-ttu-id="02521-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="02521-118">Element</span></span>|<span data-ttu-id="02521-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="02521-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02521-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="02521-120">\<identity></span></span>](identity.md)|<span data-ttu-id="02521-121">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="02521-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="02521-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02521-122">Example</span></span>  
 <span data-ttu-id="02521-123">El código siguiente especifica la representación codificada de un certificado usada para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="02521-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="02521-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="02521-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="02521-125">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="02521-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="02521-126">\<identity></span><span class="sxs-lookup"><span data-stu-id="02521-126">\<identity></span></span>](identity.md)
