---
title: Especificar valores predeterminados para nuevas filas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], default values for new rows
- DataGridView control [Windows Forms], data entry
- rows [Windows Forms], specifying default values
- DataGridView control [Windows Forms], default values for new rows
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
ms.openlocfilehash: 364f922aefc10e57f2ed7f3a0c2a5b25c922d87a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742932"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a>Cómo: Especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms
Puede hacer que la entrada de datos sea más cómoda cuando la aplicación rellena los valores predeterminados para las filas recién agregadas. Con la clase <xref:System.Windows.Forms.DataGridView>, puede rellenar los valores predeterminados con el evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>. Este evento se desencadena cuando el usuario escribe los nuevos registros en la fila. Cuando el código controle este evento, puede rellenar las celdas deseadas con los valores de su elección.  
  
 En el ejemplo de código siguiente se muestra cómo especificar los valores predeterminados para las nuevas filas mediante el evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
- Función `NewCustomerId` para generar valores de `CustomerID` únicos.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
