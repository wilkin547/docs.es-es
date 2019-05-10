---
title: Procedimiento Aplicar una transformación a un elemento cuando se produce un evento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
ms.openlocfilehash: 8f04db274432c0e89c6839bef825976c8a2f853c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630751"
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>Procedimiento Aplicar una transformación a un elemento cuando se produce un evento
En este ejemplo se muestra cómo aplicar un <xref:System.Windows.Media.ScaleTransform> cuando se produce un evento. El concepto que se muestra aquí es el mismo que se utiliza para aplicar otros tipos de transformaciones. Para obtener más información acerca de los tipos de transformaciones disponibles, consulte el <xref:System.Windows.Media.Transform> clase o [información general sobre transformaciones](transforms-overview.md).  
  
 Puede aplicar una transformación a un elemento de cualquiera de estas dos maneras:  
  
- Si lo hace *no* desea que la transformación afecte al diseño, utilice el <xref:System.Windows.UIElement.RenderTransform%2A> propiedad del elemento.  
  
- Si desea que la transformación afecte al diseño, utilice el <xref:System.Windows.FrameworkElement.LayoutTransform%2A> propiedad del elemento.  
  
 El ejemplo siguiente aplica un <xref:System.Windows.Media.ScaleTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad de un botón. Cuando se mueve el mouse sobre el botón, el <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> propiedades de la <xref:System.Windows.Media.ScaleTransform> se establecen en `2`, lo que hace que el botón se agrande. Cuando el mouse se aleja del botón, <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> y <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> se establecen en `1`, lo que hace que el botón para volver a su tamaño original.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[ButtonTransform#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](~/samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [Información general sobre transformaciones](transforms-overview.md)
- [Temas "Cómo..."](transformations-how-to-topics.md)
- [Información general sobre eventos enrutados](../advanced/routed-events-overview.md)
