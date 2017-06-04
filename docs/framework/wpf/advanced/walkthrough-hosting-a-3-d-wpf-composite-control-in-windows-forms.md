---
title: "Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles compuestos, hospedar WPF en"
  - "hospedar contenido de WPF en formularios Windows Forms"
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms
En este tutorial se muestra cómo crear un control de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] compuesto y hospedarlo en controles y formularios de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] mediante el control <xref:System.Windows.Forms.Integration.ElementHost>.  
  
 En este tutorial, se implementa un <xref:System.Windows.Controls.UserControl> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que contiene dos controles secundarios.  <xref:System.Windows.Controls.UserControl> muestra un cono tridimensional \(3D\).  Representar objetos 3D es mucho más fácil con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  Por consiguiente, resulta lógico hospedar una clase <xref:System.Windows.Controls.UserControl> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para crear los gráficos 3D en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el <xref:System.Windows.Controls.UserControl> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Crear el proyecto host de formularios Windows Forms.  
  
-   Hospedar el <xref:System.Windows.Controls.UserControl> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Para ver una lista de código completa de las tareas mostradas en este tutorial, vea [Hosting a 3\-D WPF Composite Control in Windows Forms Sample](http://go.microsoft.com/fwlink/?LinkID=160001).  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
<a name="To_Create_the_UserControl"></a>   
## Crear el control de usuario  
  
#### Para crear el control de usuario  
  
1.  Cree un proyecto de biblioteca de controles de usuario de WPF denominado `HostingWpfUserControlInWf`.  
  
2.  Abra UserControl1.xaml en [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
3.  Reemplace el código generado con el siguiente código.  
  
     En este código se define un control de usuario \(<xref:System.Windows.Controls.UserControl?displayProperty=fullName>\) que contiene dos controles secundarios.  El primer control secundario es un control <xref:System.Windows.Controls.Label?displayProperty=fullName>; el segundo es un control <xref:System.Windows.Controls.Viewport3D> que muestra un cono 3D.  
  
     [!code-xml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## Crear el proyecto host de formularios Windows Forms  
  
#### Para crear el proyecto host  
  
1.  Agregue un proyecto de aplicación de Windows denominado `WpfUserControlHost` a la solución.  Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/es-es/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  En el Explorador de soluciones, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration.dll.  
  
3.  Agregue referencias a los ensamblados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] siguientes:  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  Agregue una referencia al proyecto `HostingWpfUserControlInWf`.  
  
5.  En el Explorador de soluciones, configure el proyecto `WpfUserControlHost` como proyecto de inicio.  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## Hospedar el control de usuario de Windows Presentation Foundation  
  
#### Para hospedar el control de usuario  
  
1.  En el Diseñador de Windows Forms, abra Form1.  
  
2.  En la ventana Propiedades, seleccione **Eventos** y haga doble clic en el evento <xref:System.Windows.Forms.Form.Load> para crear un controlador de eventos.  
  
     Se abrirá el Editor de código para el controlador de eventos `Form1_Load` recién generado.  
  
3.  Reemplace el código de Form1.cs con el código siguiente.  
  
     El controlador de eventos `Form1_Load` crea una instancia de `UserControl1` y la agrega  `` a la colección de controles secundarios del control <xref:System.Windows.Forms.Integration.ElementHost>.  El control <xref:System.Windows.Forms.Integration.ElementHost> se agrega a la colección de controles secundarios del formulario.  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  Presione F5 para compilar y ejecutar la aplicación.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Ejemplo Hosting a WPF Composite Control in Windows Forms](http://go.microsoft.com/fwlink/?LinkID=160001)