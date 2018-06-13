---
title: 'Cómo: Alojar controles en celdas DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 730a0677dbc405617c7075402ba0c20dfbd8724d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534052"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a><span data-ttu-id="bde84-102">Cómo: Alojar controles en celdas DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bde84-102">How to: Host Controls in Windows Forms DataGridView Cells</span></span>
<span data-ttu-id="bde84-103">El control <xref:System.Windows.Forms.DataGridView> proporciona varios tipos de columna, permitiendo a sus usuarios escribir y editar valores de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="bde84-103">The <xref:System.Windows.Forms.DataGridView> control provides several column types, enabling your users to enter and edit values in a variety of ways.</span></span> <span data-ttu-id="bde84-104">No obstante, si estos tipos de columna no satisfacen sus necesidades de entrada de datos, puede crear sus propios tipos de columna con celdas que alojen los controles que elija.</span><span class="sxs-lookup"><span data-stu-id="bde84-104">If these column types do not meet your data-entry needs, however, you can create your own column types with cells that host controls of your choosing.</span></span> <span data-ttu-id="bde84-105">Para ello, debe definir clases que deriven de <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="bde84-105">To do this, you must define classes that derive from <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewCell>.</span></span> <span data-ttu-id="bde84-106">También debe definir una clase que derive de <xref:System.Windows.Forms.Control> e implemente la interfaz <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="bde84-106">You must also define a class that derives from <xref:System.Windows.Forms.Control> and implements the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
 <span data-ttu-id="bde84-107">El ejemplo de código siguiente muestra cómo crear una columna de calendario.</span><span class="sxs-lookup"><span data-stu-id="bde84-107">The following code example shows how to create a calendar column.</span></span> <span data-ttu-id="bde84-108">Las celdas de esta columna muestran fechas en celdas de cuadro de texto normales, pero cuando el usuario edita una celda, aparece un control <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="bde84-108">The cells of this column display dates in ordinary text box cells, but when the user edits a cell, a <xref:System.Windows.Forms.DateTimePicker> control appears.</span></span> <span data-ttu-id="bde84-109">Para evitar tener que implementar nuevamente la funcionalidad de visualización de cuadro de texto, la clase `CalendarCell` deriva de la clase <xref:System.Windows.Forms.DataGridViewTextBoxCell>, en lugar de heredar directamente la clase <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="bde84-109">In order to avoid having to implement text box display functionality again, the `CalendarCell` class derives from the <xref:System.Windows.Forms.DataGridViewTextBoxCell> class rather than inheriting the <xref:System.Windows.Forms.DataGridViewCell> class directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bde84-110">Al derivar de <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> y agregar nuevas propiedades a la clase derivada, asegúrese de invalidar el método `Clone` para copiar las nuevas propiedades durante las operaciones de clonación.</span><span class="sxs-lookup"><span data-stu-id="bde84-110">When you derive from <xref:System.Windows.Forms.DataGridViewCell> or <xref:System.Windows.Forms.DataGridViewColumn> and add new properties to the derived class, be sure to override the `Clone` method to copy the new properties during cloning operations.</span></span> <span data-ttu-id="bde84-111">También debe llamar al método `Clone` de la clase base para copiar las propiedades de la clase base a la nueva celda o columna.</span><span class="sxs-lookup"><span data-stu-id="bde84-111">You should also call the base class's `Clone` method so that the properties of the base class are copied to the new cell or column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bde84-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bde84-112">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bde84-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="bde84-113">Compiling the Code</span></span>  
 <span data-ttu-id="bde84-114">El ejemplo siguiente requiere:</span><span class="sxs-lookup"><span data-stu-id="bde84-114">The following example requires:</span></span>  
  
-   <span data-ttu-id="bde84-115">Referencias a los ensamblados System y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="bde84-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bde84-116">Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="bde84-116">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bde84-117">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="bde84-117">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="bde84-118">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="bde84-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bde84-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bde84-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <xref:System.Windows.Forms.DateTimePicker>  
 [<span data-ttu-id="bde84-120">Personalizar el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bde84-120">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="bde84-121">Arquitectura del control DataGridView</span><span class="sxs-lookup"><span data-stu-id="bde84-121">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [<span data-ttu-id="bde84-122">Tipos de columnas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bde84-122">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
