---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: ba1484644c57651fc0feadcc61d71d03eec1899b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254935"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="76cb6-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="76cb6-101">\<servicePrincipalName></span></span>
<span data-ttu-id="76cb6-102">Especifica la identidad de un servicio por su Nombre de entidad de seguridad de servicio (SPN).</span><span class="sxs-lookup"><span data-stu-id="76cb6-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="76cb6-103">Para obtener más información acerca de cómo establecer el SPN, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="76cb6-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="76cb6-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="76cb6-104">\<identity></span></span>  
<span data-ttu-id="76cb6-105">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="76cb6-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76cb6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76cb6-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76cb6-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76cb6-107">Attributes and Elements</span></span>  
 <span data-ttu-id="76cb6-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76cb6-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76cb6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="76cb6-109">Attributes</span></span>  
  
|<span data-ttu-id="76cb6-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="76cb6-110">Attribute</span></span>|<span data-ttu-id="76cb6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="76cb6-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76cb6-112">value</span><span class="sxs-lookup"><span data-stu-id="76cb6-112">value</span></span>|<span data-ttu-id="76cb6-113">El nombre por el que un cliente identifica de manera unívoca una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="76cb6-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="76cb6-114">Si instala varias instancias de un servicio en equipos a lo largo de un bosque, cada instancia debe tener su propio SPN.</span><span class="sxs-lookup"><span data-stu-id="76cb6-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="76cb6-115">Una instancia de servicio determinada puede tener varios SPN si hay varios nombres que los clientes pueden usar para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="76cb6-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76cb6-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76cb6-116">Child Elements</span></span>  
 <span data-ttu-id="76cb6-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="76cb6-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76cb6-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76cb6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="76cb6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="76cb6-119">Element</span></span>|<span data-ttu-id="76cb6-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="76cb6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76cb6-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="76cb6-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="76cb6-122">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="76cb6-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76cb6-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76cb6-123">Remarks</span></span>  
 <span data-ttu-id="76cb6-124">Un cliente segura de Windows Communication Foundation (WCF) que se conecta a un punto de conexión con esta identidad utiliza SPN al realizar la autenticación de SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="76cb6-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76cb6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="76cb6-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="76cb6-126">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="76cb6-126">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="76cb6-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="76cb6-127">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
