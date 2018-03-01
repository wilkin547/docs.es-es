---
title: "Sindicación en WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1f7f5fd65fc298107a66e2049c059f3cc58b3d44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-syndication"></a><span data-ttu-id="dab41-102">Sindicación en WCF</span><span class="sxs-lookup"><span data-stu-id="dab41-102">WCF Syndication</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="dab41-103"> proporciona compatibilidad para trabajar con facilidad con las fuentes de distribución de Atom, RSS u otros formatos personalizados, que permiten su lectura y creación, así como su exposición en un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="dab41-103"> provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="dab41-104">Los temas de esta sección describen en detalle este modelo de programación para la sindicación.</span><span class="sxs-lookup"><span data-stu-id="dab41-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dab41-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dab41-105">In This Section</span></span>  
 [<span data-ttu-id="dab41-106">Información general de redifusión en WCF</span><span class="sxs-lookup"><span data-stu-id="dab41-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="dab41-107">Proporciona información general acerca de la compatibilidad de sindicación proporcionada por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dab41-107">Provides an overview of syndication support provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="dab41-108">Arquitectura de redifusión</span><span class="sxs-lookup"><span data-stu-id="dab41-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="dab41-109">Describe las clases del modelo de objetos y la extensibilidad de sindicación.</span><span class="sxs-lookup"><span data-stu-id="dab41-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="dab41-110">Asignación del modelo de objetos de distribución de WCF a Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="dab41-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="dab41-111">Describe cómo se representan las fuentes dentro del modelo de objetos de sindicación de WCF, y cómo se convierten en fuentes RSS y Átomo.</span><span class="sxs-lookup"><span data-stu-id="dab41-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="dab41-112">Creación de una fuente RSS básica</span><span class="sxs-lookup"><span data-stu-id="dab41-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="dab41-113">Muestra cómo crear un servicio que hace que una fuente RSS básica esté disponible.</span><span class="sxs-lookup"><span data-stu-id="dab41-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="dab41-114">Creación de una fuente básica de Atom</span><span class="sxs-lookup"><span data-stu-id="dab41-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="dab41-115">Muestra cómo crear un servicio que hace que una fuente ÁTOMO básica esté disponible.</span><span class="sxs-lookup"><span data-stu-id="dab41-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="dab41-116">Exposición de una fuente como Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="dab41-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="dab41-117">Muestra cómo crear un servicio que hace que la misma fuente esté disponible con ÁTOMO y RSS.</span><span class="sxs-lookup"><span data-stu-id="dab41-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="dab41-118">Extensibilidad de la distribución</span><span class="sxs-lookup"><span data-stu-id="dab41-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="dab41-119">Describe los métodos para agregar elementos y atributos personalizados a una fuente de distribución.</span><span class="sxs-lookup"><span data-stu-id="dab41-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dab41-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="dab41-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dab41-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="dab41-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab41-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="dab41-122">See Also</span></span>  
 [<span data-ttu-id="dab41-123">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="dab41-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="dab41-124">Confianza parcial</span><span class="sxs-lookup"><span data-stu-id="dab41-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
