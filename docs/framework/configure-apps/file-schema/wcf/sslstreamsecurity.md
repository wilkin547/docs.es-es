---
title: '&lt;sslStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a86e1aae7ddd5389f098e532ae2c2cc67f4085e3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752408"
---
# <a name="ltsslstreamsecuritygt"></a><span data-ttu-id="a0413-102">&lt;sslStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="a0413-102">&lt;sslStreamSecurity&gt;</span></span>
<span data-ttu-id="a0413-103">Representa un elemento de enlace personalizado que admite seguridad del canal mediante una secuencia de SSL.</span><span class="sxs-lookup"><span data-stu-id="a0413-103">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="a0413-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a0413-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a0413-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="a0413-105">\<bindings></span></span>  
<span data-ttu-id="a0413-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a0413-106">\<customBinding></span></span>  
<span data-ttu-id="a0413-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a0413-107">\<binding></span></span>  
<span data-ttu-id="a0413-108">\<sslStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="a0413-108">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0413-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0413-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"      sslProtocols="Ssl3|Tls|Tls11|Tls12" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0413-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0413-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a0413-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0413-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0413-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0413-112">Attributes</span></span>  
  
|<span data-ttu-id="a0413-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="a0413-113">Attribute</span></span>|<span data-ttu-id="a0413-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0413-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0413-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="a0413-115">requireClientCertificate</span></span>|<span data-ttu-id="a0413-116">Un valor booleano que especifica si se requiere un certificado de cliente para este enlace.</span><span class="sxs-lookup"><span data-stu-id="a0413-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="a0413-117">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="a0413-117">The default is `false`.</span></span>|  
|<span data-ttu-id="a0413-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="a0413-118">sslProtocols</span></span>|<span data-ttu-id="a0413-119">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="a0413-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="a0413-120">El valor predeterminado es Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="a0413-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0413-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0413-121">Child Elements</span></span>  
 <span data-ttu-id="a0413-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a0413-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0413-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0413-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a0413-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0413-124">Element</span></span>|<span data-ttu-id="a0413-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0413-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0413-126">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="a0413-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a0413-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a0413-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0413-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0413-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
 [<span data-ttu-id="a0413-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="a0413-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a0413-130">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="a0413-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a0413-131">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a0413-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a0413-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a0413-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
