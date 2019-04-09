---
title: Sindicación en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
ms.openlocfilehash: 198b664ff52b42b7f393eec3e8162f3a12037d9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175921"
---
# <a name="wcf-syndication"></a><span data-ttu-id="986c4-102">Sindicación en WCF</span><span class="sxs-lookup"><span data-stu-id="986c4-102">WCF Syndication</span></span>
<span data-ttu-id="986c4-103">Windows Communication Foundation (WCF) proporciona compatibilidad para trabajar fácilmente con las fuentes de distribución de Atom, RSS u otros formatos personalizados, que permiten leer y crearlos, así como su exposición en un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="986c4-103">Windows Communication Foundation (WCF) provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="986c4-104">Los temas de esta sección describen en detalle este modelo de programación para la sindicación.</span><span class="sxs-lookup"><span data-stu-id="986c4-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="986c4-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="986c4-105">In This Section</span></span>  
 [<span data-ttu-id="986c4-106">Información general de distribución de WCF</span><span class="sxs-lookup"><span data-stu-id="986c4-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="986c4-107">Proporciona información general de compatibilidad de la distribución de WCF.</span><span class="sxs-lookup"><span data-stu-id="986c4-107">Provides an overview of syndication support provided by WCF.</span></span>  
  
 [<span data-ttu-id="986c4-108">Arquitectura de distribución</span><span class="sxs-lookup"><span data-stu-id="986c4-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="986c4-109">Describe las clases del modelo de objetos y la extensibilidad de sindicación.</span><span class="sxs-lookup"><span data-stu-id="986c4-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="986c4-110">Asignación del modelo de objetos de distribución de WCF a Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="986c4-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="986c4-111">Describe cómo se representan las fuentes dentro del modelo de objetos de sindicación de WCF, y cómo se convierten en fuentes RSS y Átomo.</span><span class="sxs-lookup"><span data-stu-id="986c4-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="986c4-112">Filtrar para crear una fuente RSS básica</span><span class="sxs-lookup"><span data-stu-id="986c4-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="986c4-113">Muestra cómo crear un servicio que hace que una fuente RSS básica esté disponible.</span><span class="sxs-lookup"><span data-stu-id="986c4-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="986c4-114">Filtrar para crear una fuente Atom básica</span><span class="sxs-lookup"><span data-stu-id="986c4-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="986c4-115">Muestra cómo crear un servicio que hace que una fuente ÁTOMO básica esté disponible.</span><span class="sxs-lookup"><span data-stu-id="986c4-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="986c4-116">Filtrar para exponer una fuente como Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="986c4-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="986c4-117">Muestra cómo crear un servicio que hace que la misma fuente esté disponible con ÁTOMO y RSS.</span><span class="sxs-lookup"><span data-stu-id="986c4-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="986c4-118">Extensibilidad de la distribución</span><span class="sxs-lookup"><span data-stu-id="986c4-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="986c4-119">Describe los métodos para agregar elementos y atributos personalizados a una fuente de distribución.</span><span class="sxs-lookup"><span data-stu-id="986c4-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="986c4-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="986c4-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="986c4-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="986c4-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="986c4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="986c4-122">See also</span></span>

- [<span data-ttu-id="986c4-123">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="986c4-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="986c4-124">Confianza parcial</span><span class="sxs-lookup"><span data-stu-id="986c4-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
