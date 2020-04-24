---
title: 'Cómo: Controlar el evento MouseDoubleClick para cada elemento de un control ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 7bbc7bad36b3b1f2c92065e5f5699e5a86ac6189
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646107"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a><span data-ttu-id="78fd3-102">Cómo: Controlar el evento MouseDoubleClick para cada elemento de un control ListView</span><span class="sxs-lookup"><span data-stu-id="78fd3-102">How to: Handle the MouseDoubleClick Event for Each Item in a ListView</span></span>
<span data-ttu-id="78fd3-103">Para controlar un evento para <xref:System.Windows.Controls.ListView>un elemento en un , <xref:System.Windows.Controls.ListViewItem>debe agregar un controlador de eventos a cada .</span><span class="sxs-lookup"><span data-stu-id="78fd3-103">To handle an event for an item in a <xref:System.Windows.Controls.ListView>, you need to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span> <span data-ttu-id="78fd3-104">Cuando <xref:System.Windows.Controls.ListView> a está enlazado a un origen de datos, no se crea explícitamente un <xref:System.Windows.Controls.ListViewItem> <xref:System.Windows.EventSetter> , pero se <xref:System.Windows.Controls.ListViewItem>puede controlar el evento para cada elemento agregando un estilo de un .</span><span class="sxs-lookup"><span data-stu-id="78fd3-104">When a <xref:System.Windows.Controls.ListView> is bound to a data source, you don't explicitly create a <xref:System.Windows.Controls.ListViewItem>, but you can handle the event for each item by adding an <xref:System.Windows.EventSetter> to a style of a <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78fd3-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="78fd3-105">Example</span></span>  
 <span data-ttu-id="78fd3-106">En el ejemplo siguiente <xref:System.Windows.Controls.ListView> se crea <xref:System.Windows.Style> un enlazado a <xref:System.Windows.Controls.ListViewItem>datos y se crea un controlador para agregar un controlador de eventos a cada .</span><span class="sxs-lookup"><span data-stu-id="78fd3-106">The following example creates a data-bound <xref:System.Windows.Controls.ListView> and creates a <xref:System.Windows.Style> to add an event handler to each <xref:System.Windows.Controls.ListViewItem>.</span></span>  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="78fd3-107">En el ejemplo <xref:System.Windows.Controls.Control.MouseDoubleClick> siguiente se controla el evento.</span><span class="sxs-lookup"><span data-stu-id="78fd3-107">The following example handles the <xref:System.Windows.Controls.Control.MouseDoubleClick> event.</span></span>  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> <span data-ttu-id="78fd3-108">Aunque es más común <xref:System.Windows.Controls.ListView> enlazar a a un origen de datos, puede <xref:System.Windows.Controls.ListViewItem> usar un estilo para <xref:System.Windows.Controls.ListView> agregar un controlador de <xref:System.Windows.Controls.ListViewItem>eventos a cada uno en un no enlazado a datos, independientemente de si crea explícitamente un archivo .</span><span class="sxs-lookup"><span data-stu-id="78fd3-108">Although it is most common to bind a <xref:System.Windows.Controls.ListView> to a data source, you can use a style to add an event handler to each <xref:System.Windows.Controls.ListViewItem> in a non-data-bound <xref:System.Windows.Controls.ListView> regardless of whether you explicitly create a <xref:System.Windows.Controls.ListViewItem>.</span></span>  <span data-ttu-id="78fd3-109">Para obtener más información acerca <xref:System.Windows.Controls.ListViewItem> de los <xref:System.Windows.Controls.ItemsControl>controles creados explícita e implícitamente, vea .</span><span class="sxs-lookup"><span data-stu-id="78fd3-109">For more information about explicitly and implicitly created <xref:System.Windows.Controls.ListViewItem> controls, see <xref:System.Windows.Controls.ItemsControl>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78fd3-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="78fd3-110">See also</span></span>

- <xref:System.Xml.XmlElement>
- [<span data-ttu-id="78fd3-111">Descripción general del enlace de datos</span><span class="sxs-lookup"><span data-stu-id="78fd3-111">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="78fd3-112">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="78fd3-112">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="78fd3-113">Enlazar a datos XML mediante consultas XMLDataProvider y XPath</span><span class="sxs-lookup"><span data-stu-id="78fd3-113">Bind to XML Data Using an XMLDataProvider and XPath Queries</span></span>](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [<span data-ttu-id="78fd3-114">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="78fd3-114">ListView Overview</span></span>](listview-overview.md)
