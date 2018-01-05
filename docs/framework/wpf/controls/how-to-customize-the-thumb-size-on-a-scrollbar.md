---
title: "Cómo: Personalizar el tamaño de un control de posición en un objeto ScrollBar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e88a7afb9c98179fbcb4a67217edd411d4fe9567
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a>Cómo: Personalizar el tamaño de un control de posición en un objeto ScrollBar
Este tema explica cómo establecer el <xref:System.Windows.Controls.Primitives.Thumb> de un <xref:System.Windows.Controls.Primitives.ScrollBar> a un tamaño fijo y cómo especificar un tamaño mínimo para el <xref:System.Windows.Controls.Primitives.Thumb> de un <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="description"></a>Descripción  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Primitives.ScrollBar> que tiene un <xref:System.Windows.Controls.Primitives.Thumb> con un tamaño fijo. El ejemplo se establece la <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> propiedad de la <xref:System.Windows.Controls.Primitives.Thumb> a <xref:System.Double.NaN> y establece el alto de la <xref:System.Windows.Controls.Primitives.Thumb>.  Para crear una horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> que tiene un ancho fijo, establezca el ancho de la <xref:System.Windows.Controls.Primitives.Thumb>.  
  
## <a name="code"></a>Código  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a>Descripción  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Primitives.ScrollBar> que tiene un <xref:System.Windows.Controls.Primitives.Thumb> con un tamaño mínimo. En el ejemplo se establece el valor de <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>. Para crear una horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> con un <xref:System.Windows.Controls.Primitives.Thumb> que tiene un ancho mínimo, establezca el <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.  
  
## <a name="code"></a>Código  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a>Vea también  
 [ScrollBar Styles and Templates](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md) (Estilos y plantillas de ScrollBar)
