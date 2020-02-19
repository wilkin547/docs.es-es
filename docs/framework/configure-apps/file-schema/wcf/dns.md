---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: e49a564c9793b371425b2b787586bb9d3cbed58b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452232"
---
# <a name="dns"></a><span data-ttu-id="d514a-101">\<> DNS</span><span class="sxs-lookup"><span data-stu-id="d514a-101">\<dns></span></span>
<span data-ttu-id="d514a-102">Especifica la identidad esperada del servidor.</span><span class="sxs-lookup"><span data-stu-id="d514a-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="d514a-103">Esta identidad es válida para el modo de autenticación de certificado X509 si el certificado del servidor contiene un DNS con el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="d514a-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="d514a-104">También es válido para el modo de autenticación de Windows si el SPN tiene el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="d514a-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="d514a-105">Para obtener más información sobre cómo establecer el valor del elemento, vea [identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d514a-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="d514a-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d514a-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d514a-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d514a-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d514a-108">&nbsp;&nbsp;&nbsp;&nbsp;\<[**cliente**](client.md) ></span><span class="sxs-lookup"><span data-stu-id="d514a-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="d514a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**extremo**](endpoint-of-client.md) ></span><span class="sxs-lookup"><span data-stu-id="d514a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="d514a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**identity >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="d514a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="d514a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**DNS** ></span><span class="sxs-lookup"><span data-stu-id="d514a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d514a-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d514a-112">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d514a-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d514a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d514a-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d514a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d514a-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="d514a-115">Attributes</span></span>  
  
|<span data-ttu-id="d514a-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="d514a-116">Attribute</span></span>|<span data-ttu-id="d514a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d514a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d514a-118">value</span><span class="sxs-lookup"><span data-stu-id="d514a-118">value</span></span>|<span data-ttu-id="d514a-119">DNS del certificado.</span><span class="sxs-lookup"><span data-stu-id="d514a-119">The DNS of the certificate.</span></span> <span data-ttu-id="d514a-120">DNS es un protocolo de estándar de la industria usado para buscar equipos en una red basada en IP.</span><span class="sxs-lookup"><span data-stu-id="d514a-120">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="d514a-121">Los usuarios pueden recordar nombres para mostrar, como `https://go.microsoft.com/fwlink/?prd=10929` o `https://go.microsoft.com/fwlink/?LinkID=96165`, más fáciles que las direcciones basadas en números, como 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="d514a-121">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d514a-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d514a-122">Child Elements</span></span>  
 <span data-ttu-id="d514a-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d514a-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d514a-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d514a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d514a-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d514a-125">Element</span></span>|<span data-ttu-id="d514a-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="d514a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d514a-127">\<Identity ></span><span class="sxs-lookup"><span data-stu-id="d514a-127">\<identity></span></span>](identity.md)|<span data-ttu-id="d514a-128">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="d514a-128">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d514a-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d514a-129">Example</span></span>  
 <span data-ttu-id="d514a-130">El código de configuración siguiente especifica el DNS de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="d514a-130">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="d514a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d514a-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="d514a-132">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="d514a-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d514a-133">\<Identity ></span><span class="sxs-lookup"><span data-stu-id="d514a-133">\<identity></span></span>](identity.md)
