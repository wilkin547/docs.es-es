---
title: Filtrar Aplicar estilo a controles en un elemento ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 580b56ebb47aa7bd50da0a966ccf60f7ea9fb2a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217788"
---
# <a name="how-to-style-controls-on-a-toolbar"></a>Filtrar Aplicar estilo a controles en un elemento ToolBar
El <xref:System.Windows.Controls.ToolBar> define <xref:System.Windows.ResourceKey> objetos para especificar el estilo de los controles dentro de la <xref:System.Windows.Controls.ToolBar>.  Para aplicar estilo a un control en un <xref:System.Windows.Controls.ToolBar>, establezca el `x:key` atributo del estilo a un <xref:System.Windows.ResourceKey> definido en <xref:System.Windows.Controls.ToolBar>.  
  
 El <xref:System.Windows.Controls.ToolBar> define los siguientes elementos <xref:System.Windows.ResourceKey> objetos:  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define estilos para los controles dentro de un <xref:System.Windows.Controls.ToolBar>.  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a>Vea también

- [Aplicar estilos y plantillas](styling-and-templating.md)
