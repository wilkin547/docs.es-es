---
title: 'Cómo: Utilizar un objeto ThicknessConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 6c8f9e83468a7b189b96efca2e175c0f3fe0dfff
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43735428"
---
# <a name="how-to-use-a-thicknessconverter-object"></a>Cómo: Utilizar un objeto ThicknessConverter
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra cómo crear una instancia de <xref:System.Windows.ThicknessConverter> y usarlo para cambiar el grosor del borde.  
  
 El ejemplo define un método personalizado llamado `changeThickness`; en primer lugar, este método convierte el contenido de un <xref:System.Windows.Controls.ListBoxItem>, tal como se define en otro [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo a una instancia de <xref:System.Windows.Thickness>y posteriormente convierte el contenido en un <xref:System.String>. Este método pasa el <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.ThicknessConverter> objeto, que convierte el <xref:System.Windows.Controls.ContentControl.Content%2A> de un <xref:System.Windows.Controls.ListBoxItem> a una instancia de <xref:System.Windows.Thickness>. Este valor, a continuación, se pasa como el valor de la <xref:System.Windows.Controls.Border.BorderThickness%2A> propiedad de la <xref:System.Windows.Controls.Border>.  
  
 En este ejemplo no se ejecuta.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Thickness>  
 <xref:System.Windows.ThicknessConverter>  
 <xref:System.Windows.Controls.Border>  
 [Cómo: cambiar la propiedad Margin](https://msdn.microsoft.com/library/8a313efd-5f99-4097-b4c1-8fa49d8379a2)  
 [Cómo: convertir un elemento ListBoxItem en un nuevo tipo de datos](https://msdn.microsoft.com/library/7a080b88-184e-4b27-bb61-d42bafba9727)  
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
