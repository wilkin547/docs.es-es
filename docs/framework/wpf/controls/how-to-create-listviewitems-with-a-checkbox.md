---
title: "Cómo: Crear controles ListViewItems con un control CheckBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6ebb3671dcc65d690fde5d4796c9034553eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a><span data-ttu-id="58984-102">Cómo: Crear controles ListViewItems con un control CheckBox</span><span class="sxs-lookup"><span data-stu-id="58984-102">How to: Create ListViewItems with a CheckBox</span></span>
<span data-ttu-id="58984-103">Este ejemplo muestra cómo mostrar una columna de <xref:System.Windows.Controls.CheckBox> controla en un <xref:System.Windows.Controls.ListView> control que usa un <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="58984-103">This example shows how to display a column of <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58984-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58984-104">Example</span></span>  
 <span data-ttu-id="58984-105">Para crear una columna que contiene <xref:System.Windows.Controls.CheckBox> controla en un <xref:System.Windows.Controls.ListView>, cree un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="58984-105">To create a column that contains <xref:System.Windows.Controls.CheckBox> controls in a <xref:System.Windows.Controls.ListView>, create a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="58984-106">A continuación, establezca el <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> de un <xref:System.Windows.Controls.GridViewColumn> a la <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="58984-106">Then set the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> of a <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 <span data-ttu-id="58984-107">El ejemplo siguiente muestra un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="58984-107">The following example shows a <xref:System.Windows.DataTemplate> that contains a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="58984-108">El ejemplo se enlaza la <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> propiedad de la <xref:System.Windows.Controls.CheckBox> a la <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> valor de propiedad de la <xref:System.Windows.Controls.ListViewItem> que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="58984-108">The example binds the <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> property of the <xref:System.Windows.Controls.CheckBox> to the <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> property value of the <xref:System.Windows.Controls.ListViewItem> that contains it.</span></span> <span data-ttu-id="58984-109">Por lo tanto, cuando la <xref:System.Windows.Controls.ListViewItem> que contiene el <xref:System.Windows.Controls.CheckBox> está seleccionada, la <xref:System.Windows.Controls.CheckBox> está activada.</span><span class="sxs-lookup"><span data-stu-id="58984-109">Therefore, when the <xref:System.Windows.Controls.ListViewItem> that contains the <xref:System.Windows.Controls.CheckBox> is selected, the <xref:System.Windows.Controls.CheckBox> is checked.</span></span>  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 <span data-ttu-id="58984-110">En el ejemplo siguiente se muestra cómo crear una columna de <xref:System.Windows.Controls.CheckBox> controles.</span><span class="sxs-lookup"><span data-stu-id="58984-110">The following example shows how to create a column of <xref:System.Windows.Controls.CheckBox> controls.</span></span> <span data-ttu-id="58984-111">Convertir la columna, el ejemplo establece la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> propiedad de la <xref:System.Windows.Controls.GridViewColumn> a la <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="58984-111">To make the column, the example sets the <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> property of the <xref:System.Windows.Controls.GridViewColumn> to the <xref:System.Windows.DataTemplate>.</span></span>  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a><span data-ttu-id="58984-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="58984-112">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="58984-113">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="58984-113">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="58984-114">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="58984-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="58984-115">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="58984-115">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
