---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: c5c7ec2b18143ff4d71540a60e24b8225ca4db16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738594"
---
# \<sslStreamSecurity>
<span data-ttu-id="76819-101">Representa un elemento de enlace personalizado que admite seguridad del canal mediante una secuencia de SSL.</span><span class="sxs-lookup"><span data-stu-id="76819-101">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="76819-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76819-102">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76819-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76819-103">Attributes and Elements</span></span>  
 <span data-ttu-id="76819-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76819-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76819-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="76819-105">Attributes</span></span>  
  
|<span data-ttu-id="76819-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="76819-106">Attribute</span></span>|<span data-ttu-id="76819-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="76819-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76819-108">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="76819-108">requireClientCertificate</span></span>|<span data-ttu-id="76819-109">Un valor booleano que especifica si se requiere un certificado de cliente para este enlace.</span><span class="sxs-lookup"><span data-stu-id="76819-109">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="76819-110">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="76819-110">The default is `false`.</span></span>|  
|<span data-ttu-id="76819-111">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="76819-111">sslProtocols</span></span>|<span data-ttu-id="76819-112">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="76819-112">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="76819-113">El valor predeterminado es Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="76819-113">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76819-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76819-114">Child Elements</span></span>  
 <span data-ttu-id="76819-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="76819-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76819-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76819-116">Parent Elements</span></span>  
  
|<span data-ttu-id="76819-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="76819-117">Element</span></span>|<span data-ttu-id="76819-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="76819-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="76819-119">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="76819-119">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76819-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76819-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="76819-121">Enlaces</span><span class="sxs-lookup"><span data-stu-id="76819-121">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="76819-122">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="76819-122">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="76819-123">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="76819-123">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
