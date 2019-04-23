---
title: Procedimiento Animar un control Popup
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150116"
---
# <a name="how-to-animate-a-popup"></a>Procedimiento Animar un control Popup
En este ejemplo se muestra dos maneras de animar una <xref:System.Windows.Controls.Primitives.Popup> control.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se establece la <xref:System.Windows.Controls.Primitives.PopupAnimation> propiedad con un valor de <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, lo que hace que el <xref:System.Windows.Controls.Primitives.Popup> a "diapositiva en" cuando aparezca.  
  
 Para girar el <xref:System.Windows.Controls.Primitives.Popup>, este ejemplo se asigna un <xref:System.Windows.Media.RotateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad en el <xref:System.Windows.Controls.Canvas>, que es el elemento secundario de la <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Para que la transformación funcione correctamente, debe establecer en el ejemplo el <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> propiedad `true`. Además, el <xref:System.Windows.FrameworkElement.Margin%2A> en el <xref:System.Windows.Controls.Canvas> contenido debe especificar el espacio suficiente para el <xref:System.Windows.Controls.Primitives.Popup> se va a girar.  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 El ejemplo siguiente se muestra cómo un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento, que se produce cuando un <xref:System.Windows.Controls.Button> se hace clic en, los desencadenadores del <xref:System.Windows.Media.Animation.Storyboard> que comienza la animación.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [Temas "Cómo..."](popup-how-to-topics.md)
- [Información general sobre el control Popup](popup-overview.md)
