---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 0d03844a58de5b4af93f276de75c88af6efed3f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153799"
---
# \<servicePrincipalName>

<span data-ttu-id="b360a-101">Especifica la identidad de un servicio por su Nombre de entidad de seguridad de servicio (SPN).</span><span class="sxs-lookup"><span data-stu-id="b360a-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="b360a-102">Para obtener más información acerca de cómo establecer el SPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b360a-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="b360a-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b360a-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b360a-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b360a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="b360a-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b360a-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b360a-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="b360a-106">Attributes</span></span>  
  
|<span data-ttu-id="b360a-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="b360a-107">Attribute</span></span>|<span data-ttu-id="b360a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b360a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b360a-109">value</span><span class="sxs-lookup"><span data-stu-id="b360a-109">value</span></span>|<span data-ttu-id="b360a-110">Nombre por el que un cliente identifica de forma exclusiva una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="b360a-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="b360a-111">Si instala varias instancias de un servicio en equipos a lo largo de un bosque, cada instancia debe tener su propio SPN.</span><span class="sxs-lookup"><span data-stu-id="b360a-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="b360a-112">Una instancia de servicio determinada puede tener varios SPN si hay varios nombres que los clientes pueden usar para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="b360a-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b360a-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b360a-113">Child Elements</span></span>  

 <span data-ttu-id="b360a-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b360a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b360a-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b360a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b360a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b360a-116">Element</span></span>|<span data-ttu-id="b360a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b360a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="b360a-118">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="b360a-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b360a-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b360a-119">Remarks</span></span>  

 <span data-ttu-id="b360a-120">Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el SPN al realizar la autenticación SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b360a-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b360a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b360a-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="b360a-122">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="b360a-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
