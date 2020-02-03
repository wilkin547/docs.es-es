---
title: Agregar columnas al control ListView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 627f8627aac861877a05c13def07427199807754
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744611"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>Cómo: Agregar columnas al control ListView de formularios Windows Forms mediante el Diseñador

El control <xref:System.Windows.Forms.ListView> de Windows Forms puede mostrar varias columnas para cada elemento de la lista en la vista de **detalles** . Puede utilizar las columnas para mostrar varios tipos de información sobre cada elemento de lista. Por ejemplo, una lista de archivos podría mostrar el nombre de archivo, el tipo de archivo, el tamaño y la fecha en que se modificó el archivo por última vez. Para obtener información sobre cómo rellenar las columnas una vez creadas, vea [Cómo: Mostrar subelementos en columnas con el control ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.ListView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-columns-in-the-designer"></a>Para agregar columnas en el diseñador

1. En la ventana **propiedades** , establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> del control en <xref:System.Windows.Forms.View.Details>.

2. En la ventana **propiedades** , haga clic en el botón de **puntos suspensivos** (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.ListView.Columns%2A>.

     Aparece el editor de la **colección ColumnHeader** .

3. Use el botón **Agregar** para agregar nuevas columnas. Después, puede seleccionar el encabezado de columna y establecer su texto (el título de la columna), la alineación del texto y el ancho.

## <a name="see-also"></a>Consulte también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Agregar y quitar elementos con el control ListView de Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Mostrar subelementos en columnas con el control ListView de Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Mostrar iconos del control ListView de Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
