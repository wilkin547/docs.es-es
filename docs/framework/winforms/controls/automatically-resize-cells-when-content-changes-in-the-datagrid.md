---
title: 'Cómo: Cambiar automáticamente el tamaño de las celdas cuando se modifica el contenido en un control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: f93d2ddc0e60c6d66efb43fe672f4c3076af85f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525796"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e54f8-102">Cómo: Cambiar automáticamente el tamaño de las celdas cuando se modifica el contenido en un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e54f8-102">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e54f8-103">Puede configurar el control <xref:System.Windows.Forms.DataGridView> para que ajuste el tamaño de sus filas, columnas y encabezados automáticamente siempre que cambie el contenido, para que las celdas sean siempre lo suficientemente grandes para mostrar los valores sin recortarlos.</span><span class="sxs-lookup"><span data-stu-id="e54f8-103">You can configure the <xref:System.Windows.Forms.DataGridView> control to resize its rows, columns, and headers automatically whenever content changes, so that cells are always large enough to display their values without clipping.</span></span>  
  
 <span data-ttu-id="e54f8-104">Tiene muchas opciones para restringir qué celdas se usan para determinar los nuevos tamaños.</span><span class="sxs-lookup"><span data-stu-id="e54f8-104">You have many options to restrict which cells are used to determine the new sizes.</span></span> <span data-ttu-id="e54f8-105">Por ejemplo, puede configurar el control para ajustar automáticamente el ancho de sus columnas basándose solo en los valores de las filas que se muestran actualmente.</span><span class="sxs-lookup"><span data-stu-id="e54f8-105">For example, you can configure the control to automatically resize the width of its columns based only on the values in rows that are currently displayed.</span></span> <span data-ttu-id="e54f8-106">De esta forma evita la falta de eficiencia al trabajar con grandes cantidades de filas, aunque en este caso quizás quiera usar métodos de ajuste de tamaño como <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> para ajustar el tamaño en el momento que elija.</span><span class="sxs-lookup"><span data-stu-id="e54f8-106">With this, you can avoid inefficiency when working with large numbers of rows, although in this case, you might want to use sizing methods such as <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> to adjust sizes at times of your choosing.</span></span>  
  
 <span data-ttu-id="e54f8-107">Para obtener más información sobre el cambio de tamaño automático, consulte [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e54f8-107">For more information about automatic resizing, see [Sizing Options in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="e54f8-108">El ejemplo de código siguiente muestra las opciones disponibles para el ajuste de tamaño automático.</span><span class="sxs-lookup"><span data-stu-id="e54f8-108">The following code example demonstrates the options available for automatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e54f8-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e54f8-109">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e54f8-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e54f8-110">Compiling the Code</span></span>  
 <span data-ttu-id="e54f8-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e54f8-111">This example requires:</span></span>  
  
-   <span data-ttu-id="e54f8-112">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e54f8-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="e54f8-113">Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e54f8-113">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e54f8-114">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="e54f8-114">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="e54f8-115">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="e54f8-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e54f8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e54f8-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>  
 <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>  
 <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>  
 [<span data-ttu-id="e54f8-117">Cambiar el tamaño de columnas y filas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e54f8-117">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="e54f8-118">Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e54f8-118">Sizing Options in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="e54f8-119">Cambiar mediante programación el tamaño de las celdas para ajustar el contenido en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e54f8-119">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
