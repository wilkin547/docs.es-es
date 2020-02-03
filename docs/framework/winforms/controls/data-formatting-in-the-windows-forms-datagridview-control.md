---
title: Formato de datos en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: a041bcc5e1b65afb3123f1f42e0f1b5a479b5764
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743985"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Formato de datos en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> proporciona la conversión automática entre los valores de celda y los tipos de datos que las columnas primarias muestran. Las columnas de cuadro de texto, por ejemplo, muestran representaciones de cadena de valores de fecha, hora, número y enumeración, y convierten los valores de cadena especificados por el usuario en los tipos requeridos por el almacén de datos.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Aplicar formato a la clase DataGridViewCellStyle  
 El control <xref:System.Windows.Forms.DataGridView> proporciona el formato de datos básico de los valores de celda a través de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>. Puede usar la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> para dar formato a los valores de fecha, hora, número y enumeración de la referencia cultural predeterminada actual mediante los especificadores de formato descritos en [formatos de tipos](../../../standard/base-types/formatting-types.md). También puede dar formato a estos valores para referencias culturales específicas mediante la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>. El formato especificado se usa para mostrar los datos y para analizar los datos que el usuario escribe en el formato especificado.  
  
 La clase <xref:System.Windows.Forms.DataGridViewCellStyle> proporciona propiedades de formato adicionales para WordWrap, la alineación del texto y la presentación personalizada de valores NULL de la base de datos. Para más información, consulte [Cómo: Dar formato a datos en el control DataGridView de Windows Forms](how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Aplicar formato al evento CellFormatting  
 Si el formato básico no satisface sus necesidades, puede proporcionar un formato de datos personalizado en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>. El <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> pasado al controlador tiene una propiedad <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> que contiene inicialmente el valor de la celda. Normalmente, este valor se convierte automáticamente al tipo de presentación. Para convertir el valor usted mismo, establezca la propiedad <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> en un valor del tipo de presentación.  
  
> [!NOTE]
> Si hay una cadena de formato en vigor para la celda, reemplaza el cambio del valor de la propiedad <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> a menos que establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> en `true`.  
  
 El evento <xref:System.Windows.Forms.DataGridView.CellFormatting> también es útil cuando se desea establecer propiedades de <xref:System.Windows.Forms.DataGridViewCellStyle> para celdas individuales basadas en sus valores. Para obtener más información, vea [Cómo: personalizar el formato de datos en el control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Si el análisis predeterminado de los valores especificados por el usuario no satisface sus necesidades, puede controlar el evento <xref:System.Windows.Forms.DataGridView.CellParsing> del control <xref:System.Windows.Forms.DataGridView> para proporcionar el análisis personalizado.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Dar formato a datos en el control DataGridView de Windows Forms](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
