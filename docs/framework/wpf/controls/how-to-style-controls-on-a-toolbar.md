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
# <a name="how-to-style-controls-on-a-toolbar"></a><span data-ttu-id="78228-102">Filtrar Aplicar estilo a controles en un elemento ToolBar</span><span class="sxs-lookup"><span data-stu-id="78228-102">How to: Style Controls on a ToolBar</span></span>
<span data-ttu-id="78228-103">El <xref:System.Windows.Controls.ToolBar> define <xref:System.Windows.ResourceKey> objetos para especificar el estilo de los controles dentro de la <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="78228-103">The <xref:System.Windows.Controls.ToolBar> defines <xref:System.Windows.ResourceKey> objects to specify the style of controls within the <xref:System.Windows.Controls.ToolBar>.</span></span>  <span data-ttu-id="78228-104">Para aplicar estilo a un control en un <xref:System.Windows.Controls.ToolBar>, establezca el `x:key` atributo del estilo a un <xref:System.Windows.ResourceKey> definido en <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="78228-104">To style a control in a <xref:System.Windows.Controls.ToolBar>, set the `x:key` attribute of the style to a <xref:System.Windows.ResourceKey> defined in <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 <span data-ttu-id="78228-105">El <xref:System.Windows.Controls.ToolBar> define los siguientes elementos <xref:System.Windows.ResourceKey> objetos:</span><span class="sxs-lookup"><span data-stu-id="78228-105">The <xref:System.Windows.Controls.ToolBar> defines the following <xref:System.Windows.ResourceKey> objects:</span></span>  
  
-   <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
-   <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a><span data-ttu-id="78228-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78228-106">Example</span></span>  
 <span data-ttu-id="78228-107">En el ejemplo siguiente se define estilos para los controles dentro de un <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="78228-107">The following example defines styles for the controls within a <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a><span data-ttu-id="78228-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="78228-108">See also</span></span>

- [<span data-ttu-id="78228-109">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="78228-109">Styling and Templating</span></span>](styling-and-templating.md)
