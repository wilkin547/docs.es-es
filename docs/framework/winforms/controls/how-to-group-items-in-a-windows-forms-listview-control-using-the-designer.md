---
title: Agrupar elementos en el control ListView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 935d8d75517e1028e686ca229f6ada656f58b01e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736681"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="f4f74-102">Cómo: Agrupar elementos en un control ListView de formularios Windows Forms mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="f4f74-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="f4f74-103">La característica de agrupación del control <xref:System.Windows.Forms.ListView> permite mostrar conjuntos de elementos relacionados en grupos.</span><span class="sxs-lookup"><span data-stu-id="f4f74-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="f4f74-104">Estos grupos se separan en la pantalla por los encabezados de grupo horizontal que contienen los títulos de grupo.</span><span class="sxs-lookup"><span data-stu-id="f4f74-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="f4f74-105">Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes mediante la agrupación alfabética de elementos, por fecha o cualquier otra agrupación lógica.</span><span class="sxs-lookup"><span data-stu-id="f4f74-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="f4f74-106">En la imagen siguiente se muestran algunos elementos agrupados:</span><span class="sxs-lookup"><span data-stu-id="f4f74-106">The following image shows some grouped items:</span></span>

![Números separados en grupos impares e impares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="f4f74-108">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="f4f74-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="f4f74-109">Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f4f74-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="f4f74-110">Para habilitar la agrupación, primero debe crear uno o más objetos <xref:System.Windows.Forms.ListViewGroup> en el diseñador o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f4f74-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="f4f74-111">Una vez definido un grupo, puede asignarle elementos.</span><span class="sxs-lookup"><span data-stu-id="f4f74-111">Once a group has been defined, you can assign items to it.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="f4f74-112">Para agregar o quitar grupos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="f4f74-112">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="f4f74-113">En la ventana **propiedades** , haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad <xref:System.Windows.Forms.ListView.Groups%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4f74-113">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="f4f74-114">Aparece el editor de la **colección ListViewGroup** .</span><span class="sxs-lookup"><span data-stu-id="f4f74-114">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="f4f74-115">Para agregar un grupo, haga clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="f4f74-115">To add a group, click the **Add** button.</span></span> <span data-ttu-id="f4f74-116">Después, puede establecer las propiedades del nuevo grupo, como las propiedades <xref:System.Windows.Forms.ListViewGroup.Header%2A> y <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4f74-116">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="f4f74-117">Para quitar un grupo, selecciónelo y haga clic en el botón **quitar** .</span><span class="sxs-lookup"><span data-stu-id="f4f74-117">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="f4f74-118">Para asignar elementos a grupos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="f4f74-118">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="f4f74-119">En la ventana **propiedades** , haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4f74-119">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="f4f74-120">Aparece el editor de la **colección ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="f4f74-120">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="f4f74-121">Para agregar un nuevo elemento, haga clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="f4f74-121">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="f4f74-122">Después, puede establecer las propiedades del nuevo elemento, como las propiedades <xref:System.Windows.Forms.ListViewItem.Text%2A> y <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4f74-122">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="f4f74-123">Seleccione la propiedad <xref:System.Windows.Forms.ListViewItem.Group%2A> y elija un grupo de la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f4f74-123">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4f74-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4f74-124">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="f4f74-125">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="f4f74-125">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="f4f74-126">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="f4f74-126">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="f4f74-127">Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4f74-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
