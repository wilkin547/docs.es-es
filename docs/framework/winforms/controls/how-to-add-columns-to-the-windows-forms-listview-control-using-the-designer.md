---
title: Procedimiento para agregar columnas al control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 48fd223c8e770e64513d79ef9d24f93321c98332
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322100"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Procedimiento para agregar columnas al control ListView de formularios Windows Forms mediante el diseñador
Los formularios de Windows <xref:System.Windows.Forms.ListView> control puede mostrar varias columnas para cada lista de elementos cuando se encuentra en la **detalles** vista. Puede usar las columnas para mostrar varios tipos de información sobre cada elemento de lista. Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, tipo de archivo, tamaño y fecha de que última modificación del archivo. Para obtener información sobre cómo rellenar las columnas una vez que se crean, vea [Cómo: Mostrar subelementos en columnas con el Windows Forms Control ListView](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.ListView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-columns-in-the-designer"></a>Para agregar columnas en el diseñador  
  
1. En el **propiedades** ventana, establezca el control <xref:System.Windows.Forms.ListView.View%2A> propiedad <xref:System.Windows.Forms.View.Details>.  
  
2. En el **propiedades** ventana, haga clic en el **puntos suspensivos** botón (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a el <xref:System.Windows.Forms.ListView.Columns%2A> propiedad.  
  
     El **Editor de la colección ColumnHeader** aparece.  
  
3. Use la **agregar** para agregar nuevas columnas. A continuación, puede seleccionar el encabezado de columna y establezca su texto (el título de la columna), la alineación del texto y el ancho.  
  
## <a name="see-also"></a>Vea también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Cómo: Agregar y quitar elementos con el Control ListView de formularios de Windows](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Cómo: Mostrar subelementos en columnas con el Control ListView de formularios de Windows](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Cómo: Mostrar iconos para el Control ListView de formularios de Windows](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Cómo: Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
