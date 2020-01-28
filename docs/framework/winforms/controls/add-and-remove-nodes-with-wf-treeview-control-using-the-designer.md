---
title: Agregar y quitar nodos con el control TreeView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732243"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a>Cómo: Agregar y quitar nodos de un control TreeView de formularios Windows Forms mediante el Diseñador

Dado que el control Windows Forms <xref:System.Windows.Forms.TreeView> muestra los nodos de forma jerárquica, al agregar un nodo, debe prestar atención a cuál es su nodo primario.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.TreeView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-add-or-remove-nodes-in-the-designer"></a>Para agregar o quitar nodos en el diseñador

1. Seleccione el control <xref:System.Windows.Forms.TreeView>.

2. En la ventana **propiedades** , haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A>.

     Aparece el **Editor TreeNode** .

3. Para agregar nodos, debe existir un nodo raíz; Si no existe ninguna, primero debe agregar una raíz haciendo clic en el botón **Agregar raíz** . Después, puede agregar nodos secundarios seleccionando la raíz o cualquier otro nodo y haciendo clic en el botón **Agregar secundario** .

4. Para eliminar nodos, seleccione el nodo que desea eliminar y, a continuación, haga clic en el botón **eliminar** .

## <a name="see-also"></a>Vea también

- [TreeView (control)](treeview-control-windows-forms.md)
- [Información general del control TreeView](treeview-control-overview-windows-forms.md)
- [Establecer iconos del control TreeView de formularios Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Determinar en qué nodo de TreeView se hizo clic](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
