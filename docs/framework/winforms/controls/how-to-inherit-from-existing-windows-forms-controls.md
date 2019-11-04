---
title: 'Cómo: Heredar de controles de formularios Windows Forms existentes'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 063f5bb87b6348ee83573cf1506c9fabdaf651ee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460569"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="e038f-102">Cómo: Heredar de controles de formularios Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="e038f-102">How to: Inherit from Existing Windows Forms Controls</span></span>

<span data-ttu-id="e038f-103">Si desea ampliar la funcionalidad de un control existente, puede crear un control derivado a partir de un control existente a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="e038f-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="e038f-104">Al heredar a partir de un control existente, hereda toda la funcionalidad y las propiedades visuales del control.</span><span class="sxs-lookup"><span data-stu-id="e038f-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="e038f-105">Por ejemplo, si estuviera creando un control heredado de <xref:System.Windows.Forms.Button>, el nuevo control tendría un aspecto y actuaría exactamente igual que un control de <xref:System.Windows.Forms.Button> estándar.</span><span class="sxs-lookup"><span data-stu-id="e038f-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="e038f-106">A continuación, podría extender o modificar la funcionalidad del nuevo control mediante la implementación de métodos y propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="e038f-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="e038f-107">En algunos controles, también puede cambiar la apariencia visual del control heredado invalidando su método <xref:System.Windows.Forms.Control.OnPaint%2A>.</span><span class="sxs-lookup"><span data-stu-id="e038f-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="e038f-108">Para crear un control heredado</span><span class="sxs-lookup"><span data-stu-id="e038f-108">To create an inherited control</span></span>

1. <span data-ttu-id="e038f-109">En Visual Studio, cree un nuevo proyecto de **aplicación de Windows Forms** .</span><span class="sxs-lookup"><span data-stu-id="e038f-109">In Visual Studio, create a new **Windows Forms Application** project.</span></span>

1. <span data-ttu-id="e038f-110">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e038f-110">From the **Project** menu, choose **Add New Item**.</span></span>

    <span data-ttu-id="e038f-111">Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="e038f-111">The **Add New Item** dialog box appears.</span></span>

1. <span data-ttu-id="e038f-112">En el cuadro de diálogo **Agregar nuevo elemento**, haga doble clic en **Control personalizado**.</span><span class="sxs-lookup"><span data-stu-id="e038f-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

    <span data-ttu-id="e038f-113">Se agrega un nuevo control personalizado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e038f-113">A new custom control is added to your project.</span></span>

1. <span data-ttu-id="e038f-114">Si usa:</span><span class="sxs-lookup"><span data-stu-id="e038f-114">If you using:</span></span>

    - <span data-ttu-id="e038f-115">Visual Basic, en la parte superior de **Explorador de soluciones**, haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="e038f-115">Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="e038f-116">Expanda CustomControl1.vb y, a continuación, abra CustomControl1.Designer.vb en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="e038f-116">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>
    - <span data-ttu-id="e038f-117">C#, abra CustomControl1.cs en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="e038f-117">C#, open CustomControl1.cs in the Code Editor.</span></span>

1. <span data-ttu-id="e038f-118">Busque la declaración de clase, que hereda de <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="e038f-118">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

1. <span data-ttu-id="e038f-119">Cambie la clase base para el control a partir del que desee heredar.</span><span class="sxs-lookup"><span data-stu-id="e038f-119">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="e038f-120">Por ejemplo, si desea heredar de <xref:System.Windows.Forms.Button>, cambie la declaración de clase a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e038f-120">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. <span data-ttu-id="e038f-121">Si está utilizando Visual Basic, guarde y cierre CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="e038f-121">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="e038f-122">Abra CustomControl1.vb en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="e038f-122">Open CustomControl1.vb in the Code Editor.</span></span>

1. <span data-ttu-id="e038f-123">Implemente los métodos o propiedades personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="e038f-123">Implement any custom methods or properties that your control will incorporate.</span></span>

1. <span data-ttu-id="e038f-124">Si desea modificar la apariencia gráfica del control, invalide el método <xref:System.Windows.Forms.Control.OnPaint%2A>.</span><span class="sxs-lookup"><span data-stu-id="e038f-124">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e038f-125">Reemplazar <xref:System.Windows.Forms.Control.OnPaint%2A> no le permitirá modificar la apariencia de todos los controles.</span><span class="sxs-lookup"><span data-stu-id="e038f-125">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="e038f-126">Los controles que tienen todo su dibujo realizado por Windows (por ejemplo, <xref:System.Windows.Forms.TextBox>) nunca llaman a su método de <xref:System.Windows.Forms.Control.OnPaint%2A> y, por tanto, nunca usarán el código personalizado.</span><span class="sxs-lookup"><span data-stu-id="e038f-126">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="e038f-127">Consulte la documentación de ayuda del control determinado que desea modificar para ver si el método <xref:System.Windows.Forms.Control.OnPaint%2A> está disponible.</span><span class="sxs-lookup"><span data-stu-id="e038f-127">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="e038f-128">Para obtener una lista de todos los controles de Windows Form, vea el artículo sobre [controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e038f-128">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="e038f-129">Si un control no tiene <xref:System.Windows.Forms.Control.OnPaint%2A> enumerado como un método de miembro, no se puede modificar su apariencia invalidando este método.</span><span class="sxs-lookup"><span data-stu-id="e038f-129">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="e038f-130">Para información sobre el dibujo personalizado, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="e038f-130">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. <span data-ttu-id="e038f-131">Guarde y pruebe el control.</span><span class="sxs-lookup"><span data-stu-id="e038f-131">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="e038f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e038f-132">See also</span></span>

- [<span data-ttu-id="e038f-133">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="e038f-133">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="e038f-134">Cómo: Heredar de una clase de control</span><span class="sxs-lookup"><span data-stu-id="e038f-134">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="e038f-135">Cómo: Heredar de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="e038f-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="e038f-136">Cómo: Crear controles de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e038f-136">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="e038f-137">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e038f-137">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="e038f-138">Tutorial: heredar de un control Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e038f-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
