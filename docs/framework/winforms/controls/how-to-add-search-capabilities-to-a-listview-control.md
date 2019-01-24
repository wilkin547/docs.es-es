---
title: Procedimiento Agregar capacidades de búsqueda a un Control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: 0f8b9535539f7f9cd8d0c8ba3a362e9ab7bef03a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716796"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a><span data-ttu-id="3d6f8-102">Procedimiento Agregar capacidades de búsqueda a un Control ListView</span><span class="sxs-lookup"><span data-stu-id="3d6f8-102">How to: Add Search Capabilities to a ListView Control</span></span>
<span data-ttu-id="3d6f8-103">A menudo, cuando se trabaja con una amplia lista de elementos en un <xref:System.Windows.Forms.ListView> control, desea ofrecer capacidades de búsqueda para el usuario.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-103">Oftentimes when working with a large list of items in a <xref:System.Windows.Forms.ListView> control, you want to offer search capabilities to the user.</span></span> <span data-ttu-id="3d6f8-104">El <xref:System.Windows.Forms.ListView> control ofrece esta funcionalidad de dos maneras diferentes: coincidencia de texto y búsqueda de ubicación.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-104">The <xref:System.Windows.Forms.ListView> control offers this capability in two different ways: text matching and location searching.</span></span>  
  
 <span data-ttu-id="3d6f8-105">El <xref:System.Windows.Forms.ListView.FindItemWithText%2A> método le permite realizar una búsqueda de texto en un <xref:System.Windows.Forms.ListView> en la vista de lista o detalles, dada una cadena de búsqueda y una inicial y final opcional índice.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-105">The <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method allows you to perform a text search on a <xref:System.Windows.Forms.ListView> in list or details view, given a search string and an optional starting and ending index.</span></span> <span data-ttu-id="3d6f8-106">En cambio, el <xref:System.Windows.Forms.ListView.FindNearestItem%2A> método le permite encontrar un elemento en un <xref:System.Windows.Forms.ListView> en el icono o el icono de vista, dado un conjunto de coordenadas x e y y una dirección de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-106">In contrast, the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method allows you to find an item in a <xref:System.Windows.Forms.ListView> in icon or tile view, given a set of x- and y-coordinates and a direction to search.</span></span>  
  
### <a name="to-find-an-item-using-text"></a><span data-ttu-id="3d6f8-107">Para encontrar un elemento usando el texto</span><span class="sxs-lookup"><span data-stu-id="3d6f8-107">To find an item using text</span></span>  
  
1.  <span data-ttu-id="3d6f8-108">Crear un <xref:System.Windows.Forms.ListView> con el <xref:System.Windows.Forms.ListView.View%2A> propiedad establecida en <xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.List>y, a continuación, rellene el <xref:System.Windows.Forms.ListView> con elementos.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-108">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.ListView.View%2A> property set to <xref:System.Windows.Forms.View.Details> or <xref:System.Windows.Forms.View.List>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="3d6f8-109">Llame a la <xref:System.Windows.Forms.ListView.FindItemWithText%2A> método, pasando el texto del elemento que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-109">Call the <xref:System.Windows.Forms.ListView.FindItemWithText%2A> method, passing the text of the item you would like to find.</span></span>  
  
3.  <span data-ttu-id="3d6f8-110">En el ejemplo de código siguiente se muestra cómo crear un <xref:System.Windows.Forms.ListView>, rellenarla con los elementos y usar la entrada de texto del usuario para encontrar un elemento en la lista.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-110">The following code example demonstrates how to create a basic <xref:System.Windows.Forms.ListView>, populate it with items, and use text input from the user to find an item in the list.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a><span data-ttu-id="3d6f8-111">Para buscar un elemento mediante las coordenadas x e y</span><span class="sxs-lookup"><span data-stu-id="3d6f8-111">To find an item using x- and y-coordinates</span></span>  
  
1.  <span data-ttu-id="3d6f8-112">Crear un <xref:System.Windows.Forms.ListView> con el <xref:System.Windows.Forms.View> propiedad establecida en <xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>y, a continuación, rellene el <xref:System.Windows.Forms.ListView> con elementos.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-112">Create a <xref:System.Windows.Forms.ListView> with the <xref:System.Windows.Forms.View> property set to <xref:System.Windows.Forms.View.SmallIcon> or <xref:System.Windows.Forms.View.LargeIcon>, and then populate the <xref:System.Windows.Forms.ListView> with items.</span></span>  
  
2.  <span data-ttu-id="3d6f8-113">Llame a la <xref:System.Windows.Forms.ListView.FindNearestItem%2A> método, pasando el deseado: coordenadas x e y- y la dirección que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-113">Call the <xref:System.Windows.Forms.ListView.FindNearestItem%2A> method, passing the desired x- and y-coordinates and the direction you would like to search.</span></span>  
  
3.  <span data-ttu-id="3d6f8-114">En el ejemplo de código siguiente se muestra cómo crear un icono básico <xref:System.Windows.Forms.ListView>, rellenarla con los elementos y capture el <xref:System.Windows.Forms.Control.MouseDown> eventos para buscar el elemento más cercano en la búsqueda hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="3d6f8-114">The following code example demonstrates how to create a basic icon <xref:System.Windows.Forms.ListView>, populate it with items, and capture the <xref:System.Windows.Forms.Control.MouseDown> event to find the nearest item in the up direction.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3d6f8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d6f8-115">See also</span></span>
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [<span data-ttu-id="3d6f8-116">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="3d6f8-116">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [<span data-ttu-id="3d6f8-117">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="3d6f8-117">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
- [<span data-ttu-id="3d6f8-118">Cómo: Agregar y quitar elementos con el Control ListView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="3d6f8-118">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
