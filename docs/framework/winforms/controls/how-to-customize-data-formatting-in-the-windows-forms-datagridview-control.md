---
title: Procedimiento para personalizar el formato de los datos en el control DataGridView de formularios Windows Forms
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
ms.openlocfilehash: 948e9bf485b42b445491a4da9f8de7ae7974075c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592831"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="56e58-102">Procedimiento para personalizar el formato de los datos en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56e58-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="56e58-103">En el ejemplo de código siguiente, se muestra cómo implementar un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> que cambia la manera en que se muestran las celdas según sus valores y columnas.</span><span class="sxs-lookup"><span data-stu-id="56e58-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="56e58-104">Las celdas de la columna `Balance` que contienen números negativos tienen un fondo rojo.</span><span class="sxs-lookup"><span data-stu-id="56e58-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="56e58-105">También puede dar formato a estas celdas como moneda para que se muestren paréntesis alrededor de los valores negativos.</span><span class="sxs-lookup"><span data-stu-id="56e58-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="56e58-106">Para obtener más información, vea [Cómo: Formato de datos en la Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="56e58-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="56e58-107">Las celdas de la columna `Priority` muestran imágenes en lugar de los valores de celda textual correspondientes.</span><span class="sxs-lookup"><span data-stu-id="56e58-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="56e58-108">La propiedad <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> de <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> se utiliza para obtener el valor de celda textual y establecer el valor de presentación de imagen correspondiente.</span><span class="sxs-lookup"><span data-stu-id="56e58-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56e58-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56e58-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="56e58-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="56e58-110">Compiling the Code</span></span>  
 <span data-ttu-id="56e58-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="56e58-111">This example requires:</span></span>  
  
- <span data-ttu-id="56e58-112">Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="56e58-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="56e58-113">Las imágenes <xref:System.Drawing.Bitmap> denominadas `highPri.bmp`, `mediumPri.bmp` y `lowPri.bmp` que residen en el mismo directorio que el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="56e58-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e58-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="56e58-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="56e58-115">Mostrar datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56e58-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="56e58-116">Cómo: Formato de datos en la Windows Forms DataGridView Control</span><span class="sxs-lookup"><span data-stu-id="56e58-116">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="56e58-117">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56e58-117">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="56e58-118">Formato de datos en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56e58-118">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
