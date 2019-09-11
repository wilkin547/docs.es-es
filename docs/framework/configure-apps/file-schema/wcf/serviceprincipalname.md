---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854995"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="35684-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="35684-101">\<servicePrincipalName></span></span>
<span data-ttu-id="35684-102">Especifica la identidad de un servicio por su Nombre de entidad de seguridad de servicio (SPN).</span><span class="sxs-lookup"><span data-stu-id="35684-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="35684-103">Para obtener más información acerca de cómo establecer el SPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="35684-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="35684-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="35684-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="35684-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="35684-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="35684-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de cliente**](client.md)</span><span class="sxs-lookup"><span data-stu-id="35684-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="35684-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de extremo**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="35684-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="35684-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de identidad**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="35684-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="35684-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> servicePrincipalName**</span><span class="sxs-lookup"><span data-stu-id="35684-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35684-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35684-110">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35684-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="35684-111">Attributes and Elements</span></span>  
 <span data-ttu-id="35684-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="35684-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35684-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="35684-113">Attributes</span></span>  
  
|<span data-ttu-id="35684-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="35684-114">Attribute</span></span>|<span data-ttu-id="35684-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="35684-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35684-116">valor</span><span class="sxs-lookup"><span data-stu-id="35684-116">value</span></span>|<span data-ttu-id="35684-117">El nombre por el que un cliente identifica de manera unívoca una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="35684-117">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="35684-118">Si instala varias instancias de un servicio en equipos a lo largo de un bosque, cada instancia debe tener su propio SPN.</span><span class="sxs-lookup"><span data-stu-id="35684-118">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="35684-119">Una instancia de servicio determinada puede tener varios SPN si hay varios nombres que los clientes pueden usar para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="35684-119">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35684-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="35684-120">Child Elements</span></span>  
 <span data-ttu-id="35684-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="35684-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35684-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="35684-122">Parent Elements</span></span>  
  
|<span data-ttu-id="35684-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="35684-123">Element</span></span>|<span data-ttu-id="35684-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="35684-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35684-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="35684-125">\<identity></span></span>](identity.md)|<span data-ttu-id="35684-126">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="35684-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35684-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35684-127">Remarks</span></span>  
 <span data-ttu-id="35684-128">Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el SPN al realizar la autenticación SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="35684-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35684-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="35684-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="35684-130">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="35684-130">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="35684-131">\<identity></span><span class="sxs-lookup"><span data-stu-id="35684-131">\<identity></span></span>](identity.md)
