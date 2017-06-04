---
title: "Tutorial: Asignar el contenido de WPF en Windows Forms en tiempo de dise&#241;o | Microsoft Docs"
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
  - "ElementHost (control), asignar contenido de WPF en tiempo de diseño"
  - "interoperabilidad [WPF]"
  - "Windows Forms, asignaciones de contenido"
  - "contenido WPF [Windows Forms], asignar en tiempo de diseño"
  - "WPF (control de usuario), hospedar en Windows Forms"
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Tutorial: Asignar el contenido de WPF en Windows Forms en tiempo de dise&#241;o
Este tutorial muestra cómo seleccionar los tipos de control de Windows Presentation Foundation \(WPF\) que desea mostrar en el formulario.  Puede seleccionar cualquier tipo de control WPF incluido en su proyecto.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear los tipos de controles WPF.  
  
-   Seleccionar los controles WPF.  
  
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
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C\# llamado `SelectingWpfContent`.  
  
## Crear los tipos de control WPF  
 Después de agregar los tipos de control WPF al proyecto, puede hospedarlos en diferentes controles <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### Para crear tipos de control WPF  
  
1.  Agregue un nuevo proyecto de <xref:System.Windows.Controls.UserControl> de WPF a la solución.  Use el nombre predeterminado del tipo de control, `UserControl1.xaml`.  Para obtener más información, consulte [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.  Para obtener más información, consulte [Cómo: Seleccionar y mover elementos en la superficie de diseño](http://msdn.microsoft.com/es-es/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  En la ventana **Propiedades**, establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en `200`.  
  
4.  Agregue un control <xref:System.Windows.Controls.TextBox?displayProperty=fullName> al <xref:System.Windows.Controls.UserControl> y establezca el valor de la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> en Hosted Content.  
  
5.  Agregue un segundo <xref:System.Windows.Controls.UserControl> de WPF al proyecto.  Use el nombre predeterminado del tipo de control, `UserControl2.xaml`.  
  
6.  En la ventana **Propiedades**, establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en `200`.  
  
7.  Agregue un control <xref:System.Windows.Controls.TextBox?displayProperty=fullName> al <xref:System.Windows.Controls.UserControl> y establezca el valor de la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> en Hosted Content 2.  
  
 **Nota** Por lo general, debería hospedar contenido WPF más sofisticado.  El control <xref:System.Windows.Controls.TextBox?displayProperty=fullName> se usa aquí únicamente con fines ilustrativos.  
  
1.  Compile el proyecto.  
  
## Seleccionar controles WPF  
 Puede asignar contenido de WPF diferente a un control <xref:System.Windows.Forms.Integration.ElementHost>, que ya hospeda contenido.  
  
#### Para seleccionar controles WPF  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **Cuadro de herramientas**, haga doble clic en `UserControl1` para crear una instancia de `UserControl1` en el formulario.  
  
     La instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> llamado `elementHost1`.  
  
3.  En el panel de etiquetas inteligentes de `elementHost1`, abra la lista desplegable **Seleccionar contenido hospedable**.  
  
4.  Seleccione **UserControl2** en el cuadro de lista desplegable.  
  
     El control `elementHost1` ahora hospeda una instancia del tipo `UserControl2`.  
  
5.  En la ventana **Propiedades**, confirme que la propiedad <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> está establecida en **UserControl2**.  
  
6.  En el **Cuadro de herramientas**, en el grupo **Interoperabilidad con WPF**, arrastre un <xref:System.Windows.Forms.Integration.ElementHost> al formulario.  
  
     El nombre predeterminado del nuevo control es `elementHost2`.  
  
7.  En el panel de etiquetas inteligentes de `elementHost2`, abra la lista desplegable **Seleccionar contenido hospedable**.  
  
8.  Seleccione **UserControl1** en la lista desplegable.  
  
9. El control `elementHost2` ahora hospeda una instancia del tipo `UserControl1`.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)