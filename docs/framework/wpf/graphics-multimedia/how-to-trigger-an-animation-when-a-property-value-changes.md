---
title: "C&#243;mo: Activar una animaci&#243;n al cambiar el valor de una propiedad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "animación, iniciar cuando cambian los valores de propiedad"
  - "Guiones gráficos, iniciar cuando cambian los valores de propiedad"
  - "desencadenar animación"
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Activar una animaci&#243;n al cambiar el valor de una propiedad
En este ejemplo se muestra cómo utilizar un objeto <xref:System.Windows.Trigger> para iniciar un objeto <xref:System.Windows.Media.Animation.Storyboard> cuando cambia un valor de propiedad.  Puede utilizar <xref:System.Windows.Trigger> dentro de <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.DataTemplate>.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza un objeto <xref:System.Windows.Trigger> para animar la propiedad <xref:System.Windows.UIElement.Opacity%2A> de un control <xref:System.Windows.Controls.Button> cuando el valor de su propiedad <xref:System.Windows.UIElement.IsMouseOver%2A> pasa a ser `true`.  
  
 [!code-xml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 Las animaciones aplicadas por objetos <xref:System.Windows.Trigger> de propiedad se comportan de un modo más complejo que las animaciones de <xref:System.Windows.EventTrigger> o que aquéllas que se inician mediante métodos de <xref:System.Windows.Media.Animation.Storyboard>.  Se "continúan" con animaciones definidas por otros objetos <xref:System.Windows.Trigger>, pero se crean con <xref:System.Windows.EventTrigger> y animaciones activadas por métodos.  
  
## Vea también  
 <xref:System.Windows.Trigger>   
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)