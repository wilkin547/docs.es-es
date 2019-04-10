---
title: Filtrar para dar formato a datos en el control DataGridView de formularios Windows Forms
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
ms.openlocfilehash: 62701edfdb3cf2729cb401ad12a12ee4f524287b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221305"
---
# <a name="how-to-format-data-in-the-windows-forms-datagridview-control"></a>Filtrar para dar formato a datos en el control DataGridView de formularios Windows Forms
Los procedimientos siguientes muestran el formato básico de los valores de celda mediante la <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> propiedad de un <xref:System.Windows.Forms.DataGridView> control y de columnas específicas en un control. Para obtener información sobre los formatos de datos avanzados, vea [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-format-currency-and-date-values"></a>Para dar formato a moneda y valores de fecha  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. El ejemplo de código siguiente establece el formato de columnas específicas utilizando la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de las columnas. Los valores en la `UnitPrice` columna aparecen en el formato de moneda específico de la referencia cultural actual, con valores negativos entre paréntesis. Los valores en la `ShipDate` columna aparecen en el formato de fecha corta de específicos de la referencia cultural actual. Para obtener más información acerca de <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> valores, vea [aplicar formato a tipos](../../../standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### <a name="to-customize-the-display-of-null-database-values"></a>Para personalizar la presentación de valores null de la base de datos  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. El siguiente ejemplo de código utiliza el <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> propiedad para no mostrar "ninguna entrada" en todas las celdas que contienen valores iguales a <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### <a name="to-enable-wordwrap-in-text-based-cells"></a>Para habilitar wordwrap en celdas basado en texto  
  
-   Establecer el <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> propiedad de un <xref:System.Windows.Forms.DataGridViewCellStyle> a uno de los <xref:System.Windows.Forms.DataGridViewTriState> valores de enumeración. El siguiente ejemplo de código utiliza el <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> propiedad para establecer el modo de ajuste para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### <a name="to-specify-the-text-alignment-of-datagridview-cells"></a>Para especificar la alineación del texto de las celdas de DataGridView  
  
-   Establecer el <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> propiedad de un <xref:System.Windows.Forms.DataGridViewCellStyle> a uno de los <xref:System.Windows.Forms.DataGridViewContentAlignment> valores de enumeración. El ejemplo de código siguiente establece la alineación de una columna específica mediante la <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> propiedad de la columna.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para estos ejemplos se necesita:  
  
-   Un <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` que contiene una columna denominada `UnitPrice`, una columna denominada `ShipDate`y una columna denominada `CustomerName`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Para conseguir la máxima escalabilidad, se recomienda compartir <xref:System.Windows.Forms.DataGridViewCellStyle> objetos a través de varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo para cada elemento por separado. Para obtener más información, consulte [mejores prácticas para escalar el DataGridView Control de Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de formularios Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Formato de datos en el control DataGridView de formularios Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Filtrar para personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
- [Aplicación de formato a tipos](../../../standard/base-types/formatting-types.md)
