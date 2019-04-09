---
title: Filtrar para agregar y quitar nodos con el control TreeView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: cfac0d02ec1effdd521ca68ae4cb44b5a5a7a597
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124857"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="c86ba-102">Filtrar para agregar y quitar nodos con el control TreeView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="c86ba-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="c86ba-103">Dado que los Windows Forms <xref:System.Windows.Forms.TreeView> control muestra los nodos de forma jerárquica, al agregar un nodo que debe prestar atención a lo que es su nodo primario.</span><span class="sxs-lookup"><span data-stu-id="c86ba-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="c86ba-104">El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.TreeView> control.</span><span class="sxs-lookup"><span data-stu-id="c86ba-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="c86ba-105">Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c86ba-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c86ba-106">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="c86ba-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c86ba-107">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="c86ba-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c86ba-108">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c86ba-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="c86ba-109">Para agregar o quitar nodos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="c86ba-109">To add or remove nodes in the designer</span></span>  
  
1.  <span data-ttu-id="c86ba-110">Seleccione el control <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="c86ba-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2.  <span data-ttu-id="c86ba-111">En el **propiedades** ventana, haga clic en el **puntos suspensivos** (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) situado junto a el <xref:System.Windows.Forms.TreeView.Nodes%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c86ba-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="c86ba-112">El **Editor TreeNode** aparece.</span><span class="sxs-lookup"><span data-stu-id="c86ba-112">The **TreeNode Editor** appears.</span></span>  
  
3.  <span data-ttu-id="c86ba-113">Para agregar nodos, debe existir un nodo raíz; Si no existe, primero debe agregar una raíz, haga clic en el **Agregar raíz** botón.</span><span class="sxs-lookup"><span data-stu-id="c86ba-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="c86ba-114">A continuación, puede agregar nodos secundarios, seleccione la raíz o cualquier otro nodo y haga clic en el **agregar secundario** botón.</span><span class="sxs-lookup"><span data-stu-id="c86ba-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4.  <span data-ttu-id="c86ba-115">Para eliminar los nodos, seleccione el nodo para eliminar y, a continuación, haga clic en el **eliminar** botón.</span><span class="sxs-lookup"><span data-stu-id="c86ba-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c86ba-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c86ba-116">See also</span></span>

- [<span data-ttu-id="c86ba-117">TreeView (Control)</span><span class="sxs-lookup"><span data-stu-id="c86ba-117">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="c86ba-118">Información general sobre el control TreeView</span><span class="sxs-lookup"><span data-stu-id="c86ba-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="c86ba-119">Filtrar para establecer iconos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c86ba-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="c86ba-120">Filtrar para iterar todos los nodos del control TreeView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c86ba-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="c86ba-121">Filtrar para determinar en qué nodo de TreeView se hizo clic</span><span class="sxs-lookup"><span data-stu-id="c86ba-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="c86ba-122">Filtrar para agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c86ba-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
