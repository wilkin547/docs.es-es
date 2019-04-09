---
title: Filtrar Controlar el evento MouseDoubleClick para cada elemento de un control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 443e5c620ef5bf240d3e317f0234aac0b29b456f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145085"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="bf121-102">Filtrar Controlar el evento MouseDoubleClick para cada elemento de un control ListView</span><span class="sxs-lookup"><span data-stu-id="bf121-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="bf121-103">Para controlar un evento para un elemento en un <xref:System.Windows.Controls.ListView>, deberá agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="bf121-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="bf121-104">Cuando un <xref:System.Windows.Controls.ListView> está enlazado a un origen de datos, no cree explícitamente un <xref:System.Windows.Controls.ListViewItem>, pero se puede controlar el evento para cada elemento mediante la adición de un <xref:System.Windows.EventSetter> a un estilo de un <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="bf121-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf121-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf121-105">Example</span></span>  
 <span data-ttu-id="bf121-106">En el ejemplo siguiente se crea un enlace de datos <xref:System.Windows.Controls.ListView> y crea un <xref:System.Windows.Style> para agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="bf121-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="bf121-107">El ejemplo siguiente se controla el <xref:System.Windows.Controls.Control.MouseDoubleClick> eventos.</span><span class="sxs-lookup"><span data-stu-id="bf121-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  <span data-ttu-id="bf121-108">Aunque es más común para enlazar un <xref:System.Windows.Controls.ListView> a un origen de datos, puede utilizar un estilo para agregar un controlador de eventos a cada <xref:System.Windows.Controls.ListViewItem> en una no enlazado a datos <xref:System.Windows.Controls.ListView> independientemente de si crea explícitamente una <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="bf121-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="bf121-109">Para obtener más información acerca de forma explícita e implícitamente creado <xref:System.Windows.Controls.ListViewItem> los controles, vea <xref:System.Windows.Controls.ItemsControl>.</span><span class="sxs-lookup"><span data-stu-id="bf121-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf121-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf121-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="bf121-111">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="bf121-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="bf121-112">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="bf121-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="bf121-113">Enlazar a datos XML mediante XMLDataProvider y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="bf121-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="bf121-114">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="bf121-114">ListView Overview</span></span>](listview-overview.md)
