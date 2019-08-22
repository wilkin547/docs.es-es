---
title: Filtrar para definir un icono para un botón de la barra de herramientas mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666203"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="37943-102">Filtrar para definir un icono para un botón de la barra de herramientas mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="37943-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="37943-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="37943-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="37943-104"><xref:System.Windows.Forms.ToolBar>los botones pueden mostrar iconos dentro de ellos para facilitar su identificación por parte de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="37943-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="37943-105">Esto se consigue mediante la adición de imágenes <xref:System.Windows.Forms.ImageList> al componente y su asociación con el <xref:System.Windows.Forms.ToolBar> control.</span><span class="sxs-lookup"><span data-stu-id="37943-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="37943-106">El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ToolBar> contenga un <xref:System.Windows.Forms.ImageList> control y un componente.</span><span class="sxs-lookup"><span data-stu-id="37943-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="37943-107">Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="37943-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="37943-108">Para establecer un icono para un botón de la barra de herramientas en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="37943-108">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="37943-109">Agregue imágenes al <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="37943-109">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="37943-110">Para obtener más información, vea [Cómo: Agregue o quite imágenes de ImageList con el diseñador](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="37943-110">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="37943-111">Seleccione el <xref:System.Windows.Forms.ToolBar> control en el formulario.</span><span class="sxs-lookup"><span data-stu-id="37943-111">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="37943-112">En la ventana **propiedades** , establezca la <xref:System.Windows.Forms.ToolBar> propiedad del <xref:System.Windows.Forms.ToolBar.ImageList%2A> control en el <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="37943-112">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="37943-113">Haga clic <xref:System.Windows.Forms.ToolBar> en la <xref:System.Windows.Forms.ToolBar.Buttons%2A> propiedad del control para seleccionarla y haga clic en![los puntos suspensivos (el botón de puntos suspensivos (...) en](./media/visual-studio-ellipsis-button.png)el botón ventana Propiedades de Visual Studio.) para abrir el editor de la **colección ToolBarButton**.</span><span class="sxs-lookup"><span data-stu-id="37943-113">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="37943-114">Use el botón **Agregar** para agregar botones al <xref:System.Windows.Forms.ToolBar> control.</span><span class="sxs-lookup"><span data-stu-id="37943-114">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="37943-115">En la ventana **propiedades** que aparece en el panel de la derecha del editor de la **colección ToolBarButton**, establezca la <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> propiedad de cada botón de la barra de herramientas en uno de los valores de la lista, que se obtiene a partir de las imágenes que agregó al <xref:System.Windows.Forms.ImageList> componente.</span><span class="sxs-lookup"><span data-stu-id="37943-115">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="37943-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="37943-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="37943-117">Cómo: Desencadenar eventos de menú para botones de barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="37943-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="37943-118">ToolBar (control)</span><span class="sxs-lookup"><span data-stu-id="37943-118">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="37943-119">ImageList (componente)</span><span class="sxs-lookup"><span data-stu-id="37943-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
