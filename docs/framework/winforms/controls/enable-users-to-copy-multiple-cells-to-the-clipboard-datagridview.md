---
title: Permitir a los usuarios copiar varias celdas en el Portapapeles desde el control DataGridView
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
ms.openlocfilehash: 2bb74a1f0c59b28ab496ce9c89c1c1b5f9d8147b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745777"
---
# <a name="how-to-enable-users-to-copy-multiple-cells-to-the-clipboard-from-the-windows-forms-datagridview-control"></a><span data-ttu-id="96ce6-102">Cómo: Permitir que los usuarios copien varias celdas en el Portapapeles desde el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="96ce6-102">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="96ce6-103">Cuando se habilita la copia de celdas, los datos de su control <xref:System.Windows.Forms.DataGridView> son más fácilmente accesibles para otras aplicaciones mediante el <xref:System.Windows.Forms.Clipboard>.</span><span class="sxs-lookup"><span data-stu-id="96ce6-103">When you enable cell copying, you make the data in your <xref:System.Windows.Forms.DataGridView> control easily accessible to other applications through the <xref:System.Windows.Forms.Clipboard>.</span></span> <span data-ttu-id="96ce6-104">Los valores de las celdas seleccionadas se convierten en cadenas y se agregan al Portapapeles como valores de texto delimitados por tabulaciones para pegarlos en aplicaciones como el Bloc de notas y Excel, y como una tabla con formato HTML para pegarlos en aplicaciones como Word.</span><span class="sxs-lookup"><span data-stu-id="96ce6-104">The values of the selected cells are converted to strings and added to the Clipboard as tab-delimited text values for pasting into applications like Notepad and Excel, and as an HTML-formatted table for pasting into applications like Word.</span></span>  
  
 <span data-ttu-id="96ce6-105">Puede configurar la copia de celdas para copiar solo valores de celda, para incluir el texto de encabezado de filas y columnas en los datos del Portapapeles, o para incluir el texto de encabezado solo cuando los usuarios seleccionan filas o columnas completas.</span><span class="sxs-lookup"><span data-stu-id="96ce6-105">You can configure cell copying to copy cell values only, to include row and column header text in the Clipboard data, or to include header text only when users select entire rows or columns.</span></span>  
  
 <span data-ttu-id="96ce6-106">Según el modo de selección, los usuarios pueden seleccionar varios grupos de celdas desconectados.</span><span class="sxs-lookup"><span data-stu-id="96ce6-106">Depending on the selection mode, users can select multiple disconnected groups of cells.</span></span> <span data-ttu-id="96ce6-107">Cuando el usuario copia las celdas en el Portapapeles, no se copian las filas y columnas que no tienen celdas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="96ce6-107">When a user copies cells to the Clipboard, rows and columns with no selected cells are not copied.</span></span> <span data-ttu-id="96ce6-108">Todas las demás filas o columnas se convierten en filas y columnas de la tabla de datos que se copia en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="96ce6-108">All other rows or columns become rows and columns in the table of data copied to the Clipboard.</span></span> <span data-ttu-id="96ce6-109">Las celdas no seleccionadas en estas filas o columnas se copian como marcadores de posición en blanco en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="96ce6-109">Unselected cells in these rows or columns are copied as blank placeholders to the Clipboard.</span></span>  
  
### <a name="to-enable-cell-copying"></a><span data-ttu-id="96ce6-110">Para habilitar la copia de celdas</span><span class="sxs-lookup"><span data-stu-id="96ce6-110">To enable cell copying</span></span>  
  
- <span data-ttu-id="96ce6-111">Establecer la propiedad <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="96ce6-111">Set the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#15)]
     [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#15)]  
  
## <a name="example"></a><span data-ttu-id="96ce6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="96ce6-112">Example</span></span>  
 <span data-ttu-id="96ce6-113">En el ejemplo de código completo siguiente se muestra cómo se copian las celdas en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="96ce6-113">The following complete code example demonstrates how cells are copied to the Clipboard.</span></span> <span data-ttu-id="96ce6-114">Este ejemplo incluye un botón que copia las celdas seleccionadas en el Portapapeles usando el método <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> y muestra el contenido del Portapapeles en un cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="96ce6-114">This example includes a button that copies the selected cells to the Clipboard using the <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A?displayProperty=nameWithType> method and displays the Clipboard contents in a text box.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/CS/datagridviewclipboarddemo.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewClipboardDemo#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewClipboardDemo/VB/datagridviewclipboarddemo.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="96ce6-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="96ce6-115">Compiling the Code</span></span>  
 <span data-ttu-id="96ce6-116">Este código requiere:</span><span class="sxs-lookup"><span data-stu-id="96ce6-116">This code requires:</span></span>  
  
- <span data-ttu-id="96ce6-117">Referencias a los ensamblados N:System y N:System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="96ce6-117">References to the N:System and N:System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96ce6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="96ce6-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>
- <xref:System.Windows.Forms.DataGridView.GetClipboardContent%2A>
- [<span data-ttu-id="96ce6-119">Selección y uso del Portapapeles con el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="96ce6-119">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
