---
title: '&lt;certificate&gt; para &lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a9eabd25712136ef98f452cc15470bce1893527e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="15cba-102">&lt;certificate&gt; para &lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="15cba-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="15cba-103">Especifica un certificado X.509 usado para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="15cba-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="15cba-104">Para obtener más información acerca de cómo establecer el valor del elemento, vea [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="15cba-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="15cba-105">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="15cba-105">\<identity></span></span>  
<span data-ttu-id="15cba-106">\<certificado ></span><span class="sxs-lookup"><span data-stu-id="15cba-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15cba-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15cba-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15cba-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="15cba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="15cba-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="15cba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15cba-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="15cba-110">Attributes</span></span>  
  
|<span data-ttu-id="15cba-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="15cba-111">Attribute</span></span>|<span data-ttu-id="15cba-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="15cba-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15cba-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="15cba-113">encodedValue</span></span>|<span data-ttu-id="15cba-114">Una codificación Base64 del certificado.</span><span class="sxs-lookup"><span data-stu-id="15cba-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15cba-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="15cba-115">Child Elements</span></span>  
 <span data-ttu-id="15cba-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="15cba-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15cba-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="15cba-117">Parent Elements</span></span>  
  
|<span data-ttu-id="15cba-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="15cba-118">Element</span></span>|<span data-ttu-id="15cba-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="15cba-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15cba-120">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="15cba-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="15cba-121">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="15cba-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="15cba-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15cba-122">Example</span></span>  
 <span data-ttu-id="15cba-123">El código siguiente especifica la representación codificada de un certificado usada para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="15cba-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>  
  <certificate encodedValue = " MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="15cba-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="15cba-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [<span data-ttu-id="15cba-125">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="15cba-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="15cba-126">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="15cba-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
