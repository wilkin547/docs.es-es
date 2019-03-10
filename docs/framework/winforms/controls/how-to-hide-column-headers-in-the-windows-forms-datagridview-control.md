---
title: Filtrar Ocultar encabezados de columna en el Control DataGridView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], hiding column headers
- column headers [Windows Forms], hiding
- DataGridView control [Windows Forms], column headers
ms.assetid: e4ad5f68-50d2-4b9e-93ee-9d622423a8ab
ms.openlocfilehash: b9b78020a567d05ea000be97bb116b4f8353d56c
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709463"
---
# <a name="how-to-hide-column-headers-in-the-windows-forms-datagridview-control"></a>Procedimiento Ocultar encabezados de columna en el Control DataGridView de Windows Forms
A veces querrá mostrar un <xref:System.Windows.Forms.DataGridView> sin encabezados de columna. En el <xref:System.Windows.Forms.DataGridView> (control), el <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A> valor de propiedad determina si se muestran los encabezados de columna.  
  
### <a name="to-hide-the-column-headers"></a>Para ocultar los encabezados de columna  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType> en `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#062)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#062](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#062)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersVisible%2A?displayProperty=nameWithType>
- [Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
