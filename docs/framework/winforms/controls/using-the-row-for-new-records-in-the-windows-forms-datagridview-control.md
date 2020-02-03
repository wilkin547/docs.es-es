---
title: Usar la fila para nuevos registros en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 2fcd35f8c4d04909cdbc26f6a4293fdd570385b8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728339"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms
Cuando se usa un <xref:System.Windows.Forms.DataGridView> para editar datos en la aplicación, a menudo se desea ofrecer a los usuarios la capacidad de agregar nuevas filas de datos al almacén de datos. El control <xref:System.Windows.Forms.DataGridView> admite esta funcionalidad proporcionando una fila para los nuevos registros, que siempre se muestra como la última fila. Se marca con un símbolo de asterisco (*) en el encabezado de fila. En las secciones siguientes se describen algunas de las cosas que debe tener en cuenta al programar con la fila para los nuevos registros habilitados.  
  
## <a name="displaying-the-row-for-new-records"></a>Mostrar la fila de los nuevos registros  
 Utilice la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> para indicar si se muestra la fila para los nuevos registros. El valor predeterminado de esta propiedad es `true`.  
  
 En el caso del enlace de datos, la fila de los nuevos registros se mostrará si la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> del control y la propiedad <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> del origen de datos son ambos `true`. Si cualquiera de los dos `false`, no se mostrará la fila.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Rellenar la fila para los nuevos registros con datos predeterminados  
 Cuando el usuario selecciona la fila de los nuevos registros como la fila actual, el control <xref:System.Windows.Forms.DataGridView> provoca el evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
 Este evento proporciona acceso al nuevo <xref:System.Windows.Forms.DataGridViewRow> y le permite rellenar la nueva fila con datos predeterminados. Para obtener más información, vea [Cómo: especificar valores predeterminados para nuevas filas en el control DataGridView de Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Colección Rows  
 La fila de los nuevos registros está contenida en la colección de <xref:System.Windows.Forms.DataGridView.Rows%2A> del control <xref:System.Windows.Forms.DataGridView>, pero se comporta de forma diferente en dos aspectos:  
  
- La fila de los nuevos registros no se puede quitar de la colección de <xref:System.Windows.Forms.DataGridView.Rows%2A> mediante programación. Si se intenta, se produce una <xref:System.InvalidOperationException>. El usuario tampoco puede eliminar la fila de los nuevos registros. El método <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> no quita esta fila de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>.  
  
- No se puede agregar ninguna fila después de la fila para los nuevos registros. Si se intenta, se produce una <xref:System.InvalidOperationException>. Como resultado, la fila de los nuevos registros siempre es la última fila del control <xref:System.Windows.Forms.DataGridView>. Los métodos de <xref:System.Windows.Forms.DataGridViewRowCollection> que agregan filas (<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>y <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>), todos los métodos de inserción de llamadas internamente cuando la fila de nuevos registros está presente.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Personalización visual de la fila para los nuevos registros  
 Cuando se crea la fila para los nuevos registros, se basa en la fila especificada por la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>. Los estilos de celda no especificados para esta fila se heredan de otras propiedades. Para obtener más información sobre la herencia del estilo de celda, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Los valores iniciales que se muestran en las celdas de la fila para los nuevos registros se recuperan de la propiedad <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> de cada celda. En el caso de las celdas de tipo <xref:System.Windows.Forms.DataGridViewImageCell>, esta propiedad devuelve una imagen de marcador de posición. En caso contrario, esta propiedad devuelve `null`. Puede invalidar esta propiedad para devolver un valor personalizado. Sin embargo, estos valores iniciales se pueden reemplazar por un controlador de eventos <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> cuando el foco entra en la fila de nuevos registros.  
  
 Los iconos estándar del encabezado de esta fila, que son una flecha o un asterisco, no se exponen públicamente. Si desea personalizar los iconos, tendrá que crear una clase de <xref:System.Windows.Forms.DataGridViewRowHeaderCell> personalizada.  
  
 Los iconos estándar utilizan la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> de la <xref:System.Windows.Forms.DataGridViewCellStyle> en uso por la celda de encabezado de fila. Los iconos estándar no se representan si no hay espacio suficiente para mostrarlos completamente.  
  
 Si la celda del encabezado de fila tiene establecido un valor de cadena y no hay suficiente espacio para el texto y el icono, el icono se quita primero.  
  
## <a name="sorting"></a>Ordenación  
 En el modo sin enlazar, los nuevos registros siempre se agregarán al final de la <xref:System.Windows.Forms.DataGridView> incluso si el usuario ha ordenado el contenido de la <xref:System.Windows.Forms.DataGridView>. El usuario deberá volver a aplicar la ordenación para ordenar la fila a la posición correcta; Este comportamiento es similar al del control <xref:System.Windows.Forms.ListView>.  
  
 En los modos de enlace de datos y virtuales, el comportamiento de inserción cuando se aplica una ordenación dependerá de la implementación del modelo de datos. En el caso de ADO.NET, la fila se ordena inmediatamente en la posición correcta.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Otras notas de la fila para los nuevos registros  
 No se puede establecer la propiedad <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> de esta fila en `false`. Si se intenta, se produce una <xref:System.InvalidOperationException>.  
  
 La fila de los nuevos registros siempre se crea en el estado no seleccionado.  
  
## <a name="virtual-mode"></a>Modo virtual  
 Si está implementando el modo virtual, deberá realizar un seguimiento de Cuándo se necesita una fila para los nuevos registros en el modelo de datos y cuándo revertir la adición de la fila. La implementación exacta de esta funcionalidad depende de la implementación del modelo de datos y de su semántica de transacción, por ejemplo, si el ámbito de confirmación está en el nivel de celda o de fila. Para obtener más información, vea [modo virtual en el control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
- [Especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)
