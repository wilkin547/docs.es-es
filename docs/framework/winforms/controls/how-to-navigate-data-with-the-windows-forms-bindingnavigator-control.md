---
title: Procedimiento para explorar datos con el control BindingNavigator de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingNavigator control [Windows Forms], navigating data
- data [Windows Forms], navigating
- data navigation
- examples [Windows Forms], BindingNavigator control
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
ms.openlocfilehash: 0c2fdf820b9b42a592c422cf77362598c5e5eed7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913606"
---
# <a name="how-to-navigate-data-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="99ee8-102">Procedimiento para explorar datos con el control BindingNavigator de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="99ee8-102">How to: Navigate Data with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="99ee8-103">La incorporación del control <xref:System.Windows.Forms.BindingNavigator> de Windows Forms permite a los desarrolladores proporcionar a los usuarios finales una sencilla interfaz de usuario de navegación y manipulación de datos en los formularios que creen.</span><span class="sxs-lookup"><span data-stu-id="99ee8-103">The advent of the <xref:System.Windows.Forms.BindingNavigator> control in Windows Forms enables developers to provide end users with a simple data navigation and manipulation user interface on the forms they create.</span></span>  
  
 <span data-ttu-id="99ee8-104">El control <xref:System.Windows.Forms.BindingNavigator> es un control <xref:System.Windows.Forms.ToolStrip> con botones preconfigurados para navegar al registro primero, último, anterior y siguiente en un conjunto de datos, así como botones para agregar y eliminar registros.</span><span class="sxs-lookup"><span data-stu-id="99ee8-104">The <xref:System.Windows.Forms.BindingNavigator> control is a <xref:System.Windows.Forms.ToolStrip> control with buttons preconfigured for navigation to the first, last, next, and previous record in a data set, as well as buttons to add and delete records.</span></span> <span data-ttu-id="99ee8-105">Agregar botones al control <xref:System.Windows.Forms.BindingNavigator> es fácil porque es un control <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="99ee8-105">Adding buttons to the <xref:System.Windows.Forms.BindingNavigator> control is easy, because it is a <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="99ee8-106">Para obtener ejemplos, vea [Cómo: Agregar una carga, guardar y cancelar botones a la Windows Forms Control BindingNavigator](load-save-and-cancel-bindingnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="99ee8-106">For examples, see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](load-save-and-cancel-bindingnavigator.md).</span></span>  
  
 <span data-ttu-id="99ee8-107">Por cada botón del control <xref:System.Windows.Forms.BindingNavigator> hay un miembro correspondiente del componente <xref:System.Windows.Forms.BindingSource> que permite la misma funcionalidad mediante programación.</span><span class="sxs-lookup"><span data-stu-id="99ee8-107">For each button on the <xref:System.Windows.Forms.BindingNavigator> control, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically allows the same functionality.</span></span> <span data-ttu-id="99ee8-108">Por ejemplo, el botón <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> corresponde al método <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> del componente <xref:System.Windows.Forms.BindingSource>, el botón <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> corresponde al método <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A>, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="99ee8-108">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span> <span data-ttu-id="99ee8-109">Como resultado, habilitar el control <xref:System.Windows.Forms.BindingNavigator> para navegar por los registros de datos es tan sencillo como establecer la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> en el componente <xref:System.Windows.Forms.BindingSource> correspondiente en el formulario.</span><span class="sxs-lookup"><span data-stu-id="99ee8-109">As a result, enabling the <xref:System.Windows.Forms.BindingNavigator> control to navigate data records is a simple as setting its <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the appropriate <xref:System.Windows.Forms.BindingSource> component on the form.</span></span>  
  
### <a name="to-set-up-the-bindingnavigator-control"></a><span data-ttu-id="99ee8-110">Para configurar el control BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="99ee8-110">To set up the BindingNavigator control</span></span>  
  
1. <span data-ttu-id="99ee8-111">Agregue un componente <xref:System.Windows.Forms.BindingSource> llamado `bindingSource1` y dos controles <xref:System.Windows.Forms.TextBox> llamados `textBox1` y `textBox2`.</span><span class="sxs-lookup"><span data-stu-id="99ee8-111">Add a <xref:System.Windows.Forms.BindingSource> component named `bindingSource1` and two <xref:System.Windows.Forms.TextBox> controls named `textBox1` and `textBox2`.</span></span>  
  
2. <span data-ttu-id="99ee8-112">Enlace `bindingSource1` a los datos y los controles de cuadro de texto a `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="99ee8-112">Bind `bindingSource1` to data, and the textbox controls to `bindingSource1`.</span></span> <span data-ttu-id="99ee8-113">Para ello, pegue el siguiente código en el formulario y llame a `LoadData` desde el constructor del formulario o al método de control de eventos <xref:System.Windows.Forms.Form.Load>.</span><span class="sxs-lookup"><span data-stu-id="99ee8-113">To do this, paste the following code into your form and call `LoadData` from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="99ee8-114">Agregue un control <xref:System.Windows.Forms.BindingNavigator> llamado `bindingNavigator1` al formulario.</span><span class="sxs-lookup"><span data-stu-id="99ee8-114">Add a <xref:System.Windows.Forms.BindingNavigator> control named `bindingNavigator1` to your form.</span></span>  
  
4. <span data-ttu-id="99ee8-115">Establezca la propiedad <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> de `bindingNavigator1` en `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="99ee8-115">Set the <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property for `bindingNavigator1` to `bindingSource1`.</span></span> <span data-ttu-id="99ee8-116">Puede hacerlo con el diseñador o en el código.</span><span class="sxs-lookup"><span data-stu-id="99ee8-116">You can do this with the designer or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="99ee8-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99ee8-117">Example</span></span>  
 <span data-ttu-id="99ee8-118">El ejemplo de código siguiente es el ejemplo completo de los pasos enumerados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="99ee8-118">The following code example is the complete example for the steps listed previously.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99ee8-119">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="99ee8-119">Compiling the Code</span></span>  
 <span data-ttu-id="99ee8-120">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="99ee8-120">This example requires:</span></span>  
  
-   <span data-ttu-id="99ee8-121">Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.Xml.</span><span class="sxs-lookup"><span data-stu-id="99ee8-121">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="99ee8-122">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="99ee8-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="99ee8-123">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="99ee8-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ee8-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="99ee8-124">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="99ee8-125">BindingNavigator (control)</span><span class="sxs-lookup"><span data-stu-id="99ee8-125">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="99ee8-126">Control ToolStrip</span><span class="sxs-lookup"><span data-stu-id="99ee8-126">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
