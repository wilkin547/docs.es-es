---
title: Establecer iconos para el control TreeView
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
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737265"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="4ab5f-102">Cómo: Establecer iconos del control TreeView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ab5f-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="4ab5f-103">El control <xref:System.Windows.Forms.TreeView> de Windows Forms puede mostrar iconos junto a cada nodo.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="4ab5f-104">Los iconos se colocan a la izquierda inmediata del texto del nodo.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="4ab5f-105">Para mostrar estos iconos, debe asociar la vista de árbol a un control de <xref:System.Windows.Forms.ImageList>.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="4ab5f-106">Para obtener más información sobre las listas de imágenes, vea [ImageList (componente](imagelist-component-windows-forms.md) ) y [Cómo: agregar o quitar imágenes con el componente ImageList de Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="4ab5f-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ab5f-107">Un error en Microsoft .NET Framework versión 1,1 impide que las imágenes aparezcan en <xref:System.Windows.Forms.TreeView> nodos cuando la aplicación llama a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4ab5f-108">Para evitar este error, llame a <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> en el método `Main` inmediatamente después de llamar a <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="4ab5f-109">Este error se corrigió en .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-109">This bug is fixed in .NET Framework 2.0.</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="4ab5f-110">Para mostrar imágenes en una vista de árbol</span><span class="sxs-lookup"><span data-stu-id="4ab5f-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="4ab5f-111">Establezca la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> del control <xref:System.Windows.Forms.TreeView> en el control de <xref:System.Windows.Forms.ImageList> existente que desee usar.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="4ab5f-112">Estas propiedades se pueden establecer en el diseñador con el ventana Propiedades o en el código.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="4ab5f-113">Establezca las propiedades <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> y <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> del nodo.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="4ab5f-114">La propiedad <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> determina la imagen que se muestra para los Estados normal y expandido del nodo, y la propiedad <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> determina la imagen que se muestra para el estado seleccionado del nodo.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="4ab5f-115">Estas propiedades se pueden establecer en el código o en el editor TreeNode.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="4ab5f-116">Para abrir el editor TreeNode, haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A> en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="4ab5f-116">To open the TreeNode Editor, click the ellipsis button ( ![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ab5f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ab5f-117">See also</span></span>

- [<span data-ttu-id="4ab5f-118">Información general del control TreeView</span><span class="sxs-lookup"><span data-stu-id="4ab5f-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="4ab5f-119">Agregar y quitar nodos con el control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ab5f-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="4ab5f-120">Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ab5f-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="4ab5f-121">Determinar en qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="4ab5f-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="4ab5f-122">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4ab5f-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
