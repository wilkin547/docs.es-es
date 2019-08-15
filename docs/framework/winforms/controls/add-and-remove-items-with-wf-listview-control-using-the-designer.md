---
title: Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 62665746ea9fcd1553717b02b1f1349dc6415ab2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040088"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="5d299-102">Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="5d299-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="5d299-103">El proceso de agregar un elemento a un control <xref:System.Windows.Forms.ListView> de Windows Forms consiste principalmente en especificar el elemento y asignarle propiedades.</span><span class="sxs-lookup"><span data-stu-id="5d299-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="5d299-104">La adición o eliminación de elementos de lista se puede realizar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="5d299-104">Adding or removing list items can be done at any time.</span></span>

<span data-ttu-id="5d299-105">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ListView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="5d299-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="5d299-106">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5d299-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="5d299-107">Para agregar o quitar elementos mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="5d299-107">To add or remove items using the designer</span></span>

1. <span data-ttu-id="5d299-108">Seleccione el control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="5d299-108">Select the <xref:System.Windows.Forms.ListView> control.</span></span>

2. <span data-ttu-id="5d299-109">En la ventana **propiedades** , haga clic en los![ **puntos suspensivos** (el botón de puntos suspensivos (...) del botón](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio. <xref:System.Windows.Forms.ListView.Items%2A> ) situado junto a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5d299-109">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="5d299-110">Aparece el editor de la **colección ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="5d299-110">The **ListViewItem Collection Editor** appears.</span></span>

3. <span data-ttu-id="5d299-111">Para agregar un elemento, haga clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="5d299-111">To add an item, click the **Add** button.</span></span> <span data-ttu-id="5d299-112">Después, puede establecer las propiedades del nuevo elemento, como las <xref:System.Windows.Forms.ListView.Text%2A> propiedades y. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A></span><span class="sxs-lookup"><span data-stu-id="5d299-112">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

4. <span data-ttu-id="5d299-113">Para quitar un elemento, selecciónelo y haga clic en el botón **quitar** .</span><span class="sxs-lookup"><span data-stu-id="5d299-113">To remove an item, select it and click the **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d299-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d299-114">See also</span></span>

- [<span data-ttu-id="5d299-115">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="5d299-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="5d299-116">Cómo: Agregar columnas al control Windows Forms ListView</span><span class="sxs-lookup"><span data-stu-id="5d299-116">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5d299-117">Procedimientos: Mostrar subelementos en columnas con el control ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d299-117">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5d299-118">Procedimientos: Mostrar iconos del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d299-118">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="5d299-119">Cómo: Agregar información personalizada a un control TreeView o ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5d299-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="5d299-120">Cómo: Agrupar elementos en un control Windows Forms ListView</span><span class="sxs-lookup"><span data-stu-id="5d299-120">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
