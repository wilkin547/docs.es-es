---
title: Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 86e61afd0882fea9015cdfe3b40e6d3cd329391b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734966"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms
Cuando se usa un <xref:System.Windows.Forms.DataGridView> para modificar los datos en la aplicación, a menudo desea ofrecer a los usuarios la capacidad de agregar nuevas filas de datos al almacén de datos. El <xref:System.Windows.Forms.DataGridView> control admite esta funcionalidad proporcionando una fila para los nuevos registros, siempre se muestra como la última fila. Se marca con un símbolo de asterisco (*) en el encabezado de fila. Las secciones siguientes tratan algunas de las cosas que debe considerar cuando se programa con la fila de nuevos registros habilitada.  
  
## <a name="displaying-the-row-for-new-records"></a>Mostrar la fila para los nuevos registros  
 Use el <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> propiedad para indicar si se muestra la fila de nuevos registros. El valor predeterminado de esta propiedad es `true`.  
  
 Para los datos enlazados caso, se mostrará la fila para los nuevos registros si la <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> propiedad del control y el <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> son propiedad del origen de datos `true`. Si se da alguna `false` , a continuación, la fila no se mostrarán.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Rellenar la fila para los nuevos registros con datos predeterminados  
 Cuando el usuario selecciona la fila para los nuevos registros como la fila actual, el <xref:System.Windows.Forms.DataGridView> control provoca la <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> eventos.  
  
 Este evento proporciona acceso a la nueva <xref:System.Windows.Forms.DataGridViewRow> y le permite rellenar la nueva fila con datos predeterminados. Para obtener más información, vea [Cómo: Especificar valores predeterminados para nuevas filas en el Control DataGridView de formularios de Windows](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>La colección de filas  
 La fila para los nuevos registros se encuentra en la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.Rows%2A> colección pero tiene un comportamiento diferente en dos aspectos:  
  
-   No se puede quitar la fila de nuevos registros desde el <xref:System.Windows.Forms.DataGridView.Rows%2A> colección mediante programación. Un <xref:System.InvalidOperationException> se produce si se intentara. También, el usuario no puede eliminar la fila de nuevos registros. El <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> método no quita esta fila desde la <xref:System.Windows.Forms.DataGridView.Rows%2A> colección.  
  
-   Después de la fila para los nuevos registros no se puede agregar ninguna fila. Un <xref:System.InvalidOperationException> se produce si se intentara. Como resultado, la fila de nuevos registros es siempre la última fila de la <xref:System.Windows.Forms.DataGridView> control. Los métodos de <xref:System.Windows.Forms.DataGridViewRowCollection> que agregan filas:<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, y <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, todos los métodos de inserción internamente a cuando la fila de nuevos registros está presente.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Personalización visual de la fila para los nuevos registros  
 Cuando se crea la fila de nuevos registros, se basa en la fila especificada por el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> propiedad. Los estilos de celda que no se especifican para esta fila se heredan de otras propiedades. Para obtener más información sobre la herencia de estilo de celda, vea [estilos de celda en el DataGridView Control de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Los valores iniciales que se muestra por las celdas de la fila para nuevos registros se recuperan de cada celda <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> propiedad. Para las celdas de tipo <xref:System.Windows.Forms.DataGridViewImageCell>, esta propiedad devuelve una imagen de marcador de posición. En caso contrario, esta propiedad devuelve `null`. Puede invalidar esta propiedad para devolver un valor personalizado. Sin embargo, estos valores iniciales se pueden reemplazar por un <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> controlador de eventos cuando el foco entra en la fila para los nuevos registros.  
  
 Los iconos estándar para el encabezado de la fila, que son una flecha o un asterisco, no se exponen públicamente. Si desea personalizar los iconos, deberá crear una personalizada <xref:System.Windows.Forms.DataGridViewRowHeaderCell> clase.  
  
 Los iconos estándar utilizan el <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellStyle> en uso por la celda de encabezado de fila. No se representan los iconos estándar si no hay suficiente espacio para mostrarlos por completo.  
  
 Si la celda de encabezado de fila tiene un valor de cadena establecida y no hay espacio suficiente para el texto y el icono, se quita primero el icono.  
  
## <a name="sorting"></a>Ordenar  
 En el modo independiente, nuevos registros siempre se agregarán al final de la <xref:System.Windows.Forms.DataGridView> incluso si el usuario haya ordenado el contenido de la <xref:System.Windows.Forms.DataGridView>. El usuario tendrá que vuelva a aplicar el criterio de ordenación para ordenar la fila a la posición correcta. Este comportamiento es similar de la <xref:System.Windows.Forms.ListView> control.  
  
 En datos modos enlazados y virtuales, el comportamiento de inserción cuando se aplica un criterio de ordenación será depende de la implementación del modelo de datos. Para [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], la fila se ordena inmediatamente en la posición correcta.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Otras notas en la fila para los nuevos registros  
 No puede establecer el <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> propiedad de esta fila en `false`. Un <xref:System.InvalidOperationException> se produce si se intentara.  
  
 La fila para los nuevos registros siempre se crea en el estado no seleccionado.  
  
## <a name="virtual-mode"></a>Modo virtual  
 Si está implementando el modo virtual, deberá hacer un seguimiento cuando se necesita una fila para los nuevos registros en el modelo de datos y cuándo se debe deshacer la adición de la fila. La implementación exacta de esta funcionalidad depende de la implementación del modelo de datos y la semántica de transacción, por ejemplo, si el ámbito de confirmación está en el nivel de celda o fila. Para obtener más información, consulte [el modo Virtual en el DataGridView Control de Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
- [Cómo: Especificar valores predeterminados para nuevas filas en el Control DataGridView de formularios de Windows](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)
