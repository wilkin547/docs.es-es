---
title: Filtrar para cambiar mediante programación el tamaño de las celdas para ajustar el contenido en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: e8240d1d5ac9784bd33d65e4c79c3d5ac7595657
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138637"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0aa64-102">Filtrar para cambiar mediante programación el tamaño de las celdas para ajustar el contenido en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0aa64-102">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0aa64-103">Puede usar los métodos <xref:System.Windows.Forms.DataGridView> del control para cambiar el tamaño de las filas, columnas y encabezados para que muestren sus valores completos sin truncarlos.</span><span class="sxs-lookup"><span data-stu-id="0aa64-103">You can use the <xref:System.Windows.Forms.DataGridView> control methods to resize rows, columns, and headers so that they display their entire values without truncation.</span></span> <span data-ttu-id="0aa64-104">Puede usar estos métodos para cambiar el tamaño de los elementos <xref:System.Windows.Forms.DataGridView> cuando elija.</span><span class="sxs-lookup"><span data-stu-id="0aa64-104">You can use these methods to resize <xref:System.Windows.Forms.DataGridView> elements at times of your choosing.</span></span> <span data-ttu-id="0aa64-105">También puede configurar el control para cambiar el tamaño de estos elementos automáticamente cada vez que cambie el contenido.</span><span class="sxs-lookup"><span data-stu-id="0aa64-105">Alternately, you can configure the control to resize these elements automatically whenever content changes.</span></span> <span data-ttu-id="0aa64-106">Sin embargo, esto puede resultar poco eficiente si trabaja con grandes conjuntos de datos o si los datos cambian con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="0aa64-106">This can be inefficient, however, when you are working with large data sets or when your data changes frequently.</span></span> <span data-ttu-id="0aa64-107">Para obtener más información, consulte [opciones de ajuste de tamaño en el DataGridView Control de formularios de Windows](sizing-options-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0aa64-107">For more information, see [Sizing Options in the Windows Forms DataGridView Control](sizing-options-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="0aa64-108">Normalmente, ajustará los elementos <xref:System.Windows.Forms.DataGridView> mediante programación para ajustar su contenido solo cuando cargue nuevos datos de un origen de datos o cuando el usuario edite un valor.</span><span class="sxs-lookup"><span data-stu-id="0aa64-108">Typically, you will programmatically adjust <xref:System.Windows.Forms.DataGridView> elements to fit their content only when you load new data from a data source or when the user has edited a value.</span></span> <span data-ttu-id="0aa64-109">Esto es útil para optimizar el rendimiento, pero también es útil si quiere permitir que los usuarios cambien manualmente el tamaño de las filas y columnas con el mouse.</span><span class="sxs-lookup"><span data-stu-id="0aa64-109">This is useful to optimize performance, but it is also useful when you want to enable your users to manually resize rows and columns with the mouse.</span></span>  
  
 <span data-ttu-id="0aa64-110">El ejemplo de código siguiente muestra las opciones disponibles para cambiar el tamaño mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0aa64-110">The following code example demonstrates the options available to you for programmatic resizing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0aa64-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0aa64-111">Example</span></span>  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0aa64-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="0aa64-112">Compiling the Code</span></span>  
 <span data-ttu-id="0aa64-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="0aa64-113">This example requires:</span></span>  
  
-   <span data-ttu-id="0aa64-114">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="0aa64-114">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0aa64-115">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0aa64-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0aa64-116">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="0aa64-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0aa64-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0aa64-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [<span data-ttu-id="0aa64-118">Cambiar el tamaño de columnas y filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0aa64-118">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0aa64-119">Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0aa64-119">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0aa64-120">Filtrar para cambiar automáticamente el tamaño de las celdas cuando se modifica el contenido en un control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0aa64-120">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
