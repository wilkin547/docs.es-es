---
title: Procedimiento para agrupar elementos en un control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "69039397"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="6f6a4-102">Procedimiento para agrupar elementos en un control ListView de formularios Windows Forms mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="6f6a4-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="6f6a4-103">La característica de agrupación del <xref:System.Windows.Forms.ListView> control permite mostrar conjuntos de elementos relacionados en grupos.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="6f6a4-104">Estos grupos se separan en la pantalla por los encabezados de grupo horizontal que contienen los títulos de grupo.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="6f6a4-105">Puede usar <xref:System.Windows.Forms.ListView> grupos para facilitar la navegación por listas grandes mediante la agrupación de elementos por orden alfabético, por fecha o por cualquier otra agrupación lógica.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="6f6a4-106">En la imagen siguiente se muestran algunos elementos agrupados:</span><span class="sxs-lookup"><span data-stu-id="6f6a4-106">The following image shows some grouped items:</span></span>

![Números separados en grupos impares e impares.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="6f6a4-108">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ListView> contenga un control.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="6f6a4-109">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6f6a4-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="6f6a4-110">Para habilitar la agrupación, primero debe crear uno o más <xref:System.Windows.Forms.ListViewGroup> objetos en el diseñador o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="6f6a4-111">Una vez definido un grupo, puede asignarle elementos.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-111">Once a group has been defined, you can assign items to it.</span></span>

> [!NOTE]
> <span data-ttu-id="6f6a4-112"><xref:System.Windows.Forms.ListView>los grupos solo están disponibles [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] en cuando la aplicación <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> llama al método.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6f6a4-113">En los sistemas operativos anteriores, cualquier código relacionado con los grupos no tiene ningún efecto y los grupos no aparecerán.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="6f6a4-114">Para obtener más información, consulta <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="6f6a4-115">Para agregar o quitar grupos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="6f6a4-115">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="6f6a4-116">En la ventana **propiedades** , haga clic en los![ **puntos suspensivos** (el botón de puntos suspensivos (...) del botón](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio. <xref:System.Windows.Forms.ListView.Groups%2A> ) situado junto a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-116">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="6f6a4-117">Aparece el editor de la **colección ListViewGroup** .</span><span class="sxs-lookup"><span data-stu-id="6f6a4-117">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="6f6a4-118">Para agregar un grupo, haga clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="6f6a4-118">To add a group, click the **Add** button.</span></span> <span data-ttu-id="6f6a4-119">Después, puede establecer las propiedades del nuevo grupo, como las <xref:System.Windows.Forms.ListViewGroup.Header%2A> propiedades y. <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A></span><span class="sxs-lookup"><span data-stu-id="6f6a4-119">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="6f6a4-120">Para quitar un grupo, selecciónelo y haga clic en el botón **quitar** .</span><span class="sxs-lookup"><span data-stu-id="6f6a4-120">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="6f6a4-121">Para asignar elementos a grupos en el diseñador</span><span class="sxs-lookup"><span data-stu-id="6f6a4-121">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="6f6a4-122">En la ventana **propiedades** , haga clic en los![ **puntos suspensivos** (el botón de puntos suspensivos (...) del botón](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio. <xref:System.Windows.Forms.ListView.Items%2A> ) situado junto a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-122">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="6f6a4-123">Aparece el editor de la **colección ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="6f6a4-123">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="6f6a4-124">Para agregar un nuevo elemento, haga clic en el botón **Agregar** .</span><span class="sxs-lookup"><span data-stu-id="6f6a4-124">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="6f6a4-125">Después, puede establecer las propiedades del nuevo elemento, como las <xref:System.Windows.Forms.ListViewItem.Text%2A> propiedades y. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A></span><span class="sxs-lookup"><span data-stu-id="6f6a4-125">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="6f6a4-126">Seleccione la <xref:System.Windows.Forms.ListViewItem.Group%2A> propiedad y elija un grupo en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="6f6a4-126">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f6a4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f6a4-127">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="6f6a4-128">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="6f6a4-128">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="6f6a4-129">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="6f6a4-129">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="6f6a4-130">Cómo: Agregar y quitar elementos con el control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f6a4-130">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
