---
title: Información general sobre el control ListView
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: 9308ff6646704d16b32669827a1f26bebf6958d8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745155"
---
# <a name="listview-control-overview-windows-forms"></a>Información general del control ListView (Formularios Windows Forms)
El control <xref:System.Windows.Forms.ListView> de Windows Forms muestra una lista de elementos con iconos. Puede usar una vista de lista para crear una interfaz de usuario similar al panel derecho del Explorador de Windows. El control tiene cuatro modos de vista: LargeIcon, SmallIcon, List y details.  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Qué puede hacer con el control ListView  
  
> [!NOTE]
> Un modo de vista adicional, mosaico, solo está disponible en Windows XP y en el sistema operativo Windows Server 2003. Para obtener más información, vea [Cómo: habilitar la vista en mosaico en un control ListView de Windows Forms](how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 El modo LargeIcon muestra iconos grandes junto al texto del elemento; los elementos aparecen en varias columnas si el control es suficientemente grande. El modo SmallIcon es el mismo, salvo que muestra iconos pequeños. El modo de lista muestra iconos pequeños, pero siempre está en una sola columna. El modo de detalles muestra los elementos en varias columnas. Para obtener más información, vea [Cómo: Agregar columnas al control ListView de Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md). El modo de vista viene determinado por la propiedad <xref:System.Windows.Forms.ListView.View%2A>. Todos los modos de vista pueden mostrar imágenes de las listas de imágenes. Para obtener más información, vea [Cómo: Mostrar iconos del control ListView de Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 En la tabla siguiente se enumeran algunos de los miembros de <xref:System.Windows.Forms.ListView> y las vistas en las que son válidos.  
  
|Miembro de ListView|Vista|  
|---------------------|----------|  
|Propiedad<xref:System.Windows.Forms.ListView.Alignment%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Propiedad<xref:System.Windows.Forms.ListView.AutoArrange%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Método <xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>|<xref:System.Windows.Forms.View.Details>|  
|Propiedad<xref:System.Windows.Forms.ListView.Columns%2A>|<xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.Tile>|  
|Evento<xref:System.Windows.Forms.ListView.DrawSubItem>|<xref:System.Windows.Forms.View.Details>|  
|Método <xref:System.Windows.Forms.ListView.FindItemWithText%2A>|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>o <xref:System.Windows.Forms.View.Tile>|  
|Método <xref:System.Windows.Forms.ListView.FindNearestItem%2A>|<xref:System.Windows.Forms.View.SmallIcon> o <xref:System.Windows.Forms.View.LargeIcon>|  
|Método <xref:System.Windows.Forms.ListView.GetItemAt%2A>|<xref:System.Windows.Forms.View.Details> o <xref:System.Windows.Forms.View.Tile>|  
|Propiedad<xref:System.Windows.Forms.ListView.Groups%2A>|Todas las vistas excepto <xref:System.Windows.Forms.View.List>|  
|Propiedad<xref:System.Windows.Forms.ListView.HeaderStyle%2A>|<xref:System.Windows.Forms.View.Details>.|  
|Propiedad<xref:System.Windows.Forms.ListView.InsertionMark%2A>|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>o <xref:System.Windows.Forms.View.Tile>|  
  
 La propiedad clave del control <xref:System.Windows.Forms.ListView> es <xref:System.Windows.Forms.ListView.Items%2A>, que contiene los elementos mostrados por el control. La propiedad <xref:System.Windows.Forms.ListView.SelectedItems%2A> contiene una colección de los elementos seleccionados actualmente en el control. El usuario puede seleccionar varios elementos, por ejemplo, para arrastrar y colocar varios elementos a la vez en otro control, si la propiedad <xref:System.Windows.Forms.ListView.MultiSelect%2A> está establecida en `true`. El control <xref:System.Windows.Forms.ListView> puede mostrar las casillas junto a los elementos, si la propiedad <xref:System.Windows.Forms.ListView.CheckBoxes%2A> está establecida en `true`.  
  
 La propiedad <xref:System.Windows.Forms.ListView.Activation%2A> determina el tipo de acción que el usuario debe realizar para activar un elemento de la lista: las opciones son <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>y <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick> activación requiere un solo clic para activar el elemento. <xref:System.Windows.Forms.ItemActivation.TwoClick> activación requiere que el usuario haga doble clic para activar el elemento; un solo clic cambia el color del texto del elemento. <xref:System.Windows.Forms.ItemActivation.Standard> activación requiere que el usuario haga doble clic para activar un elemento, pero el elemento no cambia de apariencia.  
  
 El control <xref:System.Windows.Forms.ListView> también admite los estilos visuales y otras características disponibles en la plataforma Windows XP, incluida la agrupación, la vista de mosaico y las marcas de inserción.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- [ListView (control)](listview-control-windows-forms.md)
- [Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Agregar columnas al control ListView de formularios Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Mostrar iconos del control ListView de Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Mostrar subelementos en columnas con el control ListView de Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Seleccionar un elemento del control ListView de Windows Forms](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [Agrupar elementos en un control ListView de Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
- [Mostrar una marca de inserción en un control ListView de formularios Windows Forms](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [Agregar capacidades de búsqueda a un control ListView](how-to-add-search-capabilities-to-a-listview-control.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Crear una interfaz de usuario de varios paneles con Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
