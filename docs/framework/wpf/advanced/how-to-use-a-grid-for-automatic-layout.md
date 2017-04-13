---
title: "C&#243;mo: Usar una cuadr&#237;cula para el dise&#241;o autom&#225;tico | Microsoft Docs"
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
  - "diseño automático, uso de cuadrículas"
  - "cuadrículas, diseño automático"
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Usar una cuadr&#237;cula para el dise&#241;o autom&#225;tico
En este ejemplo se describe cómo utilizar una cuadrícula en el enfoque de diseño automático de la creación de una aplicación localizable.  
  
 La localización de una [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] puede ser un proceso que exija mucho tiempo.  A menudo los localizadores se ven obligados a ajustar el tamaño y la posición de los elementos, además de traducir el texto.  En el pasado, era preciso ajustar cada idioma al que se adaptaba una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Ahora, gracias a las funciones de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], es posible diseñar elementos que reducen la necesidad de ajuste.  El enfoque de escribir aplicaciones cuyo tamaño y posición se ajusta con mayor facilidad se denomina `auto layout`.  
  
 En el ejemplo de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] siguiente se muestra cómo utilizar una cuadrícula para colocar algunos botones y texto.  Observe que el alto y ancho de las celdas están establecidos en `Auto`; por consiguiente, la celda que contiene el botón con una imagen se ajusta a la imagen.  Dado que el elemento <xref:System.Windows.Controls.Grid> se puede ajustar a su contenido, puede resultar útil para aplicar el enfoque de diseño automático al diseño de aplicaciones localizables.  
  
## Ejemplo  
 En el ejemplo anterior se muestra cómo utilizar una cuadrícula.  
  
 [!code-xml[LocalizationGrid#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 En el gráfico siguiente se muestra el resultado del ejemplo de código.  
  
 ![Ejemplo de cuadrícula](../../../../docs/framework/wpf/advanced/media/glob-grid.png "glob\_grid")  
Cuadrícula  
  
## Vea también  
 [Información general sobre el uso del diseño automático](../../../../docs/framework/wpf/advanced/use-automatic-layout-overview.md)   
 [Usar el diseño automático para crear un botón](../../../../docs/framework/wpf/advanced/how-to-use-automatic-layout-to-create-a-button.md)