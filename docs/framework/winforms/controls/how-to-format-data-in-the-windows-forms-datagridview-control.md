---
title: Dar formato a los datos en el control DataGridView
description: Obtenga información sobre cómo dar formato a los valores de celda mediante la propiedad DefaultCellStyle de un control DataGridView Windows Forms y de columnas específicas de un control.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in DataGridView control
- data grids [Windows Forms], enabling wordwrap
- currency values [Windows Forms], formatting in data grids
- data grids [Windows Forms], currency values
- data grids [Windows Forms], formatting data
- data grids [Windows Forms], text alignment
- data grids [Windows Forms], date values
- cells [Windows Forms], text alignment
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
ms.openlocfilehash: d6105c1d1120876f854332e7a10106cc1caf6276
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622814"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>Procedimiento para dar formato a datos en el control DataGridView de formularios Windows Forms
Los procedimientos siguientes muestran el formato básico de los valores de celda mediante la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> propiedad de un <xref:System.Windows.Forms.DataGridView> control y de las columnas específicas de un control. Para obtener información sobre el formato de datos avanzado, vea [Cómo: personalizar el formato de datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-format-currency-and-date-values"></a>Para dar formato a los valores de fecha y moneda  
  
- Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. En el ejemplo de código siguiente se establece el formato de columnas específicas mediante la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de las columnas. Los valores de la `UnitPrice` columna aparecen en el formato de moneda específico de la referencia cultural actual, con valores negativos entre paréntesis. Los valores de la `ShipDate` columna aparecen en el formato de fecha corta específico de la referencia cultural actual. Para obtener más información sobre <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> los valores, vea [aplicar formato a tipos](../../../standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>Para personalizar la presentación de valores de base de datos null  
  
- Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. En el ejemplo de código siguiente <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> se usa la propiedad para mostrar "sin entrada" en todas las celdas que contienen valores iguales a <xref:System.DBNull.Value?displayProperty=nameWithType> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>Para habilitar WordWrap en celdas basadas en texto  
  
- Establezca la <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> propiedad de <xref:System.Windows.Forms.DataGridViewCellStyle> en uno de los <xref:System.Windows.Forms.DataGridViewTriState> valores de enumeración. En el ejemplo de código siguiente <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> se usa la propiedad para establecer el modo de ajuste para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>Para especificar la alineación del texto de las celdas de DataGridView  
  
- Establezca la <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> propiedad de <xref:System.Windows.Forms.DataGridViewCellStyle> en uno de los <xref:System.Windows.Forms.DataGridViewContentAlignment> valores de enumeración. En el ejemplo de código siguiente se establece la alineación de una columna concreta mediante la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de la columna.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Estos ejemplos requieren:  
  
- Un <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` que contiene una columna denominada `UnitPrice` , una columna denominada `ShipDate` y una columna denominada `CustomerName` .  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Para obtener la máxima escalabilidad, debe compartir <xref:System.Windows.Forms.DataGridViewCellStyle> objetos entre varias filas, columnas o celdas que usen los mismos estilos en lugar de establecer las propiedades de estilo para cada elemento por separado. Para obtener más información, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de formularios Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Formato de datos en el control DataGridView de formularios Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Procedimiento para personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [Aplicación de formato a tipos](../../../standard/base-types/formatting-types.md)
