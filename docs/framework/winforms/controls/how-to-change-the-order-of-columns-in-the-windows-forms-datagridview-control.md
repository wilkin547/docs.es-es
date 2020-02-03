---
title: Cambiar el orden de las columnas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 2aef196e9544a81f42a563783ce6c357869aa247
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746548"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a>Cómo: Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms
Cuando se usa un control <xref:System.Windows.Forms.DataGridView> para mostrar datos desde un origen de datos, a veces las columnas del esquema del origen de datos no aparecen en el orden que quiere que se muestren. Puede cambiar el orden de visualización de las columnas mediante la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> de la clase <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 En el ejemplo de código siguiente, se cambia de posición de algunas de las columnas generadas automáticamente cuando se enlaza a la tabla Customers de la base de datos de ejemplo Northwind. Para obtener más información sobre cómo enlazar el control <xref:System.Windows.Forms.DataGridView> a una tabla de base de datos, vea [Cómo: enlazar datos al control DataGridView Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: cambiar el orden de las columnas en el control DataGridView Windows Forms mediante el diseñador](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Un control <xref:System.Windows.Forms.DataGridView> denominado `customersDataGridView` que está enlazado a una tabla con los nombres de columna indicados, como la tabla `Customers` en la base de datos de ejemplo Northwind.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> y <xref:System.Xml?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Enlazar datos al control DataGridView de formularios Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
