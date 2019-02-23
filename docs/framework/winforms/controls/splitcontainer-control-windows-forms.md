---
title: SplitContainer (Control, formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: 0afc1aba32852406b975cc65ab4d4bff334d3ff7
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745468"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="c15e4-102">SplitContainer (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c15e4-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="c15e4-103">El control `SplitContainer` de Windows Forms puede considerarse como una composición de dos paneles separados por una barra móvil.</span><span class="sxs-lookup"><span data-stu-id="c15e4-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="c15e4-104">Cuando el puntero del mouse está sobre la barra, el puntero cambia de forma para mostrar que se puede mover.</span><span class="sxs-lookup"><span data-stu-id="c15e4-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c15e4-105">En el **cuadro de herramientas**, este control reemplaza el <xref:System.Windows.Forms.Splitter> control que había en la versión anterior de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c15e4-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="c15e4-106">El control `SplitContainer` es mucho más preferible que el control <xref:System.Windows.Forms.Splitter>.</span><span class="sxs-lookup"><span data-stu-id="c15e4-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="c15e4-107">La clase <xref:System.Windows.Forms.Splitter> aún se incluye en .NET Framework por motivos de compatibilidad con aplicaciones existentes, pero es muy recomendable que use el control `SplitContainer` en los nuevos proyectos.</span><span class="sxs-lookup"><span data-stu-id="c15e4-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="c15e4-108">El control `SplitContainer` le permite crear interfaces de usuario complejas; a menudo, una selección en un panel determina qué objetos se muestran en el otro panel.</span><span class="sxs-lookup"><span data-stu-id="c15e4-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="c15e4-109">Esta organización es muy eficaz para mostrar y explorar información.</span><span class="sxs-lookup"><span data-stu-id="c15e4-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="c15e4-110">Tener dos paneles permite agregar información en las áreas y la barra o "divisor" permite que los usuarios puedan cambiar el tamaño de los paneles fácilmente.</span><span class="sxs-lookup"><span data-stu-id="c15e4-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c15e4-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c15e4-111">In This Section</span></span>  
 [<span data-ttu-id="c15e4-112">Información general sobre SplitContainer (Control)</span><span class="sxs-lookup"><span data-stu-id="c15e4-112">SplitContainer Control Overview</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="c15e4-113">Presenta el control `SplitContainer` y describe las propiedades, los métodos y los eventos que se usan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="c15e4-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="c15e4-114">Cómo: Definir el cambio de tamaño y la posición de comportamiento en una ventana dividida</span><span class="sxs-lookup"><span data-stu-id="c15e4-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="c15e4-115">Describe cómo controlar el divisor dentro del control `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="c15e4-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="c15e4-116">Cómo: Dividir una ventana horizontalmente</span><span class="sxs-lookup"><span data-stu-id="c15e4-116">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="c15e4-117">Describe cómo controlar la orientación del divisor dentro del control `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="c15e4-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="c15e4-118">Cómo: Crear una interfaz de usuario de varios paneles con formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="c15e4-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="c15e4-119">Crea una interfaz de usuario de varios paneles similar a la que se usa en Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="c15e4-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="c15e4-120">Consulte también [Cómo: Dividir una ventana horizontalmente con el diseñador](how-to-split-a-window-horizontally-using-the-designer.md), [Cómo: Crear una interfaz de estilo del explorador de Windows en Windows Forms](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [Cómo: Crear una interfaz de usuario de varios paneles con formularios de Windows mediante el Diseñador de](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c15e4-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c15e4-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="c15e4-121">Reference</span></span>  
 <span data-ttu-id="c15e4-122">Clase <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="c15e4-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="c15e4-123">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="c15e4-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c15e4-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c15e4-124">Related Sections</span></span>  
 [<span data-ttu-id="c15e4-125">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c15e4-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="c15e4-126">Proporciona vínculos a temas acerca de los controles diseñados específicamente para trabajar con Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c15e4-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="c15e4-127">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c15e4-127">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="c15e4-128">Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.</span><span class="sxs-lookup"><span data-stu-id="c15e4-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
