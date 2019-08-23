---
title: Formato de datos en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: 5966f16238999655d6072c1127e5bf16aefde5e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969183"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Formato de datos en el control DataGridView de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control proporciona la conversión automática entre los valores de celda y los tipos de datos que las columnas primarias muestran. Las columnas de cuadro de texto, por ejemplo, muestran representaciones de cadena de valores de fecha, hora, número y enumeración, y convierten los valores de cadena especificados por el usuario en los tipos requeridos por el almacén de datos.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Aplicar formato a la clase DataGridViewCellStyle  
 El <xref:System.Windows.Forms.DataGridView> control proporciona el formato de datos básico de los valores <xref:System.Windows.Forms.DataGridViewCellStyle> de celda a través de la clase. Puede usar la <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> propiedad para dar formato a los valores de fecha, hora, número y enumeración de la referencia cultural predeterminada actual mediante los especificadores de formato descritos en [formatos de tipos](../../../standard/base-types/formatting-types.md). También puede dar formato a estos valores para referencias culturales específicas <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> mediante la propiedad. El formato especificado se usa para mostrar los datos y para analizar los datos que el usuario escribe en el formato especificado.  
  
 La <xref:System.Windows.Forms.DataGridViewCellStyle> clase proporciona propiedades de formato adicionales para WordWrap, la alineación del texto y la presentación personalizada de valores de base de datos null. Para obtener más información, consulte [Cómo Dar formato a los datos en el](how-to-format-data-in-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.  
  
## <a name="formatting-with-the-cellformatting-event"></a>Aplicar formato al evento CellFormatting  
 Si el formato básico no satisface sus necesidades, puede proporcionar un formato de datos personalizado en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento. El <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> pasado al controlador tiene una <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> propiedad que contiene inicialmente el valor de la celda. Normalmente, este valor se convierte automáticamente al tipo de presentación. Para convertir el valor usted mismo, establezca <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> la propiedad en un valor del tipo de presentación.  
  
> [!NOTE]
> Si una cadena de formato está en vigor para la celda, invalida el cambio del valor de <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> propiedad a menos que establezca la <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> propiedad en `true`.  
  
 El <xref:System.Windows.Forms.DataGridView.CellFormatting> evento también es útil cuando desea establecer <xref:System.Windows.Forms.DataGridViewCellStyle> propiedades para celdas individuales basadas en sus valores. Para obtener más información, consulte [Cómo Personalizar el formato de los datos en el](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)control DataGridView Windows Forms.  
  
 Si el análisis predeterminado de los valores especificados por el usuario no satisface sus necesidades, puede controlar <xref:System.Windows.Forms.DataGridView.CellParsing> el evento <xref:System.Windows.Forms.DataGridView> del control para proporcionar un análisis personalizado.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Cómo: Dar formato a los datos en el control DataGridView Windows Forms](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Cómo: Personalizar el formato de los datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
