---
title: "Cómo: Utilizar desencadenadores para aplicar un estilo a los elementos seleccionados en un control ListView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f8965ee524d6a5cb03a54ac07d8889ff9801440
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>Cómo: Utilizar desencadenadores para aplicar un estilo a los elementos seleccionados en un control ListView
Este ejemplo muestra cómo definir <xref:System.Windows.Style.Triggers%2A> para un <xref:System.Windows.Controls.ListViewItem> control para que cuando el valor de una propiedad de un <xref:System.Windows.Controls.ListViewItem> cambios, el <xref:System.Windows.Style> de la <xref:System.Windows.Controls.ListViewItem> cambia en respuesta.  
  
## <a name="example"></a>Ejemplo  
 Si desea que la <xref:System.Windows.Style> de un <xref:System.Windows.Controls.ListViewItem> para cambiar en respuesta a los cambios de propiedad, defina <xref:System.Windows.Style.Triggers%2A> para el <xref:System.Windows.Style> cambiar.  
  
 En el ejemplo siguiente se define un <xref:System.Windows.Trigger> que establece el <xref:System.Windows.Controls.Control.Foreground%2A> propiedad <xref:System.Windows.Media.Brushes.Blue%2A> y cambia el <xref:System.Windows.FrameworkElement.Cursor%2A> para mostrar una <xref:System.Windows.Input.CursorType.Hand> cuando el <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad cambia a `true`.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 En el ejemplo siguiente se define un <xref:System.Windows.MultiTrigger> que establece el <xref:System.Windows.Controls.Control.Foreground%2A> propiedad de un <xref:System.Windows.Controls.ListViewItem> a <xref:System.Windows.Media.Brushes.Yellow%2A> cuando el <xref:System.Windows.Controls.ListViewItem> es el elemento seleccionado y tiene el foco de teclado.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
