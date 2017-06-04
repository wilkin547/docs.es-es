---
title: "Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de dise&#241;o | Microsoft Docs"
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
  - "ElementHost (control)"
  - "hospedar contenido de WPF en formularios Windows Forms"
  - "interoperabilidad, WPF y Windows Forms"
  - "contenido WPF, hospedar en Windows Forms"
  - "WPF (control de usuario), hospedar en Windows Forms"
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de dise&#241;o
En este tema se muestra cómo crear un control de Windows Presentation Foundation \(WPF\) para usarlo en aplicaciones basadas en Windows Forms.  
  
 En este tutorial, realizará las tareas siguientes:  
  
-   Crear el proyecto.  
  
-   Crear un nuevo control WPF.  
  
-   Agregar el nuevo control WPF a un Windows Form.  El control WPF se hospeda en un control <xref:System.Windows.Forms.Integration.ElementHost>.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Crear el proyecto  
 El primer paso es crear el proyecto de Windows Forms.  
  
> [!NOTE]
>  Al hospedar contenido de WPF, se admiten solo proyectos de C\# y Visual Basic.  
  
#### Para crear el proyecto  
  
-   Cree un nuevo proyecto de aplicación de Windows Forms en Visual Basic o Visual C\# llamado `HostingWpf`.  
  
## Crear un nuevo control WPF  
 Crear un nuevo control WPF y agregarlo al proyecto es tan fácil como agregar cualquier otro elemento al proyecto.  El Diseñador de Windows Forms trabaja con un tipo determinado de control llamado *control compuesto* o *control de usuario*.  Para obtener más información acerca de los controles de usuario WPF, consulte <xref:System.Windows.Controls.UserControl>.  
  
> [!NOTE]
>  El tipo de <xref:System.Windows.Controls.UserControl?displayProperty=fullName> para WPF es distinto del tipo de control de usuario proporcionado por Windows Forms, que también se llama <xref:System.Windows.Forms.UserControl?displayProperty=fullName>.  
  
#### Para crear un nuevo control WPF  
  
1.  En el **Explorador de soluciones**, agregue un nuevo proyecto **Biblioteca de controles de usuario de WPF** a la solución.  Use el nombre predeterminado de la biblioteca de controles, `WpfControlLibrary1`.  El nombre predeterminado del control es `UserControl1.xaml`.  
  
     Agregar el nuevo control tiene los siguientes efectos.  
  
    -   Se agrega el archivo UserControl1.xaml.  
  
    -   Se agrega el archivo UserControl1.xaml.cs o UserControl1.xaml.vb.  Este archivo contiene el código subyacente de los controladores de eventos y otras implementaciones.  
  
    -   Se agregan referencias a ensamblados de WPF.  
  
    -   Se abre el archivo UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].  
  
2.  En la vista Diseño, asegúrese de que `UserControl1` está seleccionado.  Para obtener más información, consulte [Cómo: Seleccionar y mover elementos en la superficie de diseño](http://msdn.microsoft.com/es-es/54cb70b6-b35b-46e4-a0cc-65189399c474).  
  
3.  En la ventana **Propiedades**, establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> en `200`.  
  
4.  Desde el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Controls.TextBox?displayProperty=fullName> hasta la superficie de diseño.  
  
5.  En la ventana **Propiedades**, establezca el valor de la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> en Contenido hospedado.  
  
    > [!NOTE]
    >  Por lo general, debería hospedar contenido WPF más sofisticado.  El control <xref:System.Windows.Controls.TextBox?displayProperty=fullName> se usa aquí únicamente con fines ilustrativos.  
  
6.  Compile el proyecto.  
  
## Agregar un control WPF a un Windows Form  
 El nuevo control WPF está listo para usarse en el formulario.  Windows Forms usa el control <xref:System.Windows.Forms.Integration.ElementHost> para hospedar contenido WPF  
  
#### Para agregar un control WPF a un Windows Form  
  
1.  Abra `Form1` en el Diseñador de Windows Forms.  
  
2.  En el **Cuadro de herramientas**, busque la pestaña **Controles de usuario de WPF WPFUserControlLibrary**.  
  
3.  Arrastre una instancia de `UserControl1` hasta el formulario.  
  
    -   Se crea automáticamente un control <xref:System.Windows.Forms.Integration.ElementHost> en el formulario para hospedar el control WPF.  
  
    -   El control <xref:System.Windows.Forms.Integration.ElementHost> se llama `elementHost1` y, en la ventana **Propiedades**, puede ver que su propiedad <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> está establecida en **UserControl1**.  
  
    -   Se agregan referencias a ensamblados de WPF al proyecto.  
  
    -   El control `elementHost1` tiene un panel de etiquetas inteligentes que muestra las opciones de hospedaje disponibles.  
  
4.  En el panel de etiquetas inteligentes **Tareas de ElementHost**, seleccione **Acoplar en contenedor principal**.  
  
5.  Presione F5 para compilar y ejecutar la aplicación.  
  
## Pasos siguientes  
 Windows Forms y WPF son tecnologías diferentes, pero están diseñadas para interoperar estrechamente.  Para proporcionar un aspecto y un comportamiento más enriquecido a sus aplicaciones, pruebe lo siguiente.  
  
-   Hospede un control de Windows Forms en una página WPF.  Para obtener más información, consulte [Tutorial: Hospedar un control de Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).  
  
-   Aplique estilos visuales de Windows Forms a su contenido de WPF.  Para obtener más información, consulte [Cómo: Habilitar estilos visuales en una aplicación híbrida](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).  
  
-   Cambie el estilo de su contenido de WPF.  Para obtener más información, consulte [Tutorial: Aplicar estilos al contenido de WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)