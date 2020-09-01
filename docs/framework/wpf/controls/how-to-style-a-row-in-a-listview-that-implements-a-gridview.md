---
title: 'Cómo: aplicar un estilo a una fila en un control ListView que usa GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 4b8b8e2f1b2d7207a37205d981bf2dab3f65122e
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271950"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="b476f-102">Cómo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView</span><span class="sxs-lookup"><span data-stu-id="b476f-102">How to: Style a Row in a ListView That Implements a GridView</span></span>
<span data-ttu-id="b476f-103">En este ejemplo se muestra cómo aplicar un estilo a una fila en un <xref:System.Windows.Controls.ListView> control que utiliza un <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> modo.</span><span class="sxs-lookup"><span data-stu-id="b476f-103">This example shows how to style a row in a <xref:System.Windows.Controls.ListView> control that uses a <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b476f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b476f-104">Example</span></span>  
 <span data-ttu-id="b476f-105">Puede aplicar un estilo a una fila de un <xref:System.Windows.Controls.ListView> control estableciendo <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> en el <xref:System.Windows.Controls.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="b476f-105">You can style a row in a <xref:System.Windows.Controls.ListView> control by setting an <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> on the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="b476f-106">Establezca el estilo de los elementos que se representan como <xref:System.Windows.Controls.ListViewItem> objetos.</span><span class="sxs-lookup"><span data-stu-id="b476f-106">Set the style for its items that are represented as <xref:System.Windows.Controls.ListViewItem> objects.</span></span> <span data-ttu-id="b476f-107">El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> objeto hace referencia <xref:System.Windows.Controls.ControlTemplate> a los objetos que se usan para mostrar el contenido de la fila.</span><span class="sxs-lookup"><span data-stu-id="b476f-107">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references the <xref:System.Windows.Controls.ControlTemplate> objects that are used to display the row content.</span></span>  
  
 <span data-ttu-id="b476f-108">El ejemplo completo, del que se extraen los ejemplos siguientes, muestra una colección de información de la canción almacenada en una base de datos XML.</span><span class="sxs-lookup"><span data-stu-id="b476f-108">The complete sample, which the following examples are extracted from, displays a collection of song information that is stored in an XML database.</span></span> <span data-ttu-id="b476f-109">Cada canción de la base de datos tiene un campo de clasificación y el valor de este campo especifica cómo mostrar una fila de información de la canción.</span><span class="sxs-lookup"><span data-stu-id="b476f-109">Each song in the database has a rating field and the value of this field specifies how to display a row of song information.</span></span>  
  
 <span data-ttu-id="b476f-110">En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para los <xref:System.Windows.Controls.ListViewItem> objetos que representan las canciones de la colección Song.</span><span class="sxs-lookup"><span data-stu-id="b476f-110">The following example shows how to define <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> for the <xref:System.Windows.Controls.ListViewItem> objects that represent the songs in the song collection.</span></span> <span data-ttu-id="b476f-111"><xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Objetos de referencia <xref:System.Windows.Controls.ControlTemplate> que especifican cómo mostrar una fila de información de la canción.</span><span class="sxs-lookup"><span data-stu-id="b476f-111">The <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> references <xref:System.Windows.Controls.ControlTemplate> objects that specify how to display a row of song information.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 <span data-ttu-id="b476f-112">En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.ControlTemplate> que agrega la cadena de texto `"Strongly Recommended"` a la fila.</span><span class="sxs-lookup"><span data-stu-id="b476f-112">The following example shows a <xref:System.Windows.Controls.ControlTemplate> that adds the text string `"Strongly Recommended"` to the row.</span></span> <span data-ttu-id="b476f-113">Se hace referencia a esta plantilla en el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> y se muestra cuando la clasificación de la canción tiene un valor de 5 (cinco).</span><span class="sxs-lookup"><span data-stu-id="b476f-113">This template is referenced in the <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> and displays when the song's rating has a value of 5 (five).</span></span> <span data-ttu-id="b476f-114"><xref:System.Windows.Controls.ControlTemplate>Incluye un <xref:System.Windows.Controls.GridViewRowPresenter> objeto que coloca el contenido de la fila en columnas tal y como se define en el <xref:System.Windows.Controls.GridView> modo de vista.</span><span class="sxs-lookup"><span data-stu-id="b476f-114">The <xref:System.Windows.Controls.ControlTemplate> includes a <xref:System.Windows.Controls.GridViewRowPresenter> object that lays out the contents of the row in columns as defined by the <xref:System.Windows.Controls.GridView> view mode.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 <span data-ttu-id="b476f-115">En el ejemplo siguiente se define <xref:System.Windows.Controls.GridView> .</span><span class="sxs-lookup"><span data-stu-id="b476f-115">The following example defines <xref:System.Windows.Controls.GridView>.</span></span>  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a><span data-ttu-id="b476f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b476f-116">See also</span></span>

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="b476f-117">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="b476f-117">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="b476f-118">Información general sobre ListView</span><span class="sxs-lookup"><span data-stu-id="b476f-118">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="b476f-119">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="b476f-119">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
