---
title: 'Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de diseño'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: d17273f52d0cef118b79fef03af72522f6677073
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529826"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a><span data-ttu-id="bb4a6-102">Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="bb4a6-102">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>
<span data-ttu-id="bb4a6-103">Este tutorial muestra cómo cambiar los valores de propiedad de un control de Windows Presentation Foundation (WPF) hospedado en un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-103">This walkthrough shows you how to change property values of a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>  
  
 <span data-ttu-id="bb4a6-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="bb4a6-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="bb4a6-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-105">Create the project.</span></span>  
  
-   <span data-ttu-id="bb4a6-106">Crear el control WPF.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="bb4a6-107">Hospedar los controles WPF en un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-107">Host the WPF controls on a Windows Form.</span></span>  
  
-   <span data-ttu-id="bb4a6-108">Use el Diseñador de WPF de Visual Studio para cambiar los valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-108">Use the WPF Designer for Visual Studio to change property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb4a6-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bb4a6-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="bb4a6-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bb4a6-111">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="bb4a6-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bb4a6-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bb4a6-112">Prerequisites</span></span>  
 <span data-ttu-id="bb4a6-113">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="bb4a6-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="bb4a6-114">.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="bb4a6-115">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="bb4a6-115">Creating the Project</span></span>  
 <span data-ttu-id="bb4a6-116">El primer paso es crear el proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb4a6-117">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="bb4a6-118">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="bb4a6-118">To create the project</span></span>  
  
-   <span data-ttu-id="bb4a6-119">Crear un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `WpfHost`.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `WpfHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="bb4a6-120">Crear el control WPF</span><span class="sxs-lookup"><span data-stu-id="bb4a6-120">Creating the WPF Control</span></span>  
 <span data-ttu-id="bb4a6-121">Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-121">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="bb4a6-122">Para crear controles WPF</span><span class="sxs-lookup"><span data-stu-id="bb4a6-122">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="bb4a6-123">Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-123">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="bb4a6-124">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="bb4a6-125">Para obtener más información, consulte [Tutorial: crear nuevo WPF contenido en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="bb4a6-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="bb4a6-126">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad `Blue`.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-126">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
3.  <span data-ttu-id="bb4a6-127">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-127">Build the project.</span></span>  
  
## <a name="changing-property-values-on-the-wpf-control"></a><span data-ttu-id="bb4a6-128">Cambiar los valores de propiedad en el control WPF</span><span class="sxs-lookup"><span data-stu-id="bb4a6-128">Changing Property Values on the WPF Control</span></span>  
 <span data-ttu-id="bb4a6-129">La etiqueta inteligente <xref:System.Windows.Forms.Integration.ElementHost> permite cambiar fácilmente las propiedades del contenido WPF hospedado mediante WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-129">The <xref:System.Windows.Forms.Integration.ElementHost> smart tag makes it easy to change properties of hosted WPF content by using the WPF Designer.</span></span>  
  
#### <a name="to-host-a-wpf-control"></a><span data-ttu-id="bb4a6-130">Para hospedar un control WPF</span><span class="sxs-lookup"><span data-stu-id="bb4a6-130">To host a WPF control</span></span>  
  
1.  <span data-ttu-id="bb4a6-131">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-131">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="bb4a6-132">En el **cuadro de herramientas**, en la **controles de usuario de WPF** ficha, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-132">In the **Toolbox**, in the **WPF User Controls** tab, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="bb4a6-133">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="bb4a6-134">En el **tareas de ElementHost** panel de etiquetas inteligentes, seleccione **editar contenido hospedado**.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-134">In the **ElementHost Tasks** smart tag panel, select **Edit Hosted Content**.</span></span>  
  
     <span data-ttu-id="bb4a6-135">Se abre UserControl1.xaml en WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-135">UserControl1.xaml opens in the WPF Designer.</span></span>  
  
4.  <span data-ttu-id="bb4a6-136">En el **propiedades** ventana, establezca el valor de la <xref:System.Windows.Controls.Control.Background%2A> propiedad `Red`.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-136">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Red`.</span></span>  
  
5.  <span data-ttu-id="bb4a6-137">Recompile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-137">Rebuild the project.</span></span>  
  
6.  <span data-ttu-id="bb4a6-138">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-138">Open `Form1` in the Windows Forms Designer.</span></span>  
  
     <span data-ttu-id="bb4a6-139">La instancia de `UserControl1` tiene un fondo rojo.</span><span class="sxs-lookup"><span data-stu-id="bb4a6-139">The instance of `UserControl1` has a red background.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4a6-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb4a6-140">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="bb4a6-141">Delimitar y acoplar controles secundarios en un control TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="bb4a6-141">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="bb4a6-142">Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="bb4a6-142">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="bb4a6-143">Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste</span><span class="sxs-lookup"><span data-stu-id="bb4a6-143">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="bb4a6-144">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="bb4a6-144">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="bb4a6-145">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="bb4a6-145">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="bb4a6-146">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="bb4a6-146">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
