---
title: Procedimiento para establecer iconos del control TreeView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 1a857aade86d2366bb68ce14d716b3ce532ecb05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328418"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="b24b3-102">Procedimiento para establecer iconos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b24b3-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="b24b3-103">Los formularios de Windows <xref:System.Windows.Forms.TreeView> control puede mostrar iconos junto a cada nodo.</span><span class="sxs-lookup"><span data-stu-id="b24b3-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="b24b3-104">Los iconos se sitúan inmediatamente a la izquierda del texto del nodo.</span><span class="sxs-lookup"><span data-stu-id="b24b3-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="b24b3-105">Para mostrar estos iconos, debe asociar la vista de árbol con un <xref:System.Windows.Forms.ImageList> control.</span><span class="sxs-lookup"><span data-stu-id="b24b3-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="b24b3-106">Para obtener más información acerca de las listas de imágenes, consulte [componente ImageList](imagelist-component-windows-forms.md) y [Cómo: Agregar o quitar imágenes con el Windows Forms ImageList (componente)](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="b24b3-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b24b3-107">Un error en Microsoft .NET Framework versión 1.1 evita que las imágenes que aparecen en <xref:System.Windows.Forms.TreeView> nodos cuando la aplicación llama a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b24b3-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b24b3-108">Para evitar este error, llame a <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> en su `Main` método inmediatamente después de llamar a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="b24b3-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="b24b3-109">Este error se ha corregido en [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b24b3-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="b24b3-110">Para mostrar imágenes en una vista de árbol</span><span class="sxs-lookup"><span data-stu-id="b24b3-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="b24b3-111">Establecer el <xref:System.Windows.Forms.TreeView> del control <xref:System.Windows.Forms.TreeView.ImageList%2A> propiedad existente <xref:System.Windows.Forms.ImageList> control que desea usar.</span><span class="sxs-lookup"><span data-stu-id="b24b3-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="b24b3-112">Estas propiedades pueden establecerse en el diseñador con la ventana Propiedades o en el código.</span><span class="sxs-lookup"><span data-stu-id="b24b3-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="b24b3-113">Establecer el nodo <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> y <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> propiedades.</span><span class="sxs-lookup"><span data-stu-id="b24b3-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="b24b3-114">El <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> propiedad determina la imagen mostrada para los Estados del nodo normal y expandido y el <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> propiedad determina la imagen mostrada para el estado del nodo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b24b3-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="b24b3-115">Estas propiedades pueden establecerse en el código o dentro del Editor TreeNode.</span><span class="sxs-lookup"><span data-stu-id="b24b3-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="b24b3-116">Para abrir el Editor TreeNode, haga clic en el botón de puntos suspensivos ( ![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="b24b3-116">To open the TreeNode Editor, click the ellipsis button ( ![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b24b3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b24b3-117">See also</span></span>

- [<span data-ttu-id="b24b3-118">Información general del control TreeView</span><span class="sxs-lookup"><span data-stu-id="b24b3-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="b24b3-119">Cómo: Agregar y quitar nodos con el Control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b24b3-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="b24b3-120">Cómo: Recorrer en iteración todos los nodos de un Control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b24b3-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="b24b3-121">Cómo: Determinar qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="b24b3-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="b24b3-122">Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b24b3-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
