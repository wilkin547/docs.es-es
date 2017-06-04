---
title: "Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el Dise&#241;ador | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "aplicaciones de tipo Explorador"
  - "aplicaciones de tipo Explorador, tutoriales"
  - "ListView (control) [Windows Forms], interfaz de tipo Explorador"
  - "ListView (control) [Windows Forms], interfaz de tipo explorador"
  - "ListView (control) [Windows Forms], controles TreeView utilizados"
  - "TreeView (control) [Windows Forms], controles ListView utilizados"
  - "TreeView (control) [Windows Forms], utilizar para una interfaz de tipo Explorador"
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Tutorial: Crear una interfaz de tipo Explorador con los controles ListView y TreeView mediante el Dise&#241;ador
Una de las ventajas de Visual Studio es la capacidad de crear aplicaciones de Windows Forms con apariencia profesional en muy poco tiempo.  Un escenario común es crear una interfaz de usuario con los controles <xref:System.Windows.Forms.ListView> y <xref:System.Windows.Forms.TreeView> que se parece a la característica del Explorador de Windows de los sistemas operativos Windows.  Explorador de Windows muestra una estructura jerárquica de los archivos y carpetas en el equipo de usuario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear el formulario que contiene un control ListView y TreeView  
  
1.  En el menú **Archivo**, elija **Nuevo** y haga clic en **Proyecto**.  
  
2.  En el cuadro de diálogo **Nuevo proyecto**, siga los siguientes pasos:  
  
    1.  En las categorías, elija **Visual Basic** o **Visual C\#**.  
  
    2.  En la lista de plantillas, elija **Aplicación de Windows Forms**.  
  
3.  Haga clic en **Aceptar**.  Se crea un nuevo proyecto de formularios Windows Forms.  
  
4.  Agregue un control <xref:System.Windows.Forms.SplitContainer> al formulario y establezca su propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
5.  Agregue un objeto <xref:System.Windows.Forms.ImageList> denominado `imageList1` al formulario y use la ventana Propiedades para agregar dos imágenes: una imagen de carpeta y otra de documento, por este orden.  
  
6.  Agregue un control <xref:System.Windows.Forms.TreeView> denominado `treeview1` al formulario y colóquelo en el lado izquierdo del control <xref:System.Windows.Forms.SplitContainer>.  En la ventana Propiedades de `treeView1`, haga lo siguiente:  
  
    1.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
    2.  Establezca la propiedad <xref:System.Windows.Forms.TreeView.ImageList%2A> en `imagelist1.`.  
  
7.  Agregue un control <xref:System.Windows.Forms.ListView> denominado `listView1` al formulario y colóquelo en el lado derecho del control <xref:System.Windows.Forms.SplitContainer>.  En la ventana Propiedades de `listview1`, haga lo siguiente:  
  
    1.  Establezca la propiedad <xref:System.Windows.Forms.Control.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
    2.  Establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> en <xref:System.Windows.Forms.View>.  
  
    3.  Abra el Editor de la colección ColumnHeader haciendo clic en los puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) en la propiedad <xref:System.Windows.Forms.ListView.Columns%2A>**.** Agregue tres columnas y establezca su propiedad <xref:System.Windows.Forms.ColumnHeader.Text%2A> en `Name`, `Type` y `Last Modified`, respectivamente.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
    4.  Establezca la propiedad <xref:System.Windows.Forms.ListView.SmallImageList%2A> en `imageList1.`.  
  
8.  Implemente el código para rellenar <xref:System.Windows.Forms.TreeView> con nodos y subnodos.  Agregue este código a la clase `Form1`.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. Dado que el código anterior usa el espacio de nombres System.IO, agregue la instrucción Using o Import apropiada en la parte superior del formulario.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. Llame al método de configuración del paso anterior en el constructor del formulario o al método de control de eventos <xref:System.Windows.Forms.Form.Load>.  Agregue este código al constructor del formulario.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. Controle el evento <xref:System.Windows.Forms.TreeView.NodeMouseClick> de `treeview1` e implemente el código para que se rellene `listview1` con el contenido de un nodo cuando se haga clic en un nodo.  Agregue este código a la clase `Form1`.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     Si está utilizando C\#, asegúrese de que tiene el evento <xref:System.Windows.Forms.TreeView.NodeMouseClick> asociado a su método de control de eventos.  Agregue este código al constructor del formulario.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## Probar la aplicación  
 Puede comprobar el formulario para asegurarse de que se comporta de la forma prevista.  
  
#### Para comprobar el formulario  
  
-   Presione F5 para ejecutar la aplicación.  
  
     Verá un formulario dividido que contiene un control <xref:System.Windows.Forms.TreeView> que muestra el directorio del proyecto en la parte izquierda y un control <xref:System.Windows.Forms.ListView> en la parte derecha con tres columnas.  Puede moverse por el control <xref:System.Windows.Forms.TreeView> seleccionando nodos de directorio y el control <xref:System.Windows.Forms.ListView> se rellenará con el contenido del directorio seleccionado.  
  
## Pasos siguientes  
 Esta aplicación le da un ejemplo de cómo se utilizar juntos los controles <xref:System.Windows.Forms.TreeView> y <xref:System.Windows.Forms.ListView>.  Para obtener más información acerca del uso de estos controles, consulte los temas siguientes:  
  
-   [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [Cómo: Agregar capacidades de búsqueda a un control ListView](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [Cómo: Asociar un menú contextual a un nodo TreeView](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.TreeView>   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Cómo: Agregar y quitar nodos con el control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Cómo: Agregar columnas al control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)