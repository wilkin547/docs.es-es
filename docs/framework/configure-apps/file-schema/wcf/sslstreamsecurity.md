---
description: 'Más información acerca de: <sslStreamSecurity>'
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 77e08deb5263e330ead5df21ed1ef2dddbba28ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682701"
---
# \<sslStreamSecurity>

<span data-ttu-id="59c16-102">Representa un elemento de enlace personalizado que admite seguridad del canal mediante una secuencia de SSL.</span><span class="sxs-lookup"><span data-stu-id="59c16-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="59c16-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59c16-103">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59c16-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="59c16-104">Attributes and Elements</span></span>  

 <span data-ttu-id="59c16-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="59c16-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59c16-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="59c16-106">Attributes</span></span>  
  
|<span data-ttu-id="59c16-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="59c16-107">Attribute</span></span>|<span data-ttu-id="59c16-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="59c16-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59c16-109">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="59c16-109">requireClientCertificate</span></span>|<span data-ttu-id="59c16-110">Un valor booleano que especifica si se requiere un certificado de cliente para este enlace.</span><span class="sxs-lookup"><span data-stu-id="59c16-110">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="59c16-111">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="59c16-111">The default is `false`.</span></span>|  
|<span data-ttu-id="59c16-112">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="59c16-112">sslProtocols</span></span>|<span data-ttu-id="59c16-113">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="59c16-113">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="59c16-114">El valor predeterminado es Ssl3&#124;TLS&#124;Tls11&#124;Tls12.</span><span class="sxs-lookup"><span data-stu-id="59c16-114">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59c16-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="59c16-115">Child Elements</span></span>  

 <span data-ttu-id="59c16-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="59c16-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59c16-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="59c16-117">Parent Elements</span></span>  
  
|<span data-ttu-id="59c16-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="59c16-118">Element</span></span>|<span data-ttu-id="59c16-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="59c16-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="59c16-120">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="59c16-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59c16-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="59c16-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="59c16-122">Enlaces</span><span class="sxs-lookup"><span data-stu-id="59c16-122">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="59c16-123">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="59c16-123">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="59c16-124">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="59c16-124">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
