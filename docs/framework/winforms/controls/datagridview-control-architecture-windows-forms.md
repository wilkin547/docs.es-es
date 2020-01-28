---
title: Arquitectura del control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742530"
---
# <a name="datagridview-control-architecture-windows-forms"></a>Arquitectura del control DataGridView (formularios Windows Forms)
El control <xref:System.Windows.Forms.DataGridView> y sus clases relacionadas están diseñados para ser un sistema flexible y extensible para mostrar y editar datos tabulares. Todas estas clases están contenidas en el espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> y todas se denominan con el prefijo "DataGridView".  
  
## <a name="architecture-elements"></a>Elementos de arquitectura  
 Las clases auxiliares de <xref:System.Windows.Forms.DataGridView> principales derivan de <xref:System.Windows.Forms.DataGridViewElement>. En el modelo de objetos siguiente se ilustra el <xref:System.Windows.Forms.DataGridViewElement> jerarquía de herencia.  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos DataGridViewElement.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 La clase <xref:System.Windows.Forms.DataGridViewElement> proporciona una referencia al control <xref:System.Windows.Forms.DataGridView> primario y tiene una propiedad <xref:System.Windows.Forms.DataGridViewElement.State%2A>, que contiene un valor que representa una combinación de valores de la enumeración <xref:System.Windows.Forms.DataGridViewElementStates>.  
  
 En las secciones siguientes se describen con más detalle las clases complementarias de <xref:System.Windows.Forms.DataGridView>.  
  
### <a name="datagridviewelementstates"></a>DataGridViewElementStates  
 La enumeración <xref:System.Windows.Forms.DataGridViewElementStates> contiene los valores siguientes:  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 Los valores de esta enumeración se pueden combinar con los operadores lógicos bit a bit, por lo que la propiedad <xref:System.Windows.Forms.DataGridViewElement.State%2A> puede expresar más de un estado a la vez. Por ejemplo, un <xref:System.Windows.Forms.DataGridViewElement> se puede <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>y <xref:System.Windows.Forms.DataGridViewElementStates.Visible>simultáneamente.  
  
### <a name="cells-and-bands"></a>Celdas y bandas  
 El control <xref:System.Windows.Forms.DataGridView> consta de dos tipos fundamentales de objetos: celdas y bandas. Todas las celdas derivan de la clase base <xref:System.Windows.Forms.DataGridViewCell>. Los dos tipos de bandas, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewRow>, derivan de la clase base <xref:System.Windows.Forms.DataGridViewBand>.  
  
 El control <xref:System.Windows.Forms.DataGridView> interopera con varias clases, pero lo más frecuente es <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>y <xref:System.Windows.Forms.DataGridViewRow>.  
  
### <a name="datagridviewcell"></a>DataGridViewCell  
 La celda es la unidad fundamental de interacción para el <xref:System.Windows.Forms.DataGridView>. La presentación se centra en las celdas y la entrada de datos se realiza a menudo a través de las celdas. Puede tener acceso a las celdas mediante el <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> colección de la clase <xref:System.Windows.Forms.DataGridViewRow> y puede tener acceso a las celdas seleccionadas mediante la colección <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> del control <xref:System.Windows.Forms.DataGridView>. El siguiente modelo de objetos ilustra este uso y muestra el <xref:System.Windows.Forms.DataGridViewCell> jerarquía de herencia.  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 El <xref:System.Windows.Forms.DataGridViewCell> tipo es una clase base abstracta de la que se derivan todos los tipos de celda. <xref:System.Windows.Forms.DataGridViewCell> y sus tipos derivados no son Windows Forms controles, sino algunos controles de Windows Forms host. Cualquier funcionalidad de edición admitida por una celda se controla normalmente mediante un control hospedado.  
  
 <xref:System.Windows.Forms.DataGridViewCell> objetos no controlan sus propias características de apariencia y dibujo de la misma forma que los controles de Windows Forms. En su lugar, el <xref:System.Windows.Forms.DataGridView> es responsable de la apariencia de sus objetos <xref:System.Windows.Forms.DataGridViewCell>. Puede influir significativamente en la apariencia y el comportamiento de las celdas interactuando con las propiedades y eventos del control <xref:System.Windows.Forms.DataGridView>. Si tiene requisitos especiales para las personalizaciones que están más allá de las capacidades del control <xref:System.Windows.Forms.DataGridView>, puede implementar su propia clase que deriva de <xref:System.Windows.Forms.DataGridViewCell> o de una de sus clases secundarias.  
  
 En la lista siguiente se muestran las clases derivadas de <xref:System.Windows.Forms.DataGridViewCell>:  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- Los tipos de celda personalizados  
  
