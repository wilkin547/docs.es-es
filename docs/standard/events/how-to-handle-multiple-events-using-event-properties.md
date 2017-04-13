---
title: "C&#243;mo: Controlar varios eventos mediante propiedades de eventos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controlar eventos [.NET Framework], con varios eventos"
  - "propiedades de eventos [.NET Framework]"
  - "eventos [.NET Framework], múltiple"
  - "varios eventos [.NET Framework]"
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Controlar varios eventos mediante propiedades de eventos
Para poder utilizar propiedades de evento, hay que definirlas en la clase que provoca los eventos y, a continuación, establecer los delegados de las propiedades de evento en las clases que controlan los eventos.  Para implementar varias propiedades de evento en una clase, esta clase deberá almacenar internamente y mantener el delegado definido para cada evento.  Para hacerlo, uno de los enfoques típicos consiste en implementar una colección de delegados que se indice por medio de una clave de evento.  
  
 Para almacenar los delegados de cada evento, puede utilizar la clase <xref:System.ComponentModel.EventHandlerList> o implementar su propia colección.  La clase de colección debe proporcionar métodos para establecer, obtener acceso y recuperar el delegado del controlador de eventos basándose en la clave del evento.  Por ejemplo, se puede utilizar una clase <xref:System.Collections.Hashtable> o derivar una clase personalizada a partir de la clase <xref:System.Collections.DictionaryBase>.  No es necesario exponer los detalles de implementación de la colección de delegados fuera de la clase.  
  
 Cada una de las propiedades de evento de la clase define un método de descriptor de acceso add y un método de descriptor de acceso remove.  El descriptor de acceso add de una propiedad de evento agrega la instancia de delegado de entrada a la colección de delegados.  El descriptor de acceso remove de una propiedad de evento quita la instancia de delegado de entrada de la colección de delegados.  Los descriptores de acceso de las propiedades de eventos utilizan la clave predefinida de la propiedad de evento para agregar y quitar instancias en la colección de delegados.  
  
### Para controlar varios eventos mediante las propiedades de evento  
  
1.  Defina una colección de delegados dentro de la clase que provoca los eventos.  
  
2.  Defina una clave para cada evento.  
  
3.  Defina las propiedades de evento de la clase que provoca los eventos.  
  
4.  Utilice la colección de delegados para implementar los métodos de descriptor de acceso add y remove de las propiedades de evento.  
  
5.  Utilice las propiedades de evento públicas para agregar y quitar delegados de controlador de eventos en las clases que controlan los eventos.  
  
## Ejemplo  
 En el siguiente ejemplo de C\#, se implementan las propiedades de evento `MouseDown` y `MouseUp` mediante el uso de <xref:System.ComponentModel.EventHandlerList> para almacenar el delegado de cada evento.  Las palabras clave de las construcciones de propiedades de evento están en negrita.  
  
> [!NOTE]
>  Estas propiedades no se admiten en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)].  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## Vea también  
 <xref:System.ComponentModel.EventHandlerList?displayProperty=fullName>   
 [Eventos](../../../docs/standard/events/index.md)   
 [System.Web.UI.Control.Events](frlrfSystemWebUIControlClassEventsTopic)   
 [Cómo: Declarar eventos personalizados para conservar memoria](../Topic/How%20to:%20Declare%20Custom%20Events%20To%20Conserve%20Memory%20\(Visual%20Basic\).md)