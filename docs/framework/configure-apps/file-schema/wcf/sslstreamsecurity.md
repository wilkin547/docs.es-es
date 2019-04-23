---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 67ec30b2bf3c322b949700789ce942e4281b77a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204450"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="4817d-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="4817d-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="4817d-102">Representa un elemento de enlace personalizado que admite seguridad del canal mediante una secuencia de SSL.</span><span class="sxs-lookup"><span data-stu-id="4817d-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
 <span data-ttu-id="4817d-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4817d-103">\<system.serviceModel></span></span>  
<span data-ttu-id="4817d-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4817d-104">\<bindings></span></span>  
<span data-ttu-id="4817d-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4817d-105">\<customBinding></span></span>  
<span data-ttu-id="4817d-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="4817d-106">\<binding></span></span>  
<span data-ttu-id="4817d-107">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="4817d-107">\<sslStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4817d-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4817d-108">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4817d-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4817d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4817d-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4817d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4817d-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="4817d-111">Attributes</span></span>  
  
|<span data-ttu-id="4817d-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="4817d-112">Attribute</span></span>|<span data-ttu-id="4817d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="4817d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4817d-114">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="4817d-114">requireClientCertificate</span></span>|<span data-ttu-id="4817d-115">Un valor booleano que especifica si se requiere un certificado de cliente para este enlace.</span><span class="sxs-lookup"><span data-stu-id="4817d-115">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="4817d-116">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="4817d-116">The default is `false`.</span></span>|  
|<span data-ttu-id="4817d-117">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="4817d-117">sslProtocols</span></span>|<span data-ttu-id="4817d-118">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="4817d-118">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="4817d-119">El valor predeterminado es Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="4817d-119">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4817d-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4817d-120">Child Elements</span></span>  
 <span data-ttu-id="4817d-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4817d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4817d-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4817d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4817d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4817d-123">Element</span></span>|<span data-ttu-id="4817d-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="4817d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4817d-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="4817d-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4817d-126">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="4817d-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4817d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4817d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="4817d-128">Enlaces</span><span class="sxs-lookup"><span data-stu-id="4817d-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4817d-129">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="4817d-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4817d-130">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4817d-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4817d-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4817d-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
