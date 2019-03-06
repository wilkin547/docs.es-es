---
title: Filtrar Crear controles TreeView simples o complejos
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 9b19443c80818809122b0bbfc7c7dae7b4b40da5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368930"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a><span data-ttu-id="0653b-102">Filtrar Crear controles TreeView simples o complejos</span><span class="sxs-lookup"><span data-stu-id="0653b-102">How to: Create Simple or Complex TreeViews</span></span>
<span data-ttu-id="0653b-103">En este ejemplo se muestra cómo crear simples o complejas <xref:System.Windows.Controls.TreeView> controles.</span><span class="sxs-lookup"><span data-stu-id="0653b-103">This example shows how to create simple or complex <xref:System.Windows.Controls.TreeView> controls.</span></span>  
  
 <span data-ttu-id="0653b-104">Un <xref:System.Windows.Controls.TreeView> consta de una jerarquía de <xref:System.Windows.Controls.TreeViewItem> controles, que pueden contener cadenas de texto simple y el contenido también más complejo, tales como <xref:System.Windows.Controls.Button> controles o <xref:System.Windows.Controls.StackPanel> con contenido incrustado.</span><span class="sxs-lookup"><span data-stu-id="0653b-104">A <xref:System.Windows.Controls.TreeView> consists of a hierarchy of <xref:System.Windows.Controls.TreeViewItem> controls, which can contain simple text strings and also more complex content, such as <xref:System.Windows.Controls.Button> controls or a <xref:System.Windows.Controls.StackPanel> with embedded content.</span></span> <span data-ttu-id="0653b-105">Puede definir explícitamente el <xref:System.Windows.Controls.TreeView> contenido o un origen de datos puede proporcionar el contenido.</span><span class="sxs-lookup"><span data-stu-id="0653b-105">You can explicitly define the <xref:System.Windows.Controls.TreeView> content or a data source can provide the content.</span></span> <span data-ttu-id="0653b-106">En este tema se proporciona ejemplos de estos conceptos.</span><span class="sxs-lookup"><span data-stu-id="0653b-106">This topic provides examples of these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0653b-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0653b-107">Example</span></span>  
 <span data-ttu-id="0653b-108">El <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedad de la <xref:System.Windows.Controls.TreeViewItem> incluye el contenido que el <xref:System.Windows.Controls.TreeView> muestra para ese elemento.</span><span class="sxs-lookup"><span data-stu-id="0653b-108">The <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property of the <xref:System.Windows.Controls.TreeViewItem> contains the content that the <xref:System.Windows.Controls.TreeView> displays for that item.</span></span> <span data-ttu-id="0653b-109">Un <xref:System.Windows.Controls.TreeViewItem> también pueden tener <xref:System.Windows.Controls.TreeViewItem> controles como sus elementos secundarios y pueden definir estos elementos secundarios mediante la <xref:System.Windows.Controls.ItemsControl.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="0653b-109">A <xref:System.Windows.Controls.TreeViewItem> can also have <xref:System.Windows.Controls.TreeViewItem> controls as its child elements and you can define these child elements by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="0653b-110">El ejemplo siguiente muestra cómo se definen explícitamente <xref:System.Windows.Controls.TreeViewItem> contenido estableciendo el <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedad en una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="0653b-110">The following example shows how to explicitly define <xref:System.Windows.Controls.TreeViewItem> content by setting the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property to a text string.</span></span>  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 <span data-ttu-id="0653b-111">El ejemplo siguiente se muestra cómo definir los elementos secundarios de un <xref:System.Windows.Controls.TreeViewItem> definiendo <xref:System.Windows.Controls.ItemsControl.Items%2A> que son <xref:System.Windows.Controls.Button> controles.</span><span class="sxs-lookup"><span data-stu-id="0653b-111">The following example show how to define child elements of a <xref:System.Windows.Controls.TreeViewItem> by defining <xref:System.Windows.Controls.ItemsControl.Items%2A> that are <xref:System.Windows.Controls.Button> controls.</span></span>  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 <span data-ttu-id="0653b-112">El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.TreeView> donde un <xref:System.Windows.Data.XmlDataProvider> proporciona <xref:System.Windows.Controls.TreeViewItem> contenido y un <xref:System.Windows.HierarchicalDataTemplate> define la apariencia del contenido.</span><span class="sxs-lookup"><span data-stu-id="0653b-112">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where an <xref:System.Windows.Data.XmlDataProvider> provides <xref:System.Windows.Controls.TreeViewItem> content and a <xref:System.Windows.HierarchicalDataTemplate> defines the appearance of the content.</span></span>  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 <span data-ttu-id="0653b-113">El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.TreeView> donde el <xref:System.Windows.Controls.TreeViewItem> contiene contenido <xref:System.Windows.Controls.DockPanel> controles con contenido incrustado.</span><span class="sxs-lookup"><span data-stu-id="0653b-113">The following example shows how to create a <xref:System.Windows.Controls.TreeView> where the <xref:System.Windows.Controls.TreeViewItem> content contains <xref:System.Windows.Controls.DockPanel> controls that have embedded content.</span></span>  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a><span data-ttu-id="0653b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0653b-114">See also</span></span>
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="0653b-115">Introducción a TreeView</span><span class="sxs-lookup"><span data-stu-id="0653b-115">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="0653b-116">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="0653b-116">How-to Topics</span></span>](treeview-how-to-topics.md)
