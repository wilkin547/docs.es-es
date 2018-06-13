---
title: 'Cómo: Crear una interfaz similar a la del Explorador de Windows en Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 2d5b79244d867ea4b6134413d42710b2eadc871e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532391"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="0abb3-102">Cómo: Crear una interfaz similar a la del Explorador de Windows en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0abb3-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="0abb3-103">El Explorador de Windows es una opción de interfaz de usuario común para aplicaciones debido a su familiaridad inmediata.</span><span class="sxs-lookup"><span data-stu-id="0abb3-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="0abb3-104">El Explorador de Windows es, básicamente, un <xref:System.Windows.Forms.TreeView> control y un <xref:System.Windows.Forms.ListView> control en paneles independientes.</span><span class="sxs-lookup"><span data-stu-id="0abb3-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="0abb3-105">Los paneles se realizan puede cambiar por un divisor.</span><span class="sxs-lookup"><span data-stu-id="0abb3-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="0abb3-106">Esta disposición de controles es muy eficaz para mostrar y explorar información.</span><span class="sxs-lookup"><span data-stu-id="0abb3-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="0abb3-107">Los pasos siguientes muestran cómo organizar los controles en un formulario similar al explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="0abb3-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="0abb3-108">No muestra cómo agregar la funcionalidad de exploración de archivos de la aplicación de explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="0abb3-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0abb3-109">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="0abb3-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0abb3-110">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="0abb3-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0abb3-111">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0abb3-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="0abb3-112">Para crear un formulario de Windows de estilo Explorador de Windows</span><span class="sxs-lookup"><span data-stu-id="0abb3-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="0abb3-113">Crear un nuevo proyecto de aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="0abb3-113">Create a new Windows Application project.</span></span> <span data-ttu-id="0abb3-114">Para ver detalles, consulte [Cómo: Crear un nuevo proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="0abb3-114">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="0abb3-115">Desde el **cuadro de herramientas**:</span><span class="sxs-lookup"><span data-stu-id="0abb3-115">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="0abb3-116">Arrastre un <xref:System.Windows.Forms.SplitContainer> control al formulario.</span><span class="sxs-lookup"><span data-stu-id="0abb3-116">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="0abb3-117">Arrastre un <xref:System.Windows.Forms.TreeView> controlar en **SplitterPanel1** (el panel de la <xref:System.Windows.Forms.SplitContainer> los controles marcados como **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="0abb3-117">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="0abb3-118">Arrastre un <xref:System.Windows.Forms.ListView> controlar en **SplitterPanel2** (el panel de la <xref:System.Windows.Forms.SplitContainer> los controles marcados como **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="0abb3-118">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="0abb3-119">Seleccione los tres controles presionando la tecla CTRL y haciendo clic a su vez.</span><span class="sxs-lookup"><span data-stu-id="0abb3-119">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="0abb3-120">Cuando se selecciona el <xref:System.Windows.Forms.SplitContainer> de control, haga clic en la barra de división, en lugar de los paneles.</span><span class="sxs-lookup"><span data-stu-id="0abb3-120">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0abb3-121">No utilice la **seleccionar todo** comando el **editar** menú.</span><span class="sxs-lookup"><span data-stu-id="0abb3-121">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="0abb3-122">Si lo hace, la propiedad necesaria en el paso siguiente no aparecerá en la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="0abb3-122">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="0abb3-123">En el **propiedades** ventana, establezca el <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="0abb3-123">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="0abb3-124">Presione F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0abb3-124">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="0abb3-125">El formulario muestra una interfaz de usuario de dos partes, similar a la que el Explorador de Windows.</span><span class="sxs-lookup"><span data-stu-id="0abb3-125">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0abb3-126">Cuando se arrastra el divisor, los paneles de tamaño.</span><span class="sxs-lookup"><span data-stu-id="0abb3-126">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0abb3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0abb3-127">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="0abb3-128">Crear una interfaz de usuario de varios paneles con Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0abb3-128">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [<span data-ttu-id="0abb3-129">Definir el comportamiento de cambio de tamaño y colocación de una ventana dividida</span><span class="sxs-lookup"><span data-stu-id="0abb3-129">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [<span data-ttu-id="0abb3-130">Dividir una ventana horizontalmente</span><span class="sxs-lookup"><span data-stu-id="0abb3-130">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [<span data-ttu-id="0abb3-131">SplitContainer (control)</span><span class="sxs-lookup"><span data-stu-id="0abb3-131">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
