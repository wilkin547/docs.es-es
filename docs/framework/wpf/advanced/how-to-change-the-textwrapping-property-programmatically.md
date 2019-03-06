---
title: Filtrar Cambiar la propiedad TextWrapping mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 70dc73fe16ebb98e466c4363e5ac26562329dcd4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362271"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a>Filtrar Cambiar la propiedad TextWrapping mediante programación
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo cambiar el valor de la <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> propiedad mediante programación.  
  
 Tres <xref:System.Windows.Controls.Button> elementos se colocan dentro de un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Cada <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos para un <xref:System.Windows.Controls.Button> se corresponde con un controlador de eventos en el código. Los controladores de eventos usan el mismo nombre que el <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> valor también se aplicarán en `txt2` cuando se hace clic en el botón. Además, el texto en `txt1` (un <xref:System.Windows.Controls.TextBlock> no se muestra en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) se actualiza para reflejar el cambio en la propiedad.  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
