---
title: Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], changing order
- DataGridView control [Windows Forms], column order
- data grids [Windows Forms], changing column order
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
ms.openlocfilehash: 90d262e738f092215e88e38e31169d74059e4401
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228801"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control"></a>Procedimiento para cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms
Cuando se usa un control <xref:System.Windows.Forms.DataGridView> para mostrar datos desde un origen de datos, a veces las columnas del esquema del origen de datos no aparecen en el orden que quiere que se muestren. Puede cambiar el orden de visualización de las columnas mediante la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> de la clase <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 En el ejemplo de código siguiente, se cambia de posición de algunas de las columnas generadas automáticamente cuando se enlaza a la tabla Customers de la base de datos de ejemplo Northwind. Para obtener más información sobre cómo enlazar la <xref:System.Windows.Forms.DataGridView> control a una tabla de base de datos, vea [Cómo: Enlazar datos a la Windows Forms DataGridView Control](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Cambiar el orden de columnas en el Control de DataGridView de Windows Forms mediante el diseñador](change-the-order-of-columns-in-the-datagrid-using-the-designer.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `customersDataGridView` que está enlazado a una tabla con los nombres de columna indicados, como la tabla `Customers` en la base de datos de ejemplo Northwind.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, <xref:System.Data?displayProperty=nameWithType> y <xref:System.Xml?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Cómo: Enlazar datos al Control DataGridView de formularios Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
