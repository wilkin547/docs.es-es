---
description: 'Más información acerca de: <dns>'
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: a5c0601a027c72b4d6307261793bd5725979db92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803898"
---
# \<dns>

<span data-ttu-id="6d5aa-102">Especifica la identidad esperada del servidor.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="6d5aa-103">Esta identidad es válida para el modo de autenticación de certificado X509 si el certificado del servidor contiene un DNS con el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="6d5aa-104">También es válido para el modo de autenticación de Windows si el SPN tiene el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="6d5aa-105">Para obtener más información sobre cómo establecer el valor del elemento, vea [identidad del servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6d5aa-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**  
  
## <a name="syntax"></a><span data-ttu-id="6d5aa-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d5aa-106">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d5aa-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6d5aa-107">Attributes and Elements</span></span>  

 <span data-ttu-id="6d5aa-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d5aa-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="6d5aa-109">Attributes</span></span>  
  
|<span data-ttu-id="6d5aa-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="6d5aa-110">Attribute</span></span>|<span data-ttu-id="6d5aa-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d5aa-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d5aa-112">value</span><span class="sxs-lookup"><span data-stu-id="6d5aa-112">value</span></span>|<span data-ttu-id="6d5aa-113">DNS del certificado.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-113">The DNS of the certificate.</span></span> <span data-ttu-id="6d5aa-114">DNS es un protocolo de estándar de la industria usado para buscar equipos en una red basada en IP.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-114">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="6d5aa-115">Los usuarios pueden recordar nombres para mostrar, como `https://go.microsoft.com/fwlink/?prd=10929` o `https://go.microsoft.com/fwlink/?LinkID=96165` , más sencillos que las direcciones basadas en números, como 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-115">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d5aa-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6d5aa-116">Child Elements</span></span>  

 <span data-ttu-id="6d5aa-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d5aa-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6d5aa-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6d5aa-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d5aa-119">Element</span></span>|<span data-ttu-id="6d5aa-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d5aa-120">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="6d5aa-121">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6d5aa-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d5aa-122">Example</span></span>  

 <span data-ttu-id="6d5aa-123">El código de configuración siguiente especifica el DNS de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="6d5aa-123">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="6d5aa-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d5aa-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="6d5aa-125">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="6d5aa-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
