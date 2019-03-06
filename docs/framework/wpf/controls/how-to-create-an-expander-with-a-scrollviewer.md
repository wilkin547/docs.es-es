---
title: Filtrar Crear un control Expander con un control ScrollViewer
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 9e7c023ec371dd6695ffba3368502e5b593c4608
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369544"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>Procedimiento Crear un control Expander con un control ScrollViewer
En este ejemplo se muestra cómo crear un <xref:System.Windows.Controls.Expander> control que contiene contenido complejo, como una imagen y texto. El ejemplo también incluye el contenido de la <xref:System.Windows.Controls.Expander> en un <xref:System.Windows.Controls.ScrollViewer> control.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.Expander>. El ejemplo se usa un <xref:System.Windows.Controls.Primitives.BulletDecorator> control, que contiene una imagen y texto, con el fin de definir el <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>. Un <xref:System.Windows.Controls.ScrollViewer> control proporciona un método para desplazar el contenido expandido.  
  
 Tenga en cuenta que el ejemplo establece la <xref:System.Windows.FrameworkElement.Height%2A> propiedad en el <xref:System.Windows.Controls.ScrollViewer> en lugar de en el contenido. Si el <xref:System.Windows.FrameworkElement.Height%2A> se establece en el contenido, el <xref:System.Windows.Controls.ScrollViewer> no permite al usuario desplazar el contenido. El <xref:System.Windows.FrameworkElement.Width%2A> propiedad está establecida en el <xref:System.Windows.Controls.Expander> control y esta configuración se aplica a la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> y el contenido expandido.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.Expander>
- [Información general sobre el control Expander](expander-overview.md)
- [Temas "Cómo..."](expander-how-to-topics.md)
