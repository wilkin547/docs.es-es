---
title: 'Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
ms.openlocfilehash: 55b426fbe95bac269183a649ecd839175a8cbdda
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44185014"
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="7b228-102">Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes</span><span class="sxs-lookup"><span data-stu-id="7b228-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="7b228-103">En este tutorial se muestra cómo copiar un control de Windows Presentation Foundation (WPF) de un Windows Form a otro.</span><span class="sxs-lookup"><span data-stu-id="7b228-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="7b228-104">En este tutorial, realizará las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="7b228-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="7b228-105">Crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7b228-105">Create the project.</span></span>  
  
-   <span data-ttu-id="7b228-106">Copiar un control WPF.</span><span class="sxs-lookup"><span data-stu-id="7b228-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b228-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="7b228-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7b228-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="7b228-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7b228-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="7b228-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7b228-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="7b228-110">Prerequisites</span></span>  
 <span data-ttu-id="7b228-111">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="7b228-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="7b228-112">.</span><span class="sxs-lookup"><span data-stu-id="7b228-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="7b228-113">Crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="7b228-113">Creating the Project</span></span>  
 <span data-ttu-id="7b228-114">El primer paso es crear el proyecto de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7b228-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b228-115">Al hospedar contenido de WPF, solo se admiten proyectos de C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7b228-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="7b228-116">Para crear el proyecto</span><span class="sxs-lookup"><span data-stu-id="7b228-116">To create the project</span></span>  
  
-   <span data-ttu-id="7b228-117">Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C# llamado `CopyElementHost`.</span><span class="sxs-lookup"><span data-stu-id="7b228-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="7b228-118">Copiar un control WPF</span><span class="sxs-lookup"><span data-stu-id="7b228-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="7b228-119">Después de agregar un control WPF al proyecto, puede copiarlo a otros formularios del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7b228-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="7b228-120">Para copiar un control WPF</span><span class="sxs-lookup"><span data-stu-id="7b228-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="7b228-121">Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.</span><span class="sxs-lookup"><span data-stu-id="7b228-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="7b228-122">Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="7b228-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="7b228-123">Para obtener más información, consulte [Tutorial: crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="7b228-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="7b228-124">Compile el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7b228-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="7b228-125">Abra `Form1` en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7b228-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="7b228-126">Desde el **cuadro de herramientas**, arrastre una instancia de `UserControl1` hasta el formulario.</span><span class="sxs-lookup"><span data-stu-id="7b228-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="7b228-127">La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="7b228-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="7b228-128">Con `elementHost1` seleccionado, presione CTRL+C para copiarlo en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="7b228-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="7b228-129">Agregue un nuevo Windows Form al proyecto.</span><span class="sxs-lookup"><span data-stu-id="7b228-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="7b228-130">Use el nombre predeterminado para el tipo de formulario, `Form2`.</span><span class="sxs-lookup"><span data-stu-id="7b228-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="7b228-131">Con `Form2` abierto en el Diseñador de Windows Forms, presione CTRL+V para pegar una copia de `elementHost1` en el formulario.</span><span class="sxs-lookup"><span data-stu-id="7b228-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="7b228-132">El control copiado también se llama `elementHost1`, porque es un campo privado de la clase `Form2`.</span><span class="sxs-lookup"><span data-stu-id="7b228-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="7b228-133">No hay ningún conflicto de nombres con el `elementHost1` en la clase `Form1`.</span><span class="sxs-lookup"><span data-stu-id="7b228-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b228-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b228-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="7b228-135">Migración e interoperabilidad</span><span class="sxs-lookup"><span data-stu-id="7b228-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="7b228-136">Utilizar controles WPF</span><span class="sxs-lookup"><span data-stu-id="7b228-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="7b228-137">Diseño de XAML en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7b228-137">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
