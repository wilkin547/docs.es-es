---
title: "C&#243;mo: Establecer el fondo de un control Panel de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "colores de fondo, controles de panel de Windows Forms"
  - "imágenes de fondo, controles de panel de Windows Forms"
  - "colores, controles de panel de Windows Forms"
  - "Panel (control) [Windows Forms], fondo"
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Establecer el fondo de un control Panel de formularios Windows Forms mediante el Dise&#241;ador
Un control <xref:System.Windows.Forms.Panel> de un formulario Windows Forms puede mostrar tanto un color como una imagen de fondo.  La propiedad <xref:System.Windows.Forms.Control.BackColor%2A> establece el color de fondo para los controles que contiene el panel, como, por ejemplo, etiquetas y botones de radio.  Si la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> no está establecida, la selección de <xref:System.Windows.Forms.Control.BackColor%2A> rellenará todo el panel.  Si la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A> está establecida, la imagen se mostrará detrás de los controles contenidos en el panel.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.Panel>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para establecer el fondo en el Diseñador de Windows Forms  
  
1.  Seleccione el control <xref:System.Windows.Forms.Panel>.  
  
2.  En la ventana **Propiedades**, haga clic en el botón de flecha que se encuentra junto a la propiedad <xref:System.Windows.Forms.Control.BackColor%2A> para que aparezca una ventana con tres fichas.  
  
3.  Seleccione la ficha **Personalizar** para mostrar una paleta de colores.  
  
4.  Seleccione la ficha **Web** o **Sistema** para mostrar una lista de nombres de colores predefinidos y, a continuación, seleccione un color.  
  
5.  En la ventana **Propiedades**, haga clic en el botón de flecha junto a la propiedad <xref:System.Windows.Forms.Control.BackgroundImage%2A>.  
  
6.  En el cuadro de diálogo  **Abrir**, seleccione el archivo que desea mostrar.  
  
## Vea también  
 <xref:System.Windows.Forms.Control.BackColor%2A>   
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>   
 [Control Panel](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)   
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Cómo: Agrupar controles con el control Panel de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)