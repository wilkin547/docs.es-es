---
title: "Cómo: Heredar de controles de formularios Windows Forms existentes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6e6133576d65e95ac42a1680de152d84892e2c5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="94cc6-102">Cómo: Heredar de controles de formularios Windows Forms existentes</span><span class="sxs-lookup"><span data-stu-id="94cc6-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="94cc6-103">Si desea ampliar la funcionalidad de un control existente, puede crear un control derivado a partir de un control existente a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="94cc6-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="94cc6-104">Al heredar a partir de un control existente, hereda toda la funcionalidad y las propiedades visuales del control.</span><span class="sxs-lookup"><span data-stu-id="94cc6-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="94cc6-105">Por ejemplo, si estuviera creando un control que se hereda de <xref:System.Windows.Forms.Button>, el nuevo control tendría un aspecto y actúan como exactamente un estándar <xref:System.Windows.Forms.Button> control.</span><span class="sxs-lookup"><span data-stu-id="94cc6-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="94cc6-106">A continuación, podría extender o modificar la funcionalidad del nuevo control mediante la implementación de métodos y propiedades personalizados.</span><span class="sxs-lookup"><span data-stu-id="94cc6-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="94cc6-107">En algunos controles, también puede cambiar la apariencia visual del control heredado reemplazando su <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="94cc6-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94cc6-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="94cc6-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="94cc6-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="94cc6-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="94cc6-110">Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="94cc6-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="94cc6-111">Para crear un control heredado</span><span class="sxs-lookup"><span data-stu-id="94cc6-111">To create an inherited control</span></span>  
  
1.  <span data-ttu-id="94cc6-112">Cree un nuevo proyecto de  **aplicación de Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="94cc6-112">Create a new **Windows Forms Application** project.</span></span>  
  
2.  <span data-ttu-id="94cc6-113">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="94cc6-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="94cc6-114">Aparecerá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="94cc6-114">The **Add New Item** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="94cc6-115">En el cuadro de diálogo **Agregar nuevo elemento**, haga doble clic en **Control personalizado**.</span><span class="sxs-lookup"><span data-stu-id="94cc6-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="94cc6-116">Se agrega un nuevo control personalizado al proyecto.</span><span class="sxs-lookup"><span data-stu-id="94cc6-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="94cc6-117">Si usa Visual Basic, en la parte superior del **Explorador de soluciones**, haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="94cc6-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="94cc6-118">Expanda CustomControl1.vb y, a continuación, abra CustomControl1.Designer.vb en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="94cc6-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5.  <span data-ttu-id="94cc6-119">Si está utilizando C#, abra CustomControl1.cs en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="94cc6-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6.  <span data-ttu-id="94cc6-120">Busque la declaración de clase que hereda de <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="94cc6-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7.  <span data-ttu-id="94cc6-121">Cambie la clase base para el control a partir del que desee heredar.</span><span class="sxs-lookup"><span data-stu-id="94cc6-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="94cc6-122">Por ejemplo, si desea heredar de <xref:System.Windows.Forms.Button>, cambie la declaración de clase a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="94cc6-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  <span data-ttu-id="94cc6-123">Si está utilizando Visual Basic, guarde y cierre CustomControl1.Designer.vb.</span><span class="sxs-lookup"><span data-stu-id="94cc6-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="94cc6-124">Abra CustomControl1.vb en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="94cc6-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="94cc6-125">Implemente los métodos o propiedades personalizados que vaya a incorporar el control.</span><span class="sxs-lookup"><span data-stu-id="94cc6-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="94cc6-126">Si desea modificar la apariencia gráfica del control, reemplace el <xref:System.Windows.Forms.Control.OnPaint%2A> método.</span><span class="sxs-lookup"><span data-stu-id="94cc6-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="94cc6-127">Reemplazar <xref:System.Windows.Forms.Control.OnPaint%2A> no le permitirá modificar la apariencia de todos los controles.</span><span class="sxs-lookup"><span data-stu-id="94cc6-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="94cc6-128">Los controles que tienen todas su dibujo realizado por Windows (por ejemplo, <xref:System.Windows.Forms.TextBox>) nunca llaman a su <xref:System.Windows.Forms.Control.OnPaint%2A> (método) y, por tanto, usará nunca el código personalizado.</span><span class="sxs-lookup"><span data-stu-id="94cc6-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="94cc6-129">Consulte la documentación de ayuda para un control determinado que desea modificar para ver si el <xref:System.Windows.Forms.Control.OnPaint%2A> método está disponible.</span><span class="sxs-lookup"><span data-stu-id="94cc6-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="94cc6-130">Para obtener una lista de todos los controles de Windows Form, vea el artículo sobre [controles que se utilizan en Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="94cc6-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="94cc6-131">Si no dispone de un control <xref:System.Windows.Forms.Control.OnPaint%2A> aparece como un método de miembro, no se puede modificar su apariencia invalidando este método.</span><span class="sxs-lookup"><span data-stu-id="94cc6-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="94cc6-132">Para información sobre el dibujo personalizado, vea [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="94cc6-132">For more information about custom painting, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
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
  
11. <span data-ttu-id="94cc6-133">Guarde y pruebe el control.</span><span class="sxs-lookup"><span data-stu-id="94cc6-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94cc6-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="94cc6-134">See Also</span></span>  
 [<span data-ttu-id="94cc6-135">Variedades de controles personalizados</span><span class="sxs-lookup"><span data-stu-id="94cc6-135">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="94cc6-136">Cómo: Heredar de la clase control</span><span class="sxs-lookup"><span data-stu-id="94cc6-136">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="94cc6-137">Cómo: Heredar de una clase UserControl</span><span class="sxs-lookup"><span data-stu-id="94cc6-137">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="94cc6-138">Cómo: Crear controles para Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94cc6-138">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="94cc6-139">Solucionar problemas de controladores de eventos heredados en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94cc6-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="94cc6-140">Tutorial: Heredar de un control de Windows Forms con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94cc6-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="94cc6-141">Tutorial: Heredar de un control de Windows Forms con Visual C#</span><span class="sxs-lookup"><span data-stu-id="94cc6-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
