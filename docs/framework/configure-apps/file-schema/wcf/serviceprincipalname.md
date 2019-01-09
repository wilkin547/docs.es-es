---
title: '&lt;servicePrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: a22a905744980d0b370023e6236734a9bb0d6357
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150648"
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="6c5cd-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="6c5cd-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="6c5cd-103">Especifica la identidad de un servicio por su Nombre de entidad de seguridad de servicio (SPN).</span><span class="sxs-lookup"><span data-stu-id="6c5cd-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="6c5cd-104">Para obtener más información acerca de cómo establecer el SPN, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6c5cd-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="6c5cd-105">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="6c5cd-105">\<identity></span></span>  
<span data-ttu-id="6c5cd-106">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="6c5cd-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c5cd-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c5cd-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c5cd-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6c5cd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6c5cd-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c5cd-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c5cd-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="6c5cd-110">Attributes</span></span>  
  
|<span data-ttu-id="6c5cd-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="6c5cd-111">Attribute</span></span>|<span data-ttu-id="6c5cd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c5cd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c5cd-113">value</span><span class="sxs-lookup"><span data-stu-id="6c5cd-113">value</span></span>|<span data-ttu-id="6c5cd-114">El nombre por el que un cliente identifica de manera unívoca una instancia de un servicio.</span><span class="sxs-lookup"><span data-stu-id="6c5cd-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="6c5cd-115">Si instala varias instancias de un servicio en equipos a lo largo de un bosque, cada instancia debe tener su propio SPN.</span><span class="sxs-lookup"><span data-stu-id="6c5cd-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="6c5cd-116">Una instancia de servicio determinada puede tener varios SPN si hay varios nombres que los clientes pueden usar para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="6c5cd-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c5cd-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6c5cd-117">Child Elements</span></span>  
 <span data-ttu-id="6c5cd-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c5cd-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c5cd-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c5cd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6c5cd-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c5cd-120">Element</span></span>|<span data-ttu-id="6c5cd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c5cd-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c5cd-122">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="6c5cd-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="6c5cd-123">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="6c5cd-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c5cd-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c5cd-124">Remarks</span></span>  
 <span data-ttu-id="6c5cd-125">Un cliente segura de Windows Communication Foundation (WCF) que se conecta a un punto de conexión con esta identidad utiliza SPN al realizar la autenticación de SSPI con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="6c5cd-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c5cd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c5cd-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="6c5cd-127">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="6c5cd-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="6c5cd-128">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="6c5cd-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
