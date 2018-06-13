---
title: 'Cómo: Personalizar fuentes con el proveedor de reflexión (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: 984a4aac43689be0ec80e7f6c289e8d5229e9e1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358013"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="1ed4d-102">Cómo: Personalizar fuentes con el proveedor de reflexión (Data Services de WCF)</span><span class="sxs-lookup"><span data-stu-id="1ed4d-102">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="1ed4d-103"> le permite personalizar la serialización Atom en una respuesta del servicio de datos para que las propiedades de una entidad se puedan asignar a los elementos no usados que se definen en el protocolo AtomPub.</span><span class="sxs-lookup"><span data-stu-id="1ed4d-103"> enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="1ed4d-104">En este tema se muestra cómo definir los atributos de asignación para los tipos de entidad de un modelo de datos que se define usando el proveedor de reflexión.</span><span class="sxs-lookup"><span data-stu-id="1ed4d-104">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="1ed4d-105">Para obtener más información, consulte [personalización de fuente](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ed4d-105">For more information, see [Feed Customization](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="1ed4d-106">El modelo de datos en este ejemplo se define en el tema [Cómo: crear un servicio de datos mediante el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="1ed4d-106">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ed4d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ed4d-107">Example</span></span>  
 <span data-ttu-id="1ed4d-108">En el ejemplo siguiente, las dos propiedades del tipo `Order` se asignan a elementos Atom existentes.</span><span class="sxs-lookup"><span data-stu-id="1ed4d-108">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="1ed4d-109">La propiedad `Product` del tipo `Item` se asigna a un atributo de fuente personalizado en un espacio de nombres independiente.</span><span class="sxs-lookup"><span data-stu-id="1ed4d-109">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="1ed4d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ed4d-110">Example</span></span>  
 <span data-ttu-id="1ed4d-111">En el ejemplo anterior se devuelve el resultado siguiente para el identificador URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span><span class="sxs-lookup"><span data-stu-id="1ed4d-111">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="1ed4d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ed4d-112">See Also</span></span>  
 [<span data-ttu-id="1ed4d-113">Proveedor de reflexión</span><span class="sxs-lookup"><span data-stu-id="1ed4d-113">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
