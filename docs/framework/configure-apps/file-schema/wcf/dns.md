---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: ce12d0a82c8a443994559ed772496897f359b4e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166678"
---
# <a name="dns"></a><span data-ttu-id="3e75b-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="3e75b-101">\<dns></span></span>
<span data-ttu-id="3e75b-102">Especifica la identidad esperada del servidor.</span><span class="sxs-lookup"><span data-stu-id="3e75b-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="3e75b-103">Esta identidad es válida para el modo de autenticación de certificado X509 si el certificado del servidor contiene un DNS con el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="3e75b-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="3e75b-104">También es válido para el modo de autenticación de Windows si el SPN tiene el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="3e75b-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="3e75b-105">Para obtener más información acerca de cómo establecer el valor del elemento, vea [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="3e75b-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="3e75b-106">\<identity></span><span class="sxs-lookup"><span data-stu-id="3e75b-106">\<identity></span></span>  
<span data-ttu-id="3e75b-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="3e75b-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e75b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e75b-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e75b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3e75b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3e75b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3e75b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e75b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="3e75b-111">Attributes</span></span>  
  
|<span data-ttu-id="3e75b-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="3e75b-112">Attribute</span></span>|<span data-ttu-id="3e75b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e75b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3e75b-114">value</span><span class="sxs-lookup"><span data-stu-id="3e75b-114">value</span></span>|<span data-ttu-id="3e75b-115">DNS del certificado.</span><span class="sxs-lookup"><span data-stu-id="3e75b-115">The DNS of the certificate.</span></span> <span data-ttu-id="3e75b-116">DNS es un protocolo de estándar de la industria usado para buscar equipos en una red basada en IP.</span><span class="sxs-lookup"><span data-stu-id="3e75b-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="3e75b-117">Los usuarios pueden recordar nombres para mostrar, como [ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929) o [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), más fácil que las direcciones basadas en números, como 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="3e75b-117">Users can remember display names, such as [https://go.microsoft.com/fwlink/?prd=10929](https://go.microsoft.com/fwlink/?prd=10929) or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3e75b-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3e75b-118">Child Elements</span></span>  
 <span data-ttu-id="3e75b-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3e75b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3e75b-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3e75b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3e75b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3e75b-121">Element</span></span>|<span data-ttu-id="3e75b-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e75b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3e75b-123">\<identity></span><span class="sxs-lookup"><span data-stu-id="3e75b-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="3e75b-124">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="3e75b-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3e75b-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e75b-125">Example</span></span>  
 <span data-ttu-id="3e75b-126">El código de configuración siguiente especifica el DNS de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="3e75b-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="3e75b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e75b-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="3e75b-128">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="3e75b-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3e75b-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="3e75b-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
