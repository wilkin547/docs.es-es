---
title: "C&#243;mo: Agregar botones a un control ToolBar mediante el Dise&#241;ador | Microsoft Docs"
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
  - "ejemplos [Windows Forms], barras de herramientas"
  - "ToolBar (control) [Windows Forms], agregar botones"
  - "ToolBar (control) [Windows Forms], agregar menús desplegables"
  - "ToolBar (control) [Windows Forms], agregar separadores"
  - "barras de herramientas [Windows Forms], agregar botones"
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Agregar botones a un control ToolBar mediante el Dise&#241;ador
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.ToolBar>, este control <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 Una parte integral del control <xref:System.Windows.Forms.ToolBar> la constituyen los botones que se le agregan.  Estos botones se pueden utilizar para proporcionar acceso sencillo a comandos de menú o, de forma alternativa, pueden incluirse en otra área de la interfaz de usuario de la aplicación para exponer comandos a los usuarios que no están disponibles en la estructura de menús.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.ToolBar>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar botones en tiempo de diseño  
  
1.  Seleccione el control <xref:System.Windows.Forms.ToolBar>.  
  
2.  En la ventana **Propiedades**, haga clic en la propiedad <xref:System.Windows.Forms.ToolBar.Buttons%2A> para seleccionarla y clic en el botón de **puntos suspensivos** \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) para abrir el **Editor de la colección ToolBarButton**\(\).  
  
3.  Utilice los botones **Agregar** y **Quitar** para agregar y quitar botones del control <xref:System.Windows.Forms.ToolBar>.  
  
4.  Configure las propiedades de los botones individuales en la ventana **Propiedades** que aparece en el panel en el lateral derecho del editor.  En la tabla siguiente se muestran algunas propiedades importantes a tener en cuenta.  
  
    |Propiedad.|Descripción|  
    |----------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Establece el menú que se va a mostrar en el botón de lista desplegable de la barra de herramientas.  La propiedad <xref:System.Windows.Forms.ToolBarButton.Style%2A> del botón de la barra de herramientas debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle>.  Esta propiedad acepta una instancia de la clase <xref:System.Windows.Forms.ContextMenu> como una referencia.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Establece si hay un botón de la barra de herramientas de tipo alternar parcialmente presionado.  La propiedad <xref:System.Windows.Forms.ToolBarButton.Style%2A> del botón de la barra de herramientas debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Establece si hay actualmente un botón de la barra de herramientas de tipo alternar en estado presionado.  La propiedad <xref:System.Windows.Forms.ToolBarButton.Style%2A> del botón de la barra de herramientas debe establecerse en <xref:System.Windows.Forms.ToolBarButtonStyle> o <xref:System.Windows.Forms.ToolBarButtonStyle>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Establece el estilo de los botones de la barra de herramientas.  Debe ser uno de los valores de la enumeración <xref:System.Windows.Forms.ToolBarButtonStyle>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Cadena de texto mostrada en el botón.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Texto que aparece como ToolTip para el botón.|  
  
5.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo y crear los paneles especificados.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolBar>   
 [Cómo: Definir un icono para un botón ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)   
 [Cómo: Desencadenar eventos de menú para los botones de la barra de herramientas](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)   
 [Información general del control ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)   
 [Barra de herramientas \(Control\)](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)