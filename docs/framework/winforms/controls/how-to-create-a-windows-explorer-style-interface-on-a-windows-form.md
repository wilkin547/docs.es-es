---
title: "C&#243;mo: Crear una interfaz similar a la del Explorador de Windows en Windows Forms | Microsoft Docs"
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
  - "formularios, de tipo Explorador de Windows"
  - "SplitContainer (control) [Windows Forms], interfaz de tipo Explorador"
  - "Explorador de Windows, crear con formularios Windows Forms"
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Crear una interfaz similar a la del Explorador de Windows en Windows Forms
La interfaz del Explorador de Windows es una interfaz de usuario que se elige con frecuencia para aplicaciones debido a su familiaridad inmediata.  
  
 El Explorador de Windows es fundamentalmente un control <xref:System.Windows.Forms.TreeView> y un control <xref:System.Windows.Forms.ListView> situados en paneles independientes.  Existe un divisor que permite modificar el tamaño de los paneles.  Esta organización de los controles es muy eficaz para mostrar y explorar información.  
  
 Los pasos siguientes muestran cómo organizar los controles en un formulario similar al Explorador de Windows.  No se explica cómo agregar la funcionalidad de exploración de archivos de la aplicación Explorador de Windows.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear un Windows Form similar al Explorador de Windows  
  
1.  Cree un proyecto nuevo de aplicación para Windows.  Para obtener información detallada, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En el **Cuadro de herramientas**:  
  
    1.  Arrastre un control <xref:System.Windows.Forms.SplitContainer> a su formulario.  
  
    2.  Arrastre un control <xref:System.Windows.Forms.TreeView> y suéltelo en **SplitterPanel1** \(el panel del control <xref:System.Windows.Forms.SplitContainer> marcado como **Panel1**\).  
  
    3.  Arrastre un control <xref:System.Windows.Forms.ListView> y suéltelo en **SplitterPanel2** \(el panel del control <xref:System.Windows.Forms.SplitContainer> marcado como **Panel2**\).  
  
3.  Seleccione los tres controles presionando la tecla CTRL y haciendo clic en ellos uno a uno.  Al seleccionar el control <xref:System.Windows.Forms.SplitContainer>, haga clic en la barra de división, en lugar de en los paneles.  
  
    > [!NOTE]
    >  No utilice el comando **Seleccionar todo** del menú **Edición**.  De lo contrario, la propiedad que se necesita en el paso siguiente no aparecerá en la ventana **Propiedades**.  
  
4.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
5.  Presione F5 para ejecutar la aplicación.  
  
     El formulario muestra una interfaz de usuario dividida en dos partes, similar a la del Explorador de Windows.  
  
    > [!NOTE]
    >  Si arrastra el divisor, los paneles cambian de tamaño.  
  
## Vea también  
 <xref:System.Windows.Forms.SplitContainer>   
 [Cómo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)   
 [Cómo: Definir el comportamiento de cambio de tamaño y colocación de una ventana dividida](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)   
 [Cómo: Dividir una ventana horizontalmente](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)   
 [SplitContainer \(Control\)](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)