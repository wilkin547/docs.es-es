---
title: '&lt;RSA&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 714036b6f7cb64fd12cd48eabb4203279431e5a6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltrsagt"></a><span data-ttu-id="50a73-102">&lt;RSA&gt;</span><span class="sxs-lookup"><span data-stu-id="50a73-102">&lt;rsa&gt;</span></span>
<span data-ttu-id="50a73-103">Un cliente WCF seguro que se conecta a un punto de conexión con esta identidad comprueba que las notificaciones presentadas por el servidor contienen una notificación que incluye la clave pública RSA utilizada para construir esta identidad.</span><span class="sxs-lookup"><span data-stu-id="50a73-103">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="50a73-104">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="50a73-104">\<identity></span></span>  
<span data-ttu-id="50a73-105">\<RSA ></span><span class="sxs-lookup"><span data-stu-id="50a73-105">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50a73-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50a73-106">Syntax</span></span>  
  
```xml  
<rsa value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50a73-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="50a73-107">Attributes and Elements</span></span>  
 <span data-ttu-id="50a73-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios</span><span class="sxs-lookup"><span data-stu-id="50a73-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50a73-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="50a73-109">Attributes</span></span>  
  
|<span data-ttu-id="50a73-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="50a73-110">Attribute</span></span>|<span data-ttu-id="50a73-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="50a73-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50a73-112">value</span><span class="sxs-lookup"><span data-stu-id="50a73-112">value</span></span>|<span data-ttu-id="50a73-113">Cadena opcional.</span><span class="sxs-lookup"><span data-stu-id="50a73-113">Optional String.</span></span> <span data-ttu-id="50a73-114">El valor de clave pública de RSA con la que se va a comparar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="50a73-114">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50a73-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="50a73-115">Child Elements</span></span>  
 <span data-ttu-id="50a73-116">Ninguna</span><span class="sxs-lookup"><span data-stu-id="50a73-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50a73-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="50a73-117">Parent Elements</span></span>  
  
|<span data-ttu-id="50a73-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="50a73-118">Element</span></span>|<span data-ttu-id="50a73-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="50a73-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50a73-120">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="50a73-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="50a73-121">Especifica la identidad del servicio que va a autenticar el cliente.</span><span class="sxs-lookup"><span data-stu-id="50a73-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50a73-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50a73-122">Remarks</span></span>  
 <span data-ttu-id="50a73-123">Una comprobación de RSA le permite restringir específicamente la autenticación a un certificado único basado en su clave RSA o que generó su propio valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="50a73-123">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="50a73-124">Esto habilita una autenticación más estricta de una clave RSA específica en el gasto del servicio que ya no trabaja con clientes existentes si se cambia el valor de clave de RSA.</span><span class="sxs-lookup"><span data-stu-id="50a73-124">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="50a73-125">Para obtener más información acerca del uso de identidad para validar un servicio a un cliente, consulte [autenticación e identidad de servicio](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="50a73-125">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50a73-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50a73-126">Example</span></span>  
 <span data-ttu-id="50a73-127">El código de configuración siguiente especifica el valor de clave pública de un certificado X.509 que se usa para autenticar un servidor.</span><span class="sxs-lookup"><span data-stu-id="50a73-127">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <rsa value = "0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"/>  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50a73-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="50a73-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.RsaEndpointIdentity>  
 [<span data-ttu-id="50a73-129">Autenticación e identidad de servicio</span><span class="sxs-lookup"><span data-stu-id="50a73-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="50a73-130">\<identidad ></span><span class="sxs-lookup"><span data-stu-id="50a73-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