### <a name="datagridviewcolumn"></a>DataGridViewColumn  
 El esquema del almacén de datos asociado del control de <xref:System.Windows.Forms.DataGridView> se expresa en las columnas del control de <xref:System.Windows.Forms.DataGridView>. Puede tener acceso a las columnas del control <xref:System.Windows.Forms.DataGridView> mediante la colección <xref:System.Windows.Forms.DataGridView.Columns%2A>. Puede tener acceso a las columnas seleccionadas mediante el <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> colección. El siguiente modelo de objetos ilustra este uso y muestra el <xref:System.Windows.Forms.DataGridViewColumn> jerarquía de herencia.  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos DataGridViewColumn.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 Algunos de los tipos de celda clave tienen tipos de columna correspondientes. Se derivan de la clase base <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 En la lista siguiente se muestran las clases derivadas de <xref:System.Windows.Forms.DataGridViewColumn>:  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- Tipos de columna personalizados  
  
### <a name="datagridview-editing-controls"></a>Controles de edición de DataGridView  
 Las celdas que admiten la funcionalidad de edición avanzada suelen utilizar un control hospedado derivado de un control Windows Forms. Estos controles también implementan la interfaz <xref:System.Windows.Forms.IDataGridViewEditingControl>. En el modelo de objetos siguiente se muestra el uso de estos controles.  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos de control de edición de DataGridView.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 Los siguientes controles de edición se proporcionan con el control <xref:System.Windows.Forms.DataGridView>:  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Para obtener información sobre cómo crear sus propios controles de edición, vea [Cómo: hospedar controles en Windows Forms celdas de DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 En la tabla siguiente se muestra la relación entre los tipos de celda, los tipos de columna y los controles de edición.  
  
|Tipo de celda|Control hospedado|Tipo de columna|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|no disponible|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|no disponible|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|no disponible|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|no disponible|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a>DataGridViewRow  
 La clase <xref:System.Windows.Forms.DataGridViewRow> muestra los campos de datos de un registro del almacén de datos al que está asociado el control <xref:System.Windows.Forms.DataGridView>. Puede tener acceso a las filas del control <xref:System.Windows.Forms.DataGridView> mediante la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>. Puede tener acceso a las filas seleccionadas mediante el <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> colección. El siguiente modelo de objetos ilustra este uso y muestra el <xref:System.Windows.Forms.DataGridViewRow> jerarquía de herencia.  
  
 ![Diagrama que muestra la jerarquía del modelo de objetos DataGridViewRow.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 Puede derivar sus propios tipos de la clase <xref:System.Windows.Forms.DataGridViewRow>, aunque normalmente no será necesario. El control <xref:System.Windows.Forms.DataGridView> tiene varios eventos y propiedades relacionados con las filas para personalizar el comportamiento de sus objetos <xref:System.Windows.Forms.DataGridViewRow>.  
  
 Si habilita la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> del control <xref:System.Windows.Forms.DataGridView>, aparece una fila especial para agregar nuevas filas como última fila. Esta fila forma parte de la colección de <xref:System.Windows.Forms.DataGridView.Rows%2A>, pero tiene una funcionalidad especial que puede requerir su atención. Para obtener más información, vea [usar la fila para nuevos registros en el control DataGridView de Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- [Información general del control DataGridView](datagridview-control-overview-windows-forms.md)
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
