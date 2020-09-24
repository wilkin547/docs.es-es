---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: aa6bc7f5a94afc8a190d3d9d2d71ea8b38d8c25b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153578"
---
# \<sslStreamSecurity>

<span data-ttu-id="c07fd-101">Representa un elemento de enlace personalizado que admite seguridad del canal mediante una secuencia de SSL.</span><span class="sxs-lookup"><span data-stu-id="c07fd-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="c07fd-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c07fd-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c07fd-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c07fd-103">Attributes and Elements</span></span>  

 <span data-ttu-id="c07fd-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c07fd-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c07fd-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="c07fd-105">Attributes</span></span>  
  
|<span data-ttu-id="c07fd-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="c07fd-106">Attribute</span></span>|<span data-ttu-id="c07fd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c07fd-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c07fd-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="c07fd-108">requireClientCertificate</span></span>|<span data-ttu-id="c07fd-109">Un valor booleano que especifica si se requiere un certificado de cliente para este enlace.</span><span class="sxs-lookup"><span data-stu-id="c07fd-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="c07fd-110">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="c07fd-110">The default is `false`.</span></span>|  
|<span data-ttu-id="c07fd-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="c07fd-111">sslProtocols</span></span>|<span data-ttu-id="c07fd-112">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="c07fd-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="c07fd-113">El valor predeterminado es Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="c07fd-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c07fd-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c07fd-114">Child Elements</span></span>  

 <span data-ttu-id="c07fd-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c07fd-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c07fd-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c07fd-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c07fd-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="c07fd-117">Element</span></span>|<span data-ttu-id="c07fd-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c07fd-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c07fd-119">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c07fd-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c07fd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c07fd-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="c07fd-121">Enlaces</span><span class="sxs-lookup"><span data-stu-id="c07fd-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c07fd-122">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="c07fd-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c07fd-123">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c07fd-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
