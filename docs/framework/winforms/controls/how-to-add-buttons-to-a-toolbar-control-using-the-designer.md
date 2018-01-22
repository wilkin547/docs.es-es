---
title: "Cómo: Agregar botones a un control ToolBar mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5339d946f771b7ba187813dd67860aaa63a21eb3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a><span data-ttu-id="82ced-102">Cómo: Agregar botones a un control ToolBar mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="82ced-102">How to: Add Buttons to a ToolBar Control Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="82ced-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>; sin embargo, el control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="82ced-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="82ced-104">Una parte integral de la <xref:System.Windows.Forms.ToolBar> control es los botones que agregue a ella.</span><span class="sxs-lookup"><span data-stu-id="82ced-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="82ced-105">Se pueden usar para facilitar el acceso a comandos de menú, o bien, como alternativa, puede colocarse en otra área de la interfaz de usuario de la aplicación para exponer comandos a los usuarios que no están disponibles en la estructura de menús.</span><span class="sxs-lookup"><span data-stu-id="82ced-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>  
  
 <span data-ttu-id="82ced-106">El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.ToolBar> control.</span><span class="sxs-lookup"><span data-stu-id="82ced-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control.</span></span> <span data-ttu-id="82ced-107">Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="82ced-107">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82ced-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="82ced-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="82ced-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="82ced-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="82ced-110">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="82ced-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-buttons-at-design-time"></a><span data-ttu-id="82ced-111">Para agregar botones en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="82ced-111">To add buttons at design time</span></span>  
  
1.  <span data-ttu-id="82ced-112">Seleccione el control <xref:System.Windows.Forms.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="82ced-112">Select the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2.  <span data-ttu-id="82ced-113">En el **propiedades** ventana, haga clic en el <xref:System.Windows.Forms.ToolBar.Buttons%2A> propiedad para seleccionarlo y haga clic en el **puntos suspensivos** (![de pantalla de VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) para abrir el **Editor de colecciones ToolBarButton**.</span><span class="sxs-lookup"><span data-stu-id="82ced-113">In the **Properties** window, click the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it and click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="82ced-114">Use la **agregar** y **quitar** botones para agregar y quitar botones, desde el <xref:System.Windows.Forms.ToolBar> control.</span><span class="sxs-lookup"><span data-stu-id="82ced-114">Use the **Add** and **Remove** buttons to add and remove buttons from the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
4.  <span data-ttu-id="82ced-115">Configurar las propiedades de los botones individuales en la **propiedades** ventana que aparece en el panel del lado derecho del editor.</span><span class="sxs-lookup"><span data-stu-id="82ced-115">Configure the properties of the individual buttons in the **Properties** window that appears in the pane on the right side of the editor.</span></span> <span data-ttu-id="82ced-116">La tabla siguiente muestran algunas propiedades importantes a tener en cuenta.</span><span class="sxs-lookup"><span data-stu-id="82ced-116">The following table shows some important properties to consider.</span></span>  
  
    |<span data-ttu-id="82ced-117">Property</span><span class="sxs-lookup"><span data-stu-id="82ced-117">Property</span></span>|<span data-ttu-id="82ced-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="82ced-118">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|<span data-ttu-id="82ced-119">Establece el menú que se mostrará en el botón de barra de herramientas de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="82ced-119">Sets the menu to be displayed in the drop-down toolbar button.</span></span> <span data-ttu-id="82ced-120">El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span><span class="sxs-lookup"><span data-stu-id="82ced-120">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>.</span></span> <span data-ttu-id="82ced-121">Esta propiedad toma una instancia de la <xref:System.Windows.Forms.ContextMenu> clase como una referencia.</span><span class="sxs-lookup"><span data-stu-id="82ced-121">This property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|<span data-ttu-id="82ced-122">Establece si un botón de barra de herramientas Alternar parcialmente presionado.</span><span class="sxs-lookup"><span data-stu-id="82ced-122">Sets whether a toggle-style toolbar button is partially pushed.</span></span> <span data-ttu-id="82ced-123">El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span><span class="sxs-lookup"><span data-stu-id="82ced-123">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|<span data-ttu-id="82ced-124">Establece si un botón de Alternar barra de herramientas está actualmente en estado presionado.</span><span class="sxs-lookup"><span data-stu-id="82ced-124">Sets whether a toggle-style toolbar button is currently in the pushed state.</span></span> <span data-ttu-id="82ced-125">El botón de barra de herramientas <xref:System.Windows.Forms.ToolBarButton.Style%2A> propiedad debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> o <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span><span class="sxs-lookup"><span data-stu-id="82ced-125">The toolbar button's <xref:System.Windows.Forms.ToolBarButton.Style%2A> property must be set to <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> or <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|<span data-ttu-id="82ced-126">Establece el estilo del botón de barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="82ced-126">Sets the style of the toolbar button.</span></span> <span data-ttu-id="82ced-127">Debe ser uno de los valores de la <xref:System.Windows.Forms.ToolBarButtonStyle> enumeración.</span><span class="sxs-lookup"><span data-stu-id="82ced-127">Must be one of the values in the <xref:System.Windows.Forms.ToolBarButtonStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|<span data-ttu-id="82ced-128">La cadena de texto que se muestra el botón.</span><span class="sxs-lookup"><span data-stu-id="82ced-128">The text string displayed by the button.</span></span>|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|<span data-ttu-id="82ced-129">El texto que aparece como una información sobre herramientas para el botón.</span><span class="sxs-lookup"><span data-stu-id="82ced-129">The text that appears as a ToolTip for the button.</span></span>|  
  
5.  <span data-ttu-id="82ced-130">Haga clic en **Aceptar** para cerrar el cuadro de diálogo y crear los paneles especificados.</span><span class="sxs-lookup"><span data-stu-id="82ced-130">Click **OK** to close the dialog box and create the panels you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ced-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="82ced-131">See Also</span></span>  
 <xref:System.Windows.Forms.ToolBar>  
 [<span data-ttu-id="82ced-132">Definir un icono para un botón ToolBar</span><span class="sxs-lookup"><span data-stu-id="82ced-132">How to: Define an Icon for a ToolBar Button</span></span>](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [<span data-ttu-id="82ced-133">Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="82ced-133">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [<span data-ttu-id="82ced-134">Información general del control ToolBar</span><span class="sxs-lookup"><span data-stu-id="82ced-134">ToolBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [<span data-ttu-id="82ced-135">ToolBar (control)</span><span class="sxs-lookup"><span data-stu-id="82ced-135">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
