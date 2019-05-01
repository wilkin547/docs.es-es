---
title: Procedimiento Trasladar un elemento
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 9c1b873a89820e85efb99789f483c4832fb23cf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051447"
---
# <a name="how-to-translate-an-element"></a>Procedimiento Trasladar un elemento
En este ejemplo se muestra cómo trasladar (mover) un elemento mediante el uso de un <xref:System.Windows.Media.TranslateTransform>.  
  
 La <xref:System.Windows.Media.TranslateTransform> clase es especialmente útil para mover elementos dentro de paneles que no admiten el posicionamiento absoluto. Por ejemplo, aplicando un <xref:System.Windows.Media.TranslateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad de un elemento, puede mover un elemento dentro de un <xref:System.Windows.Controls.StackPanel> o <xref:System.Windows.Controls.DockPanel>.  
  
 Use la <xref:System.Windows.Media.TranslateTransform.X%2A> propiedad de la <xref:System.Windows.Media.TranslateTransform> para especificar la cantidad, en píxeles, que moverá el elemento a lo largo del eje x. Use el <xref:System.Windows.Media.TranslateTransform.Y%2A> propiedad para especificar la cantidad, en píxeles, que moverá el elemento a lo largo del eje y. Por último, aplique el <xref:System.Windows.Media.TranslateTransform> a la <xref:System.Windows.UIElement.RenderTransform%2A> propiedad del elemento.  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.TranslateTransform> para mover un elemento 50 píxeles a la derecho y 50 píxeles hacia abajo.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[transformsSample#53](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Para ver el ejemplo completo, consulte [Ejemplo de transformaciones 2D](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre transformaciones](transforms-overview.md)
