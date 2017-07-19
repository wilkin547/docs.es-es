---
title: "Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de dise&#241;o | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "interoperabilidad [WPF]"
  - "Windows Forms, cambiar las propiedades de contenido de WPF en tiempo de diseño"
  - "contenido WPF [Windows Forms], cambiar propiedades en tiempo de diseño"
  - "contenido WPF, hospedar en Windows Forms"
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de dise&#241;o
Este tutorial muestra cómo cambiar los valores de propiedad de un control de Windows Presentation Foundation \(WPF\) hospedado en un Windows Form.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear el control WPF.  
  
-   Hospedar los controles WPF en un Windows Form.  
  
-   Use el Diseñador de WPF de Visual Studio para cambiar los valores de propiedad.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
## Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, se admiten solo proyectos de C\# y Visual Basic.  
  
#### Para crear el proyecto  
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C\# llamado `WpfHost`.  
  
## Crear el control WPF  
 Después de agregar un control WPF al proyecto, puede organizarlo en el formulario.  
  
#### Para crear controles WPF  
  
1.  Agregue un nuevo <xref:System.Windows.Controls.UserControl> WPF al proyecto.  Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.  Para obtener más información, consulte [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En la ventana **Propiedades**, establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Azul`.  
  
3.  Compile el proyecto.  
  
## Cambiar los valores de propiedad en el control WPF  
 La etiqueta inteligente <xref:System.Windows.Forms.Integration.ElementHost> permite cambiar fácilmente las propiedades del contenido WPF hospedado mediante WPF Designer.  
  
#### Para hospedar un control WPF  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **Cuadro de herramientas**, en la pestaña **Controles de usuario de WPF**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
3.  En el panel de etiquetas inteligentes **Tareas de ElementHost**, seleccione **Editar contenido hospedado**.  
  
     Se abre UserControl1.xaml en WPF Designer.  
  
4.  En la ventana **Propiedades**, establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Rojo`.  
  
5.  Recompile el proyecto.  
  
6.  Abra `Form1` en el Diseñador de Windows Forms.  
  
     La instancia de `UserControl1` tiene un fondo rojo.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Cómo: Delimitar y acoplar controles secundarios en un control TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [Cómo: Alinear un control con los bordes de los formularios en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)   
 [Tutorial: Organizar controles en formularios Windows Forms mediante líneas de ajuste](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)