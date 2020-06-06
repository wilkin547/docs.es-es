---
title: <certificate> para <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850020"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="4c425-102">\<certificate> para \<identity></span><span class="sxs-lookup"><span data-stu-id="4c425-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="4c425-103">Especifica un certificado X.509 usado para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="4c425-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="4c425-104">Para obtener más información sobre cómo establecer el valor del elemento, vea [identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="4c425-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="4c425-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c425-105">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c425-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4c425-106">Attributes and Elements</span></span>  
 <span data-ttu-id="4c425-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4c425-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c425-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="4c425-108">Attributes</span></span>  
  
|<span data-ttu-id="4c425-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="4c425-109">Attribute</span></span>|<span data-ttu-id="4c425-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c425-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c425-111">encodedValue</span><span class="sxs-lookup"><span data-stu-id="4c425-111">encodedValue</span></span>|<span data-ttu-id="4c425-112">Una codificación Base64 del certificado.</span><span class="sxs-lookup"><span data-stu-id="4c425-112">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c425-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4c425-113">Child Elements</span></span>  
 <span data-ttu-id="4c425-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4c425-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c425-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4c425-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4c425-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="4c425-116">Element</span></span>|<span data-ttu-id="4c425-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c425-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="4c425-118">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="4c425-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4c425-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c425-119">Example</span></span>  
 <span data-ttu-id="4c425-120">El código siguiente especifica la representación codificada de un certificado usada para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="4c425-120">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="4c425-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4c425-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="4c425-122">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="4c425-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
