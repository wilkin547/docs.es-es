---
title: "C&#243;mo: Animar un control Popup | Microsoft Docs"
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
  - "animación, Popup (controles)"
  - "Popup (control), animar"
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Animar un control Popup
En este ejemplo se muestran dos maneras de animar un control <xref:System.Windows.Controls.Primitives.Popup>.  
  
## Ejemplo  
 En el ejemplo siguiente se establece la propiedad <xref:System.Windows.Controls.Primitives.PopupAnimation> en un valor de <xref:System.Windows.Controls.Primitives.PopupAnimation>, lo que hace que el control <xref:System.Windows.Controls.Primitives.Popup> se "deslice" al aparecer.  
  
 Para girar <xref:System.Windows.Controls.Primitives.Popup>, en este ejemplo se asigna una transformación <xref:System.Windows.Media.RotateTransform> a la propiedad <xref:System.Windows.UIElement.RenderTransform%2A> de <xref:System.Windows.Controls.Canvas>, que es el elemento secundario de <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Para que la transformación funcione correctamente, en el ejemplo se debe establecer la propiedad <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> en `true`.  Además, la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> del contenido de <xref:System.Windows.Controls.Canvas> debe especificar espacio suficiente para que <xref:System.Windows.Controls.Primitives.Popup> gire.  
  
 [!code-xml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 En el ejemplo siguiente se muestra el modo en que un evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, que se provoca al hacer clic en <xref:System.Windows.Controls.Button>, activa el objeto <xref:System.Windows.Media.Animation.Storyboard> que inicia la animación.  
  
 [!code-xml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## Vea también  
 <xref:System.Windows.UIElement.RenderTransform%2A>   
 <xref:System.Windows.Controls.Primitives.BulletDecorator>   
 <xref:System.Windows.Media.RotateTransform>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 <xref:System.Windows.Controls.Primitives.Popup>   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)   
 [Información general sobre el control Popup](../../../../docs/framework/wpf/controls/popup-overview.md)