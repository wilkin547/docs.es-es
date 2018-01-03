---
title: '&lt;userPrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34bfaeb563bd4979bf29a5e45a60730eb38700b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="26468-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="26468-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="26468-103">Especifica el Nombre principal de usuario (UPN) de un servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="26468-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="26468-104">Para obtener más información acerca de cómo establecer el UPN, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="26468-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="26468-105">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="26468-105">\<identity></span></span>  
<span data-ttu-id="26468-106">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="26468-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26468-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26468-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26468-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="26468-108">Attributes and Elements</span></span>  
 <span data-ttu-id="26468-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26468-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26468-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="26468-110">Attributes</span></span>  
  
|<span data-ttu-id="26468-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="26468-111">Attribute</span></span>|<span data-ttu-id="26468-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="26468-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26468-113">value</span><span class="sxs-lookup"><span data-stu-id="26468-113">value</span></span>|<span data-ttu-id="26468-114">Un nombre de cuenta de usuario (a veces denominado nombre de inicio de sesión de usuario) y un nombre de dominio que identifica el dominio en el que se ubica la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="26468-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="26468-115">Éste es el uso estándar para iniciar sesión en un dominio de Windows.</span><span class="sxs-lookup"><span data-stu-id="26468-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="26468-116">El formato es: someone@example.com (para una dirección de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="26468-116">The format is: someone@example.com (as for an e-mail address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26468-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="26468-117">Child Elements</span></span>  
 <span data-ttu-id="26468-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="26468-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26468-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="26468-119">Parent Elements</span></span>  
  
|<span data-ttu-id="26468-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="26468-120">Element</span></span>|<span data-ttu-id="26468-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="26468-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26468-122">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="26468-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="26468-123">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="26468-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26468-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26468-124">Remarks</span></span>  
 <span data-ttu-id="26468-125">Un cliente [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] seguro que se conecta a un extremo con esta identidad utiliza UPN al realizar la autenticación de SSPI con el extremo.</span><span class="sxs-lookup"><span data-stu-id="26468-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26468-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26468-126">Example</span></span>  
 <span data-ttu-id="26468-127">El código de configuración siguiente especifica el UPN del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="26468-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="26468-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="26468-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="26468-129">Identidad del servicio y autenticación</span><span class="sxs-lookup"><span data-stu-id="26468-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="26468-130">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="26468-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
