---
title: Filtrar para permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], copying to Clipboard
- DataGridView control [Windows Forms], copying multiple cells
- data grids [Windows Forms], copying multiple cells
- Clipboard [Windows Forms], copying multiple cells
ms.assetid: fd0403b2-d0e3-4ae0-839c-0f737e1eb4a9
ms.openlocfilehash: f7b6c37db0935dae703e9641b2c2605b2ec88126
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142238"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="9a5a9-102">Filtrar para permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a5a9-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9a5a9-103">Cuando se habilita la copia de celdas, los datos de su control <xref:System.Windows.Forms.DataGridView> son más fácilmente accesibles para otras aplicaciones mediante el <xref:System.Windows.Forms.Clipboard>.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="9a5a9-104">Los valores de las celdas seleccionadas se convierten en cadenas y se agregan al Portapapeles como valores de texto delimitados por tabulaciones para pegarlos en aplicaciones como el Bloc de notas y Excel, y como una tabla con formato HTML para pegarlos en aplicaciones como Word.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="9a5a9-105">Puede configurar la copia de celdas para copiar solo valores de celda, para incluir el texto de encabezado de filas y columnas en los datos del Portapapeles, o para incluir el texto de encabezado solo cuando los usuarios seleccionan filas o columnas completas.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="9a5a9-106">Según el modo de selección, los usuarios pueden seleccionar varios grupos de celdas desconectados.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="9a5a9-107">Cuando el usuario copia las celdas en el Portapapeles, no se copian las filas y columnas que no tienen celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="9a5a9-108">Todas las demás filas o columnas se convierten en filas y columnas de la tabla de datos que se copia en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="9a5a9-109">Las celdas no seleccionadas en estas filas o columnas se copian como marcadores de posición en blanco en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="9a5a9-110">Para habilitar la copia de celdas</span><span class="sxs-lookup"><span data-stu-id="9a5a9-110">To enable cell copying</span></span>  
  
-   <span data-ttu-id="9a5a9-111">Establecer la propiedad <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="9a5a9-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a5a9-112">Example</span></span>  
 <span data-ttu-id="9a5a9-113">En el ejemplo de código completo siguiente se muestra cómo se copian las celdas en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="9a5a9-114">Este ejemplo incluye un botón que copia las celdas seleccionadas en el Portapapeles usando el método <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> y muestra el contenido del Portapapeles en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a5a9-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9a5a9-115">Compiling the Code</span></span>  
 <span data-ttu-id="9a5a9-116">Este código requiere:</span><span class="sxs-lookup"><span data-stu-id="9a5a9-116">This code requires:</span></span>  
  
-   <span data-ttu-id="9a5a9-117">Referencias a los ensamblados N:System y N:System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="9a5a9-118">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a9-118">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9a5a9-119">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="9a5a9-119">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5a9-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a5a9-120">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [<span data-ttu-id="9a5a9-121">Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a5a9-121">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
