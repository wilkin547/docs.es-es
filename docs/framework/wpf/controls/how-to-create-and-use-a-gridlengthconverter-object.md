---
title: Filtrar Crear y usar un objeto GridLengthConverter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], creating [WPF], GridLengthConverter objects
ms.assetid: 5ab75911-e36a-4825-80e4-081c57e8e182
ms.openlocfilehash: 498d2b9c531f391f4cbeb1478469a99d381deec7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206790"
---
# <a name="how-to-create-and-use-a-gridlengthconverter-object"></a>Filtrar Crear y usar un objeto GridLengthConverter
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo crear y usar una instancia de <xref:System.Windows.GridLengthConverter>. El ejemplo define un método personalizado llamado `changeCol`, que pasan el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.GridLengthConverter> que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.GridLength>. El valor convertido, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.ColumnDefinition.Width%2A> propiedad de la <xref:System.Windows.Controls.ColumnDefinition> elemento.  
  
 El ejemplo también define un segundo método personalizado, denominado `changeColVal`. Convierte este método personalizado la <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> de un <xref:System.Windows.Controls.Slider> a un <xref:System.String> y, a continuación, pasa ese valor a la <xref:System.Windows.Controls.ColumnDefinition> como el <xref:System.Windows.Controls.ColumnDefinition.Width%2A> del elemento.  
  
 Tenga en cuenta que otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo define el contenido de un <xref:System.Windows.Controls.ListBoxItem>.  
  
 [!code-csharp[gridlengthConverterGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridlengthConverterGrid/CSharp/Window1.xaml.cs#1)]
 [!code-vb[gridlengthConverterGrid#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridlengthConverterGrid/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.GridLengthConverter>
- <xref:System.Windows.GridLength>
