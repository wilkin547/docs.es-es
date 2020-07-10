---
title: 'Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el diseñador'
description: Obtenga información sobre cómo crear una interfaz de estilo del explorador con los controles Windows Forms ListView y TreeView mediante el diseñador.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: 44d4db1ef3da85dbf411498f486882b86a05c140
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174632"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el diseñador

Una de las ventajas de Visual Studio es la posibilidad de crear aplicaciones de Windows Forms de aspecto profesional en poco tiempo. Un escenario común es la creación de una interfaz de usuario (UI) con <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controles y que se parece a la característica explorador de Windows de los sistemas operativos Windows. El explorador de Windows muestra una estructura jerárquica de los archivos y carpetas en el equipo de un usuario.

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>Para crear el formulario que contiene un control ListView y TreeView

1. En el menú **Archivo** , seleccione **Nuevo**y haga clic en **Proyecto**.

2. En el cuadro de diálogo **Nuevo proyecto** , haga lo siguiente:

    1. En las categorías, elija **Visual Basic** o **Visual C#**.

    2. En la lista de plantillas, elija **Windows Forms aplicación**.

3. Haga clic en **Aceptar**. Se crea un nuevo proyecto de Windows Forms.

4. Agregue un <xref:System.Windows.Forms.SplitContainer> control al formulario y establezca su <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad en <xref:System.Windows.Forms.DockStyle.Fill> .

5. Agregue un <xref:System.Windows.Forms.ImageList> denominado `imageList1` al formulario y use el ventana Propiedades para agregar dos imágenes: una imagen de carpeta y una imagen de documento, en ese orden.

6. Agregue un <xref:System.Windows.Forms.TreeView> control denominado `treeview1` al formulario y colóquelo en el lado izquierdo del <xref:System.Windows.Forms.SplitContainer> control. En el ventana Propiedades de, `treeView1` haga lo siguiente:

    1. Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.

    2. Establezca la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> en `imagelist1.`.

7. Agregue un <xref:System.Windows.Forms.ListView> control denominado `listView1` al formulario y colóquelo en el lado derecho del <xref:System.Windows.Forms.SplitContainer> control. En el ventana Propiedades de, `listview1` haga lo siguiente:

    1. Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.

    2. Establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View.Details>.

    3. Abra el editor de la colección ColumnHeader haciendo clic en los puntos suspensivos ( ![ el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) en la <xref:System.Windows.Forms.ListView.Columns%2A> propiedad **.** Agregue tres columnas y establezca su <xref:System.Windows.Forms.ColumnHeader.Text%2A> propiedad en `Name` , `Type` y `Last Modified` , respectivamente. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

    4. Establezca la propiedad <xref:System.Windows.Forms.ListView.SmallImageList%2A> en `imageList1.`.

8. Implemente el código para rellenar <xref:System.Windows.Forms.TreeView> con los nodos y subnodos. Agregue este código a la clase `Form1`.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. Dado que el código anterior usa el espacio de nombres System.IO, agregue la instrucción using o Import adecuada en la parte superior del formulario.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. Llame al método de configuración desde el paso anterior en el constructor del formulario o el <xref:System.Windows.Forms.Form.Load> método de control de eventos. Agregue este código al constructor del formulario.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. Controle el <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento de `treeview1` **,** e implemente el código para rellenar el `listview1` contenido de un nodo cuando se haga clic en un nodo. Agregue este código a la clase `Form1`.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     Si usa C#, asegúrese de que tiene el <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento asociado a su método de control de eventos. Agregue este código al constructor del formulario.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a>Prueba de la aplicación

Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.

#### <a name="to-test-the-form"></a>Para comprobar el formulario

- Presione F5 para ejecutar la aplicación.

     Verá un formulario dividido que contiene un <xref:System.Windows.Forms.TreeView> control que muestra el directorio del proyecto en el lado izquierdo y un <xref:System.Windows.Forms.ListView> control en el lado derecho con tres columnas. Puede atravesar el seleccionando los <xref:System.Windows.Forms.TreeView> nodos del directorio y el <xref:System.Windows.Forms.ListView> se rellena con el contenido del directorio seleccionado.

## <a name="next-steps"></a>Pasos siguientes

Esta aplicación ofrece un ejemplo de una manera de usar <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ListView> controles juntos. Para obtener más información sobre estos controles, vea los temas siguientes:

- [Procedimiento para agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [Procedimiento para agregar funcionalidades de búsqueda a un control ListView](how-to-add-search-capabilities-to-a-listview-control.md)

- [Procedimiento para asociar un menú contextual a un nodo TreeView](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [Control ListView](listview-control-windows-forms.md)
- [Procedimiento para agregar y quitar nodos con el control TreeView de formularios Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Procedimiento para agregar columnas al control ListView de formularios Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
