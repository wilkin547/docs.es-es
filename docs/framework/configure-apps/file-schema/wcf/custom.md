---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: c208a6c7305ccbbe8efb10d071de29cf1bd2cc10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165148"
---
# \<custom>

<span data-ttu-id="52fd5-101">Especifica la configuración concreta para un servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="52fd5-101">Specifies settings for a custom peer resolver service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a><span data-ttu-id="52fd5-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52fd5-102">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52fd5-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="52fd5-103">Attributes and Elements</span></span>  

 <span data-ttu-id="52fd5-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="52fd5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52fd5-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="52fd5-105">Attributes</span></span>  
  
|<span data-ttu-id="52fd5-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="52fd5-106">Attribute</span></span>|<span data-ttu-id="52fd5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="52fd5-107">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="52fd5-108">Un URI que especifica la dirección de extremo del nodo del mismo nivel que hospeda el servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="52fd5-108">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="52fd5-109">Una cadena que especifica el tipo de servicio de resolución del mismo nivel personalizado.</span><span class="sxs-lookup"><span data-stu-id="52fd5-109">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52fd5-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="52fd5-110">Child Elements</span></span>  
  
|<span data-ttu-id="52fd5-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="52fd5-111">Element</span></span>|<span data-ttu-id="52fd5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="52fd5-112">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="52fd5-113">Especifica la identidad para las resoluciones del mismo nivel personalizadas configuradas con este elemento.</span><span class="sxs-lookup"><span data-stu-id="52fd5-113">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="52fd5-114">Este elemento es del tipo <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="52fd5-114">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="52fd5-115">Una colección de encabezado de dirección usada para mensajes SOAP administrados por la resolución del mismo nivel personalizada.</span><span class="sxs-lookup"><span data-stu-id="52fd5-115">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52fd5-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="52fd5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="52fd5-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="52fd5-117">Element</span></span>|<span data-ttu-id="52fd5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="52fd5-118">Description</span></span>|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|<span data-ttu-id="52fd5-119">Una resolución del mismo nivel que se usa para resolver un Id. de malla del mismo nivel como un conjunto de direcciones del nodo del mismo nivel que representa varios nodos que participan en la malla.</span><span class="sxs-lookup"><span data-stu-id="52fd5-119">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52fd5-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52fd5-120">Remarks</span></span>  

 <span data-ttu-id="52fd5-121">Este elemento define la configuración básica para un servicio de la resolución del mismo nivel personalizado, incluso la dirección de extremo del igual que hospeda el servicio y cualquier configuración obligatoria concreta.</span><span class="sxs-lookup"><span data-stu-id="52fd5-121">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="52fd5-122">Para obtener más información sobre cómo crear un solucionador personalizado, vea [Agregar un solucionador personalizado a una aplicación de PeerChannel](/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="52fd5-122">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52fd5-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52fd5-123">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="52fd5-124">Resoluciones del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="52fd5-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="52fd5-125">[Adición de una resolución personalizada a una aplicación PeerChannel](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="52fd5-125">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
