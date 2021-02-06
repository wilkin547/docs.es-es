---
description: 'Más información acerca <certificate> de: para <identity>'
title: <certificate> para <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: b1ccda7e8e84825cc0b2b2be123fe30be449189a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639112"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="3fe6f-103">\<certificate> para \<identity></span><span class="sxs-lookup"><span data-stu-id="3fe6f-103">\<certificate> for \<identity></span></span>

<span data-ttu-id="3fe6f-104">Especifica un certificado X.509 usado para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-104">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="3fe6f-105">Para obtener más información sobre cómo establecer el valor del elemento, vea [identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="3fe6f-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="3fe6f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fe6f-106">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fe6f-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3fe6f-107">Attributes and Elements</span></span>  

 <span data-ttu-id="3fe6f-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fe6f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="3fe6f-109">Attributes</span></span>  
  
|<span data-ttu-id="3fe6f-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="3fe6f-110">Attribute</span></span>|<span data-ttu-id="3fe6f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fe6f-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3fe6f-112">encodedValue</span><span class="sxs-lookup"><span data-stu-id="3fe6f-112">encodedValue</span></span>|<span data-ttu-id="3fe6f-113">Una codificación Base64 del certificado.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-113">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fe6f-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3fe6f-114">Child Elements</span></span>  

 <span data-ttu-id="3fe6f-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3fe6f-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3fe6f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="3fe6f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="3fe6f-117">Element</span></span>|<span data-ttu-id="3fe6f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fe6f-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="3fe6f-119">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-119">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3fe6f-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3fe6f-120">Example</span></span>  

 <span data-ttu-id="3fe6f-121">El código siguiente especifica la representación codificada de un certificado usada para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="3fe6f-121">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="3fe6f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fe6f-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="3fe6f-123">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="3fe6f-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
