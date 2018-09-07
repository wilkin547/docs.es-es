---
title: 'Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el Diseñador'
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
ms.openlocfilehash: 73d3a0bef1ab075aee8e06f676ef17b853773552
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44082640"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el Diseñador
Una de las ventajas de Visual Studio es la capacidad para crear aplicaciones de Windows Forms con aspecto profesional en muy poco tiempo. Un escenario común es crear una interfaz de usuario (UI) con <xref:System.Windows.Forms.ListView> y <xref:System.Windows.Forms.TreeView> los controles que se parece a la característica Explorador de Windows de los sistemas operativos de Windows. El Explorador de Windows muestra una estructura jerárquica de los archivos y carpetas en el equipo del usuario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>Para crear el formulario que contiene un control ListView y TreeView  
  
1.  En el menú **Archivo** , elija **Nuevo**y haga clic en **Proyecto**.  
  
2.  En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:  
  
    1.  En las categorías, elija **Visual Basic** o **Visual C#**.  
  
    2.  En la lista de plantillas, elija **aplicación de Windows Forms**.  
  
3.  Haga clic en **Aceptar**. Se crea un nuevo proyecto de Windows Forms.  
  
4.  Agregar un <xref:System.Windows.Forms.SplitContainer> control al formulario y establezca su <xref:System.Windows.Forms.SplitContainer.Dock%2A> propiedad <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5.  Agregar un <xref:System.Windows.Forms.ImageList> denominado `imageList1` al formulario y usar la ventana de propiedades para agregar dos imágenes: una imagen de una carpeta y una imagen de documento, en ese orden.  
  
6.  Agregar un <xref:System.Windows.Forms.TreeView> control denominado `treeview1` al formulario y colóquelo en el lado izquierdo de la <xref:System.Windows.Forms.SplitContainer> control. En la ventana Propiedades para `treeView1` haga lo siguiente:  
  
    1.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
    2.  Establezca la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> en `imagelist1.`.  
  
7.  Agregar un <xref:System.Windows.Forms.ListView> control denominado `listView1` al formulario y colóquelo en el lado derecho de la <xref:System.Windows.Forms.SplitContainer> control. En la ventana Propiedades para `listview1` haga lo siguiente:  
  
    1.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle.Fill>.  
  
    2.  Establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View.Details>.  
  
    3.  Abra el Editor de la colección ColumnHeader haciendo clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) en el <xref:System.Windows.Forms.ListView.Columns%2A> propiedad **.** Agregue tres columnas y establezca sus <xref:System.Windows.Forms.ColumnHeader.Text%2A> propiedad `Name`, `Type`, y `Last Modified`, respectivamente. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
    4.  Establezca la propiedad <xref:System.Windows.Forms.ListView.SmallImageList%2A> en `imageList1.`.  
  
8.  Implemente el código para rellenar el <xref:System.Windows.Forms.TreeView> con nodos y subnodos. Agregue este código a la clase `Form1`.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. Puesto que el código anterior usa el espacio de nombres System.IO, el uso adecuada de agregar o importar instrucción en la parte superior del formulario.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. Llame al método de instalación desde el paso anterior en el constructor del formulario o <xref:System.Windows.Forms.Form.Load> el método de control de eventos. Agregue este código al constructor del formulario.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. Controlar la <xref:System.Windows.Forms.TreeView.NodeMouseClick> eventos para `treeview1` **,** e implemente el código para rellenar `listview1` con contenido de un nodo cuando se hace clic en un nodo. Agregue este código a la clase `Form1`.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     Si está utilizando C#, asegúrese de que tiene el <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento asociado a su método de control de eventos. Agregue este código al constructor del formulario.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a>Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### <a name="to-test-the-form"></a>Para comprobar el formulario  
  
-   Presione F5 para ejecutar la aplicación.  
  
     Verá un formulario dividido que contenga un <xref:System.Windows.Forms.TreeView> control que muestra el directorio del proyecto en el lado izquierdo, y un <xref:System.Windows.Forms.ListView> control a la derecha con tres columnas. Puede recorrer el <xref:System.Windows.Forms.TreeView> seleccionando los nodos del directorio y el <xref:System.Windows.Forms.ListView> se rellena con el contenido del directorio seleccionado.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Esta aplicación le ofrece un ejemplo de cómo puede usar <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ListView> controles juntos. Para obtener más información sobre estos controles, vea los temas siguientes:  
  
-   [Agregar información personalizada a los controles TreeView o ListView (formularios Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [Agregar capacidades de búsqueda a un control ListView](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [Asociar un menú contextual a un nodo TreeView](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.TreeView>  
 [ListView (Control)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Agregar y quitar nodos con el control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Agregar columnas al control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
