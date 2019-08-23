---
title: Procedimiento para usar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966503"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="55aa7-102">Procedimiento para usar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55aa7-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="55aa7-103">El <xref:System.Windows.Forms.DataGridView> control utiliza la plantilla de fila como base para todas las filas que se agregan al control mediante el enlace de datos o cuando se <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> llama al método sin especificar una fila existente que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="55aa7-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="55aa7-104">La plantilla de fila proporciona un mayor control sobre la apariencia y el comportamiento de las <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> filas que proporciona la propiedad.</span><span class="sxs-lookup"><span data-stu-id="55aa7-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="55aa7-105">Con la plantilla de fila, puede establecer cualquier <xref:System.Windows.Forms.DataGridViewRow> propiedad, incluida <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="55aa7-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="55aa7-106">Hay algunas situaciones en las que debe usar la plantilla de fila para lograr un efecto determinado.</span><span class="sxs-lookup"><span data-stu-id="55aa7-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="55aa7-107">Por ejemplo, la información de alto de fila no se <xref:System.Windows.Forms.DataGridViewCellStyle>puede almacenar en un, por lo que debe usar una plantilla de fila para cambiar el alto predeterminado utilizado por todas las filas.</span><span class="sxs-lookup"><span data-stu-id="55aa7-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="55aa7-108">La plantilla de fila también es útil cuando crea sus propias clases derivadas <xref:System.Windows.Forms.DataGridViewRow> de y desea que el tipo personalizado se use cuando se agreguen nuevas filas al control.</span><span class="sxs-lookup"><span data-stu-id="55aa7-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55aa7-109">La plantilla de fila solo se usa cuando se agregan filas.</span><span class="sxs-lookup"><span data-stu-id="55aa7-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="55aa7-110">No se pueden cambiar las filas existentes cambiando la plantilla de fila.</span><span class="sxs-lookup"><span data-stu-id="55aa7-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="55aa7-111">Para usar la plantilla de fila</span><span class="sxs-lookup"><span data-stu-id="55aa7-111">To use the row template</span></span>  
  
- <span data-ttu-id="55aa7-112">Establezca las propiedades en el objeto recuperado <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="55aa7-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="55aa7-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="55aa7-113">Compiling the Code</span></span>  
 <span data-ttu-id="55aa7-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="55aa7-114">This example requires:</span></span>  
  
- <span data-ttu-id="55aa7-115">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="55aa7-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="55aa7-116">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="55aa7-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55aa7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="55aa7-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="55aa7-118">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55aa7-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="55aa7-119">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="55aa7-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
