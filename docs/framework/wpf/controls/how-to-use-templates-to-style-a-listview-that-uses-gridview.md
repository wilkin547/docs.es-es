---
title: "Cómo: Utilizar plantillas para aplicar un estilo a un control ListView que utiliza un modo GridView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9abc19ca14cf512deff898f5f20d23870b8b7847
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a><span data-ttu-id="36143-102">Cómo: Utilizar plantillas para aplicar un estilo a un control ListView que utiliza un modo GridView</span><span class="sxs-lookup"><span data-stu-id="36143-102">How to: Use Templates to Style a ListView That Uses GridView</span></span>
<span data-ttu-id="36143-103">Este ejemplo muestra cómo utilizar el <xref:System.Windows.DataTemplate> y <xref:System.Windows.Style> objetos que se va a especificar la apariencia de un <xref:System.Windows.Controls.ListView> control que usa un <xref:System.Windows.Controls.GridView> el modo de vista.</span><span class="sxs-lookup"><span data-stu-id="36143-103">This example shows how to use the <xref:System.Windows.DataTemplate> and <xref:System.Windows.Style> objects to specify the appearance of a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36143-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36143-104">Example</span></span>  
 <span data-ttu-id="36143-105">Los ejemplos siguientes muestran <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> objetos que personalizan la apariencia de un encabezado de columna para un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="36143-105">The following examples show <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects that customize the appearance of a column header for a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 <span data-ttu-id="36143-106">En el ejemplo siguiente se muestra cómo usar estas <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> objetos que se va a establecer el <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> propiedades de un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="36143-106">The following example shows how to use these <xref:System.Windows.Style> and <xref:System.Windows.DataTemplate> objects to set the <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> properties of a <xref:System.Windows.Controls.GridViewColumn>.</span></span> <span data-ttu-id="36143-107">El <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad define el contenido de las celdas de la columna.</span><span class="sxs-lookup"><span data-stu-id="36143-107">The <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property defines the content of the column cells.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <span data-ttu-id="36143-108">El <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> son sólo dos de varias propiedades que puede usar para personalizar la apariencia del encabezado de columna para un <xref:System.Windows.Controls.GridView> control.</span><span class="sxs-lookup"><span data-stu-id="36143-108">The <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> and <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> are only two of several properties that you can use to customize column header appearance for a <xref:System.Windows.Controls.GridView> control.</span></span> <span data-ttu-id="36143-109">Para más información, consulte [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="36143-109">For more information, see [GridView Column Header Styles and Templates Overview](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).</span></span>  
  
 <span data-ttu-id="36143-110">En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.DataTemplate> que personaliza la apariencia de las celdas de un <xref:System.Windows.Controls.GridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="36143-110">The following example shows how to define a <xref:System.Windows.DataTemplate> that customizes the appearance of the cells in a <xref:System.Windows.Controls.GridViewColumn>.</span></span>  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 <span data-ttu-id="36143-111">En el ejemplo siguiente se muestra cómo utilizar este <xref:System.Windows.DataTemplate> para definir el contenido de un <xref:System.Windows.Controls.GridViewColumn> celda.</span><span class="sxs-lookup"><span data-stu-id="36143-111">The following example shows how to use this <xref:System.Windows.DataTemplate> to define the content of a <xref:System.Windows.Controls.GridViewColumn> cell.</span></span> <span data-ttu-id="36143-112">Esta plantilla se usa en lugar de la <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad que se muestra en la versión anterior <xref:System.Windows.Controls.GridViewColumn> ejemplo.</span><span class="sxs-lookup"><span data-stu-id="36143-112">This template is used instead of the <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> property that is shown in the previous <xref:System.Windows.Controls.GridViewColumn> example.</span></span>  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="36143-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="36143-113">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="36143-114">Información general sobre GridView</span><span class="sxs-lookup"><span data-stu-id="36143-114">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [<span data-ttu-id="36143-115">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="36143-115">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="36143-116">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="36143-116">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)
