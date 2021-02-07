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
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>Cómo: Personalizar fuentes con el proveedor de reflexión (Servicios de datos de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Servicios de datos de WCF permite personalizar la serialización Atom en una respuesta del servicio de datos para que las propiedades de una entidad se puedan asignar a elementos no usados que se definen en el protocolo AtomPub. En este tema se muestra cómo definir los atributos de asignación para los tipos de entidad de un modelo de datos que se define usando el proveedor de reflexión. Para obtener más información, vea [Personalización de fuentes](feed-customization-wcf-data-services.md).  
  
 El modelo de datos para este ejemplo se define en el tema [Cómo: crear un servicio de datos mediante el proveedor de reflexión.](create-a-data-service-using-rp-wcf-data-services.md)  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, las dos propiedades del tipo `Order` se asignan a elementos Atom existentes. La propiedad `Product` del tipo `Item` se asigna a un atributo de fuente personalizado en un espacio de nombres independiente.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo anterior se devuelve el resultado siguiente para el identificador URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>Vea también

- [Proveedor de reflexión](reflection-provider-wcf-data-services.md)
