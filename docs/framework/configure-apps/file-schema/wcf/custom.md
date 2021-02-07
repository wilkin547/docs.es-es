---
description: 'Más información acerca de: <custom>'
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 327a5d7ff1bab88a1633d7a10095e708e6b1a533
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725914"
---
# \<custom>

<span data-ttu-id="f5b5b-102">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-102">Specifies settings for a custom peer resolver service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a><span data-ttu-id="f5b5b-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5b5b-103">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5b5b-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f5b5b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f5b5b-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5b5b-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="f5b5b-106">Attributes</span></span>  
  
|<span data-ttu-id="f5b5b-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="f5b5b-107">Attribute</span></span>|<span data-ttu-id="f5b5b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5b5b-108">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="f5b5b-109">Un URI que especifica la dirección de extremo del nodo del mismo nivel que hospeda el servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-109">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="f5b5b-110">Una cadena que especifica el tipo de servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-110">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5b5b-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f5b5b-111">Child Elements</span></span>  
  
|<span data-ttu-id="f5b5b-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5b5b-112">Element</span></span>|<span data-ttu-id="f5b5b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5b5b-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="f5b5b-114">Especifica la identidad para las resoluciones del mismo nivel personalizadas configuradas con este elemento.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-114">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="f5b5b-115">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-115">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="f5b5b-116">Una colección de encabezado de dirección usada para mensajes SOAP administrados por la resolución del mismo nivel personalizada.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-116">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5b5b-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f5b5b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="f5b5b-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="f5b5b-118">Element</span></span>|<span data-ttu-id="f5b5b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5b5b-119">Description</span></span>|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|<span data-ttu-id="f5b5b-120">Una resolución del mismo nivel que se usa para resolver un Id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-120">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5b5b-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f5b5b-121">Remarks</span></span>  

 <span data-ttu-id="f5b5b-122">Este elemento define la configuración básica para un servicio de la resolución del mismo nivel personalizado, incluso la dirección de extremo del igual que hospeda el servicio y cualquier configuración obligatoria concreta.</span><span class="sxs-lookup"><span data-stu-id="f5b5b-122">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="f5b5b-123">Para obtener más información sobre cómo crear un solucionador personalizado, vea [Agregar un solucionador personalizado a una aplicación de PeerChannel](/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="f5b5b-123">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b5b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5b5b-124">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="f5b5b-125">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="f5b5b-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="f5b5b-126">[Adición de una resolución personalizada a una aplicación PeerChannel](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f5b5b-126">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
