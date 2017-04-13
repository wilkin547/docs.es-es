---
title: "C&#243;mo: Definir un icono para un bot&#243;n del control ToolBar mediante el Dise&#241;ador | Microsoft Docs"
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
  - "botones [Windows Forms], imágenes"
  - "ejemplos [Windows Forms], barras de herramientas"
  - "iconos [Windows Forms], botones de la barra de herramientas"
  - "imágenes [Windows Forms], botones de la barra de herramientas"
  - "ToolBar (control) [Windows Forms], agregar iconos a los botones"
  - "barras de herramientas [Windows Forms], agregar iconos a los botones"
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Definir un icono para un bot&#243;n del control ToolBar mediante el Dise&#241;ador
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>, este control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 Los botones <xref:System.Windows.Forms.ToolBar> pueden mostrar iconos dentro de ellos para facilitar la identificación por parte de los usuarios.  Esto se logra a través de agregar las imágenes al componente <xref:System.Windows.Forms.ImageList> y asociarlo al control <xref:System.Windows.Forms.ToolBar>.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.ToolBar> y un componente <xref:System.Windows.Forms.ImageList>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para establecer un icono para un botón de la barra de herramientas en tiempo de diseño  
  
1.  Agregue las imágenes al componente <xref:System.Windows.Forms.ImageList>.  Para obtener más información, vea [Cómo: Agregar o quitar imágenes del componente ImageList mediante el Diseñador](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2.  Seleccione el control <xref:System.Windows.Forms.ToolBar> del formulario.  
  
3.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.ToolBar.ImageList%2A> del control <xref:System.Windows.Forms.ToolBar> en el componente <xref:System.Windows.Forms.ImageList>.  
  
4.  Haga clic en la propiedad <xref:System.Windows.Forms.ToolBar.Buttons%2A> del control <xref:System.Windows.Forms.ToolBar> para seleccionarla y después haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) para abrir el **Editor de la colección ToolBarButton**.  
  
5.  Utilice el botón **Agregar** para agregar botones al control <xref:System.Windows.Forms.ToolBar>.  
  
6.  En la ventana **Propiedades** que aparece en el panel en la parte derecha del **Editor de la colección ToolBarButton**, establezca la propiedad <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> de cada botón de la barra de herramientas en uno de los valores de la lista, que se obtiene de las imágenes que se han agregado al componente <xref:System.Windows.Forms.ImageList>.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolBar>   
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [Barra de herramientas \(Control\)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)   
 [ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)