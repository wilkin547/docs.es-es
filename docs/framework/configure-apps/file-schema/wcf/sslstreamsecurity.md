---
title: <sslStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 430a378b-a742-4858-8a12-9f9b235fd627
ms.openlocfilehash: 9b7092878c604142c29dcd8d27e3c458d203f9fa
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399527"
---
# <a name="sslstreamsecurity"></a><span data-ttu-id="19aaa-101">\<sslStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="19aaa-101">\<sslStreamSecurity></span></span>
<span data-ttu-id="19aaa-102">Representa un elemento de enlace personalizado que admite seguridad del canal mediante una secuencia de SSL.</span><span class="sxs-lookup"><span data-stu-id="19aaa-102">Represents a custom binding element that supports channel security using an SSL stream.</span></span>  
  
<span data-ttu-id="19aaa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19aaa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19aaa-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="19aaa-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="19aaa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="19aaa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="19aaa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="19aaa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="19aaa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="19aaa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="19aaa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> sección sslstreamsecurity**</span><span class="sxs-lookup"><span data-stu-id="19aaa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sslStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19aaa-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19aaa-109">Syntax</span></span>  
  
```xml  
<sslStreamSecurity requireClientCertificate="Boolean"
                   sslProtocols="Ssl3|Tls|Tls11|Tls12" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19aaa-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="19aaa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="19aaa-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="19aaa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19aaa-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="19aaa-112">Attributes</span></span>  
  
|<span data-ttu-id="19aaa-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="19aaa-113">Attribute</span></span>|<span data-ttu-id="19aaa-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="19aaa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="19aaa-115">requireClientCertificate</span><span class="sxs-lookup"><span data-stu-id="19aaa-115">requireClientCertificate</span></span>|<span data-ttu-id="19aaa-116">Un valor booleano que especifica si se requiere un certificado de cliente para este enlace.</span><span class="sxs-lookup"><span data-stu-id="19aaa-116">A Boolean value that specifies if a client certificate is required for this binding.</span></span> <span data-ttu-id="19aaa-117">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="19aaa-117">The default is `false`.</span></span>|  
|<span data-ttu-id="19aaa-118">sslProtocols</span><span class="sxs-lookup"><span data-stu-id="19aaa-118">sslProtocols</span></span>|<span data-ttu-id="19aaa-119">Un valor de marca de enumeración de SslProtocols que especifica qué SslProtocols son compatibles.</span><span class="sxs-lookup"><span data-stu-id="19aaa-119">A SslProtocols enum flag value that specifies which SslProtocols are supported.</span></span> <span data-ttu-id="19aaa-120">El valor predeterminado es&#124;Ssl3&#124;TLS&#124;Tls11 Tls12.</span><span class="sxs-lookup"><span data-stu-id="19aaa-120">The default is Ssl3&#124;Tls&#124;Tls11&#124;Tls12.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19aaa-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="19aaa-121">Child Elements</span></span>  
 <span data-ttu-id="19aaa-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="19aaa-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19aaa-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="19aaa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="19aaa-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="19aaa-124">Element</span></span>|<span data-ttu-id="19aaa-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="19aaa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19aaa-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="19aaa-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="19aaa-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="19aaa-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19aaa-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="19aaa-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SslStreamSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>
- [<span data-ttu-id="19aaa-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="19aaa-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="19aaa-130">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="19aaa-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="19aaa-131">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="19aaa-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="19aaa-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="19aaa-132">\<customBinding></span></span>](custombinding.md)
