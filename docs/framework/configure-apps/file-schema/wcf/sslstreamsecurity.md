---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: f66569f36dc61a063b79a088dcbc405126a074d8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284603"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="e2b73-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="e2b73-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="e2b73-102">Representa un elemento de enlace personalizado que admite seguridad del canal mediante una secuencia de SSL.</span><span class="sxs-lookup"><span data-stu-id="e2b73-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="e2b73-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e2b73-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e2b73-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e2b73-104">\<bindings></span></span>  
<span data-ttu-id="e2b73-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e2b73-105">\<customBinding></span></span>  
<span data-ttu-id="e2b73-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="e2b73-106">\<binding></span></span>  
<span data-ttu-id="e2b73-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="e2b73-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b73-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2b73-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2b73-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e2b73-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e2b73-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e2b73-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2b73-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="e2b73-111">Attributes</span></span>  
  
|<span data-ttu-id="e2b73-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="e2b73-112">Attribute</span></span>|<span data-ttu-id="e2b73-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2b73-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e2b73-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="e2b73-114">requireClientCertificate</span></span>|<span data-ttu-id="e2b73-115">Un valor booleano que especifica si se requiere un certificado de cliente para este enlace.</span><span class="sxs-lookup"><span data-stu-id="e2b73-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="e2b73-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="e2b73-116">The default is `false`.</span></span>|  
|<span data-ttu-id="e2b73-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="e2b73-117">sslProtocols</span></span>|<span data-ttu-id="e2b73-118">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="e2b73-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="e2b73-119">El valor predeterminado es Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="e2b73-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2b73-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e2b73-120">Child Elements</span></span>  
 <span data-ttu-id="e2b73-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e2b73-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2b73-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e2b73-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e2b73-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="e2b73-123">Element</span></span>|<span data-ttu-id="e2b73-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2b73-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2b73-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="e2b73-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e2b73-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e2b73-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2b73-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2b73-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="e2b73-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e2b73-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e2b73-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="e2b73-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e2b73-130">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="e2b73-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e2b73-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e2b73-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
