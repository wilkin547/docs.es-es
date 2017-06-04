---
title: "C&#243;mo: Usar el dise&#241;o autom&#225;tico para crear un bot&#243;n | Microsoft Docs"
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
  - "diseño automático, crear botones"
  - "Button (controles), crear con diseño automático"
  - "crear, botones con diseño automático"
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Usar el dise&#241;o autom&#225;tico para crear un bot&#243;n
En este ejemplo se describe cómo utilizar el enfoque de diseño automático para crear un botón en una aplicación localizable.  
  
 La localización de una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso que exija mucho tiempo.  A menudo los localizadores se ven obligados a ajustar el tamaño y la posición de los elementos, además de traducir el texto.  En el pasado, era preciso ajustar cada idioma al que se adaptaba una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Ahora, gracias a las funciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], es posible diseñar elementos que reducen la necesidad de ajuste.  El enfoque de escribir aplicaciones cuyo tamaño y posición se ajusta con mayor facilidad se denomina `automatic layout`.  
  
 En los dos ejemplos de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguientes se crean aplicaciones que crean instancias de un botón; uno con el texto en inglés y uno con el texto en español.  Observe que el código es el mismo salvo el texto; el botón se ajusta al texto.  
  
## Ejemplo  
 [!code-xml[LocalizationBtn_snip#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 [!code-xml[LocalizationBtn#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 En el gráfico siguiente se muestra el resultado de los ejemplos de código.  
  
 ![El mismo botón con texto en diferentes idiomas](../../../../docs/framework/wpf/advanced/media/globalizationbutton.png "GlobalizationButton")  
Botón cuyo tamaño se ajusta automáticamente  
  
## Vea también  
 [Información general sobre el uso del diseño automático](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Usar una cuadrícula para el diseño automático](../../../../docs/framework/wpf/advanced/how-to-use-a-grid-for-automatic-layout.md)