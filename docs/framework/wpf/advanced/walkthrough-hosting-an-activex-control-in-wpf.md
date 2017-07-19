---
title: "Tutorial: Hospedar un control ActiveX en WPF | Microsoft Docs"
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
  - "controles ActiveX [interoperabilidad con WPF]"
  - "hospedar controles ActiveX"
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 30
---
# Tutorial: Hospedar un control ActiveX en WPF
Para habilitar la interacción mejorada con los exploradores, puede utilizar controles [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] en la aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  En este tutorial se muestra cómo hospedar [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] como un control en una página de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto.  
  
-   Crear el control ActiveX.  
  
-   Hospedar el control ActiveX en una página de WPF.  
  
 Cuando haya completado este tutorial, entenderá cómo utilizar los controles [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] en una aplicación basada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] instalado en el equipo donde está instalado [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].  
  
## Crear el proyecto  
  
#### Para crear y configurar el proyecto  
  
1.  Cree un proyecto de aplicación de WPF denominado `HostingAxInWpf`.  
  
2.  Agregue un proyecto de biblioteca de controles de Windows Forms a la solución, y asigne al proyecto el nombre `WmpAxLib`.  
  
3.  En el proyecto WmpAxLib, agregue una referencia al ensamblado del Reproductor de Windows Media, que se denomina wmp.dll.  
  
4.  Abra el **Cuadro de herramientas**.  
  
5.  Haga clic con el botón secundario del mouse en el **Cuadro de herramientas** y seleccione **Elegir elementos**.  
  
6.  Haga clic en la pestaña **Componentes COM**, seleccione el control **Reproductor de Windows Media** y, a continuación, haga clic en **Aceptar**.  
  
     El control del Reproductor de Windows Media se agregará al **Cuadro de herramientas**.  
  
7.  En el Explorador de soluciones, haga clic con el botón secundario del mouse en el archivo **UserControl1** y seleccione **Cambiar nombre**.  
  
8.  Cambie el nombre a `WmpAxControl.vb` o `WmpAxControl.cs`, según cuál sea el lenguaje utilizado.  
  
9. Si se le pregunta si desea cambiar el nombre de todas las referencias, haga clic en **Sí**.  
  
## Crear el control ActiveX  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] genera automáticamente una clase contenedora <xref:System.Windows.Forms.AxHost> para un control [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] cuando éste se agrega a una superficie de diseño.  El procedimiento siguiente crea un ensamblado administrado denominado AxInterop.WMPLib.dll.  
  
#### Para crear el control ActiveX  
  
1.  Abra WmpAxControl.vb o WmpAxControl.cs en el Diseñador de Windows Forms.  
  
2.  En el **Cuadro de herramientas**, agregue el control del Reproductor de Windows Media a la superficie de diseño.  
  
3.  En la ventana Propiedades, establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Dock%2A> del control del Reproductor de Windows Media en <xref:System.Windows.Forms.DockStyle>.  
  
4.  Compile el proyecto de biblioteca de controles WmpAxLib.  
  
## Hospedar el control ActiveX en una página de WPF  
  
#### Para hospedar el control ActiveX  
  
1.  En el proyecto HostingAxInWpf, agregue una referencia al ensamblado de interoperabilidad del control [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] generado.  
  
     Este ensamblado se denomina AxInterop.WMPLib.dll y se agregó a la carpeta Debug del proyecto WmpAxLib al importar el control del Reproductor de Windows Media.  
  
2.  Agregue una referencia al ensamblado WindowsFormsIntegration, que se denomina WindowsFormsIntegration.dll.  
  
3.  Agregue una referencia al ensamblado de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], que se denomina System.Windows.Forms.dll.  
  
4.  Abra MainWindow.xaml en WPF Designer.  
  
5.  Asigne el nombre `grid1` al elemento <xref:System.Windows.Controls.Grid>.  
  
     [!code-xml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  En la vista Diseño o en la vista XAML, seleccione el elemento <xref:System.Windows.Window>.  
  
7.  En la ventana Propiedades, haga clic en la pestaña **Eventos**.  
  
8.  Haga doble clic en el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
9. Inserte el código siguiente para controlar el evento <xref:System.Windows.FrameworkElement.Loaded>.  
  
     En este código se crea una instancia del control <xref:System.Windows.Forms.Integration.WindowsFormsHost> y se agrega una instancia del control `AxWindowsMediaPlayer` como su elemento secundario.  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. Presione F5 para compilar y ejecutar la aplicación.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)