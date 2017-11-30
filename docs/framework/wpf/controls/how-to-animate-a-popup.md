---
title: "Cómo: Animar un control Popup"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 276c1a54cfdddcde84c0702f4e84f1dc6174bbda
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-popup"></a>Cómo: Animar un control Popup
Este ejemplo muestra dos maneras de animar un <xref:System.Windows.Controls.Primitives.Popup> control.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se establece la <xref:System.Windows.Controls.Primitives.PopupAnimation> en un valor de <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, lo que hace que la <xref:System.Windows.Controls.Primitives.Popup> en "presentación" cuando aparezca.  
  
 Para girar el <xref:System.Windows.Controls.Primitives.Popup>, este ejemplo se asigna un <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad en el <xref:System.Windows.Controls.Canvas>, que es el elemento secundario de la <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Para que la transformación funcione correctamente, debe establecer en el ejemplo el <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> propiedad `true`. Además, el <xref:System.Windows.FrameworkElement.Margin%2A> en el <xref:System.Windows.Controls.Canvas> contenido debe especificar el suficiente espacio para el <xref:System.Windows.Controls.Primitives.Popup> va a girar.  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 El siguiente ejemplo se muestra cómo un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, que se produce cuando un <xref:System.Windows.Controls.Button> se hace clic, desencadenadores el <xref:System.Windows.Media.Animation.Storyboard> que comienza la animación.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Temas de procedimientos](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [Información general sobre el control Popup](../../../../docs/framework/wpf/controls/popup-overview.md)
