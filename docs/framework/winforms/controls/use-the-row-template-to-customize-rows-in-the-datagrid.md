---
title: Procedimiento Use la plantilla de filas para personalizar filas en el Control DataGridView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 215b04ce47a393a0ec3ad01957a311bc5508d24f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580244"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="93ca0-102">Procedimiento Use la plantilla de filas para personalizar filas en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93ca0-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="93ca0-103">El <xref:System.Windows.Forms.DataGridView> control usa la plantilla de fila como base para todas las filas que agregan al control mediante enlace de datos o cuando se llama a la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> método sin especificar una fila existente para usar.</span><span class="sxs-lookup"><span data-stu-id="93ca0-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="93ca0-104">La plantilla de fila ofrece un mayor control sobre la apariencia y comportamiento de las filas que el <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> proporciona la propiedad.</span><span class="sxs-lookup"><span data-stu-id="93ca0-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="93ca0-105">Con la plantilla de fila, puede establecer cualquiera <xref:System.Windows.Forms.DataGridViewRow> propiedades, incluyendo <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="93ca0-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="93ca0-106">Existen algunas situaciones donde debe usar la plantilla de fila para lograr un efecto en particular.</span><span class="sxs-lookup"><span data-stu-id="93ca0-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="93ca0-107">Por ejemplo, la información de alto de fila no pueden almacenarse en un <xref:System.Windows.Forms.DataGridViewCellStyle>, por lo que debe usar una plantilla de fila para cambiar el alto predeterminado utilizado por todas las filas.</span><span class="sxs-lookup"><span data-stu-id="93ca0-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="93ca0-108">La plantilla de fila también es útil al crear sus propias clases derivadas de <xref:System.Windows.Forms.DataGridViewRow> y desea que el tipo personalizado que se utiliza cuando se agregan nuevas filas al control.</span><span class="sxs-lookup"><span data-stu-id="93ca0-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93ca0-109">La plantilla de fila solo se usa cuando se agregan filas.</span><span class="sxs-lookup"><span data-stu-id="93ca0-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="93ca0-110">No se puede cambiar las filas existentes cambiando la plantilla de fila.</span><span class="sxs-lookup"><span data-stu-id="93ca0-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="93ca0-111">Para usar la plantilla de fila</span><span class="sxs-lookup"><span data-stu-id="93ca0-111">To use the row template</span></span>  
  
-   <span data-ttu-id="93ca0-112">Establecer propiedades en el objeto recuperado desde el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> propiedad.</span><span class="sxs-lookup"><span data-stu-id="93ca0-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93ca0-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="93ca0-113">Compiling the Code</span></span>  
 <span data-ttu-id="93ca0-114">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="93ca0-114">This example requires:</span></span>  
  
-   <span data-ttu-id="93ca0-115">Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="93ca0-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="93ca0-116">Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93ca0-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ca0-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="93ca0-117">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="93ca0-118">Estilo y formato básicos del control DataGridView en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93ca0-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="93ca0-119">Estilos de celda en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="93ca0-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
