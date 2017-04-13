---
title: "Informaci&#243;n general del control ListView (Formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListView"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "vistas de lista"
  - "listas"
  - "ListView (control) [Windows Forms], acerca del control ListView"
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general del control ListView (Formularios Windows Forms)
El control <xref:System.Windows.Forms.ListView> de Windows Forms muestra una lista de elementos con iconos.  Puede utilizar una vista de lista para crear una interfaz de usuario similar al panel derecho del Explorador de Windows.  El control tiene cuatro modos de vista: LargeIcon, SmallIcon, List y Details.  
  
## Qué se puede hacer con el control ListView  
  
> [!NOTE]
>  Un modo de vista adicional, Mosaico, sólo está disponible en el sistema operativo Windows XP y Windows Server 2003.  Para obtener más información, vea [Cómo: Habilitar la vista en mosaico en un control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 El modo LargeIcon muestra iconos grandes junto al texto de los elementos; si el control es lo suficientemente grande, los elementos aparecen en varias columnas.  El modo SmallIcon es igual, pero muestra iconos pequeños.  El modo List muestra iconos pequeños, pero siempre en una sola columna.  El modo Details muestra los elementos en varias columnas.  Para obtener información detallada, vea [Cómo: Agregar columnas al control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md).  El modo de vista se determina mediante la propiedad <xref:System.Windows.Forms.ListView.View%2A>.  Todos los modos de vista pueden mostrar imágenes procedentes de listas de imágenes.  Para obtener información detallada, vea [Cómo: Mostrar iconos del control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 La tabla siguiente muestra algunos de los miembros de <xref:System.Windows.Forms.ListView> y las vistas en que son válidos.  
  
|Miembro de ListView|View|  
|-------------------------|----------|  
|Propiedad <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View>|  
|Propiedad <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View>|  
|Método <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View>|  
|Propiedad <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View>|  
|Evento <xref:System.Windows.Forms.ListView.DrawSubItem>|<xref:System.Windows.Forms.View>|  
|Método <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View>, <xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View>|  
|Método <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View>|  
|Método <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View>|  
|Propiedad <xref:System.Windows.Forms.ListView.Groups%2A>|Todas las vistas excepto <xref:System.Windows.Forms.View>|  
|Propiedad <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View>.|  
|Propiedad <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View>, <xref:System.Windows.Forms.View> o <xref:System.Windows.Forms.View>|  
  
 La propiedad clave del control <xref:System.Windows.Forms.ListView> es <xref:System.Windows.Forms.ListView.Items%2A>, que contiene los elementos que muestra el control.  La propiedad <xref:System.Windows.Forms.ListView.SelectedItems%2A> contiene una colección de los elementos seleccionados actualmente en el control.  Si la propiedad <xref:System.Windows.Forms.ListView.MultiSelect%2A> se establece en `true`, el usuario puede seleccionar varios elementos para, por ejemplo, arrastrar y colocar en otro control varios elementos a la vez.  El control <xref:System.Windows.Forms.ListView> puede mostrar casillas junto a los elementos, si la propiedad <xref:System.Windows.Forms.ListView.CheckBoxes%2A> se establece en `true`.  
  
 La propiedad <xref:System.Windows.Forms.ListView.Activation%2A> determina qué tipo de acción debe tomar el usuario para activar un elemento de la lista: las opciones son <xref:System.Windows.Forms.ItemActivation>, <xref:System.Windows.Forms.ItemActivation> y <xref:System.Windows.Forms.ItemActivation>.  La activación <xref:System.Windows.Forms.ItemActivation> requiere un solo clic para activar el elemento.  La activación <xref:System.Windows.Forms.ItemActivation> requiere que el usuario haga doble clic para activar el elemento; un solo clic cambia el color del texto del elemento.  La activación <xref:System.Windows.Forms.ItemActivation> requiere que el usuario haga doble clic para activar un elemento, pero el elemento no cambia de aspecto.  
  
 El control <xref:System.Windows.Forms.ListView> también admite los estilos visuales y otras características disponibles en la plataforma Windows XP, incluida la agrupación, la vista en mosaico y las marcas de inserción.  Para obtener más información, vea [Características de Windows XP y controles de formularios Windows Forms](http://msdn.microsoft.com/es-es/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0).  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Cómo: Agregar columnas al control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Cómo: Mostrar iconos del control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Cómo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [Cómo: Seleccionar un elemento del control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)   
 [Cómo: Agrupar elementos en un control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)   
 [Cómo: Mostrar una marca de inserción en un control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)   
 [Cómo: Agregar capacidades de búsqueda a un control ListView](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [Cómo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)