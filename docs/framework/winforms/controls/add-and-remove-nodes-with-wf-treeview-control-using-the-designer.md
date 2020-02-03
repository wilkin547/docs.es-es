---
title: Agregar y quitar nodos con el control TreeView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732243"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="00fc9-102">Cómo: Agregar y quitar nodos de un control TreeView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="00fc9-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>

<span data-ttu-id="00fc9-103">Dado que el control Windows Forms <xref:System.Windows.Forms.TreeView> muestra los nodos de forma jerárquica, al agregar un nodo, debe prestar atención a cuál es su nodo primario.</span><span class="sxs-lookup"><span data-stu-id="00fc9-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>

<span data-ttu-id="00fc9-104">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="00fc9-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="00fc9-105">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="00fc9-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="00fc9-106">Para agregar o quitar nodos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="00fc9-106">To add or remove nodes in the designer</span></span>

1. <span data-ttu-id="00fc9-107">Seleccione el control <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="00fc9-107">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>

2. <span data-ttu-id="00fc9-108">En la ventana **propiedades** , haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A>.</span><span class="sxs-lookup"><span data-stu-id="00fc9-108">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>

     <span data-ttu-id="00fc9-109">Aparece el **Editor TreeNode** .</span><span class="sxs-lookup"><span data-stu-id="00fc9-109">The **TreeNode Editor** appears.</span></span>

3. <span data-ttu-id="00fc9-110">Para agregar nodos, debe existir un nodo raíz; Si no existe ninguna, primero debe agregar una raíz haciendo clic en el botón **Agregar raíz** .</span><span class="sxs-lookup"><span data-stu-id="00fc9-110">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="00fc9-111">Después, puede agregar nodos secundarios seleccionando la raíz o cualquier otro nodo y haciendo clic en el botón **Agregar secundario** .</span><span class="sxs-lookup"><span data-stu-id="00fc9-111">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>

4. <span data-ttu-id="00fc9-112">Para eliminar nodos, seleccione el nodo que desea eliminar y, a continuación, haga clic en el botón **eliminar** .</span><span class="sxs-lookup"><span data-stu-id="00fc9-112">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="00fc9-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00fc9-113">See also</span></span>

- [<span data-ttu-id="00fc9-114">TreeView (control)</span><span class="sxs-lookup"><span data-stu-id="00fc9-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="00fc9-115">Información general del control TreeView</span><span class="sxs-lookup"><span data-stu-id="00fc9-115">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="00fc9-116">Establecer iconos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00fc9-116">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="00fc9-117">Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00fc9-117">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="00fc9-118">Determinar en qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="00fc9-118">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="00fc9-119">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="00fc9-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
