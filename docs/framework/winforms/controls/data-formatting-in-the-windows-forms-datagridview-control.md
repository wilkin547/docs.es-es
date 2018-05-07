---
title: Formato de datos en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: ae1947cf7c3825553837fa5f1ee288114988d28f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Formato de datos en el control DataGridView de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control proporciona la conversión automática entre los valores de celda y los tipos de datos que se muestran las columnas primarias. Las columnas del cuadro de texto, por ejemplo, mostrar las representaciones de cadena de fecha, hora, número y valores de enumeración y convierten los valores de cadena proporcionada por el usuario en los tipos requeridos por el almacén de datos.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Formato con la clase DataGridViewCellStyle  
 El <xref:System.Windows.Forms.DataGridView> control proporciona un formato de datos básicos de los valores de celda mediante la <xref:System.Windows.Forms.DataGridViewCellStyle> clase. Puede usar el <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> propiedad a valores de fecha, hora, número y enumeración de formato para la referencia cultural predeterminada actual mediante los especificadores de formato se describe en [Formatting Types](../../../../docs/standard/base-types/formatting-types.md). También puede dar formato a estos valores para referencias culturales específicas mediante la <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> propiedad. El formato especificado se utiliza para mostrar datos y analizar los datos que el usuario escribe en el formato especificado.  
  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> clase proporciona propiedades de formato adicionales para el ajuste de línea, la alineación del texto y la presentación personalizada de valores null de la base de datos. Para más información, consulte [Cómo: Dar formato a datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Formato con el evento CellFormatting  
 Si el formato básico no satisface sus necesidades, puede proporcionar datos personalizados de formato en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> eventos. El <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> pasado al controlador tiene una <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> propiedad que inicialmente contiene el valor de celda. Normalmente, este valor se convierte automáticamente en el tipo de visualización. Para convertir el valor, establezca la <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> propiedad en un valor del tipo de presentación.  
  
> [!NOTE]
>  Si una cadena de formato está en vigor para la celda, reemplaza el cambio de la <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> valor de propiedad a menos que establezca el <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> propiedad `true`.  
  
 El <xref:System.Windows.Forms.DataGridView.CellFormatting> evento también es útil cuando desea establecer <xref:System.Windows.Forms.DataGridViewCellStyle> propiedades para celdas individuales basan en sus valores. Para obtener más información, consulte [Cómo: personalizar el formato de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Si el análisis predeterminado de valores especificados por el usuario no satisface sus necesidades, puede controlar la <xref:System.Windows.Forms.DataGridView.CellParsing> eventos de la <xref:System.Windows.Forms.DataGridView> control para proporcionar un análisis personalizado.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [Mostrar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Estilos de celda en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Dar formato a datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 [Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
