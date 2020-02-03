---
title: Mostrar iconos para el control ListView
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
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744506"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="ca434-102">Cómo: Mostrar iconos del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ca434-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="ca434-103">El control <xref:System.Windows.Forms.ListView> de Windows Forms puede mostrar iconos de tres listas de imágenes.</span><span class="sxs-lookup"><span data-stu-id="ca434-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="ca434-104">Las vistas List, details y SmallIcon muestran imágenes de la lista de imágenes especificada en la propiedad <xref:System.Windows.Forms.ListView.SmallImageList%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca434-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="ca434-105">La vista LargeIcon muestra imágenes de la lista de imágenes especificada en la propiedad <xref:System.Windows.Forms.ListView.LargeImageList%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca434-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="ca434-106">Una vista de lista también puede mostrar un conjunto adicional de iconos, establecido en la propiedad <xref:System.Windows.Forms.ListView.StateImageList%2A>, junto a los iconos grandes o pequeños.</span><span class="sxs-lookup"><span data-stu-id="ca434-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="ca434-107">Para obtener más información sobre las listas de imágenes, vea [ImageList (componente](imagelist-component-windows-forms.md) ) y [Cómo: agregar o quitar imágenes con el componente ImageList de Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="ca434-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="ca434-108">Para mostrar imágenes en una vista de lista</span><span class="sxs-lookup"><span data-stu-id="ca434-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="ca434-109">Establezca la propiedad adecuada (<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>o <xref:System.Windows.Forms.ListView.StateImageList%2A>) en el componente de <xref:System.Windows.Forms.ImageList> existente que desea usar.</span><span class="sxs-lookup"><span data-stu-id="ca434-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="ca434-110">Estas propiedades se pueden establecer en el diseñador con el ventana Propiedades o en el código.</span><span class="sxs-lookup"><span data-stu-id="ca434-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="ca434-111">Establezca la propiedad <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> o <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> para cada elemento de lista que tenga un icono asociado.</span><span class="sxs-lookup"><span data-stu-id="ca434-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="ca434-112">Estas propiedades se pueden establecer en el código o en el **Editor de la colección ListViewItem**.</span><span class="sxs-lookup"><span data-stu-id="ca434-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="ca434-113">Para abrir el **Editor de la colección ListViewItem**, haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A> en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="ca434-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="ca434-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca434-114">See also</span></span>

- [<span data-ttu-id="ca434-115">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="ca434-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="ca434-116">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ca434-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="ca434-117">Agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ca434-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="ca434-118">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ca434-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="ca434-119">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="ca434-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
