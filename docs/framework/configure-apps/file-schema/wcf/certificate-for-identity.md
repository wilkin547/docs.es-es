---
title: <certificate> para <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 24c39b5efaee7f8db12088d272efeb3783efab04
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198865"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="c2eeb-102">\<certificate> para \<identity></span><span class="sxs-lookup"><span data-stu-id="c2eeb-102">\<certificate> for \<identity></span></span>

<span data-ttu-id="c2eeb-103">Especifica un certificado X.509 usado para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="c2eeb-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="c2eeb-104">Para obtener más información sobre cómo establecer el valor del elemento, vea [identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c2eeb-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="c2eeb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c2eeb-105">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2eeb-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c2eeb-106">Attributes and Elements</span></span>  

 <span data-ttu-id="c2eeb-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c2eeb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2eeb-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="c2eeb-108">Attributes</span></span>  
  
|<span data-ttu-id="c2eeb-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="c2eeb-109">Attribute</span></span>|<span data-ttu-id="c2eeb-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2eeb-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2eeb-111">encodedValue</span><span class="sxs-lookup"><span data-stu-id="c2eeb-111">encodedValue</span></span>|<span data-ttu-id="c2eeb-112">Una codificación Base64 del certificado.</span><span class="sxs-lookup"><span data-stu-id="c2eeb-112">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2eeb-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c2eeb-113">Child Elements</span></span>  

 <span data-ttu-id="c2eeb-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c2eeb-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c2eeb-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c2eeb-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c2eeb-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="c2eeb-116">Element</span></span>|<span data-ttu-id="c2eeb-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2eeb-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="c2eeb-118">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="c2eeb-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c2eeb-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c2eeb-119">Example</span></span>  

 <span data-ttu-id="c2eeb-120">El código siguiente especifica la representación codificada de un certificado usada para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="c2eeb-120">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="c2eeb-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2eeb-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="c2eeb-122">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="c2eeb-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
