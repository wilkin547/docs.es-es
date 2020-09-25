---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: adfd94365ceb0ddc3164a6baef838c16027b4bc3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190143"
---
# \<dns>

<span data-ttu-id="67f47-101">Especifica la identidad esperada del servidor.</span><span class="sxs-lookup"><span data-stu-id="67f47-101">Specifies the expected identity of the server.</span></span> <span data-ttu-id="67f47-102">Esta identidad es válida para el modo de autenticación de certificado X509 si el certificado del servidor contiene un DNS con el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="67f47-102">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="67f47-103">También es válido para el modo de autenticación de Windows si el SPN tiene el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="67f47-103">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="67f47-104">Para obtener más información sobre cómo establecer el valor del elemento, vea [identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="67f47-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**  
  
## <a name="syntax"></a><span data-ttu-id="67f47-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67f47-105">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67f47-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="67f47-106">Attributes and Elements</span></span>  

 <span data-ttu-id="67f47-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="67f47-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67f47-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="67f47-108">Attributes</span></span>  
  
|<span data-ttu-id="67f47-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="67f47-109">Attribute</span></span>|<span data-ttu-id="67f47-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="67f47-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67f47-111">value</span><span class="sxs-lookup"><span data-stu-id="67f47-111">value</span></span>|<span data-ttu-id="67f47-112">DNS del certificado.</span><span class="sxs-lookup"><span data-stu-id="67f47-112">The DNS of the certificate.</span></span> <span data-ttu-id="67f47-113">DNS es un protocolo de estándar de la industria usado para buscar equipos en una red basada en IP.</span><span class="sxs-lookup"><span data-stu-id="67f47-113">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="67f47-114">Los usuarios pueden recordar nombres para mostrar, como `https://go.microsoft.com/fwlink/?prd=10929` o `https://go.microsoft.com/fwlink/?LinkID=96165` , más sencillos que las direcciones basadas en números, como 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="67f47-114">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67f47-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="67f47-115">Child Elements</span></span>  

 <span data-ttu-id="67f47-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="67f47-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67f47-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="67f47-117">Parent Elements</span></span>  
  
|<span data-ttu-id="67f47-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="67f47-118">Element</span></span>|<span data-ttu-id="67f47-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="67f47-119">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="67f47-120">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="67f47-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="67f47-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67f47-121">Example</span></span>  

 <span data-ttu-id="67f47-122">El código de configuración siguiente especifica el DNS de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="67f47-122">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="67f47-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="67f47-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="67f47-124">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="67f47-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
