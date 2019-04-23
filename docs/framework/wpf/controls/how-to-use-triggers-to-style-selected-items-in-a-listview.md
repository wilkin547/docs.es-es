---
title: Procedimiento Usar desencadenadores para aplicar un estilo a los elementos seleccionados en un control ListView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: ad64382b871bae9114a1e63257de3f8595376923
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145410"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="4c51d-102">Procedimiento Usar desencadenadores para aplicar un estilo a los elementos seleccionados en un control ListView</span><span class="sxs-lookup"><span data-stu-id="4c51d-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="4c51d-103">En este ejemplo se muestra cómo definir <xref:System.Windows.Style.Triggers%2A> para un <xref:System.Windows.Controls.ListViewItem> control para que cuando un valor de propiedad de un <xref:System.Windows.Controls.ListViewItem> cambios, el <xref:System.Windows.Style> de la <xref:System.Windows.Controls.ListViewItem> cambia en respuesta.</span><span class="sxs-lookup"><span data-stu-id="4c51d-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c51d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c51d-104">Example</span></span>  
 <span data-ttu-id="4c51d-105">Si desea que el <xref:System.Windows.Style> de un <xref:System.Windows.Controls.ListViewItem> para cambian en respuesta a los cambios de propiedades, definir <xref:System.Windows.Style.Triggers%2A> para el <xref:System.Windows.Style> cambiar.</span><span class="sxs-lookup"><span data-stu-id="4c51d-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="4c51d-106">En el ejemplo siguiente se define un <xref:System.Windows.Trigger> que establece el <xref:System.Windows.Controls.Control.Foreground%2A> propiedad <xref:System.Windows.Media.Brushes.Blue%2A> y cambia el <xref:System.Windows.FrameworkElement.Cursor%2A> para mostrar un <xref:System.Windows.Input.CursorType.Hand> cuando el <xref:System.Windows.UIElement.IsMouseOver%2A> propiedad cambia a `true`.</span><span class="sxs-lookup"><span data-stu-id="4c51d-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="4c51d-107">En el ejemplo siguiente se define un <xref:System.Windows.MultiTrigger> que establece el <xref:System.Windows.Controls.Control.Foreground%2A> propiedad de un <xref:System.Windows.Controls.ListViewItem> a <xref:System.Windows.Media.Brushes.Yellow%2A> cuando el <xref:System.Windows.Controls.ListViewItem> es el elemento seleccionado y tiene el foco de teclado.</span><span class="sxs-lookup"><span data-stu-id="4c51d-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="4c51d-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c51d-108">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="4c51d-109">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="4c51d-109">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="4c51d-110">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="4c51d-110">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="4c51d-111">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="4c51d-111">GridView Overview</span></span>](gridview-overview.md)
