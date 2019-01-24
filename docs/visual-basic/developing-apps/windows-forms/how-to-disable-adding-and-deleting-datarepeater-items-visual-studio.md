---
title: Procedimiento Deshabilitar, agregar y eliminar elementos DataRepeater (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
ms.openlocfilehash: 3a304132d0514da4c19811be2536c9516e2838f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618547"
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a><span data-ttu-id="6e721-102">Procedimiento Deshabilitar, agregar y eliminar elementos DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="6e721-102">How to: Disable Adding and Deleting DataRepeater Items (Visual Studio)</span></span>
<span data-ttu-id="6e721-103">De forma predeterminada, los usuarios pueden agregar y eliminar elementos en un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="6e721-103">By default, users can add and delete items in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="6e721-104">Los usuarios pueden agregar un nuevo elemento presionando CTRL+N cuando un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> tiene el foco o haciendo clic en el **AddNewItem** situado en el <xref:System.Windows.Forms.BindingNavigator> control.</span><span class="sxs-lookup"><span data-stu-id="6e721-104">Users can add a new item by pressing CTRL+N when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **AddNewItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span> <span data-ttu-id="6e721-105">Los usuarios pueden eliminar un elemento presionando cuando elimine un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> tiene el foco o haciendo clic en el **DeleteItem** situado en el <xref:System.Windows.Forms.BindingNavigator> control.</span><span class="sxs-lookup"><span data-stu-id="6e721-105">Users can delete an item by pressing DELETE when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **DeleteItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
 <span data-ttu-id="6e721-106">Puede deshabilitar la adición o eliminación en tiempo de diseño o en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6e721-106">You can disable adding and/or deleting at design time or at run time.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a><span data-ttu-id="6e721-107">Para deshabilitar la adición y eliminación en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="6e721-107">To disable adding and deleting at design time</span></span>  
  
1.  <span data-ttu-id="6e721-108">En el Diseñador de Windows Forms, seleccione el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span><span class="sxs-lookup"><span data-stu-id="6e721-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e721-109">Debe seleccionar la sección inferior del control.</span><span class="sxs-lookup"><span data-stu-id="6e721-109">You must select the lower section of the control.</span></span> <span data-ttu-id="6e721-110">Si selecciona la sección de la plantilla de elemento, se mostrará un conjunto diferente de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6e721-110">If you select the item template section, a different set of properties will be displayed.</span></span>  
  
2.  <span data-ttu-id="6e721-111">En la ventana Propiedades, establezca la <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> propiedad **False**.</span><span class="sxs-lookup"><span data-stu-id="6e721-111">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> property to **False**.</span></span>  
  
3.  <span data-ttu-id="6e721-112">Establecer el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> propiedad **False**.</span><span class="sxs-lookup"><span data-stu-id="6e721-112">Set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> property to **False**.</span></span>  
  
4.  <span data-ttu-id="6e721-113">En el Diseñador de Windows Forms, seleccione el <xref:System.Windows.Forms.BindingNavigator> controlar y, a continuación, haga clic en el **AddNewItem** botón (el botón con un signo más en él).</span><span class="sxs-lookup"><span data-stu-id="6e721-113">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **AddNewItem** button (the button with a plus sign on it).</span></span>  
  
5.  <span data-ttu-id="6e721-114">En la ventana Propiedades, establezca la <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> propiedad **False**.</span><span class="sxs-lookup"><span data-stu-id="6e721-114">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
6.  <span data-ttu-id="6e721-115">En el Diseñador de Windows Forms, seleccione el <xref:System.Windows.Forms.BindingNavigator> controlar y, a continuación, haga clic en el **DeleteItem** botón (el botón con una X roja en él).</span><span class="sxs-lookup"><span data-stu-id="6e721-115">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **DeleteItem** button (the button with a red X on it).</span></span>  
  
7.  <span data-ttu-id="6e721-116">En la ventana Propiedades, establezca la <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> propiedad **False**.</span><span class="sxs-lookup"><span data-stu-id="6e721-116">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
8.  <span data-ttu-id="6e721-117">En la Bandeja de componentes, seleccione el <xref:System.Windows.Forms.BindingSource> a la que el <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> está enlazado.</span><span class="sxs-lookup"><span data-stu-id="6e721-117">In the Component Tray, select the <xref:System.Windows.Forms.BindingSource> to which the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> is bound.</span></span>  
  
9. <span data-ttu-id="6e721-118">En la ventana Propiedades, establezca la <xref:System.Windows.Forms.BindingSource.AllowNew%2A> propiedad **False**.</span><span class="sxs-lookup"><span data-stu-id="6e721-118">In the Properties window, set the <xref:System.Windows.Forms.BindingSource.AllowNew%2A> property to **False**.</span></span>  
  
10. <span data-ttu-id="6e721-119">En el Diseñador de formularios de Windows, haga doble clic en el **DeleteItem** botón para abrir el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="6e721-119">In the Windows Forms Designer, double-click the **DeleteItem** button to open the Code Editor.</span></span>  
  
11. <span data-ttu-id="6e721-120">En la lista desplegable de eventos, seleccione el `BindingNavigatorDeleteItem_EnabledChanged` eventos.</span><span class="sxs-lookup"><span data-stu-id="6e721-120">In the Events drop-down list, select the `BindingNavigatorDeleteItem_EnabledChanged` event.</span></span>  
  
12. <span data-ttu-id="6e721-121">Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged` :</span><span class="sxs-lookup"><span data-stu-id="6e721-121">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="6e721-122">Este paso es necesario porque <xref:System.Windows.Forms.BindingSource> habilitará el botón **DeleteItem** cada vez que cambie el registro actual.</span><span class="sxs-lookup"><span data-stu-id="6e721-122">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a><span data-ttu-id="6e721-123">Para deshabilitar la adición y eliminación en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6e721-123">To disable adding and deleting at run time</span></span>  
  
1.  <span data-ttu-id="6e721-124">En el Diseñador de Windows Forms, haga doble clic en el formulario para abrir el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="6e721-124">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="6e721-125">Agregue el código siguiente al evento `Form_Load` :</span><span class="sxs-lookup"><span data-stu-id="6e721-125">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  <span data-ttu-id="6e721-126">Agregue el código siguiente al controlador de eventos `BindingNavigatorDeleteItem_EnabledChanged` :</span><span class="sxs-lookup"><span data-stu-id="6e721-126">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="6e721-127">Este paso es necesario porque <xref:System.Windows.Forms.BindingSource> habilitará el botón **DeleteItem** cada vez que cambie el registro actual.</span><span class="sxs-lookup"><span data-stu-id="6e721-127">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e721-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e721-128">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="6e721-129">Introducción al control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="6e721-129">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="6e721-130">Solución de problemas del control DataRepeater</span><span class="sxs-lookup"><span data-stu-id="6e721-130">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
