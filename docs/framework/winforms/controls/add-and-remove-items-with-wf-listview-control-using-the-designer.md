---
title: Agregar y quitar elementos con el control ListView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: cab40c556d9e5d21ce15bcd3d4da367bc08f33ab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732295"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a>Cómo: Agregar y quitar elementos de un control ListView de formularios Windows Forms mediante el Diseñador

El proceso de agregar un elemento a un Windows Forms control <xref:System.Windows.Forms.ListView> consiste principalmente en especificar el elemento y asignarle propiedades. La adición o eliminación de elementos de lista se puede realizar en cualquier momento.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.ListView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-items-using-the-designer"></a>Para agregar o quitar elementos mediante el diseñador

1. Seleccione el control <xref:System.Windows.Forms.ListView>.

2. En la ventana **propiedades** , haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.

     Aparece el editor de la **colección ListViewItem** .

3. Para agregar un elemento, haga clic en el botón **Agregar** . Después, puede establecer las propiedades del nuevo elemento, como las propiedades <xref:System.Windows.Forms.ListView.Text%2A> y <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.

4. Para quitar un elemento, selecciónelo y haga clic en el botón **quitar** .

## <a name="see-also"></a>Vea también

- [Información general del control ListView](listview-control-overview-windows-forms.md)
- [Agregar columnas al control ListView de formularios Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Mostrar subelementos en columnas con el control ListView de Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Mostrar iconos del control ListView de Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Agrupar elementos en un control ListView de Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
