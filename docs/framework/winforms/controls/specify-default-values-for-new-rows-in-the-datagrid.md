---
title: Procedimiento para especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms
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
ms.openlocfilehash: 879c035366c4686ceff3250a63c6ae8d8d3cfec4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651961"
---
# <a name="how-to-specify-default-values-for-new-rows-in-the-windows-forms-datagridview-control"></a>Procedimiento para especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms
Puede hacer que la entrada de datos más conveniente cuando la aplicación rellena los valores predeterminados para las filas recién agregadas. Con el <xref:System.Windows.Forms.DataGridView> (clase), se pueden rellenar los valores predeterminados con la <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> eventos. Este evento se desencadena cuando el usuario entra en la fila para los nuevos registros. Cuando el código controla este evento, puede rellenar deseadas celdas con valores de su elección.  
  
 En el ejemplo de código siguiente se muestra cómo especificar valores predeterminados para nuevas filas mediante el <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> eventos.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
- Un `NewCustomerId` función para generar un único `CustomerID` valores.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
