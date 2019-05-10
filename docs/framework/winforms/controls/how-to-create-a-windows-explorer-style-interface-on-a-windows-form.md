---
title: Procedimiento para crear una interfaz similar a la del Explorador de Windows en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 578fdf8e24803db0e0d80ff22aa5cebebbc2663e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615995"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="a9962-102">Procedimiento para crear una interfaz similar a la del Explorador de Windows en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9962-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="a9962-103">El Explorador de Windows es una opción de interfaz de usuario común para las aplicaciones debido a su familiaridad inmediata.</span><span class="sxs-lookup"><span data-stu-id="a9962-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="a9962-104">El Explorador de Windows es básicamente un <xref:System.Windows.Forms.TreeView> control y un <xref:System.Windows.Forms.ListView> control en paneles independientes.</span><span class="sxs-lookup"><span data-stu-id="a9962-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="a9962-105">Los paneles se realizan puede cambiar el tamaño por un divisor.</span><span class="sxs-lookup"><span data-stu-id="a9962-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="a9962-106">Esta organización de los controles es muy eficaz para mostrar y explorar información.</span><span class="sxs-lookup"><span data-stu-id="a9962-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="a9962-107">Los pasos siguientes muestran cómo organizar controles en un formulario similar al explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="a9962-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="a9962-108">No se muestra cómo agregar la funcionalidad de exploración de archivos de la aplicación Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="a9962-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a9962-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="a9962-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a9962-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="a9962-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a9962-111">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a9962-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="a9962-112">Para crear un formulario de Windows de estilo Explorador de Windows</span><span class="sxs-lookup"><span data-stu-id="a9962-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1. <span data-ttu-id="a9962-113">Cree un nuevo proyecto de aplicación de Windows (**archivo** > **New** > **proyecto** > **Visual C#** o **Visual Basic** > **escritorio clásico de** > **aplicación de Windows Forms**).</span><span class="sxs-lookup"><span data-stu-id="a9962-113">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="a9962-114">Desde el **cuadro de herramientas**:</span><span class="sxs-lookup"><span data-stu-id="a9962-114">From the **Toolbox**:</span></span>  
  
    1. <span data-ttu-id="a9962-115">Arrastre un <xref:System.Windows.Forms.SplitContainer> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="a9962-115">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2. <span data-ttu-id="a9962-116">Arrastre un <xref:System.Windows.Forms.TreeView> controlar en **SplitterPanel1** (el panel de la <xref:System.Windows.Forms.SplitContainer> control marcado **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="a9962-116">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3. <span data-ttu-id="a9962-117">Arrastre un <xref:System.Windows.Forms.ListView> controlar en **SplitterPanel2** (el panel de la <xref:System.Windows.Forms.SplitContainer> control marcado **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="a9962-117">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3. <span data-ttu-id="a9962-118">Presione la tecla CTRL y haciendo clic a su vez, seleccione los tres controles.</span><span class="sxs-lookup"><span data-stu-id="a9962-118">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="a9962-119">Cuando se selecciona el <xref:System.Windows.Forms.SplitContainer> de control, haga clic en la barra de división, en lugar de los paneles.</span><span class="sxs-lookup"><span data-stu-id="a9962-119">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a9962-120">No utilice el **seleccionar todo** comando el **editar** menú.</span><span class="sxs-lookup"><span data-stu-id="a9962-120">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="a9962-121">Si lo hace, la propiedad necesaria en el paso siguiente no aparecerá en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="a9962-121">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="a9962-122">En la ventana **Propiedades** , establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="a9962-122">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5. <span data-ttu-id="a9962-123">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9962-123">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="a9962-124">El formulario muestra una interfaz de usuario de dos partes, similar a la del explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="a9962-124">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a9962-125">Al arrastrar el divisor, los paneles cambian de tamaño.</span><span class="sxs-lookup"><span data-stu-id="a9962-125">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9962-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9962-126">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="a9962-127">Cómo: Crear una interfaz de usuario de varios paneles con formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="a9962-127">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="a9962-128">Cómo: Definir el cambio de tamaño y la posición de comportamiento en una ventana dividida</span><span class="sxs-lookup"><span data-stu-id="a9962-128">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="a9962-129">Cómo: Dividir una ventana horizontalmente</span><span class="sxs-lookup"><span data-stu-id="a9962-129">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="a9962-130">SplitContainer (control)</span><span class="sxs-lookup"><span data-stu-id="a9962-130">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
