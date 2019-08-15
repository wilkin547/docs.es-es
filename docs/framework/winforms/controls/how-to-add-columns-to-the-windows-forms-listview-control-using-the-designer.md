---
title: Procedimiento para agregar columnas al control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: e82fbcf63047873ebc6e5c40b8b9fbeb14a672e5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038180"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Procedimiento para agregar columnas al control ListView de formularios Windows Forms mediante el diseñador

El control <xref:System.Windows.Forms.ListView> Windows Forms puede mostrar varias columnas para cada elemento de la lista en la vista de **detalles** . Puede utilizar las columnas para mostrar varios tipos de información sobre cada elemento de lista. Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, el tipo de archivo, el tamaño y la fecha en que se modificó el archivo por última vez. Para obtener información sobre cómo rellenar las columnas una vez [creadas, consulte How to: Mostrar los subelementos en columnas con el control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)ListView Windows Forms.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ListView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).


### <a name="to-add-columns-in-the-designer"></a>Para agregar columnas en el diseñador

1. En la ventana **propiedades** , establezca la propiedad del <xref:System.Windows.Forms.ListView.View%2A> control en <xref:System.Windows.Forms.View.Details>.

2. En la **ventana Propiedades** , haga clic en el botón![de **puntos suspensivos** (el botón de puntos suspensivos (...) del](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio <xref:System.Windows.Forms.ListView.Columns%2A> .) situado junto a la propiedad.

     Aparece el editor de la **colección ColumnHeader** .

3. Use el botón **Agregar** para agregar nuevas columnas. Después, puede seleccionar el encabezado de columna y establecer su texto (el título de la columna), la alineación del texto y el ancho.

## <a name="see-also"></a>Vea también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Procedimientos: Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedimientos: Mostrar subelementos en columnas con el control ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Cómo: Mostrar iconos del control ListView de Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Procedimientos: Agregar información personalizada a un control TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
