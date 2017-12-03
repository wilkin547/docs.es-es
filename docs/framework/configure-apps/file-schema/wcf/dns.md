---
title: '&lt;DNS&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6994069ca57a078e3d8236739ecf091d9e179455
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltdnsgt"></a><span data-ttu-id="968c7-102">&lt;DNS&gt;</span><span class="sxs-lookup"><span data-stu-id="968c7-102">&lt;dns&gt;</span></span>
<span data-ttu-id="968c7-103">Especifica la identidad esperada del servidor.</span><span class="sxs-lookup"><span data-stu-id="968c7-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="968c7-104">Esta identidad es válida para el modo de autenticación de certificado X509 si el certificado del servidor contiene un DNS con el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="968c7-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="968c7-105">También es válido para el modo de autenticación de Windows si el SPN tiene el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="968c7-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="968c7-106">Para obtener más información acerca de cómo establecer el valor del elemento, vea [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="968c7-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="968c7-107">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="968c7-107">\<identity></span></span>  
<span data-ttu-id="968c7-108">\<DNS ></span><span class="sxs-lookup"><span data-stu-id="968c7-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="968c7-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="968c7-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="968c7-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="968c7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="968c7-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="968c7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="968c7-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="968c7-112">Attributes</span></span>  
  
|<span data-ttu-id="968c7-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="968c7-113">Attribute</span></span>|<span data-ttu-id="968c7-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="968c7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="968c7-115">value</span><span class="sxs-lookup"><span data-stu-id="968c7-115">value</span></span>|<span data-ttu-id="968c7-116">DNS del certificado.</span><span class="sxs-lookup"><span data-stu-id="968c7-116">The DNS of the certificate.</span></span> <span data-ttu-id="968c7-117">DNS es un protocolo de estándar de la industria usado para buscar equipos en una red basada en IP.</span><span class="sxs-lookup"><span data-stu-id="968c7-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="968c7-118">Los usuarios pueden recordar nombres para mostrar, como [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) o [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), resulta más sencillo que direcciones basadas en número, como 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="968c7-118">Users can remember display names, such as [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) or [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="968c7-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="968c7-119">Child Elements</span></span>  
 <span data-ttu-id="968c7-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="968c7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="968c7-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="968c7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="968c7-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="968c7-122">Element</span></span>|<span data-ttu-id="968c7-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="968c7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="968c7-124">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="968c7-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="968c7-125">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="968c7-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="968c7-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="968c7-126">Example</span></span>  
 <span data-ttu-id="968c7-127">El código de configuración siguiente especifica el DNS de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="968c7-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="968c7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="968c7-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [<span data-ttu-id="968c7-129">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="968c7-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="968c7-130">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="968c7-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
