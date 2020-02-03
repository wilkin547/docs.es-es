---
title: Barra de herramientas (Control)
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 027c96bb49e9446244e4b08ba93c551ef043b3c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735452"
---
# <a name="toolbar-control-windows-forms"></a><span data-ttu-id="b45dd-102">Barra de herramientas (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b45dd-102">ToolBar Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="b45dd-103">El control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control `ToolBar`; sin embargo, el control `ToolBar` se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso.</span><span class="sxs-lookup"><span data-stu-id="b45dd-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the `ToolBar` control; however, the `ToolBar` control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="b45dd-104">El control `ToolBar` de Windows Forms se usa en los formularios como una barra de controles que muestra una fila de menús desplegables y botones de mapa de bits que activan comandos.</span><span class="sxs-lookup"><span data-stu-id="b45dd-104">The Windows Forms `ToolBar` control is used on forms as a control bar that displays a row of drop-down menus and bitmapped buttons that activate commands.</span></span> <span data-ttu-id="b45dd-105">Por lo tanto, hacer clic en un botón de barra de herramientas equivale a elegir un comando de menú.</span><span class="sxs-lookup"><span data-stu-id="b45dd-105">Thus, clicking a toolbar button is equivalent to choosing a menu command.</span></span> <span data-ttu-id="b45dd-106">Los botones pueden configurarse para que aparezcan y se comporten como botones de comando, menús desplegables o separadores.</span><span class="sxs-lookup"><span data-stu-id="b45dd-106">The buttons can be configured to appear and behave as push buttons, drop-down menus, or separators.</span></span> <span data-ttu-id="b45dd-107">Normalmente, una barra de herramientas contiene botones y menús que se corresponden con los elementos de la estructura de menús de una aplicación y proporciona acceso rápido a las funciones y los comandos de una aplicación que se usan con más frecuencia.</span><span class="sxs-lookup"><span data-stu-id="b45dd-107">Typically, a toolbar contains buttons and menus that correspond to items in an application's menu structure, providing quick access to an application's most frequently used functions and commands.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b45dd-108">La propiedad `ToolBar` del control <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> propiedad toma una instancia de la clase <xref:System.Windows.Forms.ContextMenu> como referencia.</span><span class="sxs-lookup"><span data-stu-id="b45dd-108">The `ToolBar` control's <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span> <span data-ttu-id="b45dd-109">Tenga en cuenta la referencia que pasa al implementar esta clase de botón en las barras de herramientas de su aplicación, porque la propiedad aceptará cualquier objeto que herede de la clase <xref:System.Windows.Forms.Menu>.</span><span class="sxs-lookup"><span data-stu-id="b45dd-109">Carefully consider the reference you pass when implementing this sort of button on toolbars in your application, as the property will accept any object that inherits from the <xref:System.Windows.Forms.Menu> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b45dd-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b45dd-110">In This Section</span></span>  
 [<span data-ttu-id="b45dd-111">Información general del control ToolBar</span><span class="sxs-lookup"><span data-stu-id="b45dd-111">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)  
 <span data-ttu-id="b45dd-112">Presenta los conceptos generales del control `ToolBar`, que permite diseñar barras de herramientas personalizadas con las que los usuarios pueden trabajar.</span><span class="sxs-lookup"><span data-stu-id="b45dd-112">Introduces the general concepts of the `ToolBar` control, which allows you to design custom toolbars that your users can work with.</span></span>  
  
 [<span data-ttu-id="b45dd-113">Agregar botones a un control ToolBar</span><span class="sxs-lookup"><span data-stu-id="b45dd-113">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)  
 <span data-ttu-id="b45dd-114">Describe cómo agregar botones a un control `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="b45dd-114">Describes how to add buttons to a `ToolBar` control.</span></span>  
  
 [<span data-ttu-id="b45dd-115">Definir un icono para un botón ToolBar</span><span class="sxs-lookup"><span data-stu-id="b45dd-115">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)  
 <span data-ttu-id="b45dd-116">Describe cómo mostrar iconos dentro de los botones del control `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="b45dd-116">Describes how to display icons within a `ToolBar` control's buttons.</span></span>  
  
 [<span data-ttu-id="b45dd-117">Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas</span><span class="sxs-lookup"><span data-stu-id="b45dd-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)  
 <span data-ttu-id="b45dd-118">Proporciona instrucciones sobre cómo escribir código para interpretar en que botón hace clic el usuario en un control `ToolBar`.</span><span class="sxs-lookup"><span data-stu-id="b45dd-118">Gives directions on writing code to interpret which button the user clicks in a `ToolBar` control.</span></span>  
  
 <span data-ttu-id="b45dd-119">Consulte también [Cómo: definir un icono para un botón de la barra de herramientas mediante el diseñador](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [Cómo: agregar botones a un control Toolbar mediante el diseñador](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="b45dd-119">Also see [How to: Define an Icon for a ToolBar Button Using the Designer](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [How to: Add Buttons to a ToolBar Control Using the Designer](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b45dd-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="b45dd-120">Reference</span></span>  
 <span data-ttu-id="b45dd-121">Clase <xref:System.Windows.Forms.ToolBar></span><span class="sxs-lookup"><span data-stu-id="b45dd-121"><xref:System.Windows.Forms.ToolBar> class</span></span>  
 <span data-ttu-id="b45dd-122">Contiene información de referencia sobre la clase y sus miembros.</span><span class="sxs-lookup"><span data-stu-id="b45dd-122">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b45dd-123">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b45dd-123">Related Sections</span></span>  
 [<span data-ttu-id="b45dd-124">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b45dd-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="b45dd-125">Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.</span><span class="sxs-lookup"><span data-stu-id="b45dd-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="b45dd-126">ToolStrip (control)</span><span class="sxs-lookup"><span data-stu-id="b45dd-126">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)  
 <span data-ttu-id="b45dd-127">Describe las barras de herramientas que pueden hospedar menús, controles y controles de usuario en aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b45dd-127">Describes toolbars that can host menus, controls, and user controls in Windows Forms applications.</span></span>
