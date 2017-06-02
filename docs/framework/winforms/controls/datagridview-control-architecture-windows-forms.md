---
title: "Arquitectura del control DataGridView (formularios Windows Forms) | Microsoft Docs"
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
  - "DataGridView (control) [Windows Forms], arquitectura"
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# Arquitectura del control DataGridView (formularios Windows Forms)
El control <xref:System.Windows.Forms.DataGridView> y sus clases derivadas están diseñados para ser un sistema flexible y extensible para mostrar barras de herramientas y editar datos en formato de tabla.  Todas estas clases están contenidas en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> y se les denomina con el prefijo "DataGridView".  
  
## Elementos de arquitectura  
 Las clases que acompañan a la clase <xref:System.Windows.Forms.DataGridView> primaria derivan de <xref:System.Windows.Forms.DataGridViewElement>.  El siguiente modelo de objetos muestra la jerarquía de herencia de <xref:System.Windows.Forms.DataGridViewElement>.  
  
 ![Modelo de objetos DataGridViewElement](../../../../docs/framework/winforms/controls/media/datagridviewelement.png "DataGridViewElement")  
Modelo de objetos DataGridViewElement  
  
 La clase <xref:System.Windows.Forms.DataGridViewElement> proporciona una referencia al control <xref:System.Windows.Forms.DataGridView> primario y tiene una propiedad <xref:System.Windows.Forms.DataGridViewElement.State%2A> que contiene un valor que representa una combinación de valores de la enumeración <xref:System.Windows.Forms.DataGridViewElementStates>.  
  
 En las secciones siguientes se describen más detalladamente las clases que acompañan a <xref:System.Windows.Forms.DataGridView>.  
  
### DataGridViewElementStates  
 La enumeración <xref:System.Windows.Forms.DataGridViewElementStates> contiene los valores siguientes.  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates>  
  
 Los valores de esta enumeración se pueden combinar con los operadores lógicos bit a bit, de modo que la propiedad <xref:System.Windows.Forms.DataGridViewElement.State%2A> puede expresar más de un estado a la vez.  Por ejemplo, un elemento <xref:System.Windows.Forms.DataGridViewElement> puede ser simultáneamente <xref:System.Windows.Forms.DataGridViewElementStates>, <xref:System.Windows.Forms.DataGridViewElementStates> y <xref:System.Windows.Forms.DataGridViewElementStates>.  
  
### Celdas y bandas  
 El control <xref:System.Windows.Forms.DataGridView> se compone de dos tipos fundamentales de objetos: celdas y bandas.  Todas las celdas derivan de la clase base <xref:System.Windows.Forms.DataGridViewCell>.  Los dos tipos de bandas, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewRow>, derivan de la clase base <xref:System.Windows.Forms.DataGridViewBand>.  
  
 El control <xref:System.Windows.Forms.DataGridView> interopera con varias clases, pero las más habituales son: <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewRow>.  
  
### DataGridViewCell  
 La celda es la unidad fundamental de interacción para <xref:System.Windows.Forms.DataGridView>.  La presentación se centra en las celdas y la entrada de datos se suele realizar a través de las celdas.  Puede obtener acceso a las celdas utilizando la colección <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> de la clase <xref:System.Windows.Forms.DataGridViewRow> y tener acceso a las celdas seleccionadas utilizando la colección <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> del control <xref:System.Windows.Forms.DataGridView>.  El modelo de objetos siguiente muestra este uso así como la jerarquía de herencia de <xref:System.Windows.Forms.DataGridViewCell>.  
  
 ![Modelo de objetos DataGridViewCell](../../../../docs/framework/winforms/controls/media/datagridviewcell.png "DataGridViewCell")  
