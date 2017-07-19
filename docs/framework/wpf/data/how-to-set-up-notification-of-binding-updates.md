---
title: "C&#243;mo: Configurar la notificaci&#243;n de actualizaciones de enlaces | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enlace, actualizaciones, notificaciones de"
  - "enlace de datos, notificación de actualizaciones de enlaces"
  - "notificaciones, actualizaciones de enlaces"
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Configurar la notificaci&#243;n de actualizaciones de enlaces
En este ejemplo se muestra cómo establecer que se le notifique cuando se actualice la propiedad de [destino de enlace](GTMT) \(destino\) o de [origen de enlace](GTMT) \(origen\) de un enlace.  
  
## Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] genera un evento de actualización de datos cada vez que se actualiza el origen o el destino de enlace.  Internamente, este evento se utiliza para informar a la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] de que debe actualizarse, porque los datos de enlace han cambiado.  Tenga en cuenta que, para que estos eventos y el enlace uni o bidireccional funcionen correctamente, es preciso implementar la clase de datos mediante la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.  Para obtener más información, consulte [Implementar la notificación de cambio de propiedad](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Establezca la propiedad <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> o <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> \(o ambas\) en `true` en el enlace.  El controlador que se proporciona para realizar escuchas a fin de detectar este evento debe estar asociado directamente al elemento sobre cuyos cambios desea ser informado, o al contexto de datos global si desea tener conocimiento de cualquier cambio en el contexto.  
  
 A continuación figura un ejemplo que muestra cómo configurar la notificación cuando se actualiza una propiedad de destino.  
  
 [!code-xml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 A continuación, puede asignar un controlador basado en el delegado EventHandler\<T\>, *OnTargetUpdated* en este ejemplo, para controlar el evento:  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 Se pueden utilizar parámetros del evento para determinar los sobre la propiedad que ha cambiado \(como el tipo o el elemento concreto, si el mismo controlador está asociado a más de un elemento\); esto puede resultar útil si hay varias propiedades enlazadas al mismo elemento.  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)