---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 598b341e8b09acd11ba215e6add3adf9e44b2b81
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400465"
---
# <a name="custom"></a><span data-ttu-id="830ed-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="830ed-101">\<custom></span></span>
<span data-ttu-id="830ed-102">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="830ed-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="830ed-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="830ed-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="830ed-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="830ed-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="830ed-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="830ed-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="830ed-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> netPeerTcpBinding**](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="830ed-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="830ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="830ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="830ed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Solucionador >** ](resolver.md)</span><span class="sxs-lookup"><span data-stu-id="830ed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)</span></span>\
<span data-ttu-id="830ed-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> personalizado**</span><span class="sxs-lookup"><span data-stu-id="830ed-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="830ed-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="830ed-110">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="830ed-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="830ed-111">Attributes and Elements</span></span>  
 <span data-ttu-id="830ed-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="830ed-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="830ed-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="830ed-113">Attributes</span></span>  
  
|<span data-ttu-id="830ed-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="830ed-114">Attribute</span></span>|<span data-ttu-id="830ed-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="830ed-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="830ed-116">Un URI que especifica la dirección de extremo del nodo del mismo nivel que hospeda el servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="830ed-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="830ed-117">Una cadena que especifica el tipo de servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="830ed-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="830ed-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="830ed-118">Child Elements</span></span>  
  
|<span data-ttu-id="830ed-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="830ed-119">Element</span></span>|<span data-ttu-id="830ed-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="830ed-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="830ed-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="830ed-121">\<identity></span></span>](identity.md)|<span data-ttu-id="830ed-122">Especifica la identidad para las resoluciones del mismo nivel personalizadas configuradas con este elemento.</span><span class="sxs-lookup"><span data-stu-id="830ed-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="830ed-123">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="830ed-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="830ed-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="830ed-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="830ed-125">Una colección de encabezado de dirección usada para mensajes SOAP administrados por la resolución del mismo nivel personalizada.</span><span class="sxs-lookup"><span data-stu-id="830ed-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="830ed-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="830ed-126">Parent Elements</span></span>  
  
|<span data-ttu-id="830ed-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="830ed-127">Element</span></span>|<span data-ttu-id="830ed-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="830ed-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="830ed-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="830ed-129">\<resolver></span></span>](resolver.md)|<span data-ttu-id="830ed-130">Una resolución del mismo nivel que se usa para resolver un Id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="830ed-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="830ed-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="830ed-131">Remarks</span></span>  
 <span data-ttu-id="830ed-132">Este elemento define la configuración básica para un servicio de la resolución del mismo nivel personalizado, incluso la dirección de extremo del igual que hospeda el servicio y cualquier configuración obligatoria concreta.</span><span class="sxs-lookup"><span data-stu-id="830ed-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="830ed-133">Para obtener más información sobre cómo crear un solucionador personalizado, vea [Agregar un solucionador personalizado a una aplicación de PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="830ed-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="830ed-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="830ed-134">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="830ed-135">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="830ed-135">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="830ed-136">[Adición de un solucionador personalizado a una aplicación de PeerChannel](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="830ed-136">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
