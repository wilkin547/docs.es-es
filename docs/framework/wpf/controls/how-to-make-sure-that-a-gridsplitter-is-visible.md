---
title: "Cómo: Asegurarse de que un GridSplitter es visible"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b7587a093b2b43856a05693bb785a0465211782
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Cómo: Asegurarse de que un GridSplitter es visible
Este ejemplo muestra cómo asegurarse de que un <xref:System.Windows.Controls.GridSplitter> control no está oculto por los otros controles en un <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.Panel.Children%2A> de un <xref:System.Windows.Controls.Grid> control se representan en el orden en que se definen en el marcado o código. <xref:System.Windows.Controls.GridSplitter>se pueden ocultar controles por otros controles si no se define como los últimos elementos en el <xref:System.Windows.Controls.Panel.Children%2A> colección o si se otorga otro controla un mayor <xref:System.Windows.Controls.Panel.ZIndexProperty>.  
  
 Para evitar que oculta <xref:System.Windows.Controls.GridSplitter> controles, realice una de las acciones siguientes.  
  
-   Asegúrese de que <xref:System.Windows.Controls.GridSplitter> controles son las últimas <xref:System.Windows.Controls.Panel.Children%2A> agregado a la <xref:System.Windows.Controls.Grid>. El siguiente ejemplo se muestra la <xref:System.Windows.Controls.GridSplitter> como el último elemento en el <xref:System.Windows.Controls.Panel.Children%2A> colección de la <xref:System.Windows.Controls.Grid>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   Establecer el <xref:System.Windows.Controls.Panel.ZIndexProperty> en el <xref:System.Windows.Controls.GridSplitter> es mayor que un control que podría ocultarlo. En el ejemplo siguiente se proporciona el <xref:System.Windows.Controls.GridSplitter> controlar una mayor <xref:System.Windows.Controls.Panel.ZIndexProperty> que el <xref:System.Windows.Controls.Button> control.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   Establecer los márgenes del control que podría ocultar el <xref:System.Windows.Controls.GridSplitter> para que la <xref:System.Windows.Controls.GridSplitter> se expone. El ejemplo siguiente establece los márgenes de un control que podría superponerse y ocultar el <xref:System.Windows.Controls.GridSplitter>.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.GridSplitter>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
