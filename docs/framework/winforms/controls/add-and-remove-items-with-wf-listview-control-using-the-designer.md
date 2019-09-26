---
title: Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 62665746ea9fcd1553717b02b1f1349dc6415ab2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040088"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms mediante el diseñador

El proceso de agregar un elemento a un control <xref:System.Windows.Forms.ListView> de Windows Forms consiste principalmente en especificar el elemento y asignarle propiedades. La adición o eliminación de elementos de lista se puede realizar en cualquier momento.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.ListView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-items-using-the-designer"></a>Para agregar o quitar elementos mediante el diseñador

1. Seleccione el control <xref:System.Windows.Forms.ListView>.

2. En la ventana **propiedades** , haga clic en los![ **puntos suspensivos** (el botón de puntos suspensivos (...) del botón](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio. <xref:System.Windows.Forms.ListView.Items%2A> ) situado junto a la propiedad.

     Aparece el editor de la **colección ListViewItem** .

3. Para agregar un elemento, haga clic en el botón **Agregar** . Después, puede establecer las propiedades del nuevo elemento, como las <xref:System.Windows.Forms.ListView.Text%2A> propiedades y. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>

4. Para quitar un elemento, selecciónelo y haga clic en el botón **quitar** .

## <a name="see-also"></a>Vea también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Cómo: Agregar columnas al control Windows Forms ListView](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Cómo: Mostrar subelementos en columnas con el control ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Cómo: Mostrar iconos del control ListView de Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Cómo: Agregar información personalizada a un control TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Cómo: Agrupar elementos en un control Windows Forms ListView](how-to-group-items-in-a-windows-forms-listview-control.md)
