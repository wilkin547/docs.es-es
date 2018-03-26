---
title: Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e349a33c90d08606da09ebdf32de6dedb8d6a52c
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2018
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms
Cuando se usa un <xref:System.Windows.Forms.DataGridView> para modificar los datos en la aplicación, a menudo desea ofrecer a los usuarios la posibilidad de agregar nuevas filas de datos al almacén de datos. El <xref:System.Windows.Forms.DataGridView> control es compatible con esta funcionalidad proporcionando una fila para nuevos registros, que siempre se muestra como la última fila. Se marca con un símbolo de asterisco (*) en el encabezado de fila. Las secciones siguientes tratan algunas de las cosas que debe considerar cuando se programa con la fila de nuevos registros habilitada.  
  
## <a name="displaying-the-row-for-new-records"></a>Mostrar la fila para los nuevos registros  
 Use la <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> propiedad para indicar si se muestra la fila de nuevos registros. El valor predeterminado de esta propiedad es `true`.  
  
 Para los datos enlazados caso, se mostrará la fila para los nuevos registros si la <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> propiedad del control y la <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> son propiedad del origen de datos `true`. Si se da alguna `false` , a continuación, la fila no se mostrará.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Rellenar la fila para los nuevos registros con datos predeterminados  
 Cuando el usuario selecciona la fila para los nuevos registros como la fila actual, el <xref:System.Windows.Forms.DataGridView> controlar genera el <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> eventos.  
  
 Este evento proporciona acceso a la nueva <xref:System.Windows.Forms.DataGridViewRow> y permite llenar la nueva fila con datos predeterminados. Para obtener más información, vea [Cómo: especificar valores predeterminados para las nuevas filas en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>La colección de filas  
 La fila para los nuevos registros se encuentra en la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.Rows%2A> colección pero se comporta de manera diferente en dos aspectos:  
  
-   No se puede quitar la fila de nuevos registros la <xref:System.Windows.Forms.DataGridView.Rows%2A> colección mediante programación. Un <xref:System.InvalidOperationException> se produce si se intenta. También, el usuario no puede eliminar la fila de nuevos registros. El <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> método no quita esta fila desde la <xref:System.Windows.Forms.DataGridView.Rows%2A> colección.  
  
-   Puede agregar ninguna fila después de la fila para los nuevos registros. Un <xref:System.InvalidOperationException> se genera si se intenta. Como resultado, la fila para los nuevos registros siempre es la última fila de la <xref:System.Windows.Forms.DataGridView> control. Los métodos de <xref:System.Windows.Forms.DataGridViewRowCollection> que agregan filas:<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, y <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>: todas llamada a métodos de inserción internamente cuando la fila de nuevos registros está presente.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Personalización visual de la fila para los nuevos registros  
 Cuando se crea la fila de nuevos registros, se basa en la fila especificada por el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> propiedad. Los estilos de celda que no se especifican para esta fila se heredan de otras propiedades. Para obtener más información acerca de la herencia de estilo de celda, vea [estilos de celda en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Los valores iniciales mostrados por las celdas de la fila para nuevos registros se recuperan de cada celda <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> propiedad. Para las celdas de tipo <xref:System.Windows.Forms.DataGridViewImageCell>, esta propiedad devuelve una imagen de marcador de posición. En caso contrario, esta propiedad devuelve `null`. Puede invalidar esta propiedad para devolver un valor personalizado. Sin embargo, estos valores iniciales pueden ser reemplazados por un <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> controlador de eventos cuando el foco entra en la fila para los nuevos registros.  
  
 Los iconos estándares de encabezado de la fila, que son una flecha o un asterisco, no se exponen públicamente. Si desea personalizar los iconos, necesitará crear una personalizada <xref:System.Windows.Forms.DataGridViewRowHeaderCell> clase.  
  
 Los iconos estándar utilizan el <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellStyle> en uso por la celda de encabezado de fila. Los iconos estándares no se representan si no hay suficiente espacio para que se muestren por completo.  
  
 Si la celda de encabezado de fila tiene un valor de cadena establecida y, si no hay suficiente espacio para el texto y el icono, el icono se quita primero.  
  
## <a name="sorting"></a>Ordenar  
 En el modo sin enlazar, siempre se agregarán nuevos registros al final de la <xref:System.Windows.Forms.DataGridView> incluso si el usuario haya ordenado el contenido de la <xref:System.Windows.Forms.DataGridView>. El usuario deberá vuelve a aplicar el criterio de ordenación para ordenar la fila a la posición correcta. Este comportamiento es similar de la <xref:System.Windows.Forms.ListView> control.  
  
 En datos modos enlazados y virtuales, el comportamiento de inserción cuando se aplica un criterio de ordenación será depende de la implementación del modelo de datos. Para [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], la fila se ordena inmediatamente en la posición correcta.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Otras notas en la fila de nuevos registros  
 No se puede establecer la <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> propiedad de esta fila a `false`. Un <xref:System.InvalidOperationException> se genera si se intenta.  
  
 La fila para los nuevos registros siempre se crea en el estado no seleccionado.  
  
## <a name="virtual-mode"></a>Modo virtual  
 Si está implementando el modo virtual, necesitará saber si se necesita una fila de nuevos registros en el modelo de datos y cuándo se debe revertir la adición de la fila. La implementación exacta de esta funcionalidad depende de la implementación del modelo de datos y su semántica de transacción, por ejemplo, si el ámbito de confirmación está en el nivel de celda o fila. Para obtener más información, consulte [el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [Entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Especificar valores predeterminados para nuevas filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)
