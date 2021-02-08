---
description: 'Más información acerca de: <servicePrincipalName>'
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 494368f1f47f10aac8009e47a9219966c87e5eda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786699"
---
# \<servicePrincipalName>

<span data-ttu-id="2dbd4-102">Especifica la identidad de un servicio por su Nombre de entidad de seguridad de servicio (SPN).</span><span class="sxs-lookup"><span data-stu-id="2dbd4-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="2dbd4-103">Para obtener más información acerca de cómo establecer el SPN, consulte [identidad de servicio y autenticación](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2dbd4-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="2dbd4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2dbd4-104">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2dbd4-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2dbd4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="2dbd4-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2dbd4-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dbd4-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="2dbd4-107">Attributes</span></span>  
  
|<span data-ttu-id="2dbd4-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="2dbd4-108">Attribute</span></span>|<span data-ttu-id="2dbd4-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2dbd4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2dbd4-110">value</span><span class="sxs-lookup"><span data-stu-id="2dbd4-110">value</span></span>|<span data-ttu-id="2dbd4-111">Nombre por el que un cliente identifica de forma exclusiva una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="2dbd4-111">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="2dbd4-112">Si instala varias instancias de un servicio en equipos a lo largo de un bosque, cada instancia debe tener su propio SPN.</span><span class="sxs-lookup"><span data-stu-id="2dbd4-112">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="2dbd4-113">Una instancia de servicio determinada puede tener varios SPN si hay varios nombres que los clientes pueden usar para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="2dbd4-113">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dbd4-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2dbd4-114">Child Elements</span></span>  

 <span data-ttu-id="2dbd4-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2dbd4-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2dbd4-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2dbd4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="2dbd4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="2dbd4-117">Element</span></span>|<span data-ttu-id="2dbd4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="2dbd4-118">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="2dbd4-119">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="2dbd4-119">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2dbd4-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2dbd4-120">Remarks</span></span>  

 <span data-ttu-id="2dbd4-121">Un cliente de Windows Communication Foundation seguro (WCF) que se conecta a un punto de conexión con esta identidad utiliza el SPN al realizar la autenticación SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="2dbd4-121">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dbd4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dbd4-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="2dbd4-123">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="2dbd4-123">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
