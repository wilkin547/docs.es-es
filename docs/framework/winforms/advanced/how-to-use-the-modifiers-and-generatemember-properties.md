---
title: Procedimiento para usar las propiedades Modifiers y GenerateMember
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 6194ef288bd43267c2b00fa6d7c6250e90b37c75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778864"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a><span data-ttu-id="e7961-102">Procedimiento para usar las propiedades Modifiers y GenerateMember</span><span class="sxs-lookup"><span data-stu-id="e7961-102">How to: Use the Modifiers and GenerateMember Properties</span></span>
<span data-ttu-id="e7961-103">Cuando se coloca un componente en un formulario de Windows, el entorno de diseño proporciona dos propiedades: `GenerateMember` y `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="e7961-103">When you place a component on a Windows Form, two properties are provided by the design environment: `GenerateMember` and `Modifiers`.</span></span> <span data-ttu-id="e7961-104">El `GenerateMember` propiedad especifica que cuando el Diseñador de Windows Forms genera una variable miembro para un componente.</span><span class="sxs-lookup"><span data-stu-id="e7961-104">The `GenerateMember` property specifies when the Windows Forms Designer generates a member variable for a component.</span></span> <span data-ttu-id="e7961-105">El `Modifiers` propiedad es el modificador de acceso asignado a esa variable de miembro.</span><span class="sxs-lookup"><span data-stu-id="e7961-105">The `Modifiers` property is the access modifier assigned to that member variable.</span></span> <span data-ttu-id="e7961-106">Si el valor de la `GenerateMember` propiedad es `false`, el valor de la `Modifiers` propiedad no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="e7961-106">If the value of the `GenerateMember` property is `false`, the value of the `Modifiers` property has no effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7961-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="e7961-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e7961-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="e7961-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e7961-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e7961-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-specify-whether-a-component-is-a-member-of-the-form"></a><span data-ttu-id="e7961-110">Para especificar si un componente es un miembro del formulario</span><span class="sxs-lookup"><span data-stu-id="e7961-110">To specify whether a component is a member of the form</span></span>  
  
1. <span data-ttu-id="e7961-111">En el Diseñador de formularios de Windows, abra el formulario.</span><span class="sxs-lookup"><span data-stu-id="e7961-111">In the Windows Forms Designer, open your form.</span></span>  
  
2. <span data-ttu-id="e7961-112">Abra el **cuadro de herramientas**y en el formulario, coloque tres <xref:System.Windows.Forms.Button> controles.</span><span class="sxs-lookup"><span data-stu-id="e7961-112">Open the **Toolbox**, and on the form, place three <xref:System.Windows.Forms.Button> controls.</span></span>  
  
3. <span data-ttu-id="e7961-113">Establecer el `GenerateMember` y `Modifiers` propiedades para cada <xref:System.Windows.Forms.Button> control según la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7961-113">Set the `GenerateMember` and `Modifiers` properties for each <xref:System.Windows.Forms.Button> control according to the following table.</span></span>  
  
    |<span data-ttu-id="e7961-114">Nombre del botón</span><span class="sxs-lookup"><span data-stu-id="e7961-114">Button name</span></span>|<span data-ttu-id="e7961-115">Valor de GenerateMember</span><span class="sxs-lookup"><span data-stu-id="e7961-115">GenerateMember value</span></span>|<span data-ttu-id="e7961-116">Valor de modificadores</span><span class="sxs-lookup"><span data-stu-id="e7961-116">Modifiers value</span></span>|  
    |-----------------|--------------------------|---------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|<span data-ttu-id="e7961-117">Sin cambios</span><span class="sxs-lookup"><span data-stu-id="e7961-117">No change</span></span>|  
  
4. <span data-ttu-id="e7961-118">Compile la solución.</span><span class="sxs-lookup"><span data-stu-id="e7961-118">Build the solution.</span></span>  
  
5. <span data-ttu-id="e7961-119">En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="e7961-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
6. <span data-ttu-id="e7961-120">Abra el **Form1** nodo y en el **Editor de código**, abra el **Form1.Designer.vb** o **Form1.Designer.cs** archivo.</span><span class="sxs-lookup"><span data-stu-id="e7961-120">Open the **Form1** node, and in the **Code Editor**,open the **Form1.Designer.vb** or **Form1.Designer.cs** file.</span></span> <span data-ttu-id="e7961-121">Este archivo contiene el código emitido por el Diseñador de formularios de Windows.</span><span class="sxs-lookup"><span data-stu-id="e7961-121">This file contains the code emitted by the Windows Forms Designer.</span></span>  
  
7. <span data-ttu-id="e7961-122">Busque las declaraciones de los tres botones.</span><span class="sxs-lookup"><span data-stu-id="e7961-122">Find the declarations for the three buttons.</span></span> <span data-ttu-id="e7961-123">El ejemplo de código siguiente muestra las diferencias especificadas por el `GenerateMember` y `Modifiers` propiedades.</span><span class="sxs-lookup"><span data-stu-id="e7961-123">The following code example shows the differences specified by the `GenerateMember` and `Modifiers` properties.</span></span>  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  <span data-ttu-id="e7961-124">De forma predeterminada, el Diseñador de formularios de Windows asigna el `private` (`Friend` en Visual Basic) a los controles de contenedor como modificador de <xref:System.Windows.Forms.Panel>.</span><span class="sxs-lookup"><span data-stu-id="e7961-124">By default, the Windows Forms Designer assigns the `private` (`Friend` in Visual Basic) modifier to container controls like <xref:System.Windows.Forms.Panel>.</span></span> <span data-ttu-id="e7961-125">Si la base de <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> tiene un control contenedor, no se aceptarán nuevos objetos secundarios en controles y formularios heredados.</span><span class="sxs-lookup"><span data-stu-id="e7961-125">If your base <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Form> has a container control, it will not accept new children in inherited controls and forms.</span></span> <span data-ttu-id="e7961-126">La solución es cambiar el modificador del control contenedor base para `protected` o `public`.</span><span class="sxs-lookup"><span data-stu-id="e7961-126">The solution is to change the modifier of the base container control to `protected` or `public`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7961-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7961-127">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="e7961-128">Herencia visual de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7961-128">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="e7961-129">Tutorial: Demostración de la herencia Visual</span><span class="sxs-lookup"><span data-stu-id="e7961-129">Walkthrough: Demonstrating Visual Inheritance</span></span>](walkthrough-demonstrating-visual-inheritance.md)
- [<span data-ttu-id="e7961-130">Cómo: Heredar Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e7961-130">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
