---
title: Procedimiento Crear controles ListViewItems con un control CheckBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: b09d5ad11b0961febf524cec1e19cb1e59832e44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083112"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="e005c-102">Procedimiento Crear controles ListViewItems con un control CheckBox</span><span class="sxs-lookup"><span data-stu-id="e005c-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="e005c-103">En este ejemplo se muestra cómo mostrar una columna de <xref:System.Windows.Controls.CheckBox> controles en un <xref:System.Windows.Controls.ListView> control que utiliza un <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="e005c-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e005c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e005c-104">Example</span></span>  
 <span data-ttu-id="e005c-105">Para crear una columna que contiene <xref:System.Windows.Controls.CheckBox> controles en un <xref:System.Windows.Controls.ListView>, cree un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="e005c-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="e005c-106">A continuación, establezca el <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> de un <xref:System.Windows.Controls.GridViewColumn> a la <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="e005c-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="e005c-107">El ejemplo siguiente se muestra un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="e005c-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="e005c-108">El ejemplo se enlaza el <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> propiedad de la <xref:System.Windows.Controls.CheckBox> a la <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> valor de propiedad de la <xref:System.Windows.Controls.ListViewItem> que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="e005c-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="e005c-109">Por lo tanto, cuando el <xref:System.Windows.Controls.ListViewItem> que contiene el <xref:System.Windows.Controls.CheckBox> está activada, el <xref:System.Windows.Controls.CheckBox> está activada.</span><span class="sxs-lookup"><span data-stu-id="e005c-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="e005c-110">El ejemplo siguiente muestra cómo crear una columna de <xref:System.Windows.Controls.CheckBox> controles.</span><span class="sxs-lookup"><span data-stu-id="e005c-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="e005c-111">Convertir la columna, el ejemplo establece la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> propiedad de la <xref:System.Windows.Controls.GridViewColumn> a la <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="e005c-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="e005c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e005c-112">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="e005c-113">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="e005c-113">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="e005c-114">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e005c-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="e005c-115">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="e005c-115">GridView Overview</span></span>](gridview-overview.md)
