---
title: Procedimiento Personalizar el formato de datos en el Control DataGridView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
ms.openlocfilehash: b8f346e8f49b2710b55f5c52a8f7b4c6a2c416e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733199"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="9a8e7-102">Procedimiento Personalizar el formato de datos en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a8e7-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9a8e7-103">En el ejemplo de código siguiente, se muestra cómo implementar un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> que cambia la manera en que se muestran las celdas según sus valores y columnas.</span><span class="sxs-lookup"><span data-stu-id="9a8e7-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="9a8e7-104">Las celdas de la columna `Balance` que contienen números negativos tienen un fondo rojo.</span><span class="sxs-lookup"><span data-stu-id="9a8e7-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="9a8e7-105">También puede dar formato a estas celdas como moneda para que se muestren paréntesis alrededor de los valores negativos.</span><span class="sxs-lookup"><span data-stu-id="9a8e7-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="9a8e7-106">Para obtener más información, vea [Cómo: Formato de datos en la Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="9a8e7-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="9a8e7-107">Las celdas de la columna `Priority` muestran imágenes en lugar de los valores de celda textual correspondientes.</span><span class="sxs-lookup"><span data-stu-id="9a8e7-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="9a8e7-108">La propiedad <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> de <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> se utiliza para obtener el valor de celda textual y establecer el valor de presentación de imagen correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9a8e7-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a8e7-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a8e7-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a8e7-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9a8e7-110">Compiling the Code</span></span>  
 <span data-ttu-id="9a8e7-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9a8e7-111">This example requires:</span></span>  
  
-   <span data-ttu-id="9a8e7-112">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="9a8e7-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <span data-ttu-id="9a8e7-113">Las imágenes <xref:System.Drawing.Bitmap> denominadas `highPri.bmp`, `mediumPri.bmp` y `lowPri.bmp` que residen en el mismo directorio que el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="9a8e7-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="9a8e7-114">Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9a8e7-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9a8e7-115">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="9a8e7-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9a8e7-116">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms con Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9a8e7-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8e7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a8e7-117">See also</span></span>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="9a8e7-118">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a8e7-118">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9a8e7-119">Cómo: Formato de datos en la Windows Forms DataGridView Control</span><span class="sxs-lookup"><span data-stu-id="9a8e7-119">How to: Format Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9a8e7-120">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a8e7-120">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="9a8e7-121">Formato de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a8e7-121">Data Formatting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)
