---
title: "Cómo: Definir márgenes de elementos y controles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49bc3ac8c57e95e597d6b9aa505a931a6204b3f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-margins-of-elements-and-controls"></a>Cómo: Definir márgenes de elementos y controles
En este ejemplo se describe cómo establecer el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad, al cambiar cualquier valor de propiedad existente para el margen en el código subyacente. El <xref:System.Windows.FrameworkElement.Margin%2A> propiedad es una propiedad de la <xref:System.Windows.FrameworkElement> basar el elemento y, por tanto, es heredada por una variedad de controles y otros elementos.  
  
 Este ejemplo está escrito en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], con un código subyacente de los archivos que el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hace referencia a. El código subyacente se muestra tanto en un [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] y un [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] versión.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
