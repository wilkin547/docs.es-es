---
title: Desarrollar un control de formularios Windows Forms compuesto
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
ms.openlocfilehash: bfbb9091d40652bdd1ae277f3a77feefbccbf080
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196468"
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="47dd0-102">Desarrollar un control de formularios Windows Forms compuesto</span><span class="sxs-lookup"><span data-stu-id="47dd0-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="47dd0-103">Puede desarrollar un control de Windows Forms compuesto mediante la combinación de otros controles de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="47dd0-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="47dd0-104">Los controles compuestos que derivan de <xref:System.Web.UI.UserControl> se denominan controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="47dd0-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="47dd0-105">La clase base, <xref:System.Windows.Forms.UserControl>, proporciona el enrutamiento de teclado de los controles secundarios, lo que asegura que puedan recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="47dd0-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="47dd0-106">Para obtener un ejemplo de un control de usuario, consulte el <xref:System.Windows.Forms.UserControl> en [Cómo: Aplicar atributos en controles de formularios Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="47dd0-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="47dd0-107">El Diseñador de Windows Forms en Visual Studio proporciona compatibilidad enriquecida en tiempo de diseño para la creación de controles de usuario.</span><span class="sxs-lookup"><span data-stu-id="47dd0-107">The Windows Forms designer in Visual Studio provides rich design-time support for authoring user controls.</span></span>  
  
-   [<span data-ttu-id="47dd0-108">Cómo: Mostrar un Control en la elija el cuadro de diálogo de elementos de cuadro de herramientas</span><span class="sxs-lookup"><span data-stu-id="47dd0-108">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
  
-   [<span data-ttu-id="47dd0-109">Tutorial: Serializar colecciones de tipos estándar con DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="47dd0-109">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](serializing-collections-designerserializationvisibilityattribute.md)  
  
-   [<span data-ttu-id="47dd0-110">Tutorial: Heredar de un Control de Windows Forms con VisualC#</span><span class="sxs-lookup"><span data-stu-id="47dd0-110">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="47dd0-111">Cómo: Proporcionar un mapa de bits del cuadro de herramientas para un Control</span><span class="sxs-lookup"><span data-stu-id="47dd0-111">How to: Provide a Toolbox Bitmap for a Control</span></span>](how-to-provide-a-toolbox-bitmap-for-a-control.md)  
  
-   [<span data-ttu-id="47dd0-112">Cómo: Heredar de Windows existente controles de formularios</span><span class="sxs-lookup"><span data-stu-id="47dd0-112">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)  
  
-   [<span data-ttu-id="47dd0-113">Tutorial: Depurar controles personalizados de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="47dd0-113">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
  
-   [<span data-ttu-id="47dd0-114">Cómo: Heredar de la clase de Control</span><span class="sxs-lookup"><span data-stu-id="47dd0-114">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)  
  
-   [<span data-ttu-id="47dd0-115">Cómo: Probar el comportamiento de tiempo de ejecución de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="47dd0-115">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
  
-   [<span data-ttu-id="47dd0-116">Cómo: Alinear un Control con los bordes de formularios en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="47dd0-116">How to: Align a Control to the Edges of Forms at Design Time</span></span>](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
  
-   [<span data-ttu-id="47dd0-117">Cómo: Heredar de la clase UserControl</span><span class="sxs-lookup"><span data-stu-id="47dd0-117">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)  
  
-   [<span data-ttu-id="47dd0-118">Cómo: Crear controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="47dd0-118">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)  
  
-   [<span data-ttu-id="47dd0-119">Cómo: Crear controles compuestos</span><span class="sxs-lookup"><span data-stu-id="47dd0-119">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)  
  
-   [<span data-ttu-id="47dd0-120">Tutorial: Crear un Control compuesto con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47dd0-120">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="47dd0-121">Tutorial: Crear un Control compuesto con VisualC#</span><span class="sxs-lookup"><span data-stu-id="47dd0-121">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
  
-   [<span data-ttu-id="47dd0-122">Tutorial: Heredar de un Control de Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="47dd0-122">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
  
-   [<span data-ttu-id="47dd0-123">Tutorial: Crear un Control de Windows Forms que aproveche las características de tiempo de diseño de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="47dd0-123">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
  
-   <span data-ttu-id="47dd0-124">[Cómo: Crear un Control de Windows Forms que aproveche las características en tiempo de diseño](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="47dd0-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/307hck25(v=vs.120))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47dd0-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="47dd0-125">See also</span></span>

- [<span data-ttu-id="47dd0-126">Cómo: Aplicar atributos en controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="47dd0-126">How to: Apply Attributes in Windows Forms Controls</span></span>](how-to-apply-attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="47dd0-127">Desarrollar controles personalizados de Windows Forms con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="47dd0-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="47dd0-128">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="47dd0-128">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
