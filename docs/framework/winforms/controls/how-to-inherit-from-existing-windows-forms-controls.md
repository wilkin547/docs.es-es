---
title: para heredar desde controles existentes
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
ms.openlocfilehash: b0e0053816efde349c7e4d13d03bef5f8801c667
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849385"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="003ff-102">Cómo: Heredar de controles de formularios Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="003ff-102">How to: Inherit from Existing Windows Forms Controls</span></span>

<span data-ttu-id="003ff-103">Si desea ampliar la funcionalidad de un control existente, puede crear un control derivado a partir de un control existente a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="003ff-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="003ff-104">Al heredar a partir de un control existente, hereda toda la funcionalidad y las propiedades visuales del control.</span><span class="sxs-lookup"><span data-stu-id="003ff-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="003ff-105">Por ejemplo, si estuviera creando un <xref:System.Windows.Forms.Button>control heredado de , el nuevo <xref:System.Windows.Forms.Button> control se vería y actuaría exactamente como un control estándar.</span><span class="sxs-lookup"><span data-stu-id="003ff-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="003ff-106">A continuación, podría extender o modificar la funcionalidad del nuevo control mediante la implementación de métodos y propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="003ff-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="003ff-107">En algunos controles, también puede cambiar la apariencia visual <xref:System.Windows.Forms.Control.OnPaint%2A> del control heredado reemplazando su método.</span><span class="sxs-lookup"><span data-stu-id="003ff-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="003ff-108">Para crear un control heredado</span><span class="sxs-lookup"><span data-stu-id="003ff-108">To create an inherited control</span></span>

1. <span data-ttu-id="003ff-109">En Visual Studio, cree un nuevo proyecto **de aplicación de formularios Windows Forms.**</span><span class="sxs-lookup"><span data-stu-id="003ff-109">In Visual Studio, create a new **Windows Forms Application** project.</span></span>

1. <span data-ttu-id="003ff-110">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="003ff-110">From the **Project** menu, choose **Add New Item**.</span></span>

    <span data-ttu-id="003ff-111">Aparecerá el cuadro de diálogo **Agregar nuevo elemento** .</span><span class="sxs-lookup"><span data-stu-id="003ff-111">The **Add New Item** dialog box appears.</span></span>

1. <span data-ttu-id="003ff-112">En el cuadro de diálogo **Agregar nuevo elemento**, haga doble clic en **Control personalizado**.</span><span class="sxs-lookup"><span data-stu-id="003ff-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

    <span data-ttu-id="003ff-113">Se agrega un nuevo control personalizado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="003ff-113">A new custom control is added to your project.</span></span>

1. <span data-ttu-id="003ff-114">Si está utilizando:</span><span class="sxs-lookup"><span data-stu-id="003ff-114">If you're using:</span></span>

    - <span data-ttu-id="003ff-115">Visual Basic, en la parte superior del **Explorador**de soluciones , haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="003ff-115">Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="003ff-116">Expanda CustomControl1.vb y, a continuación, abra CustomControl1.Designer.vb en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="003ff-116">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>
    - <span data-ttu-id="003ff-117">Abrir CustomControl1.cs en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="003ff-117">C#, open CustomControl1.cs in the Code Editor.</span></span>

1. <span data-ttu-id="003ff-118">Busque la declaración de <xref:System.Windows.Forms.Control>clase, que hereda de .</span><span class="sxs-lookup"><span data-stu-id="003ff-118">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

1. <span data-ttu-id="003ff-119">Cambie la clase base para el control a partir del que desee heredar.</span><span class="sxs-lookup"><span data-stu-id="003ff-119">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="003ff-120">Por ejemplo, si desea <xref:System.Windows.Forms.Button>heredar de , cambie la declaración de clase a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="003ff-120">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. <span data-ttu-id="003ff-121">Si está utilizando Visual Basic, guarde y cierre CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="003ff-121">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="003ff-122">Abra CustomControl1.vb en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="003ff-122">Open CustomControl1.vb in the Code Editor.</span></span>

1. <span data-ttu-id="003ff-123">Implemente los métodos o propiedades personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="003ff-123">Implement any custom methods or properties that your control will incorporate.</span></span>

1. <span data-ttu-id="003ff-124">Si desea modificar la apariencia gráfica del <xref:System.Windows.Forms.Control.OnPaint%2A> control, invalide el método.</span><span class="sxs-lookup"><span data-stu-id="003ff-124">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="003ff-125">La <xref:System.Windows.Forms.Control.OnPaint%2A> invalidación no le permitirá modificar la apariencia de todos los controles.</span><span class="sxs-lookup"><span data-stu-id="003ff-125">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="003ff-126">Los controles que tienen toda su pintura realizada <xref:System.Windows.Forms.TextBox>por Windows <xref:System.Windows.Forms.Control.OnPaint%2A> (por ejemplo, ) nunca llaman a su método y, por lo tanto, nunca usarán el código personalizado.</span><span class="sxs-lookup"><span data-stu-id="003ff-126">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="003ff-127">Consulte la documentación de ayuda para el control determinado <xref:System.Windows.Forms.Control.OnPaint%2A> que desea modificar para ver si el método está disponible.</span><span class="sxs-lookup"><span data-stu-id="003ff-127">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="003ff-128">Para obtener una lista de todos los controles de Windows Form, vea el artículo sobre [controles que se utilizan en Windows Forms](controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="003ff-128">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="003ff-129">Si un control <xref:System.Windows.Forms.Control.OnPaint%2A> no tiene la lista como un método miembro, no puede modificar su apariencia reemplazando este método.</span><span class="sxs-lookup"><span data-stu-id="003ff-129">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="003ff-130">Para información sobre el dibujo personalizado, vea [Dibujo y representación personalizados de controles](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="003ff-130">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

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

1. <span data-ttu-id="003ff-131">Guarde y pruebe el control.</span><span class="sxs-lookup"><span data-stu-id="003ff-131">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="003ff-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="003ff-132">See also</span></span>

- [<span data-ttu-id="003ff-133">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="003ff-133">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="003ff-134">Cómo: Heredar de la clase control</span><span class="sxs-lookup"><span data-stu-id="003ff-134">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="003ff-135">Cómo: Heredar de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="003ff-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="003ff-136">Cómo: Crear controles para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="003ff-136">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="003ff-137">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="003ff-137">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="003ff-138">Tutorial: Heredar de un control de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="003ff-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
