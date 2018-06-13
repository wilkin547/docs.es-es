---
title: 'Cómo: Definir márgenes de elementos y controles'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: 41a0f1d025061cc7c1472a831fbbd5ed2f01b043
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543655"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a>Cómo: Definir márgenes de elementos y controles
En este ejemplo se describe cómo establecer el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad, al cambiar cualquier valor de propiedad existente para el margen en el código subyacente. El <xref:System.Windows.FrameworkElement.Margin%2A> propiedad es una propiedad de la <xref:System.Windows.FrameworkElement> basar el elemento y, por tanto, es heredada por una variedad de controles y otros elementos.  
  
 Este ejemplo está escrito en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], con un código subyacente de los archivos que el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hace referencia a. Se muestra el código subyacente en C# y una versión de Microsoft Visual Basic.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
