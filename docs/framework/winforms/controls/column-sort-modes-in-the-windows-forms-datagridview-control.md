---
title: "Modos de ordenaci&#243;n de columnas del control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadrículas de datos, modos de ordenación"
  - "DataGridView (control) [Windows Forms], modo de ordenación"
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Modos de ordenaci&#243;n de columnas del control DataGridView de formularios Windows Forms
Las columnas <xref:System.Windows.Forms.DataGridView> tienen tres modos de ordenación.  El modo de ordenación para cada columna se especifica mediante la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de la columna, que se puede establecer en uno de los siguientes valores de enumeración de <xref:System.Windows.Forms.DataGridViewColumnSortMode>.  
  
|Valor de `DataGridViewColumnSortMode`|Descripción|  
|-------------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Valor predeterminado para las columnas de cuadro de texto.  A no ser que los encabezados de columna se utilicen para su selección, si se hace clic en el encabezado de la columna, ordena el <xref:System.Windows.Forms.DataGridView> por esta columna y muestra un glifo que indica el criterio de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Valor predeterminado para las columnas de cuadro que no son de texto.  Puede ordenar esta columna mediante programación; sin embargo, no está pensada para su ordenación, por lo que no se reserva ningún espacio para el glifo de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode>|Puede ordenar esta columna mediante programación y se reserva un espacio para el glifo de ordenación.|  
  
 Se puede cambiar el modo de ordenación de una columna cuyos valores predeterminados sean <xref:System.Windows.Forms.DataGridViewColumnSortMode> si contiene valores que se pueden ordenar con sentido.  Por ejemplo, si se tiene una columna de base de datos que contiene números que representan estados de elementos, se pueden mostrar esos números como iconos correspondientes enlazando una columna de imagen a la columna de la base de datos.  A continuación se pueden cambiar los valores de celda numéricos por los valores de presentación de imagen en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>.  En este caso, si se establece la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> en <xref:System.Windows.Forms.DataGridViewColumnSortMode>, los usuarios podrán ordenar la columna.  La ordenación automática permitirá a los usuarios agrupar los elementos que tengan el mismo estado, incluso si los estados que se corresponden a los números no siguen una secuencia natural.  Las columnas de casilla son otro ejemplo donde la ordenación automática resulta útil para agrupar elementos del mismo estado.  
  
 Se puede ordenar mediante programación un control <xref:System.Windows.Forms.DataGridView> por los valores de cualquier columna o de varias columnas, sin tener en cuenta la configuración de <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>.  La ordenación mediante programación es útil cuando se desea proporcionar una interfaz de usuario propia para ordenar o cuando se desea implementar una ordenación personalizada.  Resulta útil proporcionar una interfaz de usuario de ordenación propia, por ejemplo, cuando se establece el modo de selección de <xref:System.Windows.Forms.DataGridView> para habilitar la selección del encabezado de columna.  En este caso, aunque los encabezados de columna no se pueden utilizar para realizar la ordenación, se querrá que los encabezados muestren el glifo de ordenación apropiado, por tanto se establece la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> en <xref:System.Windows.Forms.DataGridViewColumnSortMode>.  
  
 Las columnas establecidas en modo de ordenación mediante programación no muestran automáticamente ningún glifo de ordenación.  Para estas columnas, se debe mostrar el glifo estableciendo la propiedad <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>.  Esto es necesario si se desea flexibilidad en la ordenación personalizada.  Por ejemplo, si se ordena <xref:System.Windows.Forms.DataGridView> por varias columnas, se pueden mostrar varios glifos de ordenación o ninguno.  
  
 Aunque se puede ordenar mediante programación un <xref:System.Windows.Forms.DataGridView> por cualquier columna, algunas columnas, como las columnas de botones, pueden no contener valores que se ordenen con sentido.  En estas columnas, la configuración de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de <xref:System.Windows.Forms.DataGridViewColumnSortMode> indica que nunca se utilizarán para la ordenación, por tanto no es necesario reservar espacio en el encabezado para el glifo de ordenación.  
  
 Cuando se ordena un <xref:System.Windows.Forms.DataGridView>, se puede determinar tanto la columna de ordenación como el criterio de ordenación comprobando los valores de las propiedades <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A>.  Estos valores no tienen sentido después de una operación de ordenación personalizada.  Para obtener más información sobre la ordenación personalizada, vea la sección Ordenación personalizada de este tema.  
  
 Cuando se ordena un control <xref:System.Windows.Forms.DataGridView> que contiene columnas enlazadas y sin enlazar, no se pueden mantener los valores en las columnas sin enlazar de forma automática.  Para mantener estos valores, se debe implementar el modo virtual estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> en `true` y controlando los eventos <xref:System.Windows.Forms.DataGridView.CellValueNeeded> y <xref:System.Windows.Forms.DataGridView.CellValuePushed>.  Para obtener más información, vea [Cómo: Implementar el modo virtual en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  En modo de enlace no se admite la ordenación por columnas sin enlazar.  
  
## Ordenación mediante programación  
 Puede ordenar mediante programación un <xref:System.Windows.Forms.DataGridView> mediante una llamada al método <xref:System.Windows.Forms.DataGridView.Sort%2A>.  
  
 La sobrecarga `Sort(DataGridViewColumn,ListSortDirection)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> toma <xref:System.Windows.Forms.DataGridViewColumn> y un valor de enumeración <xref:System.ComponentModel.ListSortDirection> como parámetros.  Esta sobrecarga resulta útil cuando se ordena por columnas con valores que se pueden ordenar con sentido, pero a las que no se quiere configurar para la ordenación automática.  Cuando se llama a esta sobrecarga y se pasa a una columna con un valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de <xref:System.Windows.Forms.DataGridViewColumnSortMode?displayProperty=fullName>, las propiedades <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A> se establecen automáticamente y aparece el glifo de ordenación apropiado en el encabezado de columna.  
  
> [!NOTE]
>  Cuando el control <xref:System.Windows.Forms.DataGridView> se enlaza a un origen de datos externo mediante el establecimiento de la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>, la sobrecarga del método `Sort(DataGridViewColumn,ListSortDirection)` no funciona para las columnas sin enlazar.  Además, cuando la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es `true`, sólo se puede llamar a esta sobrecarga para las columnas enlazadas.  Para determinar si una columna tiene está enlazada a datos, se comprueba el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>.  En modo de enlace no se admite la ordenación por columnas sin enlazar.  
  
## Ordenación personalizada  
 Puede personalizar <xref:System.Windows.Forms.DataGridView> utilizando la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> o mediante el control del evento <xref:System.Windows.Forms.DataGridView.SortCompare>.  
  
 La sobrecarga del método `Sort(IComparer)` toma una instancia de una clase que implementa la interfaz <xref:System.Collections.IComparer> como parámetro.  Esta sobrecarga es útil cuando se desea proporcionar una ordenación personalizada; por ejemplo, cuando los valores de una columna no tienen un criterio de ordenación natural o cuando este criterio no es apropiado.  En este caso, no puede utilizar la ordenación automática, pero todavía los usuarios pueden ordenarlas haciendo clic en los encabezados de columna.  Se puede llamar a esta sobrecarga en un controlador para el evento <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> si no se utilizan los encabezados de columna para la selección.  
  
> [!NOTE]
>  La sobrecarga del método `Sort(IComparer)` sólo funciona cuando el control <xref:System.Windows.Forms.DataGridView> no está enlazado a un origen de datos externo y el valor de propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es `false`.  Para personalizar la ordenación de las columnas enlazadas a un origen de datos externo, se deben utilizar las operaciones de ordenación proporcionadas por el origen de datos.  En modo virtual, se deben proporcionar las propias operaciones de ordenación para columnas sin enlazar.  
  
 Para utilizar la sobrecarga del método `Sort(IComparer)`, se debe crear una clase propia que implemente la interfaz <xref:System.Collections.IComparer>.  La interfaz requiere que la clase implemente el método <xref:System.Collections.IComparer.Compare%2A?displayProperty=fullName>, al que el control <xref:System.Windows.Forms.DataGridView> pasa objetos <xref:System.Windows.Forms.DataGridViewRow> como entrada cuando se llama a la sobrecarga del método `Sort(IComparer)`.  De esta forma, se puede calcular la ordenación correcta de la fila en función de los valores de cualquier columna.  
  
 La sobrecarga del método `Sort(IComparer)` no establece las propiedades <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A>, por tanto siempre hay que establecer la propiedad <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName> para mostrar el glifo de ordenación.  
  
 Como alternativa a la sobrecarga del método `Sort(IComparer)`, se puede proporcionar la ordenación personalizada mediante la implementación de un controlador para el evento <xref:System.Windows.Forms.DataGridView.SortCompare>.  Este evento se produce cuando los usuarios hacen clic en los encabezados de las columnas configuradas para su ordenación automática o cuando se llama a la sobrecarga `Sort(DataGridViewColumn,ListSortDirection)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A>.  El evento se produce para cada par de filas del control, lo que permite calcular su orden correcto.  
  
> [!NOTE]
>  El evento <xref:System.Windows.Forms.DataGridView.SortCompare> no se produce cuando se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> o cuando el valor de propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es `true`.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=fullName>   
 [Ordenar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)   
 [Cómo: Personalizar la ordenación en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)