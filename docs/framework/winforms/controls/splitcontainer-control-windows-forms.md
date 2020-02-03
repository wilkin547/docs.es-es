---
title: SplitContainer (Control)
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: ac04f60847aa6f77c11637f37b5ec94b6f7ef341
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742907"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="40106-102">SplitContainer (Control, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="40106-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="40106-103">El control `SplitContainer` de Windows Forms puede considerarse como una composición de dos paneles separados por una barra móvil.</span><span class="sxs-lookup"><span data-stu-id="40106-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="40106-104">Cuando el puntero del mouse está sobre la barra, el puntero cambia de forma para mostrar que se puede mover.</span><span class="sxs-lookup"><span data-stu-id="40106-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40106-105">En el **cuadro de herramientas**, este control reemplaza al control <xref:System.Windows.Forms.Splitter> que estaba en la versión anterior de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="40106-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="40106-106">El control `SplitContainer` es mucho más preferible que el control <xref:System.Windows.Forms.Splitter>.</span><span class="sxs-lookup"><span data-stu-id="40106-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="40106-107">La clase <xref:System.Windows.Forms.Splitter> aún se incluye en .NET Framework por motivos de compatibilidad con aplicaciones existentes, pero es muy recomendable que use el control `SplitContainer` en los nuevos proyectos.</span><span class="sxs-lookup"><span data-stu-id="40106-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="40106-108">El control `SplitContainer` le permite crear interfaces de usuario complejas; a menudo, una selección en un panel determina qué objetos se muestran en el otro panel.</span><span class="sxs-lookup"><span data-stu-id="40106-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="40106-109">Esta organización es muy eficaz para mostrar y explorar información.</span><span class="sxs-lookup"><span data-stu-id="40106-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="40106-110">Tener dos paneles permite agregar información en las áreas y la barra o "divisor" permite que los usuarios puedan cambiar el tamaño de los paneles fácilmente.</span><span class="sxs-lookup"><span data-stu-id="40106-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40106-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="40106-111">In This Section</span></span>  
 [<span data-ttu-id="40106-112">Información general sobre SplitContainer (Control)</span><span class="sxs-lookup"><span data-stu-id="40106-112">SplitContainer Control Overview</span></span>](splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="40106-113">Presenta el control `SplitContainer` y describe las propiedades, los métodos y los eventos que se usan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="40106-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="40106-114">Definir el comportamiento de cambio de tamaño y colocación de una ventana dividida</span><span class="sxs-lookup"><span data-stu-id="40106-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="40106-115">Describe cómo controlar el divisor dentro del control `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="40106-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="40106-116">Dividir una ventana horizontalmente</span><span class="sxs-lookup"><span data-stu-id="40106-116">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="40106-117">Describe cómo controlar la orientación del divisor dentro del control `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="40106-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="40106-118">Crear una interfaz de usuario de varios paneles con Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40106-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="40106-119">Crea una interfaz de usuario de varios paneles similar a la que se usa en Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="40106-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="40106-120">Consulte también [Cómo: dividir una ventana horizontalmente con el diseñador](how-to-split-a-window-horizontally-using-the-designer.md), [Cómo: crear una interfaz de estilo del explorador de Windows en Windows Forms](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [Cómo: crear una interfaz de usuario MULTIPANEL con Windows Forms mediante el diseñador](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="40106-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="40106-121">Referencia</span><span class="sxs-lookup"><span data-stu-id="40106-121">Reference</span></span>  
 <span data-ttu-id="40106-122">Clase <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="40106-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="40106-123">Describe esta clase y contiene vínculos a todos sus miembros.</span><span class="sxs-lookup"><span data-stu-id="40106-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="40106-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="40106-124">Related Sections</span></span>  
 [<span data-ttu-id="40106-125">Controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40106-125">Windows Forms Controls</span></span>](index.md)  
 <span data-ttu-id="40106-126">Proporciona vínculos a temas acerca de los controles diseñados específicamente para trabajar con Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="40106-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="40106-127">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40106-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="40106-128">Proporciona una lista completa de controles de Windows Forms, con vínculos a información sobre su uso.</span><span class="sxs-lookup"><span data-stu-id="40106-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
