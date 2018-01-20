---
title: 'Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 064626e3975838062c2d2287d29aa268edb8f21e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>Tutorial: Hospedar un control compuesto 3 D de WPF en Windows Forms
Este tutorial muestra cómo crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] compuesto controlar y hospedarlo en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controles y formularios mediante el uso de la <xref:System.Windows.Forms.Integration.ElementHost> control.  
  
 En este tutorial, implementará un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> que contiene dos controles secundarios. La <xref:System.Windows.Controls.UserControl> muestra un cono tridimensional de (3D). Representar objetos 3D es mucho más fácil con la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que con [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Por lo tanto, tiene sentido al host una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> clase para crear gráficos 3D en [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.  
  
-   Crear el proyecto de host de formularios Windows Forms.  
  
-   Hospedar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.  
  
 Para obtener una lista de código completa de las tareas ilustradas en este tutorial, vea [hospedar un Control compuesto de WPF 3D en el ejemplo de formularios Windows Forms](http://go.microsoft.com/fwlink/?LinkID=160001).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a>Creación de la clase UserControl  
  
#### <a name="to-create-the-usercontrol"></a>Para crear el control de usuario  
  
1.  Cree un proyecto de biblioteca de controles de usuario de WPF denominado `HostingWpfUserControlInWf`.  
  
2.  Abra UserControl1.xaml en el [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
3.  Reemplace el código generado por el código siguiente.  
  
     Este código define un <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> que contiene dos controles secundarios. El primer control secundario es un <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; el segundo es un <xref:System.Windows.Controls.Viewport3D> control que muestra un cono 3D.  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a>Crear el proyecto del host de Windows Forms  
  
#### <a name="to-create-the-host-project"></a>Para crear el proyecto del host  
  
1.  Agregue un proyecto de aplicación de Windows denominado `WpfUserControlHost` a la solución. Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).  
  
2.  En el Explorador de soluciones, agregue una referencia al ensamblado WindowsFormsIntegration, denominado WindowsFormsIntegration.dll.  
  
3.  Agregue referencias a los siguientes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ensamblados:  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  Agregue una referencia al proyecto `HostingWpfUserControlInWf`.  
  
5.  En el Explorador de soluciones, establezca el `WpfUserControlHost` proyecto para que sea el proyecto de inicio.  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a>Hospedar el control de usuario de Windows Presentation Foundation  
  
#### <a name="to-host-the-usercontrol"></a>Para hospedar el control de usuario  
  
1.  En el Diseñador de Windows Forms, abra Form1.  
  
2.  En la ventana Propiedades, haga clic en **eventos**y, a continuación, haga doble clic en el <xref:System.Windows.Forms.Form.Load> evento para crear un controlador de eventos.  
  
     Se abrirá el Editor de código que acaba de generar `Form1_Load` controlador de eventos.  
  
3.  Reemplace el código en Form1.cs con el código siguiente.  
  
     El `Form1_Load` controlador de eventos crea una instancia de `UserControl1` y agrega sus el <xref:System.Windows.Forms.Integration.ElementHost> colección de controles secundarios del control. El <xref:System.Windows.Forms.Integration.ElementHost> control se agrega a la colección del formulario de controles secundarios.  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  Presione F5 para compilar y ejecutar la aplicación.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Tutorial: Hospedar un control compuesto de formularios Windows Forms en WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Hospedar un Control compuesto de WPF en el ejemplo de formularios Windows Forms](http://go.microsoft.com/fwlink/?LinkID=160001)
