---
title: Información general del control ListView (Formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: 8ceed741e72dae46f7f791b7564b7f5c38f82bc2
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664632"
---
# <a name="listview-control-overview-windows-forms"></a>Información general del control ListView (Formularios Windows Forms)
El control <xref:System.Windows.Forms.ListView> de Windows Forms muestra una lista de elementos con iconos. Puede usar una vista de lista para crear una interfaz de usuario similar al panel derecho del Explorador de Windows. El control tiene cuatro modos de vista: LargeIcon, SmallIcon, lista y detalles.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>¿Qué puede hacer con el Control ListView  
  
> [!NOTE]
>  Un modo de vista adicionales, mosaico, sólo está disponible en Windows XP y el sistema operativo Windows Server 2003. Para obtener más información, vea [Cómo: Habilitar la vista de mosaico en un Windows Forms Control ListView](../../../../docs/framework/winforms/controls/how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 El modo LargeIcon muestra iconos grandes junto al texto del elemento; los elementos aparecen en varias columnas si el control es suficientemente grande. El modo SmallIcon es el mismo, salvo en que muestra iconos pequeños. El modo de lista muestra iconos pequeños, pero siempre está en una sola columna. El modo de detalles muestra los elementos en varias columnas. Para obtener más detalles, vea [Cómo: Agregar columnas a la Windows Forms Control ListView](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md). El modo de vista viene determinada por la <xref:System.Windows.Forms.ListView.View%2A> propiedad. Todos los modos de vista pueden mostrar imágenes desde listas de imágenes. Para obtener más detalles, vea [Cómo: Mostrar iconos de la Windows Forms Control ListView](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 En la tabla siguiente se enumera algunos de los <xref:System.Windows.Forms.ListView> miembros y las vistas que son válidos.  
  
|Miembro de ListView|Ver|  
|---------------------|----------|  
|Propiedad <xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Propiedad <xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Método <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Propiedad <xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.Tile>|  
|Evento<xref:System.Windows.Forms.ListView.DrawSubItem> |<xref:System.Windows.Forms.View.Details>|  
|Método <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>o <xref:System.Windows.Forms.View.Tile>|  
|Método <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Método <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.Tile>|  
|Propiedad <xref:System.Windows.Forms.ListView.Groups%2A>|Todas las vistas excepto <xref:System.Windows.Forms.View.List>|  
|Propiedad <xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View.Details>.|  
|Propiedad <xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>o <xref:System.Windows.Forms.View.Tile>|  
  
 La propiedad de clave de la <xref:System.Windows.Forms.ListView> control es <xref:System.Windows.Forms.ListView.Items%2A>, que contiene los elementos mostrados por el control. El <xref:System.Windows.Forms.ListView.SelectedItems%2A> propiedad contiene una colección de los elementos seleccionados actualmente en el control. El usuario puede seleccionar varios elementos, por ejemplo, para arrastrar y colocar varios elementos en un momento a otro control, si la <xref:System.Windows.Forms.ListView.MultiSelect%2A> propiedad está establecida en `true`. El <xref:System.Windows.Forms.ListView> control puede mostrar casillas junto a los elementos, si la <xref:System.Windows.Forms.ListView.CheckBoxes%2A> propiedad está establecida en `true`.  
  
 El <xref:System.Windows.Forms.ListView.Activation%2A> propiedad determina qué tipo de acción debe realizar el usuario para activar un elemento en la lista: las opciones son <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, y <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick> la activación requiere un solo clic para activar el elemento. <xref:System.Windows.Forms.ItemActivation.TwoClick> activación requiere que el usuario haga doble clic para activar el elemento; un solo clic cambia el color del texto del elemento. <xref:System.Windows.Forms.ItemActivation.Standard> activación requiere que el usuario haga doble clic para activar un elemento, pero el elemento no cambia de apariencia.  
  
 El <xref:System.Windows.Forms.ListView> control también admite los estilos visuales y otras características disponibles en la plataforma Windows XP, incluida la agrupación, la vista en mosaico y marcas de inserción.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ListView>
- [ListView (Control)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [Cómo: Agregar y quitar elementos con el Control ListView de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Cómo: Agregar columnas al Control de ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Cómo: Mostrar iconos para el Control ListView de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Cómo: Mostrar subelementos en columnas con el Control ListView de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Cómo: Seleccione un elemento en el Control ListView de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [Cómo: Agrupar elementos en un Control ListView de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)
- [Cómo: Mostrar una marca de inserción en un Control ListView de formularios de Windows](../../../../docs/framework/winforms/controls/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [Cómo: Agregar capacidades de búsqueda a un Control ListView](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)
- [Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Cómo: Crear una interfaz de usuario de varios paneles con formularios de Windows](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)
