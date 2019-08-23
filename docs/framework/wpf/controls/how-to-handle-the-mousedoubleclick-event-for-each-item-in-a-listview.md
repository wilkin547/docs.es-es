---
title: Procedimiento Controlar el evento MouseDoubleClick para cada elemento de un control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7e51c810a2e1e4bf4157aa1311255c5547021b60
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962061"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="bbdb4-102">Procedimiento Controlar el evento MouseDoubleClick para cada elemento de un control ListView</span><span class="sxs-lookup"><span data-stu-id="bbdb4-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="bbdb4-103">Para controlar un evento para un elemento de un <xref:System.Windows.Controls.ListView>, debe agregar un controlador de eventos a cada. <xref:System.Windows.Controls.ListViewItem></span><span class="sxs-lookup"><span data-stu-id="bbdb4-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="bbdb4-104">Cuando un <xref:System.Windows.Controls.ListView> se enlaza a un origen de datos, no se crea explícitamente un <xref:System.Windows.Controls.ListViewItem>, pero se puede controlar el evento para <xref:System.Windows.EventSetter> cada elemento agregando a un estilo de <xref:System.Windows.Controls.ListViewItem>.</span><span class="sxs-lookup"><span data-stu-id="bbdb4-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbdb4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbdb4-105">Example</span></span>  
 <span data-ttu-id="bbdb4-106">En el ejemplo siguiente se crea un enlazado <xref:System.Windows.Controls.ListView> a datos y se crea un <xref:System.Windows.Style> para agregar un <xref:System.Windows.Controls.ListViewItem>controlador de eventos a cada.</span><span class="sxs-lookup"><span data-stu-id="bbdb4-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="bbdb4-107">En el ejemplo siguiente se <xref:System.Windows.Controls.Control.MouseDoubleClick> controla el evento.</span><span class="sxs-lookup"><span data-stu-id="bbdb4-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="bbdb4-108">Aunque <xref:System.Windows.Controls.ListView> es más común enlazar un a un origen de datos, puede usar un estilo para agregar un controlador de eventos a cada uno de ellos <xref:System.Windows.Controls.ListViewItem> en un no enlazado <xref:System.Windows.Controls.ListView> a datos, independientemente de si <xref:System.Windows.Controls.ListViewItem>crea explícitamente una.</span><span class="sxs-lookup"><span data-stu-id="bbdb4-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="bbdb4-109">Para obtener más información acerca de los controles creados <xref:System.Windows.Controls.ListViewItem> explícitamente y <xref:System.Windows.Controls.ItemsControl>de forma implícita, vea.</span><span class="sxs-lookup"><span data-stu-id="bbdb4-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbdb4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbdb4-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="bbdb4-111">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="bbdb4-111">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="bbdb4-112">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="bbdb4-112">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="bbdb4-113">Enlazar a datos XML mediante XMLDataProvider y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="bbdb4-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="bbdb4-114">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="bbdb4-114">ListView Overview</span></span>](listview-overview.md)