Modelo de objetos DataGridViewCell  
  
 El tipo <xref:System.Windows.Forms.DataGridViewCell> es una clase base abstracta, de la que derivan todos los tipos de celdas.  <xref:System.Windows.Forms.DataGridViewCell> y sus tipos derivados no son controles de Windows Forms, pero algunos hospedan controles de Windows Forms.  Un control hospedado controla normalmente cualquier función de edición admitida por una celda.  
  
 Los objetos <xref:System.Windows.Forms.DataGridViewCell> no controlan su propia apariencia y las características de dibujo de la misma manera que los controles de formularios Windows Forms.  En su lugar, <xref:System.Windows.Forms.DataGridView> se encarga de la apariencia de los objetos <xref:System.Windows.Forms.DataGridViewCell>.  Puede afectar significativamente a la apariencia y comportamiento de celdas interactuando con las propiedades y eventos del control <xref:System.Windows.Forms.DataGridView>.  Si tiene requisitos especiales de personalizaciones que van más allá de los recursos del control <xref:System.Windows.Forms.DataGridView>, puede implementar su propia clase que deriva de <xref:System.Windows.Forms.DataGridViewCell> o de una de sus clases secundarias.  
  
 La lista siguiente muestra las clases derivadas de <xref:System.Windows.Forms.DataGridViewCell>:  
  
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
  
### DataGridViewColumn  
 El esquema del almacén de datos asociado del control <xref:System.Windows.Forms.DataGridView> se expresa en las columnas del control <xref:System.Windows.Forms.DataGridView>.  Puede tener acceso a las columnas del control <xref:System.Windows.Forms.DataGridView> utilizando la colección <xref:System.Windows.Forms.DataGridView.Columns%2A>.  Puede tener acceso a las columnas seleccionadas utilizando la colección <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.  El modelo de objetos siguiente muestra este uso así como la jerarquía de herencia de <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 ![Modelo de objetos DataGridViewColumn](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.png "DataGridViewColumn")  
Modelo de objetos DataGridViewColumn  
  
 Algunos de los tipos de celda clave tienen tipos de columna correspondientes.  Éstos se derivan de la clase base <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 La lista siguiente incluye las clases derivadas de <xref:System.Windows.Forms.DataGridViewColumn>:  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   Tipos de columna personalizada  
  
### Controles de edición DataGridView  
 Las celdas que admiten funciones de edición avanzadas normalmente utilizan un control hospedado que se deriva de un control de formularios Windows Forms.  Estos controles también implementan la interfaz <xref:System.Windows.Forms.IDataGridViewEditingControl>.  El modelo de objetos siguiente muestra el uso de estos controles.  
  
 ![Modelo de objetos de control de edición de DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewediting.png "DataGridViewEditing")  
Modelo de objetos de control de edición DataGridView  
  
 Se proporcionan los controles de edición siguientes con el control <xref:System.Windows.Forms.DataGridView>:  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 Para obtener información sobre cómo crear sus propios controles de edición, vea [Cómo: Alojar controles en celdas DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
 En la tabla siguiente se muestra la relación entre los tipos de celda, tipos de columna y controles de edición.  
  
|Tipo de celda|Control hospedado|Tipo de columna|  
|-------------------|-----------------------|---------------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|no disponible|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|no disponible|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|no disponible|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|no disponible|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### DataGridViewRow  
 La clase <xref:System.Windows.Forms.DataGridViewRow> muestra campos de datos de un registro del almacén de datos al que se asocia el control <xref:System.Windows.Forms.DataGridView>.  Puede tener acceso a las filas del control <xref:System.Windows.Forms.DataGridView> utilizando la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>.  Puede tener acceso a las filas seleccionadas utilizando la colección <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>.  El modelo de objetos siguiente muestra este uso así como la jerarquía de herencia de <xref:System.Windows.Forms.DataGridViewRow>.  
  
 ![Modelo de objetos DataGridViewRow](../../../../docs/framework/winforms/controls/media/datagridviewrow.png "DataGridViewRow")  
Modelo de objetos DataGridViewRow  
  
 Puede derivar sus propios tipos de la clase <xref:System.Windows.Forms.DataGridViewRow>, aunque esto normalmente no será necesario.  El control <xref:System.Windows.Forms.DataGridView> tiene varios eventos relacionados con fila y propiedades para personalizar el comportamiento de los objetos <xref:System.Windows.Forms.DataGridViewRow>.  
  
 Si habilita la propiedad <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> del control <xref:System.Windows.Forms.DataGridView>, aparecerá en la última fila una fila especial para agregar nuevas filas.  Esta fila forma parte de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A>, pero tiene funcionalidad especial que puede requerir su atención.  Para obtener más información, vea [Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 [Información general del control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)   
 [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)   
 [Utilizar la fila de nuevos registros en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)