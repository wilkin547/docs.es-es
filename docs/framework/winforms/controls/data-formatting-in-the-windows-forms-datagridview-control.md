---
title: Formato de datos en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: b5c055bdd12a4bede6e77233726c697de424a055
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158652"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Formato de datos en el control DataGridView de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control proporciona la conversión automática entre los valores de celda y los tipos de datos que se muestran las columnas primarias. Las columnas del cuadro de texto, por ejemplo, mostrar las representaciones de cadena de fecha, hora, número y valores de enumeración y conversión los valores de cadena escrito por el usuario a los tipos requeridos por el almacén de datos.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Formato con la clase DataGridViewCellStyle  
 El <xref:System.Windows.Forms.DataGridView> control proporciona un formato de datos básicos de los valores de celda mediante la <xref:System.Windows.Forms.DataGridViewCellStyle> clase. Puede usar el <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> propiedad a valores de fecha, hora, número y enumeración de formato para la referencia cultural predeterminada actual mediante los especificadores de formato se describe en [aplicar formato a tipos](../../../standard/base-types/formatting-types.md). También puede dar formato a estos valores para referencias culturales específicas mediante la <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> propiedad. El formato especificado se utiliza para mostrar los datos y analizar los datos que el usuario escribe en el formato especificado.  
  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> clase proporciona las propiedades de formato adicionales para wordwrap, la alineación de texto y la visualización personalizada de valores null de la base de datos. Para obtener más información, vea [Cómo: Formato de datos en la Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Formato con el evento CellFormatting  
 Si el formato básico no satisface sus necesidades, puede proporcionar datos personalizados de formato en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> eventos. El <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> pasa al controlador tiene un <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> propiedad que inicialmente contiene el valor de celda. Normalmente, este valor se convierte automáticamente en el tipo de visualización. Para convertir el valor, establezca la <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> propiedad con un valor del tipo de visualización.  
  
> [!NOTE]
>  Si una cadena de formato está en vigor para la celda, reemplaza el cambio de la <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> valor de propiedad a menos que establezca el <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> propiedad `true`.  
  
 El <xref:System.Windows.Forms.DataGridView.CellFormatting> evento también es útil cuando desea establecer <xref:System.Windows.Forms.DataGridViewCellStyle> las propiedades de celdas individuales en función de sus valores. Para obtener más información, vea [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Si el análisis predeterminado de valores especificados por el usuario no satisfacen sus necesidades, puede controlar la <xref:System.Windows.Forms.DataGridView.CellParsing> eventos de la <xref:System.Windows.Forms.DataGridView> control para proporcionar un análisis personalizado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Cómo: Formato de datos en la Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
