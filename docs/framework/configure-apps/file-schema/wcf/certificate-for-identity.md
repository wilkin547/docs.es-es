---
title: <certificate> para <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850020"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="67bf9-102">\<> de certificado \<para > de identidad</span><span class="sxs-lookup"><span data-stu-id="67bf9-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="67bf9-103">Especifica un certificado X.509 usado para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="67bf9-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="67bf9-104">Para obtener más información sobre cómo establecer el valor del elemento, vea [identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="67bf9-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="67bf9-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="67bf9-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="67bf9-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="67bf9-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="67bf9-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="67bf9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="67bf9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de extremo**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="67bf9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="67bf9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de identidad**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="67bf9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="67bf9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de certificado**</span><span class="sxs-lookup"><span data-stu-id="67bf9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67bf9-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67bf9-111">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67bf9-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="67bf9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="67bf9-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="67bf9-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67bf9-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="67bf9-114">Attributes</span></span>  
  
|<span data-ttu-id="67bf9-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="67bf9-115">Attribute</span></span>|<span data-ttu-id="67bf9-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="67bf9-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67bf9-117">encodedValue</span><span class="sxs-lookup"><span data-stu-id="67bf9-117">encodedValue</span></span>|<span data-ttu-id="67bf9-118">Una codificación Base64 del certificado.</span><span class="sxs-lookup"><span data-stu-id="67bf9-118">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67bf9-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="67bf9-119">Child Elements</span></span>  
 <span data-ttu-id="67bf9-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="67bf9-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67bf9-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="67bf9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="67bf9-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="67bf9-122">Element</span></span>|<span data-ttu-id="67bf9-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="67bf9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67bf9-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="67bf9-124">\<identity></span></span>](identity.md)|<span data-ttu-id="67bf9-125">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="67bf9-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="67bf9-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67bf9-126">Example</span></span>  
 <span data-ttu-id="67bf9-127">El código siguiente especifica la representación codificada de un certificado usada para validar un servidor a un cliente.</span><span class="sxs-lookup"><span data-stu-id="67bf9-127">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="67bf9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="67bf9-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="67bf9-129">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="67bf9-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="67bf9-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="67bf9-130">\<identity></span></span>](identity.md)
