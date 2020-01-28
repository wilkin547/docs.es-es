---
title: Agregar y quitar elementos con el control ListView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732295"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="ee18b-102">Cómo: Agregar y quitar elementos de un control ListView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="ee18b-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="ee18b-103">El proceso de agregar un elemento a un Windows Forms control <xref:System.Windows.Forms.ListView> consiste principalmente en especificar el elemento y asignarle propiedades.</span><span class="sxs-lookup"><span data-stu-id="ee18b-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="ee18b-104">La adición o eliminación de elementos de lista se puede realizar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="ee18b-104">Adding or removing list items can be done at any time.</span></span>

<span data-ttu-id="ee18b-105">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="ee18b-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="ee18b-106">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ee18b-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="ee18b-107">Para agregar o quitar elementos mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="ee18b-107">To add or remove items using the designer</span></span>

1. <span data-ttu-id="ee18b-108">Seleccione el control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="ee18b-108">Select the <xref:System.Windows.Forms.ListView> control.</span></span>

2. <span data-ttu-id="ee18b-109">En la ventana **propiedades** , haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee18b-109">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="ee18b-110">Aparece el editor de la **colección ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="ee18b-110">The **ListViewItem Collection Editor** appears.</span></span>

3. <span data-ttu-id="ee18b-111">Para agregar un elemento, haga clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="ee18b-111">To add an item, click the **Add** button.</span></span> <span data-ttu-id="ee18b-112">Después, puede establecer las propiedades del nuevo elemento, como las propiedades <xref:System.Windows.Forms.ListView.Text%2A> y <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.</span><span class="sxs-lookup"><span data-stu-id="ee18b-112">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

4. <span data-ttu-id="ee18b-113">Para quitar un elemento, selecciónelo y haga clic en el botón **quitar** .</span><span class="sxs-lookup"><span data-stu-id="ee18b-113">To remove an item, select it and click the **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee18b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee18b-114">See also</span></span>

- [<span data-ttu-id="ee18b-115">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="ee18b-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="ee18b-116">Agregar columnas al control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee18b-116">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="ee18b-117">Mostrar subelementos en columnas con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee18b-117">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="ee18b-118">Mostrar iconos del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee18b-118">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="ee18b-119">Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="ee18b-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="ee18b-120">Agrupar elementos en un control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ee18b-120">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
