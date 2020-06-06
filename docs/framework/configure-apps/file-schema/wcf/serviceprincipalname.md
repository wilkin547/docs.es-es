---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854995"
---
# \<servicePrincipalName>
<span data-ttu-id="975d4-101">Especifica la identidad de un servicio por su Nombre de entidad de seguridad de servicio (SPN).</span><span class="sxs-lookup"><span data-stu-id="975d4-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="975d4-102">Para obtener más información acerca de cómo establecer el SPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="975d4-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="975d4-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="975d4-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="975d4-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="975d4-104">Attributes and Elements</span></span>  
 <span data-ttu-id="975d4-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="975d4-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="975d4-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="975d4-106">Attributes</span></span>  
  
|<span data-ttu-id="975d4-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="975d4-107">Attribute</span></span>|<span data-ttu-id="975d4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="975d4-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="975d4-109">value</span><span class="sxs-lookup"><span data-stu-id="975d4-109">value</span></span>|<span data-ttu-id="975d4-110">Nombre por el que un cliente identifica de forma exclusiva una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="975d4-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="975d4-111">Si instala varias instancias de un servicio en equipos a lo largo de un bosque, cada instancia debe tener su propio SPN.</span><span class="sxs-lookup"><span data-stu-id="975d4-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="975d4-112">Una instancia de servicio determinada puede tener varios SPN si hay varios nombres que los clientes pueden usar para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="975d4-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="975d4-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="975d4-113">Child Elements</span></span>  
 <span data-ttu-id="975d4-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="975d4-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="975d4-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="975d4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="975d4-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="975d4-116">Element</span></span>|<span data-ttu-id="975d4-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="975d4-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="975d4-118">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="975d4-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="975d4-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="975d4-119">Remarks</span></span>  
 <span data-ttu-id="975d4-120">Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el SPN al realizar la autenticación SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="975d4-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="975d4-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="975d4-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="975d4-122">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="975d4-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
