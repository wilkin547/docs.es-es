---
title: Procedimiento para agregar y quitar nodos con el control TreeView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ef3a963b5621f0b972b02a007681f600fbdb1050
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "69040070"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Procedimiento para agregar y quitar nodos con el control TreeView de formularios Windows Forms mediante el diseñador

Dado que el <xref:System.Windows.Forms.TreeView> control Windows Forms muestra los nodos de forma jerárquica, al agregar un nodo debe prestar atención a cuál es su nodo primario.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.TreeView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-nodes-in-the-designer"></a>Para agregar o quitar nodos en el diseñador

1. Seleccione el control <xref:System.Windows.Forms.TreeView>.

2. En la ventana **propiedades** , haga clic en los![ **puntos suspensivos** (el botón de puntos suspensivos (...) del botón](./media/visual-studio-ellipsis-button.png)ventana Propiedades de Visual Studio. <xref:System.Windows.Forms.TreeView.Nodes%2A> ) situado junto a la propiedad.

     Aparece el **Editor TreeNode** .

3. Para agregar nodos, debe existir un nodo raíz; Si no existe ninguna, primero debe agregar una raíz haciendo clic en el botón **Agregar raíz** . Después, puede agregar nodos secundarios seleccionando la raíz o cualquier otro nodo y haciendo clic en el botón **Agregar secundario** .

4. Para eliminar nodos, seleccione el nodo que desea eliminar y, a continuación, haga clic en el botón **eliminar** .

## <a name="see-also"></a>Vea también

- [TreeView (control)](treeview-control-windows-forms.md)
- [Información general del control TreeView](treeview-control-overview-windows-forms.md)
- [Cómo: Establecer iconos para el control TreeView Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Cómo: Recorrer en iteración todos los nodos de un control TreeView Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Cómo: Determinar en qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Cómo: Agregar información personalizada a un control TreeView o ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
