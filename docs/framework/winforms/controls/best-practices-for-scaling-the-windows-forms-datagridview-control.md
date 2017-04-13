---
title: "Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "procedimientos recomendados, DataGridView (control)"
  - "cuadrículas de datos, procedimientos recomendados"
  - "DataGridView (control) [Windows Forms], procedimientos recomendados"
  - "DataGridView (control) [Windows Forms], compartir filas"
  - "DataGridView (control) [Windows Forms], ajustar la escala"
  - "DataGridView (control) [Windows Forms], filas compartidas"
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
caps.latest.revision: 31
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms
Se ha diseñado el control <xref:System.Windows.Forms.DataGridView> para proporcionar la escalabilidad máxima.  Si tiene que mostrar grandes cantidades de datos, siga las instrucciones descritas en este tema para impedir la utilización de grandes cantidades de memoria o la disminución de la capacidad de respuesta de la interfaz de usuario \(IU\).  En este tema se tratan los siguientes materias:  
  
-   Utilizar estilos de celda eficazmente  
  
-   Utilizar menús contextuales eficazmente  
  
-   Utilizar el cambio de tamaño automático eficazmente  
  
-   Utilizar las celdas, filas y colecciones de columnas seleccionadas eficazmente  
  
-   Utilizar filas compartidas  
  
