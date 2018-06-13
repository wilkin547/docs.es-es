---
title: 'Cómo: Mostrar iconos del control ListView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 0e597ed182739947014b4f405ee2dc3149b62849
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533609"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="977a2-102">Cómo: Mostrar iconos del control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="977a2-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="977a2-103">Los formularios Windows Forms <xref:System.Windows.Forms.ListView> control puede mostrar iconos procedentes de tres listas de imágenes.</span><span class="sxs-lookup"><span data-stu-id="977a2-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="977a2-104">Las vistas de lista, detalles e iconos mostrar imágenes desde la lista de imágenes especificada en la <xref:System.Windows.Forms.ListView.SmallImageList%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="977a2-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="977a2-105">La vista LargeIcon muestra imágenes desde la lista de imágenes especificada en la <xref:System.Windows.Forms.ListView.LargeImageList%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="977a2-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="977a2-106">Una vista de lista también puede mostrar un conjunto adicional de iconos, establecer en el <xref:System.Windows.Forms.ListView.StateImageList%2A> propiedad, junto a los iconos grandes o pequeños.</span><span class="sxs-lookup"><span data-stu-id="977a2-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="977a2-107">Para obtener más información acerca de las listas de imágenes, vea [ImageList (componente)](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) y [Cómo: agregar o quitar imágenes con el componente ImageList de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="977a2-107">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="977a2-108">Para mostrar imágenes en una vista de lista</span><span class="sxs-lookup"><span data-stu-id="977a2-108">To display images in a list view</span></span>  
  
1.  <span data-ttu-id="977a2-109">Establezca la propiedad adecuada,<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, o <xref:System.Windows.Forms.ListView.StateImageList%2A>: a la existente <xref:System.Windows.Forms.ImageList> componente que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="977a2-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="977a2-110">Estas propiedades pueden establecerse en el diseñador con la ventana Propiedades o en el código.</span><span class="sxs-lookup"><span data-stu-id="977a2-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  <span data-ttu-id="977a2-111">Establecer el <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> o <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> propiedad para cada elemento de lista que tiene un icono asociado.</span><span class="sxs-lookup"><span data-stu-id="977a2-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="977a2-112">Estas propiedades pueden establecerse en código o dentro del **Editor de la colección de ListViewItem**.</span><span class="sxs-lookup"><span data-stu-id="977a2-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="977a2-113">Para abrir el **Editor de la colección de ListViewItem**, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.ListView.Items%2A>propiedad en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="977a2-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="977a2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="977a2-114">See Also</span></span>  
 [<span data-ttu-id="977a2-115">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="977a2-115">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="977a2-116">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="977a2-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="977a2-117">Agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="977a2-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="977a2-118">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="977a2-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [<span data-ttu-id="977a2-119">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="977a2-119">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
