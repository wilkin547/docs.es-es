---
description: 'Más información acerca de cómo: personalizar fuentes con el proveedor de reflexión (Servicios de datos de WCF)'
title: 'Cómo: Personalizar fuentes con el proveedor de reflexión (Servicios de datos de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: 91ac9cd3a5e882714335ce1d4ef29510d4640534
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765638"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="53765-103">Cómo: Personalizar fuentes con el proveedor de reflexión (Servicios de datos de WCF)</span><span class="sxs-lookup"><span data-stu-id="53765-103">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

<span data-ttu-id="53765-104">Servicios de datos de WCF permite personalizar la serialización Atom en una respuesta del servicio de datos para que las propiedades de una entidad se puedan asignar a elementos no usados que se definen en el protocolo AtomPub.</span><span class="sxs-lookup"><span data-stu-id="53765-104">WCF Data Services enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="53765-105">En este tema se muestra cómo definir los atributos de asignación para los tipos de entidad de un modelo de datos que se define usando el proveedor de reflexión.</span><span class="sxs-lookup"><span data-stu-id="53765-105">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="53765-106">Para obtener más información, vea [Personalización de fuentes](feed-customization-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="53765-106">For more information, see [Feed Customization](feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="53765-107">El modelo de datos para este ejemplo se define en el tema [Cómo: crear un servicio de datos mediante el proveedor de reflexión.](create-a-data-service-using-rp-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="53765-107">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="53765-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53765-108">Example</span></span>  

 <span data-ttu-id="53765-109">En el ejemplo siguiente, las dos propiedades del tipo `Order` se asignan a elementos Atom existentes.</span><span class="sxs-lookup"><span data-stu-id="53765-109">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="53765-110">La propiedad `Product` del tipo `Item` se asigna a un atributo de fuente personalizado en un espacio de nombres independiente.</span><span class="sxs-lookup"><span data-stu-id="53765-110">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="53765-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53765-111">Example</span></span>  

 <span data-ttu-id="53765-112">En el ejemplo anterior se devuelve el resultado siguiente para el identificador URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span><span class="sxs-lookup"><span data-stu-id="53765-112">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="53765-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="53765-113">See also</span></span>

- [<span data-ttu-id="53765-114">Proveedor de reflexión</span><span class="sxs-lookup"><span data-stu-id="53765-114">Reflection Provider</span></span>](reflection-provider-wcf-data-services.md)
