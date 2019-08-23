---
title: Procedimiento para crear una interfaz similar a la del Explorador de Windows en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960622"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="7deb8-102">Procedimiento para crear una interfaz similar a la del Explorador de Windows en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7deb8-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="7deb8-103">El explorador de Windows es una opción de interfaz de usuario común para las aplicaciones debido a su familiaridad.</span><span class="sxs-lookup"><span data-stu-id="7deb8-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>

 <span data-ttu-id="7deb8-104">El explorador de Windows es, esencialmente <xref:System.Windows.Forms.TreeView> , un control <xref:System.Windows.Forms.ListView> y un control en paneles independientes.</span><span class="sxs-lookup"><span data-stu-id="7deb8-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="7deb8-105">Un divisor realiza el redimensionamiento de los paneles.</span><span class="sxs-lookup"><span data-stu-id="7deb8-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="7deb8-106">Esta disposición de controles es muy eficaz para mostrar y examinar la información.</span><span class="sxs-lookup"><span data-stu-id="7deb8-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>

 <span data-ttu-id="7deb8-107">En los pasos siguientes se muestra cómo organizar los controles en un formulario similar al explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="7deb8-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="7deb8-108">No muestran cómo agregar la funcionalidad de exploración de archivos de la aplicación del explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="7deb8-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>

## <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="7deb8-109">Para crear un Windows Form con estilo Explorador de Windows</span><span class="sxs-lookup"><span data-stu-id="7deb8-109">To create a Windows Explorer-style Windows Form</span></span>

1. <span data-ttu-id="7deb8-110">Crear un nuevo proyecto de aplicación para Windows (**archivo** > **nuevo** > **proyecto** > **Visual C#**  o **Visual Basic** > **escritorio clásico**  >  **Windows Forms aplicación**).</span><span class="sxs-lookup"><span data-stu-id="7deb8-110">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="7deb8-111">En el **cuadro de herramientas**:</span><span class="sxs-lookup"><span data-stu-id="7deb8-111">From the **Toolbox**:</span></span>

    1. <span data-ttu-id="7deb8-112">Arrastre un <xref:System.Windows.Forms.SplitContainer> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="7deb8-112">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>

    2. <span data-ttu-id="7deb8-113">Arrastre un <xref:System.Windows.Forms.TreeView> control a **SplitterPanel1** ( <xref:System.Windows.Forms.SplitContainer> el panel del control marcado como **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="7deb8-113">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>

    3. <span data-ttu-id="7deb8-114">Arrastre un <xref:System.Windows.Forms.ListView> control a **SplitterPanel2** ( <xref:System.Windows.Forms.SplitContainer> el panel del control marcado como **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="7deb8-114">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>

3. <span data-ttu-id="7deb8-115">Seleccione los tres controles presionando la tecla CTRL y haciendo clic en ellos a su vez.</span><span class="sxs-lookup"><span data-stu-id="7deb8-115">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="7deb8-116">Al seleccionar el <xref:System.Windows.Forms.SplitContainer> control, haga clic en la barra de división, en lugar de en los paneles.</span><span class="sxs-lookup"><span data-stu-id="7deb8-116">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7deb8-117">No use el comando **seleccionar todo** en el menú **edición** .</span><span class="sxs-lookup"><span data-stu-id="7deb8-117">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="7deb8-118">Si lo hace, la propiedad necesaria en el paso siguiente no aparecerá en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="7deb8-118">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>

4. <span data-ttu-id="7deb8-119">En la ventana **Propiedades** , establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="7deb8-119">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="7deb8-120">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7deb8-120">Press F5 to run the application.</span></span>

     <span data-ttu-id="7deb8-121">El formulario muestra una interfaz de usuario de dos partes, similar a la del explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="7deb8-121">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7deb8-122">Al arrastrar el divisor, los paneles cambian de tamaño.</span><span class="sxs-lookup"><span data-stu-id="7deb8-122">When you drag the splitter, the panels resize themselves.</span></span>

## <a name="see-also"></a><span data-ttu-id="7deb8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7deb8-123">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="7deb8-124">Procedimientos: Cree una interfaz de usuario de MULTIPANEL con Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7deb8-124">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="7deb8-125">Cómo: Definir el comportamiento de ajuste de tamaño y colocación en una ventana dividida</span><span class="sxs-lookup"><span data-stu-id="7deb8-125">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="7deb8-126">Cómo: Dividir una ventana horizontalmente</span><span class="sxs-lookup"><span data-stu-id="7deb8-126">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="7deb8-127">SplitContainer (control)</span><span class="sxs-lookup"><span data-stu-id="7deb8-127">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
