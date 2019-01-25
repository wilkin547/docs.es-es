---
title: Procedimiento Ocultar encabezados de columna en el Control DataGridView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: 80377aa598938031f9708c4b7657594985ec0746
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717069"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="94be8-102">Procedimiento Ocultar encabezados de columna en el Control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94be8-102">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="94be8-103">A veces querrá mostrar un <xref:System.Windows.Forms.DataGridView> sin encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="94be8-103">Sometimes you will want to display a <xref:System.Windows.Forms.DataGridView> without column headers.</span></span> <span data-ttu-id="94be8-104">En el <xref:System.Windows.Forms.DataGridView> (control), el <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> valor de propiedad determina si se muestran los encabezados de columna.</span><span class="sxs-lookup"><span data-stu-id="94be8-104">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> property value determines whether the column headers are displayed.</span></span>  
  
### <a name="to-hide-the-column-headers"></a><span data-ttu-id="94be8-105">Para ocultar los encabezados de columna</span><span class="sxs-lookup"><span data-stu-id="94be8-105">To hide the column headers</span></span>  
  
-   <span data-ttu-id="94be8-106">Establezca la propiedad <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> en `false`.</span><span class="sxs-lookup"><span data-stu-id="94be8-106">Set the <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94be8-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="94be8-107">Compiling the Code</span></span>  
 <span data-ttu-id="94be8-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="94be8-108">This example requires:</span></span>  
  
-   <span data-ttu-id="94be8-109">Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="94be8-109">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="94be8-110">Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="94be8-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94be8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="94be8-111">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="94be8-112">Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="94be8-112">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
