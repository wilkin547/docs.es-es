---
title: Sindicación en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
ms.openlocfilehash: 198b664ff52b42b7f393eec3e8162f3a12037d9d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935530"
---
# <a name="wcf-syndication"></a><span data-ttu-id="4155f-102">Sindicación en WCF</span><span class="sxs-lookup"><span data-stu-id="4155f-102">WCF Syndication</span></span>
<span data-ttu-id="4155f-103">Windows Communication Foundation (WCF) proporciona compatibilidad para trabajar fácilmente con las fuentes de distribución de Atom, RSS u otros formatos personalizados, que permiten leer y crearlos, así como su exposición en un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="4155f-103">Windows Communication Foundation (WCF) provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="4155f-104">Los temas de esta sección describen en detalle este modelo de programación para la sindicación.</span><span class="sxs-lookup"><span data-stu-id="4155f-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4155f-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4155f-105">In This Section</span></span>  
 [<span data-ttu-id="4155f-106">Información general de redifusión en WCF</span><span class="sxs-lookup"><span data-stu-id="4155f-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="4155f-107">Proporciona información general de compatibilidad de la distribución de WCF.</span><span class="sxs-lookup"><span data-stu-id="4155f-107">Provides an overview of syndication support provided by WCF.</span></span>  
  
 [<span data-ttu-id="4155f-108">Arquitectura de redifusión</span><span class="sxs-lookup"><span data-stu-id="4155f-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="4155f-109">Describe las clases del modelo de objetos y la extensibilidad de sindicación.</span><span class="sxs-lookup"><span data-stu-id="4155f-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="4155f-110">Asignación del modelo de objetos de distribución de WCF a Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="4155f-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="4155f-111">Describe cómo se representan las fuentes dentro del modelo de objetos de sindicación de WCF, y cómo se convierten en fuentes RSS y Átomo.</span><span class="sxs-lookup"><span data-stu-id="4155f-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="4155f-112">Cómo: Creación de una fuente RSS básica</span><span class="sxs-lookup"><span data-stu-id="4155f-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="4155f-113">Muestra cómo crear un servicio que hace que una fuente RSS básica esté disponible.</span><span class="sxs-lookup"><span data-stu-id="4155f-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="4155f-114">Cómo: Creación de una fuente básica de Atom</span><span class="sxs-lookup"><span data-stu-id="4155f-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="4155f-115">Muestra cómo crear un servicio que hace que una fuente ÁTOMO básica esté disponible.</span><span class="sxs-lookup"><span data-stu-id="4155f-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="4155f-116">Cómo: Exponer una fuente como Atom y RSS</span><span class="sxs-lookup"><span data-stu-id="4155f-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="4155f-117">Muestra cómo crear un servicio que hace que la misma fuente esté disponible con ÁTOMO y RSS.</span><span class="sxs-lookup"><span data-stu-id="4155f-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="4155f-118">Extensibilidad de la distribución</span><span class="sxs-lookup"><span data-stu-id="4155f-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="4155f-119">Describe los métodos para agregar elementos y atributos personalizados a una fuente de distribución.</span><span class="sxs-lookup"><span data-stu-id="4155f-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4155f-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="4155f-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4155f-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4155f-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4155f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4155f-122">See also</span></span>

- [<span data-ttu-id="4155f-123">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="4155f-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="4155f-124">Confianza parcial</span><span class="sxs-lookup"><span data-stu-id="4155f-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
