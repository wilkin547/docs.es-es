---
title: Arquitectura del control DataGridView (formularios Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: d215eeaa367156c6228615a8f6e0a7f889efdf60
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713818"
---
# <a name="datagridview-control-architecture-windows-forms"></a>Arquitectura del control DataGridView (formularios Windows Forms)
El <xref:System.Windows.Forms.DataGridView> control y sus clases relacionadas están diseñadas para ser un sistema flexible y extensible para mostrar y editar datos tabulares. Estas clases están incluidas en el <xref:System.Windows.Forms?displayProperty=nameWithType> espacio de nombres y se denominan con el prefijo "DataGridView".  
  
## <a name="architecture-elements"></a>Elementos de arquitectura  
 La principal <xref:System.Windows.Forms.DataGridView> derivan clases complementarias <xref:System.Windows.Forms.DataGridViewElement>. El modelo de objetos siguiente ilustra la <xref:System.Windows.Forms.DataGridViewElement> jerarquía de herencia.  
  
 ![Modelo de objetos DataGridViewElement](./media/datagridviewelement.gif "DataGridViewElement")  
Modelo de objetos DataGridViewElement  
  
 El <xref:System.Windows.Forms.DataGridViewElement> clase proporciona una referencia al elemento primario <xref:System.Windows.Forms.DataGridView> controlar y tiene un <xref:System.Windows.Forms.DataGridViewElement.State%2A> propiedad, que contiene un valor que representa una combinación de valores de la <xref:System.Windows.Forms.DataGridViewElementStates> enumeración.  
  
 Las secciones siguientes describen el <xref:System.Windows.Forms.DataGridView> clases con más detalle complementarias.  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 El <xref:System.Windows.Forms.DataGridViewElementStates> enumeración contiene los siguientes valores:  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 Los valores de esta enumeración se pueden combinar con los operadores lógicos bit a bit, por lo que el <xref:System.Windows.Forms.DataGridViewElement.State%2A> propiedad puede expresar en más de un estado a la vez. Por ejemplo, un <xref:System.Windows.Forms.DataGridViewElement> puede ser simultáneamente <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, y <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.  
  
### <a name="cells-and-bands"></a>Las celdas y bandas  
 El <xref:System.Windows.Forms.DataGridView> control consta de dos tipos fundamentales de objetos: celdas y bandas. Todas las celdas que se derivan de la <xref:System.Windows.Forms.DataGridViewCell> clase base. Los dos tipos de bandas, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewRow>, ambos derivan de la <xref:System.Windows.Forms.DataGridViewBand> clase base.  
  
 El <xref:System.Windows.Forms.DataGridView> control interopera con varias clases, pero son detectados con más frecuencia <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, y <xref:System.Windows.Forms.DataGridViewRow>.  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 La celda es la unidad fundamental de interacción para el <xref:System.Windows.Forms.DataGridView>. La presentación se centra en las celdas y entrada de datos a menudo se realiza a través de las celdas. Puede acceder a las celdas mediante la <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> colección de la <xref:System.Windows.Forms.DataGridViewRow> clase y se pueden acceder a las celdas seleccionadas mediante la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> colección de la <xref:System.Windows.Forms.DataGridView> control. El modelo de objetos siguiente muestra este uso y muestra el <xref:System.Windows.Forms.DataGridViewCell> jerarquía de herencia.  
  
 ![Modelo de objetos DataGridViewCell](./media/datagridviewcell.gif "DataGridViewCell")  
Modelo de objetos DataGridViewCell  
  
 El <xref:System.Windows.Forms.DataGridViewCell> tipo es una clase base abstracta, de la que derivan todos los tipos de celda. <xref:System.Windows.Forms.DataGridViewCell> y sus tipos derivados no son controles de formularios Windows Forms, pero algunos controles de formularios de Windows de host. Cualquier función de edición admitida por una celda normalmente se controla mediante un control hospedado.  
  
 <xref:System.Windows.Forms.DataGridViewCell> objetos no controlan su propia apariencia y las características de dibujo de la misma manera como controles de formularios Windows Forms. En su lugar, el <xref:System.Windows.Forms.DataGridView> es responsable de la apariencia de su <xref:System.Windows.Forms.DataGridViewCell> objetos. Puede afectar significativamente a la apariencia y comportamiento de las celdas mediante la interacción con el <xref:System.Windows.Forms.DataGridView> eventos y propiedades del control. Cuando tenga requisitos especiales para las personalizaciones que van más allá de las capacidades de la <xref:System.Windows.Forms.DataGridView> control, puede implementar su propia clase que derive de <xref:System.Windows.Forms.DataGridViewCell> o uno de sus clases secundarias.  
  
 La siguiente lista muestra las clases derivadas de <xref:System.Windows.Forms.DataGridViewCell>:  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   Tipos de celda personalizados  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 El esquema de la <xref:System.Windows.Forms.DataGridView> almacén de datos adjuntos del control se expresa en el <xref:System.Windows.Forms.DataGridView> columnas del control. Puede tener acceso a la <xref:System.Windows.Forms.DataGridView> columnas del control mediante el uso de la <xref:System.Windows.Forms.DataGridView.Columns%2A> colección. Puede acceder a las columnas seleccionadas mediante la <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> colección. El modelo de objetos siguiente muestra este uso y muestra el <xref:System.Windows.Forms.DataGridViewColumn> jerarquía de herencia.  
  
 ![Modelo de objetos DataGridViewColumn](./media/datagridviewcolumn.gif "DataGridViewColumn")  
Modelo de objetos DataGridViewColumn  
  
 Algunos de los tipos de celda clave tienen tipos de columna correspondientes. Estas se derivan los <xref:System.Windows.Forms.DataGridViewColumn> clase base.  
  
 La siguiente lista muestra las clases derivadas de <xref:System.Windows.Forms.DataGridViewColumn>:  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   Tipos de columna personalizada  
  
### <a name="datagridview-editing-controls"></a>Controles de edición de DataGridView  
 Las celdas que admiten funciones de edición avanzadas normalmente utilizan un control hospedado que se deriva de un control de Windows Forms. Estos controles también implementan la <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaz. El modelo de objetos siguiente muestra el uso de estos controles.  
  
 ![Modelo de objetos de Control de edición de DataGridView](./media/datagridviewediting.gif "DataGridViewEditing")  
Modelo de objetos de control de edición de DataGridView  
  
 Los controles de edición siguientes se proporcionan con el <xref:System.Windows.Forms.DataGridView> control:  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Para obtener información acerca de cómo crear sus propios editar controles, vea [Cómo: Alojar controles en formularios de Windows las celdas de DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 En la tabla siguiente se ilustra la relación entre los tipos de celdas, tipos de columna y controles de edición.  
  
|Tipo de celda|Control hospedado|Tipo de columna|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|N/D|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|no disponible|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|no disponible|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|N/D|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 El <xref:System.Windows.Forms.DataGridViewRow> muestra clase campos de datos de un registro de los datos del almacén al que el <xref:System.Windows.Forms.DataGridView> está asociado el control. Puede tener acceso a la <xref:System.Windows.Forms.DataGridView> filas del control mediante la <xref:System.Windows.Forms.DataGridView.Rows%2A> colección. Puede acceder a las filas seleccionadas mediante la <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> colección. El modelo de objetos siguiente muestra este uso y muestra el <xref:System.Windows.Forms.DataGridViewRow> jerarquía de herencia.  
  
 ![Modelo de objetos DataGridViewRow](./media/datagridviewrow.gif "DataGridViewRow")  
Modelo de objetos DataGridViewRow  
  
 Puede derivar sus propios tipos desde el <xref:System.Windows.Forms.DataGridViewRow> clase, aunque normalmente no será necesario. El <xref:System.Windows.Forms.DataGridView> control tiene varios eventos relacionados con la fila y propiedades para personalizar el comportamiento de su <xref:System.Windows.Forms.DataGridViewRow> objetos.  
  
 Si habilita la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> una fila especial para agregar nuevas filas de propiedad, aparece como la última fila. Esta fila es parte de la <xref:System.Windows.Forms.DataGridView.Rows%2A> colección, pero tiene una funcionalidad especial que requiera su atención. Para obtener más información, consulte [utilizando la fila de nuevos registros en el DataGridView Control de Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también
- [Información general del control DataGridView](datagridview-control-overview-windows-forms.md)
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
