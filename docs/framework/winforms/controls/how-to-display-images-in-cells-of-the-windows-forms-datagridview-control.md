---
title: Procedimiento para mostrar imágenes en celdas del control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: e3a4c395e86e4091d8344bebcf99ee04474f3295
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609931"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="5c3bb-102">Procedimiento para mostrar imágenes en celdas del control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c3bb-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="5c3bb-103">Una imagen o gráfico es uno de los valores que se pueden mostrar en una fila de datos.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="5c3bb-104">Con frecuencia, estos gráficos adoptan la forma de fotografía de un empleado o un logotipo de empresa.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="5c3bb-105">Incorporación de imágenes es sencilla cuando se muestran datos dentro de la <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5c3bb-106">El <xref:System.Windows.Forms.DataGridView> control administra de forma nativa cualquier formato de imagen admitido por el <xref:System.Drawing.Image> formato usado por algunas bases de datos de imagen de clase, así como la OLE.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="5c3bb-107">Si el <xref:System.Windows.Forms.DataGridView> origen de datos del control tiene una columna de imágenes, se mostrará de forma automática el <xref:System.Windows.Forms.DataGridView> control.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="5c3bb-108">El ejemplo de código siguiente muestra cómo extraer un icono desde un recurso incrustado y convertirlo en un mapa de bits para mostrarla en todas las celdas de una columna de imagen.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="5c3bb-109">Para obtener otro ejemplo que reemplaza los valores de celda textual con las imágenes correspondientes, vea [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="5c3bb-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c3bb-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c3bb-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5c3bb-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="5c3bb-111">Compiling the Code</span></span>  
 <span data-ttu-id="5c3bb-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="5c3bb-112">This example requires:</span></span>  
  
- <span data-ttu-id="5c3bb-113">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="5c3bb-114">Un recurso de icono incrustado denominado `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-114">An embedded icon resource named `tree.ico`.</span></span>  
  
- <span data-ttu-id="5c3bb-115">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c3bb-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c3bb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c3bb-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="5c3bb-117">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c3bb-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="5c3bb-118">Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5c3bb-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
