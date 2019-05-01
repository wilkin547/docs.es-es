---
title: Procedimiento Usar la clase FontSizeConverter
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: f33a297ae07d5509d2b4d9a98636086ac433a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051044"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>Procedimiento Usar la clase FontSizeConverter
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo crear una instancia de <xref:System.Windows.FontSizeConverter> y usarlo para cambiar el tamaño de fuente.  
  
 El ejemplo define un método personalizado llamado `changeSize` que convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Double>y versiones posteriores en un <xref:System.String>. Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.FontSizeConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Double>. Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.TextBlock.FontSize%2A> propiedad de la <xref:System.Windows.Controls.TextBlock> elemento.  
  
 En este ejemplo también define un segundo método personalizado que se denomina `changeFamily`. Este método convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de la <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.String>y, a continuación, pasa ese valor a la <xref:System.Windows.Controls.TextBlock.FontFamily%2A> propiedad de la <xref:System.Windows.Controls.TextBlock> elemento.  
  
 En este ejemplo no se ejecuta.  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FontSizeConverter>