-   Impedir que las filas dejen de estar compartidas  
  
 Si tiene necesidades de rendimiento especiales, puede implementar el modo virtual y proporcionar sus propias operaciones de administración de datos.  Para obtener más información, vea [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## Utilizar estilos de celda eficazmente  
 Cada celda, fila y columna puede tener su propia información de estilo.  La información de estilo se almacena en objetos <xref:System.Windows.Forms.DataGridViewCellStyle>.  Crear objetos de estilo de celda para muchos elementos <xref:System.Windows.Forms.DataGridView> individuales pueden resultar ineficaz, sobre todo al trabajar con grandes cantidades de datos.  Para evitar un impacto en el rendimiento, utilice las instrucciones siguientes:  
  
-   Evite configurar propiedades de estilo de celda para objetos <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewRow> individuales.  Esto incluye el objeto de fila especificado por la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.  Cada nueva fila que se clona de la plantilla de fila recibirá su propia copia del objeto de estilo de celda de la plantilla.  Para obtener una escalabilidad máxima, establezca las propiedades de estilo de celda en el nivel <xref:System.Windows.Forms.DataGridView>.  Por ejemplo, establezca la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> en lugar de la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>.  
  
-   Si algunas celdas requieren un formato distinto del predeterminado, utilice las mismas instancias de <xref:System.Windows.Forms.DataGridViewCellStyle> entre grupos de celdas, filas o columnas.  Evite establecer directamente propiedades de tipo <xref:System.Windows.Forms.DataGridViewCellStyle> en celdas, filas y columnas individuales.  Para obtener un ejemplo de cómo se comparten estilos de celda, vea [Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  Para impedir también una reducción del rendimiento al establecer estilos de celda de manera individual utilice el controlador de eventos <xref:System.Windows.Forms.DataGridView.CellFormatting>.  Para obtener un ejemplo, vea [Cómo: Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   Al determinar un estilo de celda, utilice la propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=fullName> en lugar de la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=fullName>.  Al tener acceso a la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A>, se crea una nueva instancia de la clase <xref:System.Windows.Forms.DataGridViewCellStyle> si aún no se ha utilizado la propiedad.  Además, este objeto quizá no contenga la información de estilo completa para la celda si algunos estilos se heredan de la fila, columna o control.  Para obtener más información sobre herencia de estilos de celda, vea [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## Utilizar los menús contextuales eficazmente  
 Cada celda, fila y columna puede tener su propio menú contextual.  Los controles <xref:System.Windows.Forms.ContextMenuStrip> representan los menús contextuales del control <xref:System.Windows.Forms.DataGridView>.  Igual que con objetos de estilo de celda, al crear menús contextuales para gran cantidad de elementos <xref:System.Windows.Forms.DataGridView> individuales reducirá el rendimiento.  Para impedir esta situación, utilice las instrucciones siguientes:  
  
-   Evite crear menús contextuales para celdas y filas individuales.  Esto incluye la plantilla de fila, que se clona junto con su menú contextual cuando se agregan nuevas filas al control.  Para obtener una escalabilidad máxima, utilice sólo la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del control para especificar un solo menú contextual para el control completo.  
  
-   Si requiere varios menús contextuales para varias filas o celdas, controle los eventos <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> o <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>.  Estos eventos permiten que administre objetos de menú contextual, lo que le permite ajustar el rendimiento.  
  
## Utilizar el cambio de tamaño automático eficazmente  
 Se puede cambiar automáticamente el tamaño de filas, columnas y encabezados a medida que el contenido de la celda cambia de modo que el contenido completo de las celdas se muestre sin recortar.  Al cambiar los modos de ajuste de tamaño también se puede cambiar el tamaño de filas, columnas y encabezados.  Para determinar el tamaño correcto, el control <xref:System.Windows.Forms.DataGridView> debe examinar el valor de todas las celdas que debe incorporar.  Al trabajar con grandes conjuntos de datos, este análisis puede tener un impacto en el rendimiento del control cuando se produce el cambio de tamaño automático.  Para impedir la reducción del rendimiento, siga estas instrucciones:  
  
-   Evite utilizar el tamaño automático en un control <xref:System.Windows.Forms.DataGridView> con un conjunto de gran volumen de filas.  Si utiliza el tamaño automático, sólo cambie el tamaño basándose en las filas mostradas.  Utilice sólo las filas mostradas en modo virtual también.  
  
    -   Para filas y columnas, utilice el campo `DisplayedCells` o `DisplayedCellsExceptHeaders` de las enumeraciones <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode> y <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>.  
  
    -   Para los encabezados de fila, utilice el campo <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> o <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> de la enumeración <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>.  
  
-   Para obtener la escalabilidad máxima, desactive el tamaño automático y utilice el cambio de tamaño mediante programación.  
  
 Para obtener más información, vea [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## Utilizar eficazmente las celdas, filas y las colecciones de columnas seleccionadas  
 La colección <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> no se ejecuta eficazmente con grandes selecciones.  Las colecciones <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> también pueden resultar ineficaces, aunque con un grado menor porque hay muchas menos filas que celdas en un control <xref:System.Windows.Forms.DataGridView> corriente y muchas menos columnas que filas.  Para evitar las reducciones del rendimiento al trabajar con estas colecciones, utilice las instrucciones siguientes:  
  
-   Para determinar si se han seleccionado todas las celdas del <xref:System.Windows.Forms.DataGridView> antes de tener acceso al contenido de la colección <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, compruebe el valor devuelto del método <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>.  Observe, sin embargo, que este método puede producir que las filas dejen de ser compartidas.  Para obtener más información, vea la siguiente sección.  
  
-   Evite utilizar la propiedad <xref:System.Collections.ICollection.Count%2A> de <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=fullName> para determinar el número de celdas seleccionadas.  En su lugar, utilice el método <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=fullName> y pase el valor <xref:System.Windows.Forms.DataGridViewElementStates?displayProperty=fullName>.  De igual forma, utilice los métodos <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=fullName> y <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=fullName> para determinar el número de elementos seleccionados, en lugar de tener acceso a la fila y las colecciones de columnas seleccionadas.  
  
-   Evite los modos de selección basados en celdas.  En su lugar, puede establecer también la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> en <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> o <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName>.  
  
## Utilizar filas compartidas  
 El uso eficaz de la memoria se consigue en el control <xref:System.Windows.Forms.DataGridView> a través de filas compartidas.  Las filas compartirán toda la información que sea posible sobre su apariencia y comportamiento compartiendo instancias de la clase <xref:System.Windows.Forms.DataGridViewRow>.  
  
 Aunque compartir instancias de fila ahorra memoria, las filas pueden dejar de estar compartidas fácilmente.  Por ejemplo, cada vez que un usuario interactúa directamente con una celda, su fila deja de estar compartida.  Dado que no se puede evitar esto, las instrucciones de este tema resultan de utilidad sólo cuando se trabaja con grandes cantidades de datos y sólo cuando los usuarios interactuarán con un parte de los datos relativamente pequeña cada vez que se ejecuta el programa.  
  
 Una fila no se puede compartir en un control <xref:System.Windows.Forms.DataGridView> independiente si cualquiera de sus celdas contiene valores.  Cuando el control <xref:System.Windows.Forms.DataGridView> está enlazado a un origen de datos externo o cuando implementa el modo virtual y proporciona su propio origen de datos, los valores de celda se almacenan fuera del control en lugar de en otros objetos, lo que permite compartir filas.  
  
 Un objeto de fila sólo se puede compartir si el estado de todas sus celdas se puede determinar del estado de la fila y de los estados de las columnas que contienen las celdas.  Si cambia el estado de una celda de modo que ya no se puede deducir el estado de su fila y columna, no se podrá compartir la fila.  
  
 Por ejemplo, una fila no se puede compartir en cualquiera de las situaciones siguientes:  
  
-   La fila contiene una celda seleccionada única que no está en una columna seleccionada.  
  
-   La fila contiene una celda con sus propiedades <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> o <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> establecidas.  
  
-   La fila contiene <xref:System.Windows.Forms.DataGridViewComboBoxCell> con su propiedad <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> establecida.  
  
 En el modo de enlace o el modo virtual, puede proporcionar información sobre herramientas y menús contextuales para celdas individuales controlando los eventos <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> y <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>.  
  
 El control <xref:System.Windows.Forms.DataGridView> intentará utilizar automáticamente filas compartidas cada vez que se agreguen filas a <xref:System.Windows.Forms.DataGridViewRowCollection>.  Utilice las instrucciones siguientes para garantizar que se comparten las filas:  
  
-   Evite llamar a la sobrecarga `Add(Object[])` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> y la sobrecarga `Insert(Object[])` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>.  Estas sobrecargas crean automáticamente filas no compartidas.  
  
-   Asegúrese de que la fila especificada en la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName> se puede compartir en los casos siguientes:  
  
    -   Al llamar a las sobrecargas `Add()` o `Add(Int32)` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> o la sobrecarga `Insert(Int32,Int32)` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>.  
  
    -   Al aumentar el valor de la propiedad <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=fullName>.  
  
    -   Al establecer la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>.  
  
-   Asegúrese de que la fila indicada por el parámetro `indexSource` se puede compartir al llamar a los métodos: <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A> y <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>.  
  
-   Asegúrese de que se puede compartir la fila o filas especificadas cuando se llama a la sobrecarga `Add(DataGridViewRow)` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, al método <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A>, al método `Insert(Int32,DataGridViewRow)`, al método <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> y al método <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=fullName>.  
  
 Para determinar si se comparte una fila, utilice el método <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName> para recuperar el objeto de fila y, a continuación, compruebe la propiedad <xref:System.Windows.Forms.DataGridViewBand.Index%2A> del objeto.  Las filas compartidas siempre tienen un valor de propiedad <xref:System.Windows.Forms.DataGridViewBand.Index%2A> de \-1.  
  
## Impedir que las filas dejen de estar compartidas  
 Las filas compartidas pueden dejar de estar compartidas como consecuencia del código o de la acción del usuario.  Para impedir un impacto en el rendimiento, evite provocar que las filas dejen de estar compartidas.  Durante el desarrollo de aplicaciones, puede controlar el evento <xref:System.Windows.Forms.DataGridView.RowUnshared> para determinar cuándo dejan de estar compartidas las filas.  Esto resulta de utilidad al depurar problemas de uso compartido de filas.  
  
 Para impedir que las filas dejen de estar compartidas, utilice las instrucciones siguientes:  
  
-   Evite la indización de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A> o el recorrido en iteración por ésta con un bucle `foreach`.  Normalmente no necesitará obtener acceso a las filas directamente.  Los métodos <xref:System.Windows.Forms.DataGridView> que operan en filas toman argumentos de índice de fila en lugar de instancias de fila.  De forma adicional, los controladores de eventos relacionados con filas reciben objetos de argumento de evento con propiedades de fila que puede utilizar para manipular filas sin producir que éstas dejen de estar compartidas.  
  
-   Si necesita tener acceso a un objeto de fila, utilice el método <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName> y pase el índice real de la fila.  Observe, sin embargo, que al modificar un objeto de fila compartido recuperado a través de este método, se modificarán todas las filas que comparten este objeto.  La fila para los nuevos registros no se comparte con otras filas, sin embargo, esto no se verá afectado cuando modifique cualquier otra fila.  También tenga en cuenta que filas distintas representadas por una fila compartida pueden tener menús contextuales distintos.  Para recuperar el menú contextual correcto de una instancia de fila compartida, utilice el método <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> y pase el índice real de la fila.  Si en su lugar tiene acceso a la propiedad <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> de la fila compartida, se utilizará el índice de fila compartida de \-1 y no se recuperará el menú contextual correcto.  
  
-   Evite la indización de la colección <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=fullName>.  Al tener acceso directamente a una celda, se producirá que su fila primaria deje de estar compartida, que crea una instancia de un nuevo <xref:System.Windows.Forms.DataGridViewRow>.  Los controladores para los eventos relacionados con celda reciben los objetos de argumento de evento con propiedades de celda que puede utilizar para manipular las celdas sin provocar que las filas dejen de estar compartidas.  También puede utilizar la propiedad <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> para recuperar los índices de fila y columna de la celda actual sin tener acceso directamente a la celda.  
  
-   Evite los modos de selección basados en celdas.  Estos modos producen que las filas dejen de estar compartidas.  En su lugar, puede establecer también la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> en <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName> o <xref:System.Windows.Forms.DataGridViewSelectionMode?displayProperty=fullName>.  
  
-   No controle los eventos <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=fullName> o <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=fullName>.  Estos eventos hacen que las filas dejen de estar compartidas.  Además, no llame a los métodos <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=fullName> o <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=fullName>, que provocan estos eventos.  
  
-   No obtenga acceso a la colección <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=fullName> cuando el valor de propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> sea <xref:System.Windows.Forms.DataGridViewSelectionMode>, <xref:System.Windows.Forms.DataGridViewSelectionMode>, <xref:System.Windows.Forms.DataGridViewSelectionMode> o <xref:System.Windows.Forms.DataGridViewSelectionMode>.  Esto hace que las filas seleccionadas dejen de estar compartidas.  
  
-   No llame al método <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=fullName>.  Este método puede provocar que las filas dejen de estar compartidas.  
  
-   No llame al método <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=fullName> cuando el valor de propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=fullName> sea <xref:System.Windows.Forms.DataGridViewSelectionMode>.  Esto hace que todas las filas dejen de estar compartidas.  
  
-   No establezca la propiedad <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> o <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> de una celda en `false` cuando la propiedad correspondiente de su columna esté establecida en `true`.  Esto hace que todas las filas dejen de estar compartidas.  
  
-   No obtenga acceso a la propiedad <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=fullName>.  Esto hace que todas las filas dejen de estar compartidas.  
  
-   No llame a la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A>.  Al realizar la ordenación con un comparador personalizado se produce que todas las filas dejen de estar compartidas.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Ajuste del rendimiento del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)   
 [Modo virtual del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)   
 [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)   
 [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)