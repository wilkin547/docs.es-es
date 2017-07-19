---
title: "C&#243;mo: Personalizar fuentes con el proveedor de reflexi&#243;n (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Servicios de datos de Microsoft WCF, personalizar"
  - "Servicios de datos de Microsoft WCF, personalizar fuentes"
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# C&#243;mo: Personalizar fuentes con el proveedor de reflexi&#243;n (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite personalizar la serialización Atom en una respuesta del servicio de datos para que las propiedades de una entidad se puedan asignar a los elementos no usados que se definen en el protocolo AtomPub.  En este tema se muestra cómo definir los atributos de asignación para los tipos de entidad de un modelo de datos que se define usando el proveedor de reflexión.  Para obtener más información, consulta [Personalización de fuentes](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 El modelo de datos para este ejemplo se define en el tema [Cómo: Crear un servicio de datos mediante el proveedor de reflexión](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
  
## Ejemplo  
 En el ejemplo siguiente, las dos propiedades del tipo `Order` se asignan a elementos Atom existentes.  La propiedad `Product` del tipo `Item` se asigna a un atributo de fuente personalizado en un espacio de nombres independiente.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## Ejemplo  
 En el ejemplo anterior se devuelve el resultado siguiente para el identificador URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## Vea también  
 [Proveedor de reflexión](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)